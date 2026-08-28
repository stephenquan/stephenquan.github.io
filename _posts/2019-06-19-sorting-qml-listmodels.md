---
layout: default
title: "Sorting QML ListModels"
categories: [AppStudio]
author: "Stephen Quan"
tags: [AppStudio, QML, ListModels]
---

I posted [Sorting QML ListModels](https://community.esri.com/groups/appstudio/blog/2019/06/19/sorting-qml-listmodels) on [GeoNet AppStudio Blog Posts](https://community.esri.com/groups/appstudio/content?filterID=contentstatus%5Bpublished%5D~objecttype~objecttype%5Bblogpost%5D).

```javascript
    function listModelSort(listModel, compareFunction) {
        let indexes = [ ...Array(listModel.count).keys() ]
        indexes.sort( (a, b) => compareFunction( listModel.get(a), listModel.get(b) ) )
        let sorted = 0
        while ( sorted < indexes.length && sorted === indexes[sorted] ) sorted++
        if ( sorted === indexes.length ) return
        for ( let i = sorted; i < indexes.length; i++ ) {
            listModel.move( indexes[i], listModel.count - 1, 1 )
            listModel.insert( indexes[i], { } )
        }
        listModel.remove( sorted, indexes.length - sorted )
    }
```
