---
title: Paket yönetimi ile kullanarak F# Azure
description: Yönetmek için paket veya Nuget kullanma F# Azure bağımlılıkları
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: b180024e2276a2fd7786f35cb922b1aa1d91f0ad
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880014"
---
# <a name="package-management-for-f-azure-dependencies"></a>F# Azure Bağımlılıkları için Paket Yönetimi

Bir paket Yöneticisi'ni kullandığınızda, Azure geliştirme için paketler almak kolaydır. İki seçenek olan [Paket](https://fsprojects.github.io/Paket/) ve [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Paket kullanma

Kullanıyorsanız [Paket](https://fsprojects.github.io/Paket/) bağımlılık Yöneticisi olarak, kullandığınız `paket.exe` aracı Azure bağımlılıkları ekleyin. Örneğin:

```
> paket add nuget WindowsAzure.Storage
```

Veya kullanıyorsanız [Mono](https://www.mono-project.com/) platformlar arası .NET geliştirme için:

```
> mono paket.exe add nuget WindowsAzure.Storage
```

Bu ekler `WindowsAzure.Storage` kümenize paket bağımlılıklarının geçerli dizinde proje için değişiklik `paket.dependencies` dosya ve paketini indirin. Bağımlılıkları daha önce ayarlamış ya da bir proje üzerinde bağımlılıkları başka bir geliştirici tarafından Burada ayarlanan çalışıyorsanız, çözümlemek ve yerel olarak gibi bağımlılıklarını yükleyin:

```
> paket install
```

Veya, Mono geliştirme için:

```
> mono paket.exe install
```

Tüm paket bağımlılıklarını, en son sürüme şöyle güncelleştirebilirsiniz:

```
> paket update
```

Veya, Mono geliştirme için:

```
> mono paket.exe update
```

## <a name="using-nuget"></a>Nuget kullanarak

Kullanıyorsanız [NuGet](https://www.nuget.org/) bağımlılık Yöneticisi olarak, kullandığınız `nuget.exe` aracı Azure bağımlılıkları ekleyin. Örneğin:

```
> nuget install WindowsAzure.Storage -ExcludeVersion
```

Veya, Mono geliştirme için:

```
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

Bu ekler `WindowsAzure.Storage` kümenize proje geçerli dizindeki ve indirme paketi için paket bağımlılıklarının. Bağımlılıkları daha önce ayarlamış ya da bir proje üzerinde bağımlılıkları başka bir geliştirici tarafından Burada ayarlanan çalışıyorsanız, çözümlemek ve yerel olarak gibi bağımlılıklarını yükleyin:

```
> nuget restore
```

Veya, Mono geliştirme için:

```
> mono nuget.exe restore
```

Tüm paket bağımlılıklarını, en son sürüme şöyle güncelleştirebilirsiniz:

```
> nuget update
```

Veya, Mono geliştirme için:

```
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a>Başvurulan Derlemeler

Paketlerinizi kullanmak için F# komut dosyası için gereksinim duyduğunuz kullanarak paketlerinde derlemelerine bir `#r` yönergesi. Örneğin:

```
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

Gördüğünüz gibi DLL ve paket adı ile aynı tam olarak olmayabilir tam DLL adı göreli yolunu belirtmeniz gerekir. Yolun bir framework sürümünü ve büyük olasılıkla bir paket sürüm numarası içerir. Tüm yüklenmiş derlemeleri bulmak için aşağıdakine benzer bir Windows komut satırında kullanabilirsiniz:

```
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

Bir UNIX Kabuğu'nda bir şey gibi veya bu:

```
> find packages/WindowsAzure.Storage -name "*.dll"
```

Bu yüklenen derlemeler için yollar sağlar. Burada, framework sürümünüz için doğru yol seçebilirsiniz.
