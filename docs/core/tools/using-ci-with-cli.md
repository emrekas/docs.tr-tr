---
title: Sürekli Tümleştirme (CI içinde) kullanarak, .NET Core SDK'sı ve araçları
description: .NET Core SDK'sı ve araçları yapı sunucusunda'nın kullanımı hakkında bilgi.
author: guardrex
ms.date: 05/18/2017
ms.custom: seodec18
ms.openlocfilehash: c9fd9e359a22467cc8639109538522e4088df5ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61647637"
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a>Sürekli Tümleştirme (CI içinde) kullanarak, .NET Core SDK'sı ve araçları

Bu belge, bir yapı sunucusu üzerinde .NET Core SDK'sı ve araçları kullanarak özetlenmektedir. .NET Core araç takımı works hem etkileşimli olarak burada bir geliştirici komutları bir komut istemi ve otomatik olarak bir sürekli tümleştirme (CI) sunucusu burada türleri bir yapı betiği çalıştırır. Komutlarını, seçeneklerini, girdileri ve çıktıları aynıdır ve araçları ve uygulamanızı oluşturmak için bir sistem edinmenin yolunu sağlamanız yalnızca gerekenler şunlardır. Bu belge tasarım ve derleme betiklerinizde yapısı hakkında önerilerle senaryoları için CI aracı alım odaklanır.

## <a name="installation-options-for-ci-build-servers"></a>Yükleme seçenekleri için CI yapı sunucusu

### <a name="using-the-native-installers"></a>Yerel yükleyicilerden kullanma

Yerel yükleyicilerden, macOS, Linux ve Windows için kullanılabilir. Yükleyiciler, yapı sunucusunda yönetici (sudo) erişim gerektirir. Yerel bir yükleyici kullanmanın avantajı tüm araçları çalıştırmak gerekli yerel bağımlılıkları yükler ' dir. Yerel yükleyicilerden da SDK'sı sistem genelinde yüklenmesini sağlar.

macOS kullanıcılarını PKG yükleyicileri kullanmanız gerekir. Linux üzerinde Ubuntu için apt-get veya CentOS için yum gibi bir akış tabanlı Paket Yöneticisi'ni kullanarak veya paketlerini kendileri DEB veya RPM kullanma seçeneği yoktur. Windows üzerinde MSI yükleyicisini kullanın.

