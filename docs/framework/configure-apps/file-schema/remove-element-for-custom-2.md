---
title: <remove>NameValueSectionHandler ve DictionarySectionHandler için öğesi
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: cd338ff2d613be31ab1524f6baed6107f803a688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920942"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<NameValueSectionHandler ve DictionarySectionHandler için > öğesini kaldırın

Daha önce tanımlanmış bir ayarı kaldırır.

[ **\<Yapılandırma >** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<> Kaldır**

## <a name="syntax"></a>Sözdizimi

```xml
<add remove="key" />
```

## <a name="attribute"></a>Öznitelik

|           | Açıklama |
| --------- | ----------- |
| **anahtar**   | Gerekli öznitelik.<br><br>Kaldırılacak ayarın adını belirtir. |

## <a name="parent-element"></a>Üst öğe

| Öğe | Açıklama |
| ------- | ------------|
| [sectionName > öğesi  **\<** ](custom-element-2.md) | <xref:System.Configuration.NameValueSectionHandler> Ve<xref:System.Configuration.DictionarySectionHandler> sınıflarını kullanan özel yapılandırma bölümlerinin ayarlarını tanımlar. |

## <a name="child-elements"></a>Alt öğeleri

Yok.

## <a name="remarks"></a>Açıklamalar

Uygulama yapılandırma dosyası hiyerarşisinde daha yüksek bir düzeyde tanımlanmış olan ayarları kaldırabilmeniz için  **\<Remove >** öğesini kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, makine yapılandırma dosyasında daha önce tanımlanan ayarları kaldırmak için bir uygulama yapılandırma dosyasında  **\<Remove >** öğesinin nasıl kullanılacağını gösterir.

Aşağıdaki makine yapılandırma dosyası kodu,  **\<MySection >** bölümünü bildirir ve `key2`iki ayar `key1` ekler:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

Aşağıdaki uygulama yapılandırma dosyası kodu, `key2`  **\<MySection >** ayarını kaldırır:

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Yapılandırma dosyası

Bu öğe uygulama yapılandırma dosyasında, makine yapılandırma dosyasında (*Machine. config*) ve uygulama dizini düzeyinde olmayan *Web. config* dosyalarında kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

- [.NET Framework için yapılandırma dosyası şeması](index.md)
