---
title: 'İzlenecek yol: Şifreleme Uygulaması Oluşturma'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET Framework], example
- cryptography [NET Framework], cryptographic application example
- cryptography [NET Framework], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f141f21f80275a592caf3f87a5cbe0def6869c0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795011"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="3fc50-102">İzlenecek yol: Şifreleme Uygulaması Oluşturma</span><span class="sxs-lookup"><span data-stu-id="3fc50-102">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="3fc50-103">Bu izlenecek yol, şifrelemek ve içeriğin şifresini gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="3fc50-103">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="3fc50-104">Kod örnekleri, bir Windows Forms uygulaması için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="3fc50-104">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="3fc50-105">Bu uygulama, akıllı kart kullanma gibi gerçek dünya senaryolarını göstermemiz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="3fc50-105">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="3fc50-106">Bunun yerine, şifreleme ve şifre çözme temellerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="3fc50-106">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="3fc50-107">Bu izlenecek yol aşağıdaki yönergeler için şifreleme kullanır:</span><span class="sxs-lookup"><span data-stu-id="3fc50-107">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="3fc50-108">Kullanım <xref:System.Security.Cryptography.RijndaelManaged> sınıfı, şifrelemek ve kendi otomatik olarak oluşturulan kullanarak verilerin şifresini bir Simetrik algoritma <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> ve <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span><span class="sxs-lookup"><span data-stu-id="3fc50-108">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="3fc50-109">Kullanım <xref:System.Security.Cryptography.RSACryptoServiceProvider>, şifreleme ve anahtar tarafından şifrelenmiş verilerin şifresini çözmek için bir asimetrik algoritma <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="3fc50-109">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="3fc50-110">Asimetrik algoritmalar, daha küçük miktarda bir anahtarı gibi veriler için en iyi şekilde kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3fc50-110">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3fc50-111">Şifrelenmiş içeriği diğer kullanıcılarla değişimi yerine bilgisayarınızdaki verileri korumak istiyorsanız, kullanmayı <xref:System.Security.Cryptography.ProtectedData> veya <xref:System.Security.Cryptography.ProtectedMemory> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="3fc50-111">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="3fc50-112">Aşağıdaki tabloda, bu konudaki şifreleme görevleri özetler.</span><span class="sxs-lookup"><span data-stu-id="3fc50-112">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="3fc50-113">Görev</span><span class="sxs-lookup"><span data-stu-id="3fc50-113">Task</span></span>|<span data-ttu-id="3fc50-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3fc50-114">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="3fc50-115">Bir Windows Forms uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="3fc50-115">Creating a Windows Forms application</span></span>|<span data-ttu-id="3fc50-116">Uygulamayı çalıştırmak için gerekli denetimleri listeler.</span><span class="sxs-lookup"><span data-stu-id="3fc50-116">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="3fc50-117">Genel nesne bildirme</span><span class="sxs-lookup"><span data-stu-id="3fc50-117">Declaring global objects</span></span>|<span data-ttu-id="3fc50-118">Yol değişkenleri, dize bildirir <xref:System.Security.Cryptography.CspParameters>ve <xref:System.Security.Cryptography.RSACryptoServiceProvider> genel kapsamında sahip <xref:System.Windows.Forms.Form> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="3fc50-118">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="3fc50-119">Asimetrik anahtar oluşturma</span><span class="sxs-lookup"><span data-stu-id="3fc50-119">Creating an asymmetric key</span></span>|<span data-ttu-id="3fc50-120">Bir asimetrik ortak ve özel anahtar değer çifti oluşturur ve bir anahtar kapsayıcısı adını atar.</span><span class="sxs-lookup"><span data-stu-id="3fc50-120">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="3fc50-121">Bir dosya şifreleme</span><span class="sxs-lookup"><span data-stu-id="3fc50-121">Encrypting a file</span></span>|<span data-ttu-id="3fc50-122">Şifreleme için bir dosya seçmek için bir iletişim kutusu görüntüler ve dosyayı şifreler.</span><span class="sxs-lookup"><span data-stu-id="3fc50-122">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="3fc50-123">Bir dosyanın şifresini çözmek üzere</span><span class="sxs-lookup"><span data-stu-id="3fc50-123">Decrypting a file</span></span>|<span data-ttu-id="3fc50-124">Şifre çözme için şifrelenmiş bir dosya seçmek için bir iletişim kutusu görüntüler ve dosyanın şifresini çözer.</span><span class="sxs-lookup"><span data-stu-id="3fc50-124">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="3fc50-125">Özel anahtarı alma</span><span class="sxs-lookup"><span data-stu-id="3fc50-125">Getting a private key</span></span>|<span data-ttu-id="3fc50-126">Tam anahtar çiftini kullanarak anahtar kapsayıcısı adını alır.</span><span class="sxs-lookup"><span data-stu-id="3fc50-126">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="3fc50-127">Ortak anahtarı dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="3fc50-127">Exporting a public key</span></span>|<span data-ttu-id="3fc50-128">Bu anahtar yalnızca ortak parametreleri içeren bir XML dosyası kaydeder.</span><span class="sxs-lookup"><span data-stu-id="3fc50-128">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="3fc50-129">Bir ortak anahtar içeri aktarma</span><span class="sxs-lookup"><span data-stu-id="3fc50-129">Importing a public key</span></span>|<span data-ttu-id="3fc50-130">Anahtarı bir XML dosyasından anahtar kapsayıcısına yükler.</span><span class="sxs-lookup"><span data-stu-id="3fc50-130">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="3fc50-131">Uygulamayı test etme</span><span class="sxs-lookup"><span data-stu-id="3fc50-131">Testing the application</span></span>|<span data-ttu-id="3fc50-132">Bu uygulamayı test etme yordamları listeler.</span><span class="sxs-lookup"><span data-stu-id="3fc50-132">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="3fc50-133">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="3fc50-133">Prerequisites</span></span>  
 <span data-ttu-id="3fc50-134">Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:</span><span class="sxs-lookup"><span data-stu-id="3fc50-134">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="3fc50-135">Başvurular <xref:System.IO> ve <xref:System.Security.Cryptography> ad alanları.</span><span class="sxs-lookup"><span data-stu-id="3fc50-135">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="3fc50-136">Bir Windows Forms uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="3fc50-136">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="3fc50-137">Bu izlenecek yolda kod örnekleri çoğu, düğme denetimleri için olay işleyicileri olacak şekilde tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="3fc50-137">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="3fc50-138">Aşağıdaki tablo kod örneklerle eşleşmesi örnek uygulamayı ve gerekli adları için gerekli denetimleri listeler.</span><span class="sxs-lookup"><span data-stu-id="3fc50-138">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="3fc50-139">Denetim</span><span class="sxs-lookup"><span data-stu-id="3fc50-139">Control</span></span>|<span data-ttu-id="3fc50-140">Ad</span><span class="sxs-lookup"><span data-stu-id="3fc50-140">Name</span></span>|<span data-ttu-id="3fc50-141">Metin özelliği (gereken şekilde)</span><span class="sxs-lookup"><span data-stu-id="3fc50-141">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="3fc50-142">Dosya şifreleme</span><span class="sxs-lookup"><span data-stu-id="3fc50-142">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="3fc50-143">Dosyasının şifresini çözme</span><span class="sxs-lookup"><span data-stu-id="3fc50-143">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="3fc50-144">Anahtarları oluşturma</span><span class="sxs-lookup"><span data-stu-id="3fc50-144">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="3fc50-145">Ortak anahtarı dışarı aktar</span><span class="sxs-lookup"><span data-stu-id="3fc50-145">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="3fc50-146">Ortak anahtar içeri aktarma</span><span class="sxs-lookup"><span data-stu-id="3fc50-146">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="3fc50-147">Özel anahtarı alma</span><span class="sxs-lookup"><span data-stu-id="3fc50-147">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="3fc50-148">Olay işleyicilerini oluşturmak için Visual Studio Tasarımcısı'nda düğmeleri çift tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3fc50-148">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="3fc50-149">Genel nesne bildirme</span><span class="sxs-lookup"><span data-stu-id="3fc50-149">Declaring Global Objects</span></span>  
 <span data-ttu-id="3fc50-150">Aşağıdaki kod, formun oluşturucuyu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="3fc50-150">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="3fc50-151">Dize değişkenleri ortamınız ve tercihlerinizle düzenleyin.</span><span class="sxs-lookup"><span data-stu-id="3fc50-151">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="3fc50-152">Asimetrik anahtar oluşturma</span><span class="sxs-lookup"><span data-stu-id="3fc50-152">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="3fc50-153">Bu görev, şifreler ve şifresini çözer asimetrik bir anahtar oluşturur. <xref:System.Security.Cryptography.RijndaelManaged> anahtarı.</span><span class="sxs-lookup"><span data-stu-id="3fc50-153">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="3fc50-154">Bu anahtar, içeriği şifrelemek için kullanılan ve etiket denetiminde anahtar kapsayıcısı adını görüntüler.</span><span class="sxs-lookup"><span data-stu-id="3fc50-154">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="3fc50-155">Aşağıdaki kodu olarak ekleyin `Click` için olay işleyicisi `Create Keys` düğmesine (`buttonCreateAsmKeys_Click`).</span><span class="sxs-lookup"><span data-stu-id="3fc50-155">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="3fc50-156">Bir dosya şifreleme</span><span class="sxs-lookup"><span data-stu-id="3fc50-156">Encrypting a File</span></span>  
 <span data-ttu-id="3fc50-157">Bu görev, iki yöntem içerir: olay işleyicisi yöntemi için `Encrypt File` düğmesine (`buttonEncryptFile_Click`) ve `EncryptFile` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-157">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="3fc50-158">İlk yöntem, bir dosya seçmek için bir iletişim kutusu görüntüler ve dosya adını şifreleme gerçekleştirir ikinci yöntem geçirir.</span><span class="sxs-lookup"><span data-stu-id="3fc50-158">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="3fc50-159">Şifrelenmiş içeriği, anahtar ve IV tümü için kaydedilir <xref:System.IO.FileStream>, adlandırılır şifreleme paketi olarak.</span><span class="sxs-lookup"><span data-stu-id="3fc50-159">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="3fc50-160">`EncryptFile` Yöntemi şunları yapar:</span><span class="sxs-lookup"><span data-stu-id="3fc50-160">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="3fc50-161">Oluşturur bir <xref:System.Security.Cryptography.RijndaelManaged> içeriği şifrelemek için Simetrik algoritma.</span><span class="sxs-lookup"><span data-stu-id="3fc50-161">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="3fc50-162">Oluşturur bir <xref:System.Security.Cryptography.RSACryptoServiceProvider> şifrelemek için nesne <xref:System.Security.Cryptography.RijndaelManaged> anahtarı.</span><span class="sxs-lookup"><span data-stu-id="3fc50-162">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3. <span data-ttu-id="3fc50-163">Kullanan bir <xref:System.Security.Cryptography.CryptoStream> okuyun ve şifrelemek üzere nesne <xref:System.IO.FileStream> baytlara hedef blokları kaynak dosyasının <xref:System.IO.FileStream> şifrelenmiş dosya için nesne.</span><span class="sxs-lookup"><span data-stu-id="3fc50-163">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="3fc50-164">Şifrelenmiş anahtarı ve IV'yi uzunluklarının belirler ve uzunluğu değerlerine bayt dizileri oluşturur.</span><span class="sxs-lookup"><span data-stu-id="3fc50-164">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="3fc50-165">Anahtar ve IV uzunluğu değerlerine şifrelenmiş paketi yazar.</span><span class="sxs-lookup"><span data-stu-id="3fc50-165">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="3fc50-166">Şifreleme paketi aşağıdaki biçimdedir:</span><span class="sxs-lookup"><span data-stu-id="3fc50-166">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="3fc50-167">Anahtar uzunluğu, bayt 0 - 3</span><span class="sxs-lookup"><span data-stu-id="3fc50-167">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="3fc50-168">IV uzunluğu, 4-7 bayt</span><span class="sxs-lookup"><span data-stu-id="3fc50-168">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="3fc50-169">Şifrelenmiş anahtarı</span><span class="sxs-lookup"><span data-stu-id="3fc50-169">Encrypted key</span></span>  
  
