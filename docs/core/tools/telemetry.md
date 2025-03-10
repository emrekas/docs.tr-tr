---
title: .NET Core SDK telemetri
description: Analiz için kullanım bilgilerini toplayan, hangi verilerin toplandığı ve devre dışı bırakılacağı .NET Core SDK telemetri özelliklerini bulun.
author: KathleenDollard
ms.date: 08/27/2019
ms.custom: seodec18
ms.openlocfilehash: 253f69392f034e330a75ed387d9346e8a5ae2a08
ms.sourcegitcommit: 77e33b682db39955e331b8e8eda4ef1925a24e78
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2019
ms.locfileid: "70133693"
---
# <a name="net-core-sdk-telemetry"></a>.NET Core SDK telemetri

[.NET Core SDK](index.md) , .NET Core CLI çöktüğünde kullanım verilerini ve özel durum bilgilerini toplayan bir telemetri özelliği içerir. .NET Core CLI .NET Core SDK ile birlikte gelir ve .NET Core uygulamalarınızı oluşturmanızı, test etmeniz ve yayımlamanıza olanak tanıyan fiiller kümesidir. .NET ekibinin, araçların iyileştirilmesi için nasıl kullanıldığını anladığından emin olmanız önemlidir. Hatalar hakkında bilgi, takımın sorunları çözmesine ve hataları düzeltmesine yardımcı olur.

