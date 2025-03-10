---
title: Şablonlar ve C++ C# genel türler arasındaki farklar C# -Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], vs. C++ templates
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
ms.openlocfilehash: b794666501fb27d2f73a6050f85df3725050982e
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589858"
---
# <a name="differences-between-c-templates-and-c-generics-c-programming-guide"></a>C++ Şablonları ve C# Genel Türleri Arasındaki Farklar (C# Programlama Kılavuzu)
C#Genel türler C++ ve şablonlar, parametreli türler için destek sağlayan dil özellikleridir. Ancak, ikisi arasında birçok farklılık vardır. Sözdizimi düzeyinde, C# genel türler C++ şablonların karmaşıklığı olmadan parametreli türlere daha basit bir yaklaşımdır. Ayrıca, C# C++ şablonların sağladığı tüm işlevleri sağlamayı denemez. Uygulama düzeyinde, birincil farklılık, genel tür değişimlerin C# çalışma zamanında gerçekleştirildiği ve genel tür bilgilerinin, bu nedenle örneklenmiş nesneler için korunmasıdır. Daha fazla bilgi için bkz. [çalışma zamanındaki genel türler](./generics-in-the-run-time.md).  
  
 Aşağıdakiler, genel türler ve C# C++ şablonlar arasındaki önemli farklardır:  
  
- C#Genel türler, C++ şablonlarla aynı esneklik miktarını sağlamaz. Örneğin, Kullanıcı tanımlı işleçleri çağırmak mümkün olsa da, genel bir C# sınıfta aritmetik işleçleri çağırmak mümkün değildir.  
  
- C#, gibi tür olmayan şablon parametrelerine izin vermez `template C<int i> {}`.  
  
- C#Açık özelleştirmeyi desteklemez; diğer bir deyişle, belirli bir tür için bir şablonun özel bir uygulamasıdır.  
  
- C#Kısmi özelleştirmeyi desteklemez: tür bağımsız değişkenlerinin bir alt kümesi için özel bir uygulama.  
  
- C#tür parametresinin genel tür için temel sınıf olarak kullanılmasına izin vermez.  
  
- C#tür parametrelerinin varsayılan türleri olmasını sağlar.  
  
- İçinde C#, bir genel tür parametresi genel olamaz, ancak oluşturulan türler genel türler olarak kullanılabilir. C++Şablon parametrelerine izin verir.  
  
- C++şablondaki tüm tür parametreleri için geçerli olmayan koda izin verir, daha sonra tür parametresi olarak kullanılan belirli tür için denetlenir. C#, bir sınıftaki kodun, kısıtlamaları karşılayan herhangi bir türle çalışacak şekilde yazılmasına gerek duyar. Örneğin, içinde C++ aritmetik işleçleri `+` ve `-` tür parametresinin nesnelerini kullanan bir işlev yazmak mümkündür; Bu, bir türü olmayan bir tür ile şablon örneği oluşturma sırasında bir hata oluşturur. Bu işleçleri destekler. C#Buna izin vermez; izin verilen tek dil yapıları, kısıtlamalardan çıkarsanolabilecek olanlardır.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../index.md)
- [Genel Türlere Giriş](./index.md)
- [Şablonlar](/cpp/cpp/templates-cpp)
