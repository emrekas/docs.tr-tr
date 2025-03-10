---
title: F# kullanarak Azure Dosya depolama kullanmaya başlama
description: Dosya verilerini bulutta Azure dosya depolama ile depolayın ve bulut dosya paylaşımınızı bir Azure sanal makinesinden (VM) veya Windows çalıştıran şirket içi bir uygulamadan bağlayın.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: a0e3cab56ba0f3db27335822616b4976a5d9de62
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630501"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>F kullanarak Azure dosya depolama ile çalışmaya başlama\#

Azure dosya depolama, standart [sunucu Ileti bloğu (SMB) protokolünü](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)kullanarak bulutta dosya paylaşımları sunan bir hizmettir. SMB 2.1 ve SMB 3.0 desteklenir. Azure File Storage, Azure’a dosya paylaşımı kullanan eski uygulamaları maliyetli yeniden yazdırmaya ihtiyaç duymadan ve hızla taşıyabilmenizi sağlar. Azure Virtual Machines’de, Cloud Services’da veya şirket içi istemcilerde çalışan uygulamalar, bir masaüstü uygulamanın tipik SMB paylaşımı bağladığı gibi buluta bir dosya paylaşımı bağlayabilir. Ardından herhangi sayıda uygulama bileşeni eş zamanlı olarak File Storage paylaşımını bağlayıp buna erişim sağlayabilir.

