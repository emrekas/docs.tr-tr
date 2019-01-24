---
title: Şifreleme ve Şifre Çözme için Anahtarlar Oluşturma
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET Framework], keys
- symmetric keys
- asymmetric keys [.NET Framework]
- cryptography [.NET Framework], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32f9a5f92ae580839ce46476de9f9c7edcd54685
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573406"
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="5c350-102">Şifreleme ve Şifre Çözme için Anahtarlar Oluşturma</span><span class="sxs-lookup"><span data-stu-id="5c350-102">Generating Keys for Encryption and Decryption</span></span>
<span data-ttu-id="5c350-103">Anahtarları oluşturmak ve yönetmek, şifreleme işleminin önemli bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="5c350-103">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="5c350-104">Simetrik algoritmalar, bir anahtarın ve başlangıç vektörünün (IV) oluşturulmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="5c350-104">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="5c350-105">Anahtar, verinizin şifresini çözmemesi gereken herkesten gizli tutulmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5c350-105">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="5c350-106">IV'nin gizli olması gerekmez ancak her oturum için değiştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="5c350-106">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="5c350-107">Asimetrik algoritmalar bir ortak anahtarın, bir de özel anahtarın oluşturulmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="5c350-107">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="5c350-108">Ortak anahtar herhangi birine verilebilirken, özel anahtar yalnızca ortak anahtar ile şifrelenen verilerin şifresini çözecek tarafça bilinmelidir.</span><span class="sxs-lookup"><span data-stu-id="5c350-108">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="5c350-109">Bu bölümde, hem simetrik, hem de asimetrik algoritmalar için anahtarların nasıl oluşturulacağı ve yönetileceği açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="5c350-109">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="5c350-110">Simetrik Anahtarlar</span><span class="sxs-lookup"><span data-stu-id="5c350-110">Symmetric Keys</span></span>  
 <span data-ttu-id="5c350-111">.NET Framework tarafından sağlanan simetrik şifreleme sınıfları, veriler üzerine şifreleme ve şifre çözme yapabilmek için bir anahtar ve yeni bir başlatma vektörü (IV) gerektirir.</span><span class="sxs-lookup"><span data-stu-id="5c350-111">The symmetric encryption classes supplied by the .NET Framework require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="5c350-112">Varsayılan oluşturucuyu kullanarak yönetilen simetrik şifreleme sınıflarından birinin yeni bir örneğini oluşturduğunuzda, otomatik olarak yeni bir anahtar ve IV oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="5c350-112">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the default constructor, a new key and IV are automatically created.</span></span> <span data-ttu-id="5c350-113">Verilerinizin şifresini çözmesine izin verdiğiniz kişilerin aynı anahtara ve IV'ye sahip olup aynı algoritmayı kullanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="5c350-113">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="5c350-114">Genellikle, her oturum için yeni bir anahtar ve IV oluşturulmalıdır, ve ne anahtar ne de IV daha sonraki bir oturumda kullanılmak üzere saklanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5c350-114">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="5c350-115">Bir simetrik anahtarı ve IV'yi uzaktaki bir kişiye iletmek için, genellikle simetrik anahtarı asimetrik şifreleme kullanarak şifrelersiniz.</span><span class="sxs-lookup"><span data-stu-id="5c350-115">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="5c350-116">Anahtarı güvenli olmayan bir ağ üzerinde şifrelemeden göndermek güvenli değildir, çünkü anahtarı ve IV'yi yakalayan herhangi biri verilerinizin şifresini çözebilir.</span><span class="sxs-lookup"><span data-stu-id="5c350-116">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span> <span data-ttu-id="5c350-117">Şifreleme kullanarak veri değişimi hakkında daha fazla bilgi için bkz. [şifreleme düzeni oluşturma](../../../docs/standard/security/creating-a-cryptographic-scheme.md).</span><span class="sxs-lookup"><span data-stu-id="5c350-117">For more information about exchanging data by using encryption, see [Creating a Cryptographic Scheme](../../../docs/standard/security/creating-a-cryptographic-scheme.md).</span></span>  
  
 <span data-ttu-id="5c350-118">Aşağıdaki örnek, TripleDES algoritmasını uygulayan <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> sınıfının yeni bir örneğinin oluşturulmasını gösterir.</span><span class="sxs-lookup"><span data-stu-id="5c350-118">The following example shows the creation of a new instance of the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class that implements the TripleDES algorithm.</span></span>  
  
```vb  
Dim TDES As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider TDES = new TripleDESCryptoServiceProvider();  
```  
  
 <span data-ttu-id="5c350-119">Önceki kod yürütüldüğünde, yeni bir anahtar ve IV oluşturulur ve bulundukları **anahtarı** ve **IV** özellikleri, sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="5c350-119">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="5c350-120">Bazen birden çok anahtar oluşturmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="5c350-120">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="5c350-121">Bu durumda, Simetrik algoritma uygulayan bir sınıf yeni bir örneğini oluşturabilir ve çağırarak yeni bir anahtar ve IV oluşturma **GenerateKey** ve **Generateıv** yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="5c350-121">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="5c350-122">Aşağıdaki kod örneği, simetrik şifreleme sınıfının yeni bir örneğini yapıldıktan sonra yeni anahtar ve Iv'lerin oluşturma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="5c350-122">The following code example illustrates how to create new keys and IVs after a new instance of the symmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim TDES As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
