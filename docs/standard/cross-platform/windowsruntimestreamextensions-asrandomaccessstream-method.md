---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Yöntemi
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5dd2829a9a00f869af3d7f370f99361979b8106
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758800"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a>WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Yöntemi

[.NET Framework 4.5.1 ve sonraki sürümlerinde desteklenen]

Belirtilen akışı rasgele erişim akışına dönüştürür.

**Namespace:** <xref:System.IO?displayProperty=nameWithType>
**Derleme:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)

## <a name="syntax"></a>Sözdizimi

```csharp
[CLSCompliantAttribute(false)]
public static IRandomAccessStream AsRandomAccessStream(Stream stream)
```

```vb
'Declaration
<ExtensionAttribute> _
<CLSCompliantAttribute(False)> _
Public Shared Function AsRandomAccessStream ( _
        stream As Stream) As IRandomAccessStream
```

## <a name="parameters"></a>Parametreler

`stream`

Türü: <xref:System.IO.Stream?displayProperty=nameWithType>  
Dönüştürülecek akış.

## <a name="return-value"></a>Dönüş Değeri

Türü: <xref:Windows.Storage.Streams.RandomAccessStream>  
A [!INCLUDE[wrt](../../../includes/wrt-md.md)] dönüştürülmüş akımı temsil rasgele erişim akışı.

## <a name="exceptions"></a>Özel Durumlar

|Özel Durum|Koşul|
|---------------|---------------|
|<xref:System.NotSupportedException>|Dönüştürülecek akış, aramayı desteklemez.|

## <a name="remarks"></a>Açıklamalar

Bu genişletme yöntemi yalnızca Windows Mağazası uygulamaları geliştirirken kullanılabilir. Bu yöntem Windows Mağazası uygulamalarında akışlarla çalışmak için uygun bir yol sağlar. Dönüştürmek istediğiniz .NET Framework akışının aramayı desteklemelidir. Daha fazla bilgi için <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> yöntemi.

> [!IMPORTANT]
> Bu API, .NET Framework 4.5.1 ve sonraki sürümlerde, ancak 4.5 sürümünde desteklenir.

## <a name="version-information"></a>Sürüm Bilgileri

**Windows Store uygulamaları için .NET**

Desteklenir: Windows 8.1

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: .NET Framework akışları ve Windows çalışma zamanı akışları arasında dönüştürme](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
