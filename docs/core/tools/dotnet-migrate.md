---
title: DotNet geçiş komutu
description: DotNet Migrate komutu bir projeyi ve tüm bağımlılıklarını geçirir.
ms.date: 06/26/2019
ms.openlocfilehash: 86f11592e774da12b010886aaa1e30cee063fea6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202539"
---
# <a name="dotnet-migrate"></a>dotnet migrate

**Bu konu şu şekilde geçerlidir: ✓** .NET Core 1. x SDK ve sonraki sürümleri

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Ad

`dotnet migrate`-Preview 2 .NET Core projesini .NET Core SDK stilinde bir projeye geçirir.

> [!NOTE]
> `dotnet migrate`, sonraki önizleme sürümündeki .NET Core 3,0 SDK 'dan kaldırılır.

## <a name="synopsis"></a>Özeti

```console
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a>Açıklama

Komutu geçerli bir Preview 2 *Project. JSON*tabanlı projeyi geçerli bir .NET Core SDK stili csproj projesine geçirir. `dotnet migrate`

Varsayılan olarak, komut kök projeyi ve kök projenin içerdiği tüm proje başvurularını geçirir. Bu davranış, `--skip-project-references` çalışma zamanında seçeneği kullanılarak devre dışıdır.

Aşağıdaki varlıklarda geçiş yapılabilir:

* Geçirilecek *Project. JSON* dosyasını belirterek tek bir proje.
* Global. json dosyasında bir yolu geçirerek *Global. JSON* dosyasında belirtilen tüm dizinler.
* Çözümde başvurulan projeleri geçirirken *çözüm. sln* dosyası.
* Verilen dizinin tüm alt dizinlerinde özyinelemeli olarak.

Komut, geçirilen *Project. JSON* dosyasını dizin yoksa oluşturduğu bir `backup` dizin içinde tutar. `dotnet migrate` Bu davranış `--skip-backup` seçeneği kullanılarak geçersiz kılınır.

Varsayılan olarak, geçiş işlemi geçiş işleminin durumunu standart çıktıya (STDOUT) verir. `--report-file <REPORT_FILE>` Seçeneğini kullanırsanız, çıkış dosyaya kaydedilir.

Komutu yalnızca geçerli Preview 2 *Project. JSON*tabanlı projeleri destekler. `dotnet migrate` Bu, DNX veya Preview 1 *Project. JSON*tabanlı projeleri doğrudan MSBuild/csproj projelerine geçirebileceğiniz anlamına gelir. Önce projeyi bir Preview 2 *Project. JSON*tabanlı projeye el ile geçirmeniz ve ardından projeyi geçirmek için `dotnet migrate` komutunu kullanmanız gerekir.

## <a name="arguments"></a>Arguments

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

Aşağıdakilerden birinin yolu:

* geçirilecek bir *Project. JSON* dosyası.
* *Global. JSON* dosyası: *Global. JSON* içinde belirtilen klasörler geçirilir.
* bir *çözüm. sln* dosyası: çözümde başvurulan projeler geçirilir.
* geçirilecek Dizin: özyinelemeli olarak *Project. JSON* dosyalarını belirtilen dizin içinde geçirilecek şekilde arar.

Hiçbir şey belirtilmemişse, varsayılan olarak geçerli dizine ayarlanır.

## <a name="options"></a>Seçenekler

`--format-report-file-json <REPORT_FILE>`

Geçiş raporu dosyasını kullanıcı iletileri yerine JSON olarak çıkar.

`-h|--help`

Komut için kısa bir yardım yazdırır.

`-r|--report-file <REPORT_FILE>`

Konsola ek olarak çıkış geçiş raporu.

`-s|--skip-project-references [Debug|Release]`

Proje başvurularını geçirmeyi atlayın. Varsayılan olarak, proje başvuruları yinelemeli olarak geçirilir.

`--skip-backup`

Başarılı geçişten sonra *Project. JSON*, *Global. JSON*ve  *\*. xproj* ' ı `backup` bir dizine taşımayı atlayın.

`-t|--template-file <TEMPLATE_FILE>`

Geçiş için kullanılacak şablon csproj dosyası. Varsayılan olarak, tarafından bırakılan ile `dotnet new console` aynı şablon kullanılır.

`-v|--sdk-package-version <VERSION>`

Geçirilen uygulamada başvurulan SDK paketinin sürümü. Varsayılan, ' deki `dotnet new`SDK sürümüdür.

`-x|--xproj-file <FILE>`

Kullanılacak xproj dosyasının yolu. Proje dizininde birden fazla xproj olduğunda gereklidir.

## <a name="examples"></a>Örnekler

Geçerli dizindeki bir projeyi ve projenin tüm proje bağımlılıklarını geçirin:

`dotnet migrate`

*Global. JSON* dosyasının içerdiği tüm projeleri geçirin:

`dotnet migrate path/to/global.json`

Yalnızca geçerli projeyi geçirin ve projeden projeye (P2P) bağımlılıkları yoktur. Ayrıca, belirli bir SDK sürümünü kullanın:

`dotnet migrate -s -v 1.0.0-preview4`
