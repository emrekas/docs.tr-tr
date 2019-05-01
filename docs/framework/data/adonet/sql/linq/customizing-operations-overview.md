---
title: 'İşlemleri Özelleştirme: Genel Bakış'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 29fb75271b7bc324d462078e94e4a28534986fba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038099"
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="bfea8-102">İşlemleri Özelleştirme: Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="bfea8-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="bfea8-103">Varsayılan olarak, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dinamik SQL ekleme, güncelleştirme ve silme işlemleri eşlemesini göre oluşturur.</span><span class="sxs-lookup"><span data-stu-id="bfea8-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="bfea8-104">Ancak, uygulamada genellikle güvenlik, doğrulama ve benzeri sağlamak için kendi iş mantıklarını eklemesini istersiniz.</span><span class="sxs-lookup"><span data-stu-id="bfea8-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="bfea8-105">Bu işlemler özelleştirmeye yönelik teknikler arasında şunlar yer alır.</span><span class="sxs-lookup"><span data-stu-id="bfea8-105">techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="bfea8-106">Yükleme Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="bfea8-106">Loading Options</span></span>  
 <span data-ttu-id="bfea8-107">Sorgularınızdaki, veritabanına bağlanmak için ana hedef ilgili ne kadar veri alınır kontrol edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bfea8-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="bfea8-108">Bu işlev büyük ölçüde kullanılarak uygulanan <xref:System.Data.Linq.DataLoadOptions>.</span><span class="sxs-lookup"><span data-stu-id="bfea8-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="bfea8-109">Daha fazla bilgi için [Ertelenen hemen yükleme](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="bfea8-109">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="bfea8-110">Kısmi Yöntemler</span><span class="sxs-lookup"><span data-stu-id="bfea8-110">Partial Methods</span></span>  
 <span data-ttu-id="bfea8-111">Kendi varsayılan eşlemesinde [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] iş mantığınızı uygulamanıza yardımcı olmak için kısmi yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="bfea8-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="bfea8-112">Daha fazla bilgi için [ekleyerek iş mantığı kullanarak kısmi yöntemler](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="bfea8-112">For more information, see [Adding Business Logic By Using Partial Methods](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="bfea8-113">Saklı yordamları ve kullanıcı tanımlı işlevleri</span><span class="sxs-lookup"><span data-stu-id="bfea8-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="bfea8-114">saklı yordamları ve kullanıcı tanımlı işlevleri destekler.</span><span class="sxs-lookup"><span data-stu-id="bfea8-114">supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="bfea8-115">Saklı yordamlar, sık sık operations özelleştirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bfea8-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="bfea8-116">Daha fazla bilgi için [saklı yordamlar](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="bfea8-116">For more information, see [Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfea8-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="bfea8-117">See also</span></span>

- [<span data-ttu-id="bfea8-118">Insert, Update ve Delete İşlemlerini Özelleştirme</span><span class="sxs-lookup"><span data-stu-id="bfea8-118">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
