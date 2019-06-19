---
title: <msxsl:script> Kullanarak XSLT Stil Sayfası Betiğini Oluşturma
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 60e2541b-0cea-4b2e-a4fa-85f4c50f1bef
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 617f1da8f9b5b26ddfb2910ac0c06a6898d8ab6e
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170935"
---
# <a name="xslt-stylesheet-scripting-using-msxslscript"></a><span data-ttu-id="d741b-102">XSLT stil sayfası komut dosyalarını kullanarak \<msxsl: script ></span><span class="sxs-lookup"><span data-stu-id="d741b-102">XSLT Stylesheet Scripting Using \<msxsl:script></span></span>
<span data-ttu-id="d741b-103"><xref:System.Xml.Xsl.XslTransform> Sınıfı destekler kullanarak katıştırılmış betik `script` öğesi.</span><span class="sxs-lookup"><span data-stu-id="d741b-103">The <xref:System.Xml.Xsl.XslTransform> class supports embedded scripting using the `script` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d741b-104"><xref:System.Xml.Xsl.XslTransform> Sınıfı .NET Framework 2. 0'kullanılmıyor.</span><span class="sxs-lookup"><span data-stu-id="d741b-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="d741b-105">Genişletilebilir Stil Sayfası Dil Dönüşümleri (XSLT) dönüştürmeleri için kullanarak gerçekleştirebileceğiniz <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="d741b-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="d741b-106">Bkz: [XslCompiledTransform sınıfını kullanma](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) ve [geçirme gelen XslTransform sınıfı](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="d741b-106">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="d741b-107"><xref:System.Xml.Xsl.XslTransform> Sınıfı destekler kullanarak katıştırılmış betik `script` öğesi.</span><span class="sxs-lookup"><span data-stu-id="d741b-107">The <xref:System.Xml.Xsl.XslTransform> class supports embedded scripting using the `script` element.</span></span> <span data-ttu-id="d741b-108">Stil sayfası yüklendiğinde, herhangi bir tanımlı işlevlere Microsoft Ara dili (MSIL) bir sınıf tanımı içinde sarmalanmış tarafından derlenir ve sonuç olarak performans kaybı olmadan sahip.</span><span class="sxs-lookup"><span data-stu-id="d741b-108">When the style sheet is loaded, any defined functions are compiled to Microsoft intermediate language (MSIL) by being wrapped in a class definition and have no performance loss as a result.</span></span>  
  
 <span data-ttu-id="d741b-109">`<msxsl:script>` Öğesi aşağıda tanımlanmıştır:</span><span class="sxs-lookup"><span data-stu-id="d741b-109">The `<msxsl:script>` element is defined below:</span></span>  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 <span data-ttu-id="d741b-110">Burada `msxsl` bir önek ad alanına bağlı `urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="d741b-110">where `msxsl` is a prefix bound to the namespace `urn:schemas-microsoft-com:xslt`.</span></span>  
  
 <span data-ttu-id="d741b-111">`language` Özniteliği zorunlu değildir, ancak belirtilirse, değeri aşağıdakilerden biri olmalıdır: C#, VB, JScript, JavaScript, VisualBasic veya CSharp.</span><span class="sxs-lookup"><span data-stu-id="d741b-111">The `language` attribute is not mandatory, but if specified, its value must be one of the following: C#, VB, JScript, JavaScript, VisualBasic, or CSharp.</span></span> <span data-ttu-id="d741b-112">Belirtilmezse, dil için JScript Varsayılanları.</span><span class="sxs-lookup"><span data-stu-id="d741b-112">If not specified, the language defaults to JScript.</span></span> <span data-ttu-id="d741b-113">`language-name` 'JavaScript' ve 'javascript' eşdeğer olacak şekilde duyarlı değildir.</span><span class="sxs-lookup"><span data-stu-id="d741b-113">The `language-name` is not case-sensitive, so 'JavaScript' and 'javascript' are equivalent.</span></span>  
  
 <span data-ttu-id="d741b-114">`implements-prefix` Özniteliği zorunludur.</span><span class="sxs-lookup"><span data-stu-id="d741b-114">The `implements-prefix` attribute is mandatory.</span></span> <span data-ttu-id="d741b-115">Bu öznitelik, bir ad alanı bildirin ve komut dosyası bloğu ile ilişkilendirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="d741b-115">This attribute is used to declare a namespace and associate it with the script block.</span></span> <span data-ttu-id="d741b-116">Bu özniteliğin değeri ad alanını temsil eden önekidir.</span><span class="sxs-lookup"><span data-stu-id="d741b-116">The value of this attribute is the prefix that represents the namespace.</span></span> <span data-ttu-id="d741b-117">Bu ad herhangi bir yerde bir stil sayfası içinde tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="d741b-117">This namespace can be defined somewhere in a style sheet.</span></span>  
  
 <span data-ttu-id="d741b-118">Çünkü `msxsl:script` öğenin ait olduğu ad alanına `urn:schemas-microsoft-com:xslt`, stil sayfası, ad alanı bildirimi içermelidir `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="d741b-118">Because the `msxsl:script` element belongs to the namespace `urn:schemas-microsoft-com:xslt`, the style sheet must include the namespace declaration `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span></span>  
  
 <span data-ttu-id="d741b-119">Komut dosyasını çağıran yoksa <xref:System.Security.Permissions.SecurityPermissionFlag> bir stil sayfası betik hiçbir zaman derleyeceği sonra erişim izni ve çağrısı <xref:System.Xml.Xsl.XslTransform.Load%2A> başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="d741b-119">If the caller of the script does not have <xref:System.Security.Permissions.SecurityPermissionFlag> access permission, then the script in a style sheet will never compile and the call to <xref:System.Xml.Xsl.XslTransform.Load%2A> will fail.</span></span>  
  
 <span data-ttu-id="d741b-120">Çağıranın varsa `UnmanagedCode` izni, kod derlenir, ancak izin verilen işlemler yükleme zamanında sağlanan kanıt bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="d741b-120">If the caller has `UnmanagedCode` permission, the script compiles, but the operations that are allowed are dependent on the evidence that is supplied at load time.</span></span>  
  
 <span data-ttu-id="d741b-121">Aşağıdakilerden birini kullanıyorsanız <xref:System.Xml.Xsl.XslTransform.Load%2A> ele yöntemleri bir <xref:System.Xml.XmlReader> veya <xref:System.Xml.XPath.XPathNavigator> stil sayfası yüklemek için kullanmanız gerekir <xref:System.Xml.Xsl.XslTransform.Load%2A> alan aşırı yüklemesini bir <xref:System.Security.Policy.Evidence> parametre bağımsız değişkenlerinden biri olarak.</span><span class="sxs-lookup"><span data-stu-id="d741b-121">If you are using one of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that take an <xref:System.Xml.XmlReader> or <xref:System.Xml.XPath.XPathNavigator> to load the style sheet, you need to use the <xref:System.Xml.Xsl.XslTransform.Load%2A> overload that takes an <xref:System.Security.Policy.Evidence> parameter as one of its arguments.</span></span> <span data-ttu-id="d741b-122">Kanıt sağlamak için çağıranın olmalıdır <xref:System.Security.Permissions.SecurityPermissionFlag> izin vermesini `Evidence` betik derleme için.</span><span class="sxs-lookup"><span data-stu-id="d741b-122">To provide evidence, the caller must have <xref:System.Security.Permissions.SecurityPermissionFlag> permission to supply `Evidence` for the script assembly.</span></span> <span data-ttu-id="d741b-123">Çağıranın bu izni yok. ardından ayarlayabilirler `Evidence` parametresi `null`.</span><span class="sxs-lookup"><span data-stu-id="d741b-123">If the caller does not have this permission, then they can set the `Evidence` parameter to `null`.</span></span> <span data-ttu-id="d741b-124">Bu neden <xref:System.Xml.Xsl.XslTransform.Load%2A> betik bulursa başarısız işlev.</span><span class="sxs-lookup"><span data-stu-id="d741b-124">This causes the <xref:System.Xml.Xsl.XslTransform.Load%2A> function to fail if it finds script.</span></span> <span data-ttu-id="d741b-125">`ControlEvidence` İzni yüksek derecede güvenilen koda verilen yalnızca çok güçlü bir izin olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="d741b-125">The `ControlEvidence` permission is considered a very powerful permission that should only be granted to highly trusted code.</span></span>  
  
 <span data-ttu-id="d741b-126">Kanıt derlemenizden almak için kullanın `this.GetType().Assembly.Evidence`.</span><span class="sxs-lookup"><span data-stu-id="d741b-126">To get the evidence from your assembly, use `this.GetType().Assembly.Evidence`.</span></span> <span data-ttu-id="d741b-127">Bir Tekdüzen Kaynak Tanımlayıcısı (URI) öğesinden kanıt sağlamak için kullanın `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.</span><span class="sxs-lookup"><span data-stu-id="d741b-127">To get the evidence from a Uniform Resource Identifier (URI), use `Evidence e = XmlSecureResolver.CreateEvidenceForUrl(stylesheetURI)`.</span></span>  
  
 <span data-ttu-id="d741b-128">Kullanırsanız <xref:System.Xml.Xsl.XslTransform.Load%2A> ele yöntemleri bir <xref:System.Xml.XmlResolver> ancak hiçbir `Evidence`, derleme için güvenlik bölgesi varsayılan olarak tam güven için.</span><span class="sxs-lookup"><span data-stu-id="d741b-128">If you use <xref:System.Xml.Xsl.XslTransform.Load%2A> methods that take an <xref:System.Xml.XmlResolver> but no `Evidence`, the security zone for the assembly defaults to Full Trust.</span></span> <span data-ttu-id="d741b-129">Daha fazla bilgi için <xref:System.Security.SecurityZone> ve [adlandırılmış izin kümeleri](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d741b-129">For more information, see <xref:System.Security.SecurityZone> and [Named Permission Sets](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span></span>  
  
 <span data-ttu-id="d741b-130">İşlevler içinde bildirilebilir `msxsl:script` öğesi.</span><span class="sxs-lookup"><span data-stu-id="d741b-130">Functions can be declared within the `msxsl:script` element.</span></span> <span data-ttu-id="d741b-131">Aşağıdaki tabloda, varsayılan olarak desteklenen ad alanlarını gösterir.</span><span class="sxs-lookup"><span data-stu-id="d741b-131">The following table shows the namespaces that are supported by default.</span></span> <span data-ttu-id="d741b-132">Listelenen ad alanlarını dışında sınıfları kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d741b-132">You can use classes outside the listed namespaces.</span></span> <span data-ttu-id="d741b-133">Ancak, bu sınıflar, tam olarak nitelenmiş olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d741b-133">However, these classes must be fully qualified.</span></span>  
  
|<span data-ttu-id="d741b-134">Varsayılan ad alanları</span><span class="sxs-lookup"><span data-stu-id="d741b-134">Default Namespaces</span></span>|<span data-ttu-id="d741b-135">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d741b-135">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="d741b-136">Sistem</span><span class="sxs-lookup"><span data-stu-id="d741b-136">System</span></span>|<span data-ttu-id="d741b-137">Sistem sınıfı.</span><span class="sxs-lookup"><span data-stu-id="d741b-137">System class.</span></span>|  
|<span data-ttu-id="d741b-138">System.Collection</span><span class="sxs-lookup"><span data-stu-id="d741b-138">System.Collection</span></span>|<span data-ttu-id="d741b-139">Koleksiyon sınıfları.</span><span class="sxs-lookup"><span data-stu-id="d741b-139">Collection classes.</span></span>|  
|<span data-ttu-id="d741b-140">System.Text</span><span class="sxs-lookup"><span data-stu-id="d741b-140">System.Text</span></span>|<span data-ttu-id="d741b-141">Metin sınıflar.</span><span class="sxs-lookup"><span data-stu-id="d741b-141">Text classes.</span></span>|  
|<span data-ttu-id="d741b-142">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="d741b-142">System.Text.RegularExpressions</span></span>|<span data-ttu-id="d741b-143">Normal ifade sınıfları.</span><span class="sxs-lookup"><span data-stu-id="d741b-143">Regular expression classes.</span></span>|  
|<span data-ttu-id="d741b-144">System.Xml</span><span class="sxs-lookup"><span data-stu-id="d741b-144">System.Xml</span></span>|<span data-ttu-id="d741b-145">Çekirdek XML sınıfları.</span><span class="sxs-lookup"><span data-stu-id="d741b-145">Core XML classes.</span></span>|  
|<span data-ttu-id="d741b-146">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="d741b-146">System.Xml.Xsl</span></span>|<span data-ttu-id="d741b-147">XSLT sınıflar.</span><span class="sxs-lookup"><span data-stu-id="d741b-147">XSLT classes.</span></span>|  
|<span data-ttu-id="d741b-148">System.Xml.XPath</span><span class="sxs-lookup"><span data-stu-id="d741b-148">System.Xml.XPath</span></span>|<span data-ttu-id="d741b-149">XML Path Language (XPath) sınıflar.</span><span class="sxs-lookup"><span data-stu-id="d741b-149">XML Path Language (XPath) classes.</span></span>|  
|<span data-ttu-id="d741b-150">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="d741b-150">Microsoft.VisualBasic</span></span>|<span data-ttu-id="d741b-151">Microsoft Visual Basic komut dosyası için sınıflar sağlar.</span><span class="sxs-lookup"><span data-stu-id="d741b-151">Classes for Microsoft Visual Basic scripts.</span></span>|  
  
 <span data-ttu-id="d741b-152">Bildirilen bir işlev, bir komut dosyası bloğu içinde yer alır.</span><span class="sxs-lookup"><span data-stu-id="d741b-152">When a function is declared, it is contained in a script block.</span></span> <span data-ttu-id="d741b-153">Stil sayfaları, birden çok komut dosyası blokları, diğerinden bağımsız çalışan her içerebilir.</span><span class="sxs-lookup"><span data-stu-id="d741b-153">Style sheets can contain multiple script blocks, each operating independent of the other.</span></span> <span data-ttu-id="d741b-154">Bir betik bloğu içinde yürütülen, aynı ad ve aynı komut dosyası dili bildirildiği sürece başka bir betik bloğu içinde tanımlanan bir işlev çağrısı yapamazsınız anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="d741b-154">That means that if you are executing inside a script block, you cannot call a function that you defined in another script block unless it is declared to have the same namespace and the same scripting language.</span></span> <span data-ttu-id="d741b-155">Çünkü her betik bloğu kendi dilinde olabilir ve blok o dil ayrıştırıcı dilbilgisi kurallara göre ayrıştırılır kullanılan dilin doğru sözdizimini kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="d741b-155">Because each script block can be in its own language, and the block is parsed according to the grammar rules of that language parser, you must use the correct syntax for the language in use.</span></span> <span data-ttu-id="d741b-156">Bir C# betik bloğu içinde varsa, örneğin, bir XML açıklama düğümü kullanmak için bir hata ise `<!-- an XML comment -->` bloğundaki.</span><span class="sxs-lookup"><span data-stu-id="d741b-156">For example, if you are in a C# script block, then it is an error to use an XML comment node `<!-- an XML comment -->` in the block.</span></span>  
  
 <span data-ttu-id="d741b-157">Sağlanan bağımsız değişkenler ve dönüş değerleri betik işlevleri tarafından tanımlanan World Wide Web Consortium (W3C) XPath veya XSLT türlerinden biri olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d741b-157">The supplied arguments and return values defined by the script functions must be one of the World Wide Web Consortium (W3C) XPath or XSLT types.</span></span> <span data-ttu-id="d741b-158">Aşağıdaki tablo W3C türleri karşılık gelen gösterir (tür) eşdeğeri .NET Framework sınıfları ve W3C türü olup olmadığını bir XPath türü veya XSLT türü.</span><span class="sxs-lookup"><span data-stu-id="d741b-158">The following table shows the corresponding W3C types, the equivalent .NET Framework classes (Type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="d741b-159">Tür</span><span class="sxs-lookup"><span data-stu-id="d741b-159">Type</span></span>|<span data-ttu-id="d741b-160">Eşdeğeri .NET Framework sınıfı (tür)</span><span class="sxs-lookup"><span data-stu-id="d741b-160">Equivalent .NET Framework Class (Type)</span></span>|<span data-ttu-id="d741b-161">XPath türü veya XSLT türü</span><span class="sxs-lookup"><span data-stu-id="d741b-161">XPath type or XSLT type</span></span>|  
|----------|----------------------------------------------|-----------------------------|  
|<span data-ttu-id="d741b-162">Dize</span><span class="sxs-lookup"><span data-stu-id="d741b-162">String</span></span>|<span data-ttu-id="d741b-163">System.String</span><span class="sxs-lookup"><span data-stu-id="d741b-163">System.String</span></span>|<span data-ttu-id="d741b-164">XPath</span><span class="sxs-lookup"><span data-stu-id="d741b-164">XPath</span></span>|  
|<span data-ttu-id="d741b-165">Boole değeri</span><span class="sxs-lookup"><span data-stu-id="d741b-165">Boolean</span></span>|<span data-ttu-id="d741b-166">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="d741b-166">System.Boolean</span></span>|<span data-ttu-id="d741b-167">XPath</span><span class="sxs-lookup"><span data-stu-id="d741b-167">XPath</span></span>|  
|<span data-ttu-id="d741b-168">Sayı</span><span class="sxs-lookup"><span data-stu-id="d741b-168">Number</span></span>|<span data-ttu-id="d741b-169">System.Double</span><span class="sxs-lookup"><span data-stu-id="d741b-169">System.Double</span></span>|<span data-ttu-id="d741b-170">XPath</span><span class="sxs-lookup"><span data-stu-id="d741b-170">XPath</span></span>|  
|<span data-ttu-id="d741b-171">Sonuç ağacı parçası</span><span class="sxs-lookup"><span data-stu-id="d741b-171">Result Tree Fragment</span></span>|<span data-ttu-id="d741b-172">System.Xml.XPath.XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d741b-172">System.Xml.XPath.XPathNavigator</span></span>|<span data-ttu-id="d741b-173">XSLT</span><span class="sxs-lookup"><span data-stu-id="d741b-173">XSLT</span></span>|  
|<span data-ttu-id="d741b-174">Düğüm kümesi</span><span class="sxs-lookup"><span data-stu-id="d741b-174">Node Set</span></span>|<span data-ttu-id="d741b-175">System.Xml.XPath.XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="d741b-175">System.Xml.XPath.XPathNodeIterator</span></span>|<span data-ttu-id="d741b-176">XPath</span><span class="sxs-lookup"><span data-stu-id="d741b-176">XPath</span></span>|  
  
 <span data-ttu-id="d741b-177">Betik işlevi aşağıdaki sayısal türlerin yararlanıyorsa: Int16, Uınt16, Int32, Uınt32, Int64, UInt64, tek veya ondalık, bunlar zorunlu için çift, hangi W3C XPath türü sayıya eşler.</span><span class="sxs-lookup"><span data-stu-id="d741b-177">If the script function utilizes one of the following numeric types: Int16, UInt16, Int32, UInt32, Int64, UInt64, Single, or Decimal, they are forced to Double, which maps to the W3C XPath type number.</span></span> <span data-ttu-id="d741b-178">Diğer tüm türlerin bir dizeye çağırarak zorlanır `ToString` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d741b-178">All other types are forced to a string by calling the `ToString` method.</span></span>  
  
 <span data-ttu-id="d741b-179">Betik işlevi kullanır yukarıda belirtenlere dışında bir tür veya işlev derlenemiyor varsa, stil sayfası yüklenir içine <xref:System.Xml.Xsl.XslTransform> nesnesi, bir özel durum harekete geçirilir.</span><span class="sxs-lookup"><span data-stu-id="d741b-179">If the script function utilizes a type other than the ones mentioned above, or if the function does not compile when the style sheet is loaded into the <xref:System.Xml.Xsl.XslTransform> object, an exception is thrown.</span></span>  
  
 <span data-ttu-id="d741b-180">Kullanırken `msxsl:script` öğesi kesinlikle önerilir dili ne olursa olsun kodun içindeki CDATA bölümüne yerleştirilmesi.</span><span class="sxs-lookup"><span data-stu-id="d741b-180">When using the `msxsl:script` element, it is highly recommended that the script, regardless of language, be placed inside a CDATA section.</span></span> <span data-ttu-id="d741b-181">Örneğin, aşağıdaki XML kodunuzu nereye yerleştirileceğini CDATA bölümü şablonunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="d741b-181">For example, the following XML shows the template of the CDATA section where your code is placed.</span></span>  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    <![CDATA[  
    ... your code here ...  
    ]]>  
</msxsl:script>  
```  
  
 <span data-ttu-id="d741b-182">Operatörler, tanımlayıcılar ya da belirli bir dil için sınırlayıcılar XML olarak yanlış olası olduğundan tüm betik içeriği bir CDATA bölümde yerleştirilmesi önerilir.</span><span class="sxs-lookup"><span data-stu-id="d741b-182">It is highly recommended that all script content be placed in a CDATA section, because operators, identifiers, or delimiters for a given language have the potential of being misinterpreted as XML.</span></span> <span data-ttu-id="d741b-183">Aşağıdaki örnek komut dosyasında mantıksal AND işlecinin kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="d741b-183">The following example shows the use of the logical AND operator in script.</span></span>  
  
```xml  
<msxsl:script implements-prefix='yourprefix' language='CSharp'>  
    public string book(string abc, string xyz)  
    {  
        if ((abc == bar) && (abc == xyz)) return bar + xyz;  
        else return null;  
    }  
</msxsl:script>  
```  
  
 <span data-ttu-id="d741b-184">Bu, kodlarına kaçış için özel durum oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d741b-184">This throws an exception because the ampersands are not escaped.</span></span> <span data-ttu-id="d741b-185">Belge XML olarak yüklenir ve hiçbir özel olarak değerlendirilmesi arasındaki metni uygulanan `msxsl:script` öğesi etiketleri.</span><span class="sxs-lookup"><span data-stu-id="d741b-185">The document is loaded as XML, and no special treatment is applied to the text between the `msxsl:script` element tags.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d741b-186">Örnek</span><span class="sxs-lookup"><span data-stu-id="d741b-186">Example</span></span>  
 <span data-ttu-id="d741b-187">Aşağıdaki örnek bir katıştırılmış betik, RADIUS verilmiş bir daire çevresi hesaplamak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="d741b-187">The following example uses an embedded script to calculate the circumference of a circle given its radius.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "calc.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XmlTextWriter to output to the console.               
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
    writer.Formatting = Formatting.Indented  
  
    'Transform the file.  
    xslt.Transform(doc, Nothing, writer, Nothing)  
    writer.Close()  
  End Sub   
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "number.xml";  
   private const String stylesheet = "calc.xsl";  
  
   public static void Main()  
   {  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XmlTextWriter to output to the console.               
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
    writer.Formatting = Formatting.Indented;  
  
    //Transform the file.  
    xslt.Transform(doc, null, writer, null);  
    writer.Close();  
  }  
}  
```  
  
## <a name="input"></a><span data-ttu-id="d741b-188">Giriş</span><span class="sxs-lookup"><span data-stu-id="d741b-188">Input</span></span>  
 <span data-ttu-id="d741b-189">Number.XML</span><span class="sxs-lookup"><span data-stu-id="d741b-189">number.xml</span></span>  
  
```xml  
<?xml version='1.0'?>  
<data>  
  <circle>  
    <radius>12</radius>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
  </circle>  
</data>  
```  
  
 <span data-ttu-id="d741b-190">CALC.xsl</span><span class="sxs-lookup"><span data-stu-id="d741b-190">calc.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
    xmlns:user="urn:my-scripts">  
  
  <msxsl:script language="C#" implements-prefix="user">  
     <![CDATA[  
     public double circumference(double radius)  
     {  
       double pi = 3.14;  
       double circ = pi*radius*2;  
       return circ;  
     }  
      ]]>  
   </msxsl:script>  
  
  <xsl:template match="data">    
  <circles>  
  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="user:circumference(radius)"/>   
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a><span data-ttu-id="d741b-191">Çıkış</span><span class="sxs-lookup"><span data-stu-id="d741b-191">Output</span></span>  
  
```xml  
<circles xmlns:msxsl="urn:schemas-microsoft-com:xslt" xmlns:user="urn:my-scripts">  
  <circle>  
    <radius>12</radius>  
    <circumference>75.36</circumference>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
    <circumference>235.5</circumference>  
  </circle>  
</circles>    
```  
  
## <a name="see-also"></a><span data-ttu-id="d741b-192">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d741b-192">See also</span></span>

- [<span data-ttu-id="d741b-193">XslTransform Sınıfı XSLT İşlemcisini Uygular</span><span class="sxs-lookup"><span data-stu-id="d741b-193">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
