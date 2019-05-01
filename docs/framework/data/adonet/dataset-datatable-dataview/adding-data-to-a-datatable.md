---
title: DataTable’a Veri Ekleme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: ec4ad84a39afe21ef77507732e5e0e417d45f3e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034534"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="998c5-102">DataTable’a Veri Ekleme</span><span class="sxs-lookup"><span data-stu-id="998c5-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="998c5-103">Oluşturduktan sonra bir <xref:System.Data.DataTable> ve sütunları ve kısıtlamaları kullanarak yapısını tanımlamak, tabloya yeni satır veri ekleyin.</span><span class="sxs-lookup"><span data-stu-id="998c5-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="998c5-104">Yeni bir satır eklemek için yeni bir değişken türü olarak bildirin <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="998c5-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="998c5-105">Yeni bir **DataRow** çağırdığınızda nesnesi döndürülen <xref:System.Data.DataTable.NewRow%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="998c5-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="998c5-106">**DataTable** oluşturur sonra **DataRow** nesne temel tablosunun yapısı üzerinde tarafından tanımlanan <xref:System.Data.DataColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="998c5-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="998c5-107">Aşağıdaki örnek yeni bir satır çağırarak denetlediği oluşturma işlemini gösterir **NewRow** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="998c5-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="998c5-108">Ardından, aşağıdaki örnekte gösterildiği gibi bir dizini veya sütun adı'nı kullanarak yeni eklenen satır işleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="998c5-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="998c5-109">Yeni satır veri eklendikten sonra **Ekle** satır eklemek için kullanılan yöntemi <xref:System.Data.DataRowCollection>aşağıdaki kodda gösterilen.</span><span class="sxs-lookup"><span data-stu-id="998c5-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="998c5-110">Ayrıca, çağırabilirsiniz **Ekle** değerleri dizisi geçirerek yeni bir satır eklemek için yöntemi yazılı olarak <xref:System.Object>aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="998c5-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="998c5-111">Bir dizisi olarak yazılan değerlerin geçirerek **nesne**, **Ekle** yöntemi içindeki tabloya yeni bir satır oluşturur ve nesne dizideki değerleri için sütun değerlerini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="998c5-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="998c5-112">Dizideki değerleri tablodaki göründükleri sıraya göre sütunlara sıralı olarak eşleştirilir unutmayın.</span><span class="sxs-lookup"><span data-stu-id="998c5-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="998c5-113">Aşağıdaki örnek 10 satır, yeni oluşturulan ekler **müşteriler** tablo.</span><span class="sxs-lookup"><span data-stu-id="998c5-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)   
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="998c5-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="998c5-114">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="998c5-115">DataTable Verilerini Düzenleme</span><span class="sxs-lookup"><span data-stu-id="998c5-115">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="998c5-116">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="998c5-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
