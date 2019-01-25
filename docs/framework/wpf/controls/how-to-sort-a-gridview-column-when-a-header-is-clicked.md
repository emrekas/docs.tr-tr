---
title: 'Nasıl yapılır: Üstbilgi Tıklandığında GridView Sütununu Sıralama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], GridView
- controls [WPF], ListView
- ListView controls [WPF], sorting GridView columns
- GridView controls [WPF], ListView control
ms.assetid: 4865d720-d147-40ed-83a7-af7587f8aad8
ms.openlocfilehash: 2d0cca89d906a60a3f7072de27bc54b7a869a01e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694093"
---
# <a name="how-to-sort-a-gridview-column-when-a-header-is-clicked"></a>Nasıl yapılır: Üstbilgi Tıklandığında GridView Sütununu Sıralama
Bu örnek nasıl oluşturulacağını gösterir. bir <xref:System.Windows.Controls.ListView> uygulayan denetimi bir <xref:System.Windows.Controls.GridView> görüntüleme modu ve verileri, bir kullanıcı bir sütun başlığına sağ tıkladığında içerik sıralar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte tanımlayan bir <xref:System.Windows.Controls.GridView> bağlamak üç sütun ile <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, ve <xref:System.DateTime.Day%2A>, özelliklerini <xref:System.DateTime> yapısı.  
  
```xaml  
<GridView>  
  <GridViewColumn DisplayMemberBinding="{Binding Path=Year}"   
                  Header="Year"  
                  Width="100"/>  
  <GridViewColumn DisplayMemberBinding="{Binding Path=Month}"   
                  Header="Month"  
                  Width="100"/>  
  <GridViewColumn DisplayMemberBinding="{Binding Path=Day}"   
                  Header="Day"  
                  Width="100"/>  
</GridView>  
```  
  
 Veri öğeleri olarak tanımlanır aşağıdaki örnekte bir <xref:System.Collections.ArrayList> , <xref:System.DateTime> nesneleri. <xref:System.Collections.ArrayList> Olarak tanımlanan <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> için <xref:System.Windows.Controls.ListView> denetimi.  
  