- <span data-ttu-id="3fc50-170">IV</span><span class="sxs-lookup"><span data-stu-id="3fc50-170">IV</span></span>  
  
- <span data-ttu-id="3fc50-171">Şifre metni</span><span class="sxs-lookup"><span data-stu-id="3fc50-171">Cipher text</span></span>  
  
 <span data-ttu-id="3fc50-172">Anahtar ve IV uzunluklarının başlangıç noktaları ve ardından dosyasının şifresini çözmek için kullanılan şifreleme paketinin tüm bölümlerinin uzunlukları belirlemek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3fc50-172">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="3fc50-173">Aşağıdaki kodu olarak ekleyin `Click` için olay işleyicisi `Encrypt File` düğmesine (`buttonEncryptFile_Click`).</span><span class="sxs-lookup"><span data-stu-id="3fc50-173">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="3fc50-174">Aşağıdaki `EncryptFile` forma yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-174">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="3fc50-175">Bir dosyanın şifresini çözmek üzere</span><span class="sxs-lookup"><span data-stu-id="3fc50-175">Decrypting a File</span></span>  
 <span data-ttu-id="3fc50-176">Bu görev, olay işleyicisi yöntemi için iki yöntemi içerir. `Decrypt File` düğmesine (`buttonDecryptFile_Click`) ve `DecryptFile` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-176">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="3fc50-177">İlk yöntem, bir dosya seçmek için bir iletişim kutusu görüntüler ve şifre çözme gerçekleştiren bir ikinci yöntem dosyası adını geçirir.</span><span class="sxs-lookup"><span data-stu-id="3fc50-177">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="3fc50-178">`Decrypt` Yöntemi şunları yapar:</span><span class="sxs-lookup"><span data-stu-id="3fc50-178">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="3fc50-179">Oluşturur bir <xref:System.Security.Cryptography.RijndaelManaged> içeriğin şifresini Simetrik algoritma.</span><span class="sxs-lookup"><span data-stu-id="3fc50-179">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="3fc50-180">İlk sekiz baytı okur <xref:System.IO.FileStream> şifrelenmiş anahtar ve IV uzunluklarının alınacağı bayt dizileri halinde şifrelenmiş paketi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-180">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="3fc50-181">Anahtar ve IV şifreleme paketinden bayt dizileri ayıklar.</span><span class="sxs-lookup"><span data-stu-id="3fc50-181">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="3fc50-182">Oluşturur bir <xref:System.Security.Cryptography.RSACryptoServiceProvider> şifresini çözmek için nesne <xref:System.Security.Cryptography.RijndaelManaged> anahtarı.</span><span class="sxs-lookup"><span data-stu-id="3fc50-182">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5. <span data-ttu-id="3fc50-183">Kullanan bir <xref:System.Security.Cryptography.CryptoStream> okuyun ve şifre metin bölümünü şifresini çözmek için nesne <xref:System.IO.FileStream> şifreleme paketlemeden, bayt cinsinden bloklarında <xref:System.IO.FileStream> şifresi çözülen dosya için nesne.</span><span class="sxs-lookup"><span data-stu-id="3fc50-183">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="3fc50-184">Bu tamamlandığında, şifre çözme tamamlanır.</span><span class="sxs-lookup"><span data-stu-id="3fc50-184">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="3fc50-185">Aşağıdaki kodu olarak ekleyin `Click` için olay işleyicisi `Decrypt File` düğmesi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-185">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="3fc50-186">Aşağıdaki `DecryptFile` forma yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-186">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="3fc50-187">Ortak anahtarı dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="3fc50-187">Exporting a Public Key</span></span>  
 <span data-ttu-id="3fc50-188">Bu görev tarafından oluşturulan anahtarı kaydeder `Create Keys` dosyaya düğmesi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-188">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="3fc50-189">Bunu yalnızca ortak parametreleri aktarır.</span><span class="sxs-lookup"><span data-stu-id="3fc50-189">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="3fc50-190">Bu görevi, böylece o dosyaları için her şifreleyebilirsiniz Bob kendi ortak anahtar verme Alice senaryo benzetimini yapar.</span><span class="sxs-lookup"><span data-stu-id="3fc50-190">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="3fc50-191">He ve ilgili ortak anahtara sahip diğer özel parametreler tam anahtar çiftiyle olmadığı için bunların şifresini çözmek mümkün olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="3fc50-191">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="3fc50-192">Aşağıdaki kodu olarak ekleyin `Click` için olay işleyicisi `Export Public Key` düğmesine (`buttonExportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="3fc50-192">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="3fc50-193">Bir ortak anahtar içeri aktarma</span><span class="sxs-lookup"><span data-stu-id="3fc50-193">Importing a Public Key</span></span>  
 <span data-ttu-id="3fc50-194">Bu görev tarafından oluşturulan anahtar yalnızca ortak parametreleriyle yükler `Export Public Key` düğmesini ve anahtar kapsayıcısı adını ayarlar.</span><span class="sxs-lookup"><span data-stu-id="3fc50-194">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="3fc50-195">Bu görevi, Alice'in anahtar yalnızca ortak parametreleri ile yaptığı dosyaları için her şifreleyebilirsiniz şekilde yükleniyor Bob senaryo benzetimini yapar.</span><span class="sxs-lookup"><span data-stu-id="3fc50-195">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="3fc50-196">Aşağıdaki kodu olarak ekleyin `Click` için olay işleyicisi `Import Public Key` düğmesine (`buttonImportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="3fc50-196">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="3fc50-197">Bir özel anahtar alma</span><span class="sxs-lookup"><span data-stu-id="3fc50-197">Getting a Private Key</span></span>  
 <span data-ttu-id="3fc50-198">Bu görevi kullanılarak oluşturulan anahtarın adını anahtar kapsayıcısı adını ayarlar `Create Keys` düğmesi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-198">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="3fc50-199">Anahtar kapsayıcısı tam anahtar çiftinin özel parametrelerle içerir.</span><span class="sxs-lookup"><span data-stu-id="3fc50-199">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="3fc50-200">Bu görev Alice, Bob tarafından şifrelenmiş dosyaların şifresini çözmek için kendi özel anahtarı kullanarak bir senaryo benzetimini yapar.</span><span class="sxs-lookup"><span data-stu-id="3fc50-200">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="3fc50-201">Aşağıdaki kodu olarak ekleyin `Click` için olay işleyicisi `Get Private Key` düğmesine (`buttonGetPrivateKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="3fc50-201">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="3fc50-202">Uygulamayı Test Etme</span><span class="sxs-lookup"><span data-stu-id="3fc50-202">Testing the Application</span></span>  
 <span data-ttu-id="3fc50-203">Uygulamayı oluşturduktan sonra aşağıdaki test senaryoları gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="3fc50-203">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="3fc50-204">Anahtarları oluşturmak için şifrelemek ve şifresini çözme</span><span class="sxs-lookup"><span data-stu-id="3fc50-204">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="3fc50-205">Tıklayın `Create Keys` düğmesi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-205">Click the `Create Keys` button.</span></span> <span data-ttu-id="3fc50-206">Etiket anahtarı adını görüntüler ve tam anahtar çifti olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="3fc50-206">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="3fc50-207">Tıklayın `Export Public Key` düğmesi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-207">Click the `Export Public Key` button.</span></span> <span data-ttu-id="3fc50-208">Ortak anahtar parametreleri verme geçerli anahtar değiştirmez unutmayın.</span><span class="sxs-lookup"><span data-stu-id="3fc50-208">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="3fc50-209">Tıklayın `Encrypt File` düğmesine tıklayın ve bir dosya seçin.</span><span class="sxs-lookup"><span data-stu-id="3fc50-209">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="3fc50-210">Tıklayın `Decrypt File` düğmesine tıklayın ve yalnızca şifrelenmiş dosya belirleyin.</span><span class="sxs-lookup"><span data-stu-id="3fc50-210">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="3fc50-211">Yalnızca şifresi dosyasını inceleyin.</span><span class="sxs-lookup"><span data-stu-id="3fc50-211">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="3fc50-212">Uygulamayı kapatın ve alınırken kalıcı anahtar kapsayıcıları bir sonraki senaryoda test etmek için yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="3fc50-212">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="3fc50-213">Ortak anahtar kullanarak şifrelemek için</span><span class="sxs-lookup"><span data-stu-id="3fc50-213">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="3fc50-214">Tıklayın `Import Public Key` düğmesi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-214">Click the `Import Public Key` button.</span></span> <span data-ttu-id="3fc50-215">Etiket, anahtar adını görüntüler ve bunun yalnızca genel olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="3fc50-215">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="3fc50-216">Tıklayın `Encrypt File` düğmesine tıklayın ve bir dosya seçin.</span><span class="sxs-lookup"><span data-stu-id="3fc50-216">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="3fc50-217">Tıklayın `Decrypt File` düğmesine tıklayın ve yalnızca şifrelenmiş dosya belirleyin.</span><span class="sxs-lookup"><span data-stu-id="3fc50-217">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="3fc50-218">Özel anahtarın şifresini çözmek için sahip olması gerektiğinden bu başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="3fc50-218">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="3fc50-219">Bu senaryo, bir dosyayı başka bir kişi için şifrelemek için yalnızca ortak anahtarın gösterir.</span><span class="sxs-lookup"><span data-stu-id="3fc50-219">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="3fc50-220">Genellikle söz konusu kişinin, size yalnızca ortak anahtar ve şifre çözme için özel anahtarın stopaj.</span><span class="sxs-lookup"><span data-stu-id="3fc50-220">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="3fc50-221">Özel anahtarı kullanarak şifresini çözmek için</span><span class="sxs-lookup"><span data-stu-id="3fc50-221">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="3fc50-222">Tıklayın `Get Private Key` düğmesi.</span><span class="sxs-lookup"><span data-stu-id="3fc50-222">Click the `Get Private Key` button.</span></span> <span data-ttu-id="3fc50-223">Etiket anahtarı adını görüntüler ve tam bir anahtar çifti olup olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="3fc50-223">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="3fc50-224">Tıklayın `Decrypt File` düğmesine tıklayın ve yalnızca şifrelenmiş dosya belirleyin.</span><span class="sxs-lookup"><span data-stu-id="3fc50-224">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="3fc50-225">Tam anahtar çifti şifresini çözmek için sahip olduğunuz için bu başarılı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="3fc50-225">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc50-226">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3fc50-226">See also</span></span>

- [<span data-ttu-id="3fc50-227">Şifreleme Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="3fc50-227">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
