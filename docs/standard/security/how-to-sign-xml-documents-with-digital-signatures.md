---
title: 'Nasıl yapılır: XML Belgelerini Dijital İmzalarla imzalama'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signatures, XML signing
- System.Security.Cryptography.SignedXml class
- digital signatures, XML signing
- System.Security.Cryptography.RSACryptoServiceProvider class
- XML digital signatures
- XML signing
- signing XML
ms.assetid: 99692ac1-d8c9-42d7-b1bf-2737b01037e4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 39e053ea9ca0b2fdc548a4b9447d34e852816a61
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324506"
---
# <a name="how-to-sign-xml-documents-with-digital-signatures"></a><span data-ttu-id="6897d-102">Nasıl yapılır: XML Belgelerini Dijital İmzalarla imzalama</span><span class="sxs-lookup"><span data-stu-id="6897d-102">How to: Sign XML Documents with Digital Signatures</span></span>
<span data-ttu-id="6897d-103">Sınıfları kullanabilirsiniz <xref:System.Security.Cryptography.Xml> bir XML belgesi ya da bir dijital imzaya sahip bir XML belgesi bir parçası olarak imzalamak için ad alanı.</span><span class="sxs-lookup"><span data-stu-id="6897d-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to sign an XML document or part of an XML document with a digital signature.</span></span>  <span data-ttu-id="6897d-104">XML dijital imzaları (XMLDSIG) imzalandıktan sonra veri değiştirilmiş değil olduğunu doğrulamanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="6897d-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span>  <span data-ttu-id="6897d-105">World Wide Web Consortium (W3C) öneri XMLDSIG standart hakkında daha fazla bilgi için bkz. [XML imza söz dizimi ve işleme](https://www.w3.org/TR/xmldsig-core/).</span><span class="sxs-lookup"><span data-stu-id="6897d-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
 <span data-ttu-id="6897d-106">Kod örneği, bu yordamı dijital olarak tüm bir XML belgesi oturum ve imza belgede ekleme yapmayı gösteren bir <`Signature`> öğesi.</span><span class="sxs-lookup"><span data-stu-id="6897d-106">The code example in this procedure demonstrates how to digitally sign an entire XML document and attach the signature to the document in a <`Signature`> element.</span></span>  <span data-ttu-id="6897d-107">Örnek, RSA imzalama anahtarı oluşturur, anahtarı güvenli bir anahtar kapsayıcısına ekler ve ardından bir XML belgesinin dijital olarak imzalamak için anahtar kullanır.</span><span class="sxs-lookup"><span data-stu-id="6897d-107">The example creates an RSA signing key, adds the key to a secure key container, and then uses the key to digitally sign an XML document.</span></span>  <span data-ttu-id="6897d-108">Anahtar XML dijital imzasını alınabilir veya başka bir XML belgesi imzalamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6897d-108">The key can then be retrieved to verify the XML digital signature, or can be used to sign another XML document.</span></span>  
  
 <span data-ttu-id="6897d-109">Bu yordamı kullanılarak oluşturulan bir XML dijital imza doğrulama hakkında daha fazla bilgi için bkz: [nasıl yapılır: XML belgelerinin dijital imzalarını doğrulama](../../../docs/standard/security/how-to-verify-the-digital-signatures-of-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="6897d-109">For information about how to verify an XML digital signature that was created using this procedure, see [How to: Verify the Digital Signatures of XML Documents](../../../docs/standard/security/how-to-verify-the-digital-signatures-of-xml-documents.md).</span></span>  
  
### <a name="to-digitally-sign-an-xml-document"></a><span data-ttu-id="6897d-110">Bir XML belgesinin dijital olarak imzalamak için</span><span class="sxs-lookup"><span data-stu-id="6897d-110">To digitally sign an XML document</span></span>  
  
1. <span data-ttu-id="6897d-111">Oluşturma bir <xref:System.Security.Cryptography.CspParameters> nesne ve anahtar kapsayıcısı adını belirtin.</span><span class="sxs-lookup"><span data-stu-id="6897d-111">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToSignXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="6897d-112">Bir asimetrik anahtar kullanarak Oluştur <xref:System.Security.Cryptography.RSACryptoServiceProvider> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="6897d-112">Generate an asymmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="6897d-113">Geçirdiğinizde anahtarı için anahtar kapsayıcısını otomatik olarak kaydedilir <xref:System.Security.Cryptography.CspParameters> nesnesi oluşturucusuna <xref:System.Security.Cryptography.RSACryptoServiceProvider> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="6897d-113">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="6897d-114">Bu anahtar, XML belgesi imzalamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6897d-114">This key will be used to sign the XML document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToSignXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="6897d-115">Oluşturma bir <xref:System.Xml.XmlDocument> diskten bir XML dosyası yüklenirken nesne.</span><span class="sxs-lookup"><span data-stu-id="6897d-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="6897d-116"><xref:System.Xml.XmlDocument> Nesne şifrelemek için XML öğesi içerir.</span><span class="sxs-lookup"><span data-stu-id="6897d-116">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToSignXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="6897d-117">Yeni bir <xref:System.Security.Cryptography.Xml.SignedXml> nesne ve geçirin <xref:System.Xml.XmlDocument> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="6897d-117">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToSignXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="6897d-118">İmzalama RSA anahtarı ekleme <xref:System.Security.Cryptography.Xml.SignedXml> nesne.</span><span class="sxs-lookup"><span data-stu-id="6897d-118">Add the signing RSA key to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToSignXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="6897d-119">Oluşturma bir <xref:System.Security.Cryptography.Xml.Reference> oturum gerekenler tanımlayan nesne.</span><span class="sxs-lookup"><span data-stu-id="6897d-119">Create a <xref:System.Security.Cryptography.Xml.Reference> object that describes what to sign.</span></span>  <span data-ttu-id="6897d-120">Tüm belgeyi imzalamak için ayarlanmış <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> özelliğini `""`.</span><span class="sxs-lookup"><span data-stu-id="6897d-120">To sign the entire document, set the <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> property to `""`.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToSignXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="6897d-121">Ekleme bir <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> nesnesini <xref:System.Security.Cryptography.Xml.Reference> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="6897d-121">Add an <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> object to the <xref:System.Security.Cryptography.Xml.Reference> object.</span></span>  <span data-ttu-id="6897d-122">Bir dönüştürme imzalayan kullanılan aynı şekilde XML verileri temsil etmek Doğrulayıcı sağlar.</span><span class="sxs-lookup"><span data-stu-id="6897d-122">A transformation allows the verifier to represent the XML data in the identical manner that the signer used.</span></span>  <span data-ttu-id="6897d-123">Bu doğrulama için önemli bir adımdır şekilde XML verileri farklı şekillerde temsil edilebilir.</span><span class="sxs-lookup"><span data-stu-id="6897d-123">XML data can be represented in different ways, so this step is vital to verification.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToSignXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#8)]  
  
8. <span data-ttu-id="6897d-124">Ekleme <xref:System.Security.Cryptography.Xml.Reference> nesnesini <xref:System.Security.Cryptography.Xml.SignedXml> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="6897d-124">Add the <xref:System.Security.Cryptography.Xml.Reference> object to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#9)]
     [!code-vb[HowToSignXMLDocumentRSA#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#9)]  
  
9. <span data-ttu-id="6897d-125">İmza çağırarak işlem <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6897d-125">Compute the signature by calling the <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A> method.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#10)]
     [!code-vb[HowToSignXMLDocumentRSA#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#10)]  
  
10. <span data-ttu-id="6897d-126">İmza XML gösterimini almak (bir <`Signature`> öğesi) ve yeni bir kaydetme <xref:System.Xml.XmlElement> nesne.</span><span class="sxs-lookup"><span data-stu-id="6897d-126">Retrieve the XML representation of the signature (a <`Signature`> element) and save it to a new <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#11)]
     [!code-vb[HowToSignXMLDocumentRSA#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#11)]  
  
11. <span data-ttu-id="6897d-127">Öğesine ekleme <xref:System.Xml.XmlDocument> nesne.</span><span class="sxs-lookup"><span data-stu-id="6897d-127">Append the element to the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#12)]
     [!code-vb[HowToSignXMLDocumentRSA#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#12)]  
  
12. <span data-ttu-id="6897d-128">Belgeyi kaydedin.</span><span class="sxs-lookup"><span data-stu-id="6897d-128">Save the document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#13)]
     [!code-vb[HowToSignXMLDocumentRSA#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="6897d-129">Örnek</span><span class="sxs-lookup"><span data-stu-id="6897d-129">Example</span></span>  
 <span data-ttu-id="6897d-130">Bu örnek adlı bir dosya olduğunu varsayar `test.xml` derlenmiş programın aynı dizinde bulunmaktadır.</span><span class="sxs-lookup"><span data-stu-id="6897d-130">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="6897d-131">Aşağıdaki XML adlı bir dosyaya yerleştirebilirsiniz `test.xml` ve bu örneği kullanın.</span><span class="sxs-lookup"><span data-stu-id="6897d-131">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToSignXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToSignXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6897d-132">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="6897d-132">Compiling the Code</span></span>  
  
-   <span data-ttu-id="6897d-133">Bu örneği derlemeye bir başvuru eklemek gereken `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="6897d-133">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="6897d-134">Aşağıdaki ad alanlarını içerir: <xref:System.Xml>, <xref:System.Security.Cryptography>, ve <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="6897d-134">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6897d-135">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="6897d-135">.NET Framework Security</span></span>  
 <span data-ttu-id="6897d-136">Hiçbir zaman depolayabilen veya asimetrik anahtar çifti düz metin olarak özel anahtarı.</span><span class="sxs-lookup"><span data-stu-id="6897d-136">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="6897d-137">Simetrik hem de asimetrik şifreleme anahtarları hakkında daha fazla bilgi için bkz. [şifreleme ve şifre çözme için anahtarlar oluşturma](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="6897d-137">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="6897d-138">Hiçbir zaman bir özel anahtar doğrudan sizin kaynak kodunuza ekleyin.</span><span class="sxs-lookup"><span data-stu-id="6897d-138">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="6897d-139">Katıştırılmış anahtarları kullanarak bir derlemeden kolayca da okunabilir [Ildasm.exe (IL ayrıştırıcı)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) veya Not Defteri gibi bir metin düzenleyicisinde derleme açarak.</span><span class="sxs-lookup"><span data-stu-id="6897d-139">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6897d-140">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6897d-140">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="6897d-141">Nasıl yapılır: XML Belgelerinin Dijital İmzalarını Doğrulama</span><span class="sxs-lookup"><span data-stu-id="6897d-141">How to: Verify the Digital Signatures of XML Documents</span></span>](../../../docs/standard/security/how-to-verify-the-digital-signatures-of-xml-documents.md)