Dosya depolamaya kavramsal bir genel bakış için lütfen bkz. [dosya depolaması için .net Kılavuzu](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuzu kullanmak için önce [bir Azure depolama hesabı oluşturmanız](/azure/storage/storage-create-storage-account)gerekir.
Ayrıca, bu hesap için depolama erişim anahtarınız gerekecektir.

## <a name="create-an-f-script-and-start-f-interactive"></a>F# Betik oluşturma ve etkileşimli başlatma F#

Bu makaledeki örnekler, bir F# uygulama ya da bir F# komut dosyasında kullanılabilir. Bir F# betik oluşturmak için, örneğin `.fsx` `files.fsx`, F# geliştirme ortamınızda uzantılı bir dosya oluşturun.

Daha sonra, `WindowsAzure.Storage` paketi ve bir `WindowsAzure.Storage.dll` [](https://fsprojects.github.io/Paket/) yönergekullanarakbetiğepaketvebaşvuruyüklemekiçin,paketveyaNuGetgibibirpaketyöneticisi`#r` kullanın. [](package-management.md) [](https://www.nuget.org/)

### <a name="add-namespace-declarations"></a>Ad alanı bildirimleri ekle

Aşağıdaki `open` deyimlerini `files.fsx` dosyanın en üstüne ekleyin:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Bağlantı dizenizi alın

Bu öğretici için bir Azure depolama bağlantı dizesi gerekir. Bağlantı dizeleri hakkında daha fazla bilgi için bkz. [depolama bağlantı dizelerini yapılandırma](/azure/storage/storage-configure-connection-string).

Öğreticide, aşağıdaki gibi, komut dosyası için Bağlantı dizenizi girersiniz:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Ancak, bu gerçek projeler için **önerilmez** . Depolama hesabı anahtarınız, depolama hesabınızın kök parolasıyla benzerdir. Depolama hesabı anahtarınızı korumak için her zaman özen gösterin. Diğer kullanıcılara dağıtmaktan, sabit kodlamaktan ve başkalarının erişebileceği düz metin dosyasına kaydetmekten kaçının. Güvenliğinin tehlikede olduğunu düşünüyorsanız, Azure portalını kullanarak anahtarınızı yeniden oluşturabilirsiniz.

Gerçek uygulamalar için, depolama Bağlantı dizenizi korumak için en iyi yol bir yapılandırma dosyasıdır. Bağlantı dizesini bir yapılandırma dosyasından getirmek için şunu yapabilirsiniz:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Azure Configuration Manager kullanmak isteğe bağlıdır. .NET Framework `ConfigurationManager` türü gibi bir API de kullanabilirsiniz.

### <a name="parse-the-connection-string"></a>Bağlantı dizesini ayrıştırma

Bağlantı dizesini ayrıştırmak için şunu kullanın:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Bu, döndürür `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Dosya hizmeti istemcisini oluşturma

Türü `CloudFileClient` , dosya depolama alanında depolanan dosyaları programlı olarak kullanmanıza olanak sağlar. Hizmet istemcisini oluşturmak için bir yol aşağıda verilmiştir:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Artık, verileri okuyan ve dosya depolama alanına veri yazan kodu yazmaya hazırsınız.

## <a name="create-a-file-share"></a>Dosya paylaşma oluşturma

Bu örnek, zaten yoksa bir dosya paylaşımının nasıl oluşturulacağını gösterir:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Kök dizin ve alt dizin oluşturma

Burada kök dizini alır ve kökün bir alt dizinini alırsınız. Zaten mevcut değilse oluşturun.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Metni dosya olarak karşıya yükle

Bu örnekte, metnin dosya olarak nasıl yükleneceği gösterilmektedir.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Dosyanın yerel kopyasına bir dosya indir

Burada, yeni oluşturulan dosyayı indirerek içeriği yerel bir dosyaya ekleyin.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Dosya paylaşımının en büyük boyutunu ayarlama

Aşağıdaki örnekte, bir paylaşımın geçerli kullanımının nasıl denetlenecek ve paylaşımın kotasının nasıl ayarlanacağı gösterilmektedir. `FetchAttributes`bir paylaşımın `Properties`doldurulmasında ve `SetProperties` yerel değişiklikleri Azure dosya depolama alanına yaymaya yönelik olarak çağrılmalıdır.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Dosya veya dosya paylaşımının paylaşılan erişim imzasını oluşturma

Bir dosya paylaşımında veya tek bir dosya için paylaşılan erişim imzası (SAS) oluşturabilirsiniz. Paylaşılan erişim imzalarını yönetmek için, bir dosya paylaşımında paylaşılan erişim ilkesi de oluşturabilirsiniz. Bir paylaşılan erişim ilkesinin oluşturulması önerilir, çünkü tehlikeye atılması gerekiyorsa SAS 'yi iptal etmek için bir yol sağlar.

Burada, bir paylaşımda paylaşılan erişim ilkesi oluşturun ve ardından bu ilkeyi kullanarak paylaşımdaki bir dosya üzerindeki bir SAS için kısıtlamalar sağlayabilirsiniz.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Paylaşılan erişim imzaları oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [paylaşılan erişim imzaları (SAS) kullanma](/azure/storage/storage-dotnet-shared-access-signature-part-1) ve [BLOB depolama ile SAS oluşturma ve kullanma](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Dosyaları Kopyala

Bir dosyayı başka bir dosyaya veya blob 'a ya da bir bloba bir dosyaya kopyalayabilirsiniz. Bir blobu bir dosyaya veya bir dosyayı bir bloba kopyalıyorsanız, aynı depolama hesabı içinde kopyalama olsanız bile, kaynak nesnenin kimliğini doğrulamak için bir paylaşılan erişim imzası (SAS) kullanmanız *gerekir* .

### <a name="copy-a-file-to-another-file"></a>Dosyayı başka bir dosyaya kopyalama

Burada, bir dosyayı aynı paylaşımdaki başka bir dosyaya kopyalayabilirsiniz. Bu kopyalama işlemi aynı depolama hesabındaki dosyalar arasında kopya yaptığından, kopyayı gerçekleştirmek için paylaşılan anahtar kimlik doğrulaması kullanabilirsiniz.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Blob 'a dosya kopyalama

Burada, bir dosya oluşturup aynı depolama hesabı içindeki bir bloba kopyalayabilirsiniz. Kaynak dosya için, hizmetin kopyalama işlemi sırasında kaynak dosyaya erişimin kimliğini doğrulamak için kullandığı bir SAS oluşturursunuz.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Bir blobu bir dosyaya aynı şekilde kopyalayabilirsiniz. Kaynak nesne bir blob ise, kopyalama işlemi sırasında o bloba erişim kimliğini doğrulamak için bir SAS oluşturun.

## <a name="troubleshooting-file-storage-using-metrics"></a>Ölçümleri kullanarak dosya depolama sorunlarını giderme

Azure Depolama Analizi dosya depolama için ölçümleri destekler. Ölçüm verileriyle, istekleri izleyebilir ve sorunları tanılayabilirsiniz.

[Azure portalından](https://portal.azure.com)dosya depolama ölçümlerini etkinleştirebilir veya bunu şu F# şekilde yapabilirsiniz:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Sonraki adımlar

Azure dosya depolama hakkında daha fazla bilgi için bu bağlantılara bakın.

### <a name="conceptual-articles-and-videos"></a>Kavramsal makaleler ve videolar

- [Azure dosya depolama: Windows ve Linux için sorunsuz bulut SMB dosya sistemi](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Linux ile Azure dosya depolama kullanma](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Dosya depolama için araç desteği

- [Azure depolama ile Azure PowerShell kullanma](/azure/storage/storage-powershell-guide-full)
- [Microsoft Azure Depolama ile AzCopy kullanma](/azure/storage/storage-use-azcopy)
- [Azure depolama ile Azure CLı kullanma](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Başvuru

- [.NET başvurusu için Depolama İstemci Kitaplığı](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Dosya hizmeti REST API başvurusu](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Blog gönderileri

- [Azure dosya depolama genel kullanıma sunuldu](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Azure dosya depolama alanı içinde](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Microsoft Azure dosya hizmetine giriş](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Microsoft Azure dosyalara yönelik kalıcı bağlantılar](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
