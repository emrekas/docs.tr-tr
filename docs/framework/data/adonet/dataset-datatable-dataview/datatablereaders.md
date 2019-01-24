---
title: DataTableReaders
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 9984dc9c215a34ab35524560e4dcbcd6bd12596d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602851"
---
# <a name="datatablereaders"></a><span data-ttu-id="8855a-102">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="8855a-102">DataTableReaders</span></span>
<span data-ttu-id="8855a-103"><xref:System.Data.DataTableReader> İçeriğini sunan bir <xref:System.Data.DataTable> veya <xref:System.Data.DataSet> bir veya daha fazla salt okunur, salt iletme sonucu biçiminde ayarlar.</span><span class="sxs-lookup"><span data-stu-id="8855a-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="8855a-104">Oluştururken bir **DataTableReader** gelen bir **DataTable**, ortaya çıkan **DataTableReader** nesne içeren bir sonuç aynı veri kümesini  **DataTable** uygulamayı, silindi olarak işaretlendi herhangi bir satır dışında oluşturulduğu öğesinden.</span><span class="sxs-lookup"><span data-stu-id="8855a-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="8855a-105">Orijinal ile aynı sırada sütunlar görüntülenir **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="8855a-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="8855a-106">A **DataTableReader** çağırarak oluşturulmuş olsa bile, birden çok sonuç kümesi içerebilir <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="8855a-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="8855a-107">Sonuçları aynı sırada bulunan **DataTable** içinde **veri kümesi** nesnenin <xref:System.Data.DataSet.Tables%2A> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="8855a-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8855a-108">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="8855a-108">In This Section</span></span>  
 [<span data-ttu-id="8855a-109">DataReader Oluşturma</span><span class="sxs-lookup"><span data-stu-id="8855a-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="8855a-110">Nasıl oluşturulacağı açıklanmaktadır bir **DataTableReader** nesne.</span><span class="sxs-lookup"><span data-stu-id="8855a-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="8855a-111">DataTable İçinde Gezinme</span><span class="sxs-lookup"><span data-stu-id="8855a-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="8855a-112">Kullanımını açıklar **okuma** içeriğini taşımak için yöntemi bir **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="8855a-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8855a-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8855a-113">See also</span></span>
- [<span data-ttu-id="8855a-114">ADO.NET’te Veri Alma ve Değiştirme</span><span class="sxs-lookup"><span data-stu-id="8855a-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="8855a-115">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="8855a-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
