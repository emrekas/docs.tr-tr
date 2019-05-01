---
title: DataSet’e XSLT Dönüşümü Uygulama
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: 5b3aca6a71f88762084934d0d9c7cea15b5366c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034469"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a><span data-ttu-id="f0e3f-102">DataSet’e XSLT Dönüşümü Uygulama</span><span class="sxs-lookup"><span data-stu-id="f0e3f-102">Applying an XSLT Transform to a DataSet</span></span>
<span data-ttu-id="f0e3f-103">**WriteXml** yöntemi <xref:System.Data.DataSet> içeriğini yazmanızı sağlayan bir **veri kümesi** XML verileri olarak.</span><span class="sxs-lookup"><span data-stu-id="f0e3f-103">The **WriteXml** method of the <xref:System.Data.DataSet> enables you to write the contents of a **DataSet** as XML data.</span></span> <span data-ttu-id="f0e3f-104">Ardından bu XML XSL Dönüşümleri (XSLT) kullanarak başka bir biçime dönüştürmek için genel bir görevdir.</span><span class="sxs-lookup"><span data-stu-id="f0e3f-104">A common task is to then transform that XML to another format using XSL transformations (XSLT).</span></span> <span data-ttu-id="f0e3f-105">Bununla birlikte, eşitleme bir **veri kümesi** ile bir <xref:System.Xml.XmlDataDocument> bir XSLT stil sayfası içeriğini sağlayan bir **veri kümesi** ilk içeriğini yazmak zorunda kalmadan  **Veri kümesi** kullanarak XML verilerini olarak **WriteXml**.</span><span class="sxs-lookup"><span data-stu-id="f0e3f-105">However, synchronizing a **DataSet** with an <xref:System.Xml.XmlDataDocument> enables you to apply an XSLT stylesheet to the contents of a **DataSet** without having to first write the contents of the **DataSet** as XML data using **WriteXml**.</span></span>  
  
 <span data-ttu-id="f0e3f-106">Aşağıdaki örnek dolduran bir **veri kümesi** tablolar ve ilişkiler ile eşitler **veri kümesi** ile bir **XmlDataDocument**ve bir kısmı Yazar **Veri kümesi** bir HTML dosyası kullanarak bir XSLT stil sayfası.</span><span class="sxs-lookup"><span data-stu-id="f0e3f-106">The following example populates a **DataSet** with tables and relationships, synchronizes the **DataSet** with an **XmlDataDocument**, and writes a portion of the **DataSet** as an HTML file using an XSLT stylesheet.</span></span> <span data-ttu-id="f0e3f-107">XSLT stil sayfası içeriğini aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="f0e3f-107">Following are the contents of the XSLT stylesheet.</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
<xsl:template match="CustomerOrders">  
  <HTML>  
  <STYLE>  
  BODY {font-family:verdana;font-size:9pt}  
  TD   {font-size:8pt}  
  </STYLE>  
    <BODY>  
    <TABLE BORDER="1">  
      <xsl:apply-templates select="Customers"/>  
    </TABLE>  
    </BODY>  
  </HTML>  
</xsl:template>  
  
<xsl:template match="Customers">  
    <TR><TD>  
      <xsl:value-of select="ContactName"/>, <xsl:value-of select="Phone"/><BR/>  
    </TD></TR>  
      <xsl:apply-templates select="Orders"/>  
</xsl:template>  
  
<xsl:template match="Orders">  
  <TABLE BORDER="1">  
    <TR><TD valign="top"><B>Order:</B></TD><TD valign="top"><xsl:value-of select="OrderID"/></TD></TR>  
    <TR><TD valign="top"><B>Date:</B></TD><TD valign="top"><xsl:value-of select="OrderDate"/></TD></TR>  
    <TR><TD valign="top"><B>Ship To:</B></TD>  
        <TD valign="top"><xsl:value-of select="ShipName"/><BR/>  
        <xsl:value-of select="ShipAddress"/><BR/>  
        <xsl:value-of select="ShipCity"/>, <xsl:value-of select="ShipRegion"/>  <xsl:value-of select="ShipPostalCode"/><BR/>  
        <xsl:value-of select="ShipCountry"/></TD></TR>  
  </TABLE>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="f0e3f-108">Aşağıdaki kod dolgular **veri kümesi** ve XSLT stil sayfasını uygular.</span><span class="sxs-lookup"><span data-stu-id="f0e3f-108">The following code fills the **DataSet** and applies the XSLT style sheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0e3f-109">İçin bir XSLT stil sayfası uyguluyorsanız bir **veri kümesi** ilişkileri içeren, ayarlarsanız en iyi performansı elde etmek **iç içe** özelliği <xref:System.Data.DataRelation> için **true**her biri için ilişki iç içe geçmiş.</span><span class="sxs-lookup"><span data-stu-id="f0e3f-109">If you are applying an XSLT style sheet to a **DataSet** that contains relations, you achieve best performance if you set the **Nested** property of the <xref:System.Data.DataRelation> to **true** for each nested relation.</span></span> <span data-ttu-id="f0e3f-110">Bu XSLT stil sayfalarını kullanmanızı hiyerarşi gidin ve yoğun performans XPath konumu eksenler (örneğin, önceki eşdüzey ve aşağıdaki eşdüzey stil kullanarak verileri dönüştürmek bu uygulama doğal yukarıdan aşağıya işlemesine olanak gezinebilirsiniz sayfası düğüm test ifadeleri).</span><span class="sxs-lookup"><span data-stu-id="f0e3f-110">This allows you to use XSLT style sheets that implement natural top-down processing to navigate the hierarchy and transform the data, as opposed to using performance-intensive XPath location axes (for example, preceding-sibling and following-sibling in style sheet node test expressions) to navigate it.</span></span> <span data-ttu-id="f0e3f-111">İç içe ilişkiler hakkında daha fazla bilgi için bkz. [iç içe DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="f0e3f-111">For more information on nested relations, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim xslTran As XslTransform = New XslTransform  
xslTran.Load("transform.xsl")  
  
Dim writer As XmlTextWriter = New XmlTextWriter( _  
  "xslt_output.html", System.Text.Encoding.UTF8)  
  
xslTran.Transform(xmlDoc, Nothing, writer)  
writer.Close()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
DataSet custDS = new DataSet("CustomerDataSet");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(custDS, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(custDS, "Orders");  
  
connection.Close();  
  
custDS.Relations.Add("CustOrders",  
  custDS.Tables["Customers"].Columns["CustomerID"],  
                     custDS.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(custDS);   
  
XslTransform xslTran = new XslTransform();  
xslTran.Load("transform.xsl");  
  
XmlTextWriter writer = new XmlTextWriter("xslt_output.html",   
  System.Text.Encoding.UTF8);  
  
xslTran.Transform(xmlDoc, null, writer);  
writer.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0e3f-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f0e3f-112">See also</span></span>

- [<span data-ttu-id="f0e3f-113">DataSet ve XmlDataDocument Eşitlemesi</span><span class="sxs-lookup"><span data-stu-id="f0e3f-113">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="f0e3f-114">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="f0e3f-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
