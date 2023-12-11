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

# Sample - CollectionView (Single)

```c#
// MainViewModel.cs
using CommunityToolkit.Mvvm.ComponentModel;
using System.Globalization;
namespace MauiSampleApp;
public partial class MainViewModel : ObservableObject
{
    public List<CultureInfo> Cultures { get; } = new List<CultureInfo>()
    {
        new CultureInfo("en-US"),
        new CultureInfo("es-ES"),
        new CultureInfo("fr-FR"),
        new CultureInfo("de-DE"),
        new CultureInfo("ja-JP"),
        new CultureInfo("zh-CN")
    };
    [ObservableProperty]
    private CultureInfo _selectedCulture;
    public MainViewModel()
    {
        SelectedCulture = Cultures[0]; // Won't stick
    }
}
```

```xaml
<!-- MainPage.xaml -->
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:mauiCollectionSingle"
             xmlns:g="clr-namespace:System.Globalization;assembly=netstandard"
             x:Class="MauiSampleApp.MainPage"
             x:DataType="{x:Type local:MainViewModel}">
    <ScrollView>
        <VerticalStackLayout>
            <CollectionView ItemsSource="{Binding Cultures}"
                            SelectedItem="{Binding SelectedCulture, Mode=TwoWay}"
                            SelectionMode="Single"
                            Loaded="CollectionView_Loaded">
                <CollectionView.ItemTemplate>
                    <DataTemplate x:DataType="{x:Type g:CultureInfo}">
                        <Label Text="{Binding Name}"/>
                    </DataTemplate>
                </CollectionView.ItemTemplate>
            </CollectionView>
            <Label Text="{Binding SelectedCulture, StringFormat='Selected Culture: {0}'}"/>
        </VerticalStackLayout>
    </ScrollView>
</ContentPage>
```

```c#
// MainPage.xaml.cs
namespace MauiSampleApp;

public partial class MainPage : ContentPage
{
    public MainViewModel VM { get; }
    public MainPage(MainViewModel VM)
    {
        InitializeComponent();
        BindingContext = this.VM = VM;
    }

    private void CollectionView_Loaded(object sender, EventArgs e)
    {
        VM.SelectedCulture = VM.Cultures[0]; // Workaround
    }
}
```

# See Also

https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/collectionview/?view=net-maui-8.0
https://learn.microsoft.com/en-us/dotnet/api/microsoft.maui.controls.collectionview?view=net-maui-8.0
https://learn.microsoft.com/en-us/dotnet/maui/user-interface/visual-states?view=net-maui-8.0
