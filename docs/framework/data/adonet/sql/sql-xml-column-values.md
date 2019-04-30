---
title: SQL XML Sütun Değerleri
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 803357f9ae97eee2cbbf5e777dbc1210ded26ab2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670137"
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="5f779-102">SQL XML Sütun Değerleri</span><span class="sxs-lookup"><span data-stu-id="5f779-102">SQL XML Column Values</span></span>
<span data-ttu-id="5f779-103">SQL Server'ı destekleyen `xml` veri türü ve geliştiriciler, standart davranışını kullanarak bu türü içeren sonuç kümelerini alabilir <xref:System.Data.SqlClient.SqlCommand> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="5f779-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="5f779-104">Bir `xml` sütun alınabilir, yalnızca herhangi bir sütun getirildiği (içine bir <xref:System.Data.SqlClient.SqlDataReader>, örneğin) ancak içeriği sütunun XML olarak çalışmak istiyorsanız, kullanmanız gerekir bir <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="5f779-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f779-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="5f779-105">Example</span></span>  
 <span data-ttu-id="5f779-106">Aşağıdaki konsol uygulamasında içeren her iki satır seçer bir `xml` sütun, gelen **Sales.Store** tablosundaki **AdventureWorks** veritabanını bir <xref:System.Data.SqlClient.SqlDataReader> örneği.</span><span class="sxs-lookup"><span data-stu-id="5f779-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="5f779-107">Her satırın değerini `xml` sütun kullanılarak okunur <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> yöntemi <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="5f779-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="5f779-108">Bir değeri depolanan bir <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="5f779-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="5f779-109">Kullanmanız gereken Not <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> yerine <xref:System.Data.IDataRecord.GetValue%2A> içeriği ayarlamak isterseniz yöntemi bir <xref:System.Data.SqlTypes.SqlXml> değişkeni; <xref:System.Data.IDataRecord.GetValue%2A> değerini döndürür `xml` dize olarak sütun.</span><span class="sxs-lookup"><span data-stu-id="5f779-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f779-110">**AdventureWorks** örnek veritabanı, SQL Server'ı yüklediğinizde varsayılan olarak yüklenmedi.</span><span class="sxs-lookup"><span data-stu-id="5f779-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="5f779-111">SQL Server Kurulumu çalıştırarak yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5f779-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5f779-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5f779-112">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="5f779-113">SQL Server'da XML Verileri</span><span class="sxs-lookup"><span data-stu-id="5f779-113">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)
- [<span data-ttu-id="5f779-114">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="5f779-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