En son kararlı ikili dosyaları adresten [.NET indirir](https://dotnet.microsoft.com/download). En son (ve büyük olasılıkla kararsız) yayın öncesi araçları kullanmak isterseniz, verilen bağlantıları kullanın [dotnet/core-SDK'sı GitHub deposu](https://github.com/dotnet/core-sdk#installers-and-binaries). Linux dağıtımları için `tar.gz` arşivler (olarak da bilinen `tarballs`) mevcuttur; yükleme betikleri arşivleri içinde .NET Core yüklemek için kullanın.

### <a name="using-the-installer-script"></a>Yükleyici komut dosyası kullanma

Yapı sunucunuz ile araçları almak için kolay Otomasyon yönetici olmayan yüklenmek üzere yükleyicisi betiği kullanarak sağlar. Komut dosyası araçları indirme ve onu bir varsayılan veya kullanım için belirtilen konuma ayıklayın üstlenir. Yüklemek istediğiniz araçlar ve tüm SDK'sı veya paylaşılan çalışma zamanı yüklemek isteyip istemediğinizi de belirtebilirsiniz.

Getirmek ve istenen SDK sürümünü yüklemek için yapılandırmanın başında çalıştırılacak komut dosyası yükleyici otomatik. *İstenen sürüm* oluşturmak için gereksinim duyduğunuz SDK sürümüyle projelerinizi olduğu. Betik, sunucu üzerindeki yerel bir dizinde SDK'yı yükleme, araçları yüklü konumdan çalıştırın ve ardından temizleme (veya CI service gerisini halleder temizleme) yapıdan sonra sağlar. Bu, derleme işlemi kapsülleme ve tüm yalıtım sağlar. Yükleme komut dosyası başvurusu bulundu [dotnet yükleme](dotnet-install-script.md) makalesi.

> [!NOTE]
> **Azure DevOps Services**
>
> Yükleyici komut dosyası kullanırken, yerel bağımlılıkları otomatik olarak yüklü değildir. İşletim sisteminin bunları yoksa yerel bağımlılıkları yüklemeniz gerekir. Daha fazla bilgi için [Linux üzerinde .NET Core önkoşulları](../linux-prerequisites.md).

## <a name="ci-setup-examples"></a>CI Kurulum örnekleri

Bu bölümde, çeşitli yazılım olarak hizmet (SaaS) CI çözümleri açıklamalarıyla birlikte bir PowerShell veya bash komut dosyası kullanarak bir el ile Kurulum açıklanmaktadır. Kapsanan SaaS CI çözümler [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), ve [Azure işlem hatları](https://docs.microsoft.com/azure/devops/pipelines/index).

### <a name="manual-setup"></a>El ile Kurulum

Her SaaS hizmeti oluşturma ve bir yapı işlemi yapılandırma kendi yöntemlerine sahiptir. Listelenenden farklı SaaS çözümü kullanın veya özelleştirme ötesinde önceden paketlenmiş destek gerektiren, en azından bazı el ile yapılandırma gerçekleştirmelidir.

Genel olarak, el ile Kurulum Araçlar'ı (ya da Araçları'nın en son gecelik derlemeleri) sürümünü almak ve derleme betiğinizin çalıştırma gerektirir. Bir PowerShell veya bash betiği, .NET Core komutları düzenlemek ya da yapı işlemi özetleyen bir proje dosyası kullanmak üzere kullanabilirsiniz. [Düzenleme bölümünde](#orchestrating-the-build) Bu seçenekler hakkında daha fazla ayrıntı sağlar.

CI yapı Sunucusu Kurulumu el ile gerçekleştiren bir komut dosyası oluşturduktan sonra geliştirme makinenizde yerel olarak test etmek için kodunuzu derlemek için kullanın. Komut dosyası da yerel olarak çalıştığını doğruladıktan sonra CI yapı sunucunuzu dağıtın. Görece basit bir PowerShell Betiği, bir Windows yapı sunucusuna yükleyin ve .NET Core SDK'sını elde gösterilmektedir:

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it
#   does, it's removed. This is not strictly required, but it's a
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://dot.net/v1/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

Yapı işleminizin betiğinin sonunda uygulaması sağlayın. Komut dosyası araçları edinme ve yapı işleminizin ardından yürütür. UNIX makineler için aşağıdaki bash betiğini PowerShell betiğini benzer bir şekilde açıklanan eylemleri gerçekleştirir:

```bash
#!/bin/bash
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://dot.net/v1/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### <a name="travis-ci"></a>Travis CI

Yapılandırabileceğiniz [Travis CI](https://travis-ci.org/) .NET Core SDK'sını kullanarak yüklemek için `csharp` dil ve `dotnet` anahtarı. Daha fazla bilgi için resmi Travis CI belgeleri görmek [yapı bir C#, F#, veya Visual Basic projesi](https://docs.travis-ci.com/user/languages/csharp/). Travis CI bilgileri erişim unutmayın, topluluk tarafından tutulan `language: csharp` dahil olmak üzere tüm .NET dilleri için bir dil tanımlayıcısı çalışır F#ve Mono.

Travis CI, macOS ve Linux işlerinde hem çalışan bir *matris derleme*, çalışma zamanı ortamı ve uygulamanız için derleme birleşimleri karşılamak için özel durumlar/eklemeleri bir birleşimini belirttiğiniz yerdir. Daha fazla bilgi için [yapı özelleştirme](https://docs.travis-ci.com/user/customizing-the-build) makalede Travis CI belgeleri. MSBuild tabanlı araçlar LTS (1.0.x kullanılır) ve geçerli (1.1.x) çalışma zamanları paket içerisine dâhil; SDK'sını yükleyerek oluşturmak için ihtiyacınız olan her şey aldığınız şekilde.

### <a name="appveyor"></a>AppVeyor

[AppVeyor](https://www.appveyor.com/) .NET Core 1.0.1 yükler SDK'sı ile `Visual Studio 2017` çalışan görüntüsü oluşturun. Diğer derleme görüntüleri farklı sürümleri .NET Core SDK'sı ile kullanılabilir. Daha fazla bilgi için [appveyor.yml örnek](https://github.com/dotnet/docs/blob/master/appveyor.yml) ve [derleme çalışan görüntüleri](https://www.appveyor.com/docs/build-environment/#build-worker-images) AppVeyor docs makalesinde.

.NET Core SDK'sı ikili dosyaları indirilir ve yükleme betiğini kullanarak bir alt dizinine geçin ve sonra bunlar için eklenen `PATH` ortam değişkeni. .NET Core SDK'sını birden çok sürümü ile tümleştirme testleri çalıştırmak için bir derleme matris ekleyin:

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="azure-devops-services"></a>Azure DevOps Services

Azure DevOps Services'ı, Bu yaklaşımlardan birini kullanarak .NET Core projeleri derlemek için yapılandırın:

1. Komut dosyasını çalıştırmak [el ile Kurulum adımı](#manual-setup) komutlarınızı kullanarak.
1. .NET Core Araçları'nı kullanmak üzere yapılandırılmış birden fazla Azure DevOps Hizmetleri yerleşik derleme görevlerini oluşan bir derleme oluşturun.

Her iki çözüm de geçerlidir. El ile Kurulum betiği kullanarak, yapının bir parçası olarak indirdiğiniz bu yana, aldığınız Araçları sürüm denetimi. Derleme, oluşturmanız gereken bir betikten çalıştırılır. Bu makalede, yalnızca el ile seçeneği kapsar. Derleme görevleri Azure DevOps hizmetleriyle bir derleme oluşturma hakkında daha fazla bilgi için bkz: [Azure işlem hatları](https://docs.microsoft.com/azure/devops/pipelines/index) belgeleri.

Azure DevOps Hizmetleri'nde el ile Kurulum komut dosyası kullanmak için yeni bir yapı tanımı oluşturma ve derleme adımı için çalıştırılacak komut dosyasını belirtin. Bu Azure DevOps Services kullanıcı arabirimi kullanılarak gerçekleştirilir:

1. Yeni bir derleme tanımı oluşturarak başlayın. Ne tür bir yapı, istediğiniz oluşturmak Seç tanımlamak için bir seçenek sunar ekran ulaştıktan sonra **boş** seçeneği.

   ![Boş bir yapıyı seçerek](./media/using-ci-with-cli/select-empty-build-definition.png)

1. Depo oluşturmak için yapılandırdıktan sonra yapı tanımlarına ne yönlendirilirsiniz. Seçin **derleme adımı Ekle**:

   ![Bir derleme adımı ekleme](./media/using-ci-with-cli/add-build-step.png)

1. Eklemediğiniz **görev kataloğundaki**. Katalog yapı kullanan görevler içerir. Bir komut dosyası olduğundan seçin **Ekle** için düğme **PowerShell: Bir PowerShell Betiği çalıştırmanız**.

   ![Bir PowerShell Betiği adım ekleme](./media/using-ci-with-cli/add-powershell-script.png)

1. Yapı adımının yapılandırın. Komut dosyasını oluşturduğunuz depodan ekleyin:

   ![PowerShell betiğini çalıştırmak için belirtme](./media/using-ci-with-cli/powershell-script-path.png)

## <a name="orchestrating-the-build"></a>Yapı işlemlerini

Bu belge çoğunu açıklar .NET Core araçları edinmek ve bilgiyi nasıl düzenlemek sağlamadan çeşitli CI hizmetlerini yapılandırma veya *gerçekten derleme*, kodunuzu .NET Core ile. Yapı işleminin nasıl seçimlerine, aşağıda genel hatlarıyla ele birçok faktöre bağlıdır. Derlemelerinizi her teknolojisi ile düzenleme hakkında daha fazla bilgi için belge kümelerinde sağlanan örnekleri ve kaynakları keşfedin [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), ve [Azure İşlem hatları](https://docs.microsoft.com/azure/devops/pipelines/index).

.NET Core Araçları'nı kullanarak .NET Core kod için yapı işlemini yapılandırırken alan iki genel yaklaşım kullanarak doğrudan MSBuild veya .NET Core komut satırı komutlarını kullanarak. Yapmanız gereken hangi yaklaşımın karmaşıklığı yaklaşımları ve dezavantajlarına sahip konfor düzeyinize göre belirlenir. MSBuild görevleri ve hedefleri yapı işleminizi express olanağı sağlar, ancak MSBuild proje dosyası sözdizimi öğrenme eklenen karmaşıklık ile gelir. .NET Core komut satırı araçlarını kullanarak belki de daha basit olmakla birlikte, komut dosyası dilinde düzenleme mantığını yazmanızı gerektirir `bash` veya PowerShell.

## <a name="see-also"></a>Ayrıca bkz.

- [.NET indirmeleri - Linux](https://dotnet.microsoft.com/download?initial-os=linux)
