---
title: DataView Oluşturma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 05122f7c980c4b7dfdb27eec73464a4f0556ba99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096686"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="5a242-102">DataView Oluşturma</span><span class="sxs-lookup"><span data-stu-id="5a242-102">Creating a DataView</span></span>
<span data-ttu-id="5a242-103">Oluşturmanın iki yolu vardır. bir <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="5a242-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="5a242-104">Kullanabileceğiniz **DataView** oluşturucu veya bir başvuru oluşturabilirsiniz <xref:System.Data.DataTable.DefaultView%2A> özelliği <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="5a242-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="5a242-105">**DataView** Oluşturucu boş olabilir veya ya da sürebilir bir **DataTable** tek bir bağımsız değişken olarak veya bir **DataTable** filtre ölçütlerini ve sıralama ölçütü bir satır ile birlikte Durum Filtresi.</span><span class="sxs-lookup"><span data-stu-id="5a242-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="5a242-106">Ek bağımsız değişkenleri kullanılabilir ile kullanma hakkında daha fazla bilgi için **DataView**, bkz: [sıralama ve filtreleme veri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="5a242-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="5a242-107">Çünkü dizin için bir **DataView** hem zaman yerleşik **DataView** oluşturulur ve herhangi biri **sıralama**, **RowFilter**, veya  **RowStateFilter** özellikleri değiştirildiğinde, tüm ilk sıralama düzeni sağlayan veya oluşturduğunuzda filtreleme ölçütlerini oluşturucu bağımsız en iyi performans elde **DataView**.</span><span class="sxs-lookup"><span data-stu-id="5a242-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="5a242-108">Oluşturma bir **DataView** sıralama veya filtre ölçütlerini belirtme ve ardından ayarlar olmadan **sıralama**, **RowFilter**, veya **RowStateFilter** özellikleri daha sonra en az iki kere derlenmesi için dizini neden olur: bir kez zaman **DataView** oluşturulur, ve yeniden sıralama veya filtreleme özelliklerinden herhangi birini değiştirildiği.</span><span class="sxs-lookup"><span data-stu-id="5a242-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="5a242-109">Oluşturduğunuz gerçekleştiriyorsanız bir **DataView** herhangi bir bağımsız değişken almaz Oluşturucusu kullanarak, kullanılacak mümkün olmayacaktır **DataView** ayarladığınız kadar **tablo** özelliği .</span><span class="sxs-lookup"><span data-stu-id="5a242-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="5a242-110">Aşağıdaki kod örneğinde nasıl oluşturulacağını gösterir. bir **DataView** kullanarak **DataView** Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="5a242-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="5a242-111">A **RowFilter**, **sıralama** sütun ve **DataViewRowState** ile birlikte sağlanan **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="5a242-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="5a242-112">Aşağıdaki kod örneği, varsayılan bir başvuru almak gösterilmiştir **DataView** , bir **DataTable** kullanarak **DefaultView** tablo özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="5a242-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a242-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5a242-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="5a242-114">DataViews</span><span class="sxs-lookup"><span data-stu-id="5a242-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="5a242-115">Verileri Sıralama ve Filtreleme</span><span class="sxs-lookup"><span data-stu-id="5a242-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)
- [<span data-ttu-id="5a242-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="5a242-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="5a242-117">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="5a242-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
