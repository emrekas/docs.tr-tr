---
title: DataView Yönetme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b67fab5-1722-4d2b-bfc1-247a75f0f1ee
ms.openlocfilehash: df03c68193a1068b4bdf0b6ed0923b3bbb8a046a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127718"
---
# <a name="managing-dataviews"></a><span data-ttu-id="8966c-102">DataView Yönetme</span><span class="sxs-lookup"><span data-stu-id="8966c-102">Managing DataViews</span></span>
<span data-ttu-id="8966c-103">Kullanabileceğiniz bir <xref:System.Data.DataViewManager> tüm tablolarda görünüm ayarlarını yönetmek için bir <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="8966c-103">You can use a <xref:System.Data.DataViewManager> to manage view settings for all the tables in a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="8966c-104">Gibi bir kılavuz için birden fazla tabloyu bağlamak istediğiniz bir denetim varsa, ilişkileri varlıklardan bir **DataViewManager** idealdir.</span><span class="sxs-lookup"><span data-stu-id="8966c-104">If you have a control that you want to bind to multiple tables, such as a grid that navigates relationships, a **DataViewManager** is ideal.</span></span>  
  
 <span data-ttu-id="8966c-105">**DataViewManager** koleksiyonunu içeren <xref:System.Data.DataViewSetting> tablo görünüm ayarını ayarlamak için kullanılan nesneleri <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="8966c-105">The **DataViewManager** contains a collection of <xref:System.Data.DataViewSetting> objects that are used to set the view setting of the tables in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="8966c-106"><xref:System.Data.DataViewSettingCollection> İçerir <xref:System.Data.DataViewSetting> nesne her tablo için bir **veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="8966c-106">The <xref:System.Data.DataViewSettingCollection> contains one <xref:System.Data.DataViewSetting> object for each table in a **DataSet**.</span></span> <span data-ttu-id="8966c-107">Varsayılan ayarlayabilirsiniz **ApplyDefaultSort**, **sıralama**, **RowFilter**, ve **RowStateFilter** tarafından başvurulan tablo özellikleri kullanarak kendi **DataViewSetting**.</span><span class="sxs-lookup"><span data-stu-id="8966c-107">You can set the default **ApplyDefaultSort**, **Sort**, **RowFilter**, and **RowStateFilter** properties of the referenced table by using its **DataViewSetting**.</span></span> <span data-ttu-id="8966c-108">Başvurabileceğiniz **DataViewSetting** ad veya sıra başvuru tarafından veya o belirli tabloyu nesnesine bir başvuru geçirerek belirli bir tablo için.</span><span class="sxs-lookup"><span data-stu-id="8966c-108">You can reference the **DataViewSetting** for a particular table by name or ordinal reference, or by passing a reference to that specific table object.</span></span> <span data-ttu-id="8966c-109">Koleksiyonu erişebileceğiniz **DataViewSetting** nesneler bir **DataViewManager** kullanarak **DataViewSettings** özelliği.</span><span class="sxs-lookup"><span data-stu-id="8966c-109">You can access the collection of **DataViewSetting** objects in a **DataViewManager** by using the **DataViewSettings** property.</span></span>  
  
 <span data-ttu-id="8966c-110">Aşağıdaki kod örneği dolduran bir **veri kümesi** SQL Server **Northwind** veritabanı tablolarını **müşteriler**, **siparişler**ve  **Sipariş Ayrıntıları**, tablolar arasında ilişki oluşturur, kullanan bir **DataViewManager** varsayılan ayarlamak için **DataView** ayarları ve bağlamalar bir **DataGrid**  için **DataViewManager**.</span><span class="sxs-lookup"><span data-stu-id="8966c-110">The following code example fills a **DataSet** with the SQL Server **Northwind** database tables **Customers**, **Orders**, and **Order Details**, creates the relationships between the tables, uses a **DataViewManager** to set default **DataView** settings, and binds a **DataGrid** to the **DataViewManager**.</span></span> <span data-ttu-id="8966c-111">Örnek, varsayılan ayarlar **DataView** tüm tablolar için ayarları **veri kümesi** tablonun birincil anahtara göre sıralamak için (**ApplyDefaultSort**  =  **true**) ve sonra sıralama düzenini değiştirir **müşteriler** göre sıralamak için tablo **CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="8966c-111">The example sets the default **DataView** settings for all tables in the **DataSet** to sort by the primary key of the table (**ApplyDefaultSort** = **true**), and then modifies the sort order of the **Customers** table to sort by **CompanyName**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection to Northwind.  