TDES.GenerateIV()  
TDES.GenerateKey()  
```  
  
```csharp  
TripleDESCryptoServiceProvider TDES = new TripleDESCryptoServiceProvider();  
TDES.GenerateIV();  
TDES.GenerateKey();  
```  
  
 <span data-ttu-id="5c350-123">Önceki kod yürütüldüğünde, bir anahtar ve IV oluşturulur, yeni bir örneğini **TripleDESCryptoServiceProvider** yapılır.</span><span class="sxs-lookup"><span data-stu-id="5c350-123">When the previous code is executed, a key and IV are generated when the new instance of **TripleDESCryptoServiceProvider** is made.</span></span> <span data-ttu-id="5c350-124">Başka bir anahtar ve IV oluşturulur **GenerateKey** ve **Generateıv** yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="5c350-124">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>  
  
## <a name="asymmetric-keys"></a><span data-ttu-id="5c350-125">Asimetrik Anahtarlar</span><span class="sxs-lookup"><span data-stu-id="5c350-125">Asymmetric Keys</span></span>  
 <span data-ttu-id="5c350-126">.NET Framework, asimetrik şifreleme için <xref:System.Security.Cryptography.RSACryptoServiceProvider> ve <xref:System.Security.Cryptography.DSACryptoServiceProvider> sınıflarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="5c350-126">The .NET Framework provides the <xref:System.Security.Cryptography.RSACryptoServiceProvider> and <xref:System.Security.Cryptography.DSACryptoServiceProvider> classes for asymmetric encryption.</span></span> <span data-ttu-id="5c350-127">Bu sınıflar, yeni bir örnek oluşturmak için varsayılan oluşturucuyu kullandığınızda bir ortak/özel anahtar çifti oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5c350-127">These classes create a public/private key pair when you use the default constructor to create a new instance.</span></span> <span data-ttu-id="5c350-128">Asimetrik anahtarlar birden çok oturumda kullanılmak üzere saklanabilir ya da yalnızca tek bir oturum için oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="5c350-128">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="5c350-129">Ortak anahtar genel olarak kullanılabilir olabilse de, özel anahtar dikkatle korunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5c350-129">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="5c350-130">Bir asimetrik sınıfın her yeni örneği oluşturulduğunda bir ortak/özel anahtar çifti oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="5c350-130">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="5c350-131">Sınıfın yeni bir örneği oluşturulduktan sonra, anahtar bilgileri şu iki yöntemden biriyle alınabilir:</span><span class="sxs-lookup"><span data-stu-id="5c350-131">After a new instance of the class is created, the key information can be extracted using one of two methods:</span></span>  
  
-   <span data-ttu-id="5c350-132"><xref:System.Security.Cryptography.RSA.ToXmlString%2A> Anahtar bilgilerini bir XML temsilini döndüren bir yöntem.</span><span class="sxs-lookup"><span data-stu-id="5c350-132">The <xref:System.Security.Cryptography.RSA.ToXmlString%2A> method, which returns an XML representation of the key information.</span></span>  
  
-   <span data-ttu-id="5c350-133">Anahtar bilgilerini tutan bir <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> yapısı döndüren <xref:System.Security.Cryptography.RSAParameters> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="5c350-133">The <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span>  
  
 <span data-ttu-id="5c350-134">İki yöntem de yalnızca ortak anahtar bilgisinin mi dönüleceğini yoksa hem ortak anahtar hem de özel anahtar bilgisinin mi dönüleceğini belirten bir Boolean değerini kabul eder.</span><span class="sxs-lookup"><span data-stu-id="5c350-134">Both methods accept a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span> <span data-ttu-id="5c350-135">Bir **RSACryptoServiceProvider** sınıfı değeri olarak başlatılabilir bir **RSAParameters** kullanarak yapısı <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="5c350-135">An **RSACryptoServiceProvider** class can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> method.</span></span>  
  
 <span data-ttu-id="5c350-136">Asimetrik özel anahtarlar yerel bilgisayarda asla oldukları gibi veya düz metin olarak tutulmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="5c350-136">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="5c350-137">Özel anahtarı depolamanız gerekiyorsa, bir anahtar kapsayıcısı kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5c350-137">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="5c350-138">Özel bir anahtarı bir anahtar kapsayıcısı içinde saklamak hakkında daha fazla bilgi için bkz. [nasıl yapılır: Bir anahtar kapsayıcısında asimetrik anahtarlar Store](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="5c350-138">For more on how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="5c350-139">Aşağıdaki kod örneğinde yeni bir örneğini oluşturur **RSACryptoServiceProvider** sınıfı, bir ortak/özel anahtar çifti oluşturma ve ortak anahtar bilgisini kaydeder bir **RSAParameters** yapısı.</span><span class="sxs-lookup"><span data-stu-id="5c350-139">The following code example creates a new instance of the **RSACryptoServiceProvider** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim RSA as RSACryptoServiceProvider = new RSACryptoServiceProvider()  
'Save the public key information to an RSAParameters structure.  
Dim RSAKeyInfo As RSAParameters = RSA.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
//Save the public key information to an RSAParameters structure.  
RSAParameters RSAKeyInfo = RSA.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c350-140">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5c350-140">See also</span></span>

- [<span data-ttu-id="5c350-141">Veri Şifreleme</span><span class="sxs-lookup"><span data-stu-id="5c350-141">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)
- [<span data-ttu-id="5c350-142">Verilerin Şifresini Çözme</span><span class="sxs-lookup"><span data-stu-id="5c350-142">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)
- [<span data-ttu-id="5c350-143">Şifreleme Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="5c350-143">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="5c350-144">Nasıl yapılır: Bir anahtar kapsayıcısında asimetrik anahtarlar Store</span><span class="sxs-lookup"><span data-stu-id="5c350-144">How to: Store Asymmetric Keys in a Key Container</span></span>](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md)