```xaml  
<ListView.ItemsSource>  
  <s:ArrayList>  
    <p:DateTime>1993/1/1 12:22:02</p:DateTime>  
    <p:DateTime>1993/1/2 13:2:01</p:DateTime>  
    <p:DateTime>1997/1/3 2:1:6</p:DateTime>  
    <p:DateTime>1997/1/4 13:6:55</p:DateTime>  
    <p:DateTime>1999/2/1 12:22:02</p:DateTime>  
    <p:DateTime>1998/2/2 13:2:01</p:DateTime>  
    <p:DateTime>2000/2/3 2:1:6</p:DateTime>  
    <p:DateTime>2002/2/4 13:6:55</p:DateTime>  
    <p:DateTime>2001/3/1 12:22:02</p:DateTime>  
    <p:DateTime>2006/3/2 13:2:01</p:DateTime>  
    <p:DateTime>2004/3/3 2:1:6</p:DateTime>  
    <p:DateTime>2004/3/4 13:6:55</p:DateTime>  
  </s:ArrayList>  
</ListView.ItemsSource>  
```  
  
 `s` Ve `p` tanımlayıcıları [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] etiketleri bakın meta verilerde tanımlanan ad alanı eşlemeleri [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sayfası. Aşağıdaki örnek, meta veri tanımı gösterilmektedir.  
  
```xaml  
<Window        
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    x:Class="ListViewSort.Window1"      
    xmlns:s="clr-namespace:System.Collections;assembly=mscorlib"  
    xmlns:p="clr-namespace:System;assembly=mscorlib">  
```  
  
 Örnek verileri bir sütunun içeriğine göre sıralamak için işlemek için bir olay işleyicisi tanımlar <xref:System.Windows.Controls.Primitives.ButtonBase.Click> sütun üstbilgisi düğmesine bastığınızda oluşan olay. Aşağıdaki örnek, bir olay işleyicisi belirtmek gösterilmektedir <xref:System.Windows.Controls.GridViewColumnHeader> denetimi.  
  
```xaml  
<ListView x:Name='lv' Height="150" HorizontalAlignment="Center"   
  VerticalAlignment="Center"   
  GridViewColumnHeader.Click="GridViewColumnHeaderClickedHandler"  
 >  
```  
  
 Örnek olay işleyicisi tanımlar artan ve azalan sırada sütun üstbilgisi düğmesine her bastığınızda arasındaki sıralama yönünü değiştirir. Aşağıdaki örnekte olay işleyicisi gösterir.  
  
```csharp  
public partial class Window1 : Window  
{  
    public Window1()  
    {  
        InitializeComponent();  
    }  
  
    GridViewColumnHeader _lastHeaderClicked = null;  
    ListSortDirection _lastDirection = ListSortDirection.Ascending;  
  
    void GridViewColumnHeaderClickedHandler(object sender,  
                                            RoutedEventArgs e)  
    {  
        var headerClicked = e.OriginalSource as GridViewColumnHeader;  
        ListSortDirection direction;  
  
        if (headerClicked != null)  
        {  
            if (headerClicked.Role != GridViewColumnHeaderRole.Padding)  
            {  
                if (headerClicked != _lastHeaderClicked)  
                {  
                    direction = ListSortDirection.Ascending;  
                }  
                else  
                {  
                    if (_lastDirection == ListSortDirection.Ascending)  
                    {  
                        direction = ListSortDirection.Descending;  
                    }  
                    else  
                    {  
                        direction = ListSortDirection.Ascending;  
                    }  
                }  
  
                var columnBinding = headerClicked.Column.DisplayMemberBinding as Binding;
                var sortBy = columnBinding?.Path.Path ?? headerClicked.Column.Header as string;

                Sort(sortBy, direction);
  
                if (direction == ListSortDirection.Ascending)  
                {  
                    headerClicked.Column.HeaderTemplate =  
                      Resources["HeaderTemplateArrowUp"] as DataTemplate;  
                }  
                else  
                {  
                    headerClicked.Column.HeaderTemplate =  
                      Resources["HeaderTemplateArrowDown"] as DataTemplate;  
                }  
  
                // Remove arrow from previously sorted header  
                if (_lastHeaderClicked != null && _lastHeaderClicked != headerClicked)  
                {  
                    _lastHeaderClicked.Column.HeaderTemplate = null;  
                }  
  
                _lastHeaderClicked = headerClicked;  
                _lastDirection = direction;  
            }  
        }  
    }
}
```  
  
```vb  
Partial Public Class Window1  
    Inherits Window
    Public Sub New()  
        InitializeComponent()  
    End Sub  
  
    Private _lastHeaderClicked As GridViewColumnHeader = Nothing  
    Private _lastDirection As ListSortDirection = ListSortDirection.Ascending  
  
    Private Sub GridViewColumnHeaderClickedHandler(ByVal sender As Object, ByVal e As RoutedEventArgs)  
        Dim headerClicked = TryCast(e.OriginalSource, GridViewColumnHeader)  
        Dim direction As ListSortDirection  
  
        If headerClicked IsNot Nothing Then  
            If headerClicked.Role <> GridViewColumnHeaderRole.Padding Then  
                If headerClicked IsNot _lastHeaderClicked Then  
                    direction = ListSortDirection.Ascending  
                Else  
                    If _lastDirection = ListSortDirection.Ascending Then  
                        direction = ListSortDirection.Descending  
                    Else  
                        direction = ListSortDirection.Ascending  
                    End If  
                End If  

                Dim columnBinding = TryCast(headerClicked.Column.DisplayMemberBinding, Binding)
                Dim sortBy = If(columnBinding?.Path.Path, TryCast(headerClicked.Column.Header, String))

                Sort(sortBy, direction)  

                If direction = ListSortDirection.Ascending Then
                    headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowUp"), DataTemplate)  
                Else  
                    headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowDown"), DataTemplate)  
                End If  
  
                ' Remove arrow from previously sorted header  
                If _lastHeaderClicked IsNot Nothing AndAlso _lastHeaderClicked IsNot headerClicked Then  
                    _lastHeaderClicked.Column.HeaderTemplate = Nothing  
                End If  
  
                _lastHeaderClicked = headerClicked  
                _lastDirection = direction  
            End If  
        End If  
    End Sub
End Class
```  
  
 Aşağıdaki örnek, verileri sıralamak için olay işleyicisi tarafından çağrılan Sıralama algoritması gösterir. Yeni bir oluşturarak sıralama yapılır <xref:System.ComponentModel.SortDescription> yapısı.  
  
```csharp  
private void Sort(string sortBy, ListSortDirection direction)  
{  
    ICollectionView dataView =  
      CollectionViewSource.GetDefaultView(lv.ItemsSource);  
  
    dataView.SortDescriptions.Clear();  
    SortDescription sd = new SortDescription(sortBy, direction);  
    dataView.SortDescriptions.Add(sd);  
    dataView.Refresh();  
}  
```  
  
```vb  
Private Sub Sort(ByVal sortBy As String, ByVal direction As ListSortDirection)  
    Dim dataView As ICollectionView = CollectionViewSource.GetDefaultView(lv.ItemsSource)  
  
    dataView.SortDescriptions.Clear()  
    Dim sd As New SortDescription(sortBy, direction)  
    dataView.SortDescriptions.Add(sd)  
    dataView.Refresh()  
End Sub  
```  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [ListView Genel Bakış](../../../../docs/framework/wpf/controls/listview-overview.md)
- [GridView Genel Bakış](../../../../docs/framework/wpf/controls/gridview-overview.md)
- [Nasıl Yapılır Konuları](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