' Create a Connection, DataAdapters, and a DataSet.  
Dim custDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID FROM Orders", connection)  
Dim ordDetDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection)  
  
Dim custDS As DataSet = New DataSet()  
  
' Open the Connection.  
connection.Open()  
  
    ' Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
  
    custDA.Fill(custDS, "Customers")  
    orderDA.Fill(custDS, "Orders")  
    ordDetDA.Fill(custDS, "OrderDetails")  
  
    ' Close the Connection.  
    connection.Close()  
  
    ' Create relationships.  
    custDS.Relations.Add("CustomerOrders", _  
          custDS.Tables("Customers").Columns("CustomerID"), _  
          custDS.Tables("Orders").Columns("CustomerID"))  
  
    custDS.Relations.Add("OrderDetails", _  
          custDS.Tables("Orders").Columns("OrderID"), _  
          custDS.Tables("OrderDetails").Columns("OrderID"))  
  
' Create default DataView settings.  
Dim viewManager As DataViewManager = New DataViewManager(custDS)  
  
Dim viewSetting As DataViewSetting  
For Each viewSetting In viewManager.DataViewSettings  
  viewSetting.ApplyDefaultSort = True  
Next  
  
viewManager.DataViewSettings("Customers").Sort = "CompanyName"  
  
' Bind to a DataGrid.  
Dim grid As System.Windows.Forms.DataGrid = New System.Windows.Forms.DataGrid()  
grid.SetDataBinding(viewManager, "Customers")  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection to Northwind.  
// Create a Connection, DataAdapters, and a DataSet.  
SqlDataAdapter custDA = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderDA = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID FROM Orders", connection);  
SqlDataAdapter ordDetDA = new SqlDataAdapter(  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection);  
  
DataSet custDS = new DataSet();  
  
// Open the Connection.  
connection.Open();  
  
    // Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
  
    custDA.Fill(custDS, "Customers");  
    orderDA.Fill(custDS, "Orders");  
    ordDetDA.Fill(custDS, "OrderDetails");  
  
    // Close the Connection.  
    connection.Close();  
  
    // Create relationships.  
    custDS.Relations.Add("CustomerOrders",  
          custDS.Tables["Customers"].Columns["CustomerID"],  
          custDS.Tables["Orders"].Columns["CustomerID"]);  
  
    custDS.Relations.Add("OrderDetails",  
          custDS.Tables["Orders"].Columns["OrderID"],  
          custDS.Tables["OrderDetails"].Columns["OrderID"]);  
  
// Create default DataView settings.  
DataViewManager viewManager = new DataViewManager(custDS);  
  
foreach (DataViewSetting viewSetting in viewManager.DataViewSettings)  
  viewSetting.ApplyDefaultSort = true;  
  
viewManager.DataViewSettings["Customers"].Sort = "CompanyName";  
  
// Bind to a DataGrid.  
System.Windows.Forms.DataGrid grid = new System.Windows.Forms.DataGrid();  
grid.SetDataBinding(viewManager, "Customers");  
```  
  
## <a name="see-also"></a><span data-ttu-id="8966c-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8966c-112">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataViewManager>
- <xref:System.Data.DataViewSetting>
- <xref:System.Data.DataViewSettingCollection>
- [<span data-ttu-id="8966c-113">DataViews</span><span class="sxs-lookup"><span data-stu-id="8966c-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="8966c-114">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="8966c-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
