---
title: 'Nasıl yapılır: Çok biçimli sorgu yürütme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 2b1493ffc2aaa4c3716cbd6d1ac0f350ed39a8f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746589"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="ddb1d-102">Nasıl yapılır: Çok biçimli sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="ddb1d-102">How to: Execute a Polymorphic Query</span></span>
<span data-ttu-id="ddb1d-103">Bu konuda, bir çok biçimli yürütülecek gösterilmektedir [!INCLUDE[esql](../../../../../includes/esql-md.md)] kullanarak sorgu [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) işleci.</span><span class="sxs-lookup"><span data-stu-id="ddb1d-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="ddb1d-104">Bu örnekte, kodu çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="ddb1d-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="ddb1d-105">Ekleme [Okul modeli](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) projenize ve projenizi Entity Framework kullanmak üzere yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="ddb1d-105">Add the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="ddb1d-106">Daha fazla bilgi için [nasıl yapılır: Varlık veri modeli Sihirbazı'nı](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="ddb1d-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="ddb1d-107">Uygulamanız için kod sayfasında, aşağıdakileri ekleyin `using` deyimleri (`Imports` Visual Basic'te):</span><span class="sxs-lookup"><span data-stu-id="ddb1d-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="ddb1d-108">İçindeki adımları izleyerek bir tablo başına hierrachy devralma için kavramsal model değiştirme [izlenecek yol: Devralma - tablo başına hiyerarşi eşleme](https://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55).</span><span class="sxs-lookup"><span data-stu-id="ddb1d-108">Modify the conceptual model to have a table-per-hierrachy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](https://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddb1d-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="ddb1d-109">Example</span></span>  
 <span data-ttu-id="ddb1d-110">Aşağıdaki örnek, almak ve yalnızca koleksiyonunu görüntülemek için bir OFTYPE işleci kullanır. `OnsiteCourses` koleksiyonundan `Courses`.</span><span class="sxs-lookup"><span data-stu-id="ddb1d-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a><span data-ttu-id="ddb1d-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ddb1d-111">See also</span></span>
- [<span data-ttu-id="ddb1d-112">Entity Framework için EntityClient Sağlayıcısı</span><span class="sxs-lookup"><span data-stu-id="ddb1d-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="ddb1d-113">Entity SQL Dili</span><span class="sxs-lookup"><span data-stu-id="ddb1d-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
