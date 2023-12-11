## CollectionView

The .NET Multi-platform App UI (.NET MAUI) CollectionView is a view for presenting lists of data using different layout specifications. It aims to provide a more flexible, and performant alternative to ListView.

# Properties

| Property                | Comment                                               |
| ----------------------- | ----------------------------------------------------- |
| ItemsLayout             | HorizontalList, VerticalList, ...                     |
| ItemsSource             | IEnumerable                                           |
| ItemTemplate            | DataTemplate                                          |
| ItemsUpdatingScrollMode | KeepItemsInView, KeepLastItemInView, KeepScrollOffset |
| SelectedItem            | object (supports TwoWay binding)                      |
| SelectedItems           | IList<object> (OneWay binding)                        |
| SelectionChangedCommand | No SelectionTapped                                    |
| SelectionChangedCommandParameter |                                              | 
| SelectionMode           | Multiple, None, Single                                |


# Events

| Event            | Comment                                 |
| ---------------- | --------------------------------------- |
| SelectionChanged | EventHandler<SelectionChangedEventArgs> |

# See Also

https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/collectionview/?view=net-maui-8.0
https://learn.microsoft.com/en-us/dotnet/api/microsoft.maui.controls.collectionview?view=net-maui-8.0
https://learn.microsoft.com/en-us/dotnet/maui/user-interface/visual-states?view=net-maui-8.0