Toplanan veriler anonimdir ve [Creative Commons Attribution Lisansı](https://creativecommons.org/licenses/by/4.0/)kapsamında toplu olarak yayımlanır. 

## <a name="scope"></a>Kapsam

`dotnet`iki işleve sahiptir: uygulamaları çalıştırmak ve CLı komutlarını yürütmek için. Aşağıdaki biçimde bir uygulamayı başlatmak `dotnet` için kullanılırken telemetri toplanmaz:

- `dotnet [path-to-app].dll`

Telemetri, şöyle [.NET Core CLI komutlardan](index.md)biri kullanılarak *toplanır* :

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a>Devre dışı bırakma

.NET Core SDK telemetri özelliği varsayılan olarak etkindir. Telemetri özelliğini devre dışı bırakmak için, `DOTNET_CLI_TELEMETRY_OPTOUT` ortam değişkenini veya `true`olarak `1` ayarlayın. 

Başarılı bir yükleme gerçekleştiğinde .NET Core SDK yükleyicisi tarafından tek bir telemetri girişi de gönderilir. Devre dışı bırakmak için, .NET Core SDK `DOTNET_CLI_TELEMETRY_OPTOUT` yüklemeden önce ortam değişkenini ayarlayın.

## <a name="disclosure"></a>Savunmasız

.NET Core SDK, [.NET Core CLI komutlarından](index.md) birini (örneğin, `dotnet build`) ilk kez çalıştırdığınızda aşağıdakine benzer metni görüntüler. Metin, çalıştırmakta olduğunuz SDK sürümüne bağlı olarak biraz farklılık gösterebilir. Bu "ilk çalıştırma" deneyimi, Microsoft 'un veri toplamayı nasıl bildisidir.

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is anonymous. It is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="data-points"></a>Veri noktaları

Telemetri özelliği, Kullanıcı adları veya e-posta adresleri gibi kişisel verileri toplamaz. Kodunuzu taramaz ve ad, depo veya yazar gibi proje düzeyi verileri ayıklamaz. Veriler, [Azure izleyici](https://azure.microsoft.com/services/monitor/) teknolojisini kullanan Microsoft sunucularına güvenli bir şekilde gönderilir, sınırlı erişim altında tutulur ve güvenli [Azure depolama](https://azure.microsoft.com/services/storage/) sistemlerinden katı güvenlik denetimleri altında yayımlanır.

Gizliliğinizi korumak bizim için önemlidir. Telemetrinin hassas verileri toplamasını veya verilerin güvenle veya uygun şekilde işlenmekte olduğunu düşünüyorsanız, [DotNet/CLI](https://github.com/dotnet/cli/issues) deposunda bir sorun yapın veya araştırma [dotnet@microsoft.com](mailto:dotnet@microsoft.com) için bir e-posta gönderin.

Telemetri özelliği aşağıdaki verileri toplar:

| SDK sürümleri | Veri |
|--------------|------|
| Tümü          | Çağırma zaman damgası. |
| Tümü          | Komut çağrıldı (örneğin, "Build"), 2,1 'den başlayarak karma hale getirilmiş. |
| Tümü          | Coğrafi konumu belirlemede kullanılan üç sekizli IP adresi. |
| Tümü          | İşletim sistemi ve sürümü. |
| Tümü          | SDK 'nın üzerinde çalıştığı çalışma zamanı KIMLIĞI (RID). |
| Tümü          | .NET Core SDK sürümü. |
| Tümü          | Telemetri profili: isteğe bağlı bir değer yalnızca açık Kullanıcı kabul etme ve Microsoft 'ta dahili olarak kullanılan bir değerdir. |
| > = 2.0        | Komut bağımsız değişkenleri ve seçenekleri: birkaç bağımsız değişken ve seçenek toplanır (rastgele dizeler değil). [Toplanan seçeneklere](#collected-options)bakın. 2\.1.300 sonrasında karma hale getirilir. |
| > = 2.0         | SDK 'nın bir kapsayıcıda çalışıp çalışmadığını belirtir. |
| > = 2.0         | 2,1 ' den `TargetFramework` başlayarak karma hale getirilmiş hedef çerçeveler (olaydan). |
| > = 2.0         | Karma medya Access Control (MAC) adresi: bir makine için bir şifreleme (SHA256) anonim ve benzersiz KIMLIĞI. |
| > = 2.0         | Karma hale getirilmiş geçerli çalışma dizini. |
| > = 2.0         | Karma yükleyici exe dosya adına sahip başarı raporunu yükleme. |
| > = 2.1.300     | Çekirdek sürümü. |
| > = 2.1.300     | Libc sürümü/sürümü. |
| > = 3.0.100     | Çıktının yeniden yönlendirilme (true veya false). |
| > = 3.0.100     | CLı/SDK kilitlenmesinde, özel durum türü ve yığın izlemesi (yalnızca CLı/SDK kodu, gönderilen yığın izlemesinde bulunur). Daha fazla bilgi için bkz. [.NET Core CLI/SDK kilitlenme özel durum telemetrisi toplandı](#net-core-clisdk-crash-exception-telemetry-collected). |

### <a name="collected-options"></a>Toplanan seçenekler

Bazı komutlar ek veriler gönderir. Bir komut alt kümesi ilk bağımsız değişkeni gönderir:

| Komut               | Gönderilen ilk bağımsız değişken verileri                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | İçin komut yardımı sorgulanırken.  |
| `dotnet new <arg>`    | Şablon adı (karma).             |
| `dotnet add <arg>`    | Sözcük `package` veya .`reference`      |
| `dotnet remove <arg>` | Sözcük `package` veya .`reference`      |
| `dotnet list <arg>`   | Sözcük `package` veya .`reference`      |
| `dotnet sln <arg>`    | , Veya `add` `list` sözcüğü.`remove`    |
| `dotnet nuget <arg>`  | , Veya `delete` `locals` sözcüğü.`push` |

Bir komut alt kümesi, kullanıldıkları takdirde, değerleriyle birlikte, seçili seçenekleri gönderir:

| Seçenek                  | Komutlar                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | Tüm komutlar                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`                  |
| `--framework`           | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest` |
| `--runtime`             | `dotnet build`,`dotnet publish`                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

`--verbosity` Ve`--sdk-package-version`dışında, diğer tüm değerler .NET Core 2.1.100 SDK ile başlayarak karma hale getirilir.

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a>.NET Core CLI/SDK kilitlenme özel durum telemetrisi toplandı

.NET Core CLI/SDK kilitlenirse, CLı/SDK kodunun özel durum ve yığın izlemesinin adını toplar. Bu bilgiler, sorunları değerlendirmek ve .NET Core SDK ve CLı kalitesini geliştirmek için toplanır. Bu makalede Topladığımız veriler hakkında bilgi sağlanır. Ayrıca, kullanıcıların kendi .NET Core SDK kendi sürümünü oluşturma konusunda ipuçları, kişisel veya hassas bilgilerin yanlışlıkla açıklanmasını önleyebilir.

### <a name="types-of-collected-data"></a>Toplanan veri türleri

.NET Core CLI, uygulamanızda özel durumlar değil yalnızca CLı/SDK özel durumları için bilgi toplar. Toplanan veriler, özel durumun ve yığın izlemenin adını içerir. Bu yığın izlemesi CLı/SDK kodudur.

Aşağıdaki örnek, toplanan veri türünü gösterir:

```
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-information"></a>Yanlışlıkla açıklanmaktan kaçının

.NET Core katkıda bulunanlar ve başkalarının oluşturdukları .NET Core SDK bir sürümünü çalıştıran herkes kendi SDK kaynak kodu yolunu dikkate almalıdır. Özel hata ayıklama derlemesi olan veya özel derleme sembol dosyalarıyla yapılandırılmış bir .NET Core SDK kullanırken kilitlenme oluşursa, derleme makinesinden SDK kaynak dosyası yolu, yığın izlemenin bir parçası olarak toplanır ve karma değildir.

Bu nedenle, .NET Core SDK özel derlemeleri yol adları kişisel veya hassas bilgileri sunan dizinlerde yer içermemelidir. 

## <a name="see-also"></a>Ayrıca bkz.

- [.NET Core CLI telemetri-2019 S2 verileri](https://dotnet.microsoft.com/platform/telemetry/dotnet-core-cli-2019q2)
- [Telemetri başvuru kaynağı (DotNet/CLI deposu)](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
