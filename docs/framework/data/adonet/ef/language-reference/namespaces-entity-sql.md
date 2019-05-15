---
title: Ad alanları (varlık SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 7bcd7a72df8afbd598a15ccd9a259ed11b5b9ef7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583815"
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="dbc5b-102">Ad alanları (varlık SQL)</span><span class="sxs-lookup"><span data-stu-id="dbc5b-102">Namespaces (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="dbc5b-103">Tür adları, varlık kümelerini, İşlevler ve benzeri gibi genel tanımlayıcı ad çakışmalarını önlemek için ad alanları tanıtır.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-103">introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="dbc5b-104">Ad alanı desteği [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ad alanı .NET Framework desteği benzer.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the .NET Framework.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="dbc5b-105">İki form USING yan tümcesinin sağlar: tam ad alanları (burada daha kısa bir diğer ad sağlanan ad alanı için) ve nitelenmemiş ad alanları, aşağıdaki örnekte gösterildiği gibi:</span><span class="sxs-lookup"><span data-stu-id="dbc5b-105">provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="dbc5b-106">Ad çözümleme kuralları</span><span class="sxs-lookup"><span data-stu-id="dbc5b-106">Name Resolution Rules</span></span>  
 <span data-ttu-id="dbc5b-107">Yerel kapsamlar, tanımlayıcının çözümlenemezse [!INCLUDE[esql](../../../../../../includes/esql-md.md)] adı (ad) genel kapsamlarda bulmaya çalışır.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="dbc5b-108">ilk tanımlayıcısı (ön ek) eşleşmesi tam ad alanlarından biri ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-108">first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="dbc5b-109">Bir eşleşme varsa [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tanımlayıcısının belirtilen ad alanı, kalan çözümlemeye çalışır.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="dbc5b-110">Eşleşme bulunursa, bir özel durum oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="dbc5b-111">Ardından, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (giriş bölümünde belirtilir) tüm nitelenmemiş ad tanımlayıcısı için aranacak çalışır.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="dbc5b-112">Tanımlayıcı tam olarak bir ad alanında bulunabilir, bu konuma döndürülür.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="dbc5b-113">Birden fazla ad alanı tanımlayıcı için bir eşleşme varsa, bir özel durum oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="dbc5b-114">Ad alanı tanımlayıcısı için tanımlanabilir, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sonraki dışa doğru kapsam adını geçirir ( <xref:System.Data.Common.DbCommand> veya <xref:System.Data.Common.DbConnection> nesne) aşağıdaki örnekte gösterildiği gibi:</span><span class="sxs-lookup"><span data-stu-id="dbc5b-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="dbc5b-115">.NET Framework arasındaki farklar</span><span class="sxs-lookup"><span data-stu-id="dbc5b-115">Differences from the .NET Framework</span></span>  
 <span data-ttu-id="dbc5b-116">.NET Framework'de kısmen nitelenmiş ad alanları kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-116">In the .NET Framework, you can use partially qualified namespaces.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="dbc5b-117">Bu izin vermez.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-117">does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="dbc5b-118">ADO.NET kullanımı</span><span class="sxs-lookup"><span data-stu-id="dbc5b-118">ADO.NET Usage</span></span>  
 <span data-ttu-id="dbc5b-119">Sorgular ADO.NET ifade <xref:System.Data.Common.DbCommand> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <span data-ttu-id="dbc5b-120"><xref:System.Data.Common.DbCommand> nesneler üzerinde oluşturulabilir <xref:System.Data.Common.DbConnection> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-120"><xref:System.Data.Common.DbCommand> objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="dbc5b-121">Ad alanları bir parçası olarak da belirtilebilir <xref:System.Data.Common.DbCommand> ve <xref:System.Data.Common.DbConnection> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="dbc5b-122">Varsa [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bir tanımlayıcısı çözümlenemiyor sorgunun kendisi içinde dış ad alanları (benzer kurallar temelinde) araştırıldığı.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc5b-123">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-123">See also</span></span>

- [<span data-ttu-id="dbc5b-124">Entity SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="dbc5b-124">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="dbc5b-125">Entity SQL’e Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="dbc5b-125">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
