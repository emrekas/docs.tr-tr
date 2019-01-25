---
title: SQL Server ikili ve büyük değerli veri
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: f6bd62d2e9d2f87947e01b7964c5d151690b62bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643047"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="76cf8-102">SQL Server ikili ve büyük değerli veri</span><span class="sxs-lookup"><span data-stu-id="76cf8-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="76cf8-103">SQL Server sağlayan `max` depolama kapasitesini genişletir belirticisi `varchar`, `nvarchar`, ve `varbinary` veri türleri.</span><span class="sxs-lookup"><span data-stu-id="76cf8-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="76cf8-104">`varchar(max)`, `nvarchar(max)`, ve `varbinary(max)` toplu olarak adlandırılır *büyük değerli veri türleri*.</span><span class="sxs-lookup"><span data-stu-id="76cf8-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="76cf8-105">Büyük değerli veri türleri en fazla 2 depolamak için kullanabileceğiniz ^ 31-1 bayt veri.</span><span class="sxs-lookup"><span data-stu-id="76cf8-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="76cf8-106">SQL Server 2008 veritabanı yerine dosya sisteminde depolanmış büyük değerli veri sağlayan değil bir veri türü FILESTREAM özniteliğine, ancak bunun yerine bir sütuna, tanımlanan bir öznitelik tanıtır.</span><span class="sxs-lookup"><span data-stu-id="76cf8-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76cf8-107">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="76cf8-107">In This Section</span></span>  
 [<span data-ttu-id="76cf8-108">ADO.NET İçinde Büyük Değerli (Maks) Verileri Değiştirme</span><span class="sxs-lookup"><span data-stu-id="76cf8-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="76cf8-109">Büyük değerli veri türleriyle çalışır açıklar.</span><span class="sxs-lookup"><span data-stu-id="76cf8-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="76cf8-110">FILESTREAM Verileri</span><span class="sxs-lookup"><span data-stu-id="76cf8-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="76cf8-111">FILESTREAM özniteliğine SQL Server 2008'de depolanan büyük değerli veri ile nasıl çalışılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="76cf8-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76cf8-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="76cf8-112">See also</span></span>
- [<span data-ttu-id="76cf8-113">SQL Server Veri Türleri ve ADO.NET</span><span class="sxs-lookup"><span data-stu-id="76cf8-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [<span data-ttu-id="76cf8-114">ADO.NET’te SQL Server Veri İşlemleri</span><span class="sxs-lookup"><span data-stu-id="76cf8-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)
- [<span data-ttu-id="76cf8-115">ADO.NET’te Veri Alma ve Değiştirme</span><span class="sxs-lookup"><span data-stu-id="76cf8-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="76cf8-116">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="76cf8-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
