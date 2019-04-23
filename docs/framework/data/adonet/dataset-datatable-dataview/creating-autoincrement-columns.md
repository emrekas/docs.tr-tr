---
title: AutoIncrement Sütunları Oluşturma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 99c52b93cee858511d50aba2f30f2b9f96d91ccd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090946"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="79ff2-102">AutoIncrement Sütunları Oluşturma</span><span class="sxs-lookup"><span data-stu-id="79ff2-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="79ff2-103">Benzersiz sütun değerlerini sağlamak için tabloya yeni satır eklendiğinde otomatik olarak artırmak için sütun değerlerini ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="79ff2-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="79ff2-104">Bir otomatik artan oluşturmak için <xref:System.Data.DataColumn>ayarlayın <xref:System.Data.DataColumn.AutoIncrement%2A> sütununun özellik **true**.</span><span class="sxs-lookup"><span data-stu-id="79ff2-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="79ff2-105"><xref:System.Data.DataColumn> Ardından tanımlanan değer ile başlayan <xref:System.Data.DataColumn.AutoIncrementSeed%2A> özelliği ve değeri ile her bir satır eklenmiştir **AutoIncrement** sütun tanımlı değer artırılır <xref:System.Data.DataColumn.AutoIncrementStep%2A> özelliği sütunun.</span><span class="sxs-lookup"><span data-stu-id="79ff2-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="79ff2-106">İçin **AutoIncrement** sütun öneririz, <xref:System.Data.DataColumn.ReadOnly%2A> özelliği **DataColumn** ayarlanması **true**.</span><span class="sxs-lookup"><span data-stu-id="79ff2-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="79ff2-107">Aşağıdaki örnek, 200 değeri ile başlar ve artımlı olarak 3 adımda ekleyen bir sütun oluşturmak nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="79ff2-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a><span data-ttu-id="79ff2-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="79ff2-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="79ff2-109">DataTable Şema Tanımı</span><span class="sxs-lookup"><span data-stu-id="79ff2-109">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="79ff2-110">DataTables</span><span class="sxs-lookup"><span data-stu-id="79ff2-110">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="79ff2-111">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="79ff2-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
