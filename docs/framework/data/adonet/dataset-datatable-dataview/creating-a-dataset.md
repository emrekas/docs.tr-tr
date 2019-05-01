---
title: DataSet Oluşturma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d2d17056e6dcd29ef9b5c5e8c3024a32fce32bd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879885"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="db91d-102">DataSet Oluşturma</span><span class="sxs-lookup"><span data-stu-id="db91d-102">Creating a DataSet</span></span>
<span data-ttu-id="db91d-103">Örneğini oluşturduğunuz bir <xref:System.Data.DataSet> çağırarak <xref:System.Data.DataSet> Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="db91d-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="db91d-104">İsteğe bağlı olarak bir adı bağımsız değişkenini belirtin.</span><span class="sxs-lookup"><span data-stu-id="db91d-104">Optionally specify a name argument.</span></span> <span data-ttu-id="db91d-105">İçin bir ad belirtmezseniz, <xref:System.Data.DataSet>, adı "İçin NewDataSet" olarak ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="db91d-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="db91d-106">Ayrıca yeni bir oluşturabilirsiniz <xref:System.Data.DataSet> dayanan <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="db91d-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="db91d-107">Yeni <xref:System.Data.DataSet> varolan bir tam kopya olabilir <xref:System.Data.DataSet>; bir kopyasını <xref:System.Data.DataSet> ilişkisel yapısını veya şema kopyalar ancak, var olan verilerin hiçbirini içermez <xref:System.Data.DataSet>; veya bir alt kümesini <xref:System.Data.DataSet>, var olan yalnızca değiştirilen satırları içeren <xref:System.Data.DataSet> kullanarak <xref:System.Data.DataSet.GetChanges%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="db91d-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="db91d-108">Daha fazla bilgi için [DataSet içeriklerini kopyalama](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span><span class="sxs-lookup"><span data-stu-id="db91d-108">For more information, see [Copying DataSet Contents](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="db91d-109">Aşağıdaki kod örneği olgusu yapmayı gösteren bir <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="db91d-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="db91d-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="db91d-110">See also</span></span>

- [<span data-ttu-id="db91d-111">DataAdapter’dan bir DataSet Doldurma</span><span class="sxs-lookup"><span data-stu-id="db91d-111">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="db91d-112">DataSets, DataTables ve DataViews</span><span class="sxs-lookup"><span data-stu-id="db91d-112">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="db91d-113">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="db91d-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
