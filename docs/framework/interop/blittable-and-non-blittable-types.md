---
title: Blok Halinde Kopyalanabilir ve Kopyalanamaz Türler
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2cdaa312c037714a34e25e62ad318c9bc745ea7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953185"
---
# <a name="blittable-and-non-blittable-types"></a>Blok Halinde Kopyalanabilir ve Kopyalanamaz Türler
Çoğu veri türü hem yönetilen hem de yönetilmeyen bellekte ortak bir gösterimine sahiptir ve birlikte çalışma sıralayıcısı tarafından özel işleme gerektirmez. Bu türler, yönetilen ve yönetilmeyen kod arasında geçirildiklerinde dönüştürme gerektirmediğinden *blittable türler* olarak adlandırılır.  
  
 Platform çağırma çağrılarının döndürdüğü yapıların blittable tür olması gerekir. Platform çağırma, dönüş türleri olarak blittable olmayan yapıları desteklemez.  
  
 <xref:System> Ad alanından aşağıdaki türler blittable türleridir:  
  
- <xref:System.Byte?displayProperty=nameWithType>  
  
- <xref:System.SByte?displayProperty=nameWithType>  
  
- <xref:System.Int16?displayProperty=nameWithType>  
  
- <xref:System.UInt16?displayProperty=nameWithType>  
  
- <xref:System.Int32?displayProperty=nameWithType>  
  
- <xref:System.UInt32?displayProperty=nameWithType>  
  
- <xref:System.Int64?displayProperty=nameWithType>  
  
- <xref:System.UInt64?displayProperty=nameWithType>  
  
- <xref:System.IntPtr?displayProperty=nameWithType>  
  
- <xref:System.UIntPtr?displayProperty=nameWithType>  
  
- <xref:System.Single?displayProperty=nameWithType>  
  
- <xref:System.Double?displayProperty=nameWithType>  
  
 Aşağıdaki karmaşık türler de blittable türleridir:  
  
- Tamsayılar dizisi gibi blittable türlerin tek boyutlu dizileri. Ancak, blittable türlerin değişken dizisini içeren bir tür kendi blittable değildir.  
  
- Yalnızca blittable türlerini içeren biçimlendirilen değer türleri (ve bunları biçimli türler olarak sıralanmış olmaları durumunda sınıflar). Biçimlendirilen değer türleri hakkında daha fazla bilgi için bkz. [değer türleri Için varsayılan sıralama](default-marshaling-behavior.md#default-marshaling-for-value-types).  
  
 Nesne başvuruları blittable değildir. Bu, kendileri tarafından blittable olan nesnelere başvuru dizisi içerir. Örneğin, blittable olan bir yapı tanımlayabilirsiniz, ancak bu yapılara başvuru dizisi içeren bir blittable Türü tanımlayamazsınız.  
  
 En iyi duruma getirme olarak, blittable türündeki diziler ve yalnızca blittable üyeleri içeren sınıflar sıralama [](../../../docs/framework/interop/copying-and-pinning.md) sırasında kopyalanabilir. Çağıran ve çağrılan aynı Apartment olduğunda bu türler ın/out parametreleri olarak sıralanabilen görünebilir. Ancak, bu türler aslında parametrelerde olarak sıralanır ve bağımsız değişkeni bir ın/out parametresi <xref:System.Runtime.InteropServices.InAttribute> olarak <xref:System.Runtime.InteropServices.OutAttribute> sıralamak istiyorsanız ve özniteliklerini uygulamanız gerekir.  
  
 Bazı yönetilen veri türleri, yönetilmeyen bir ortamda farklı bir temsil gerektirir. Bu blittable olmayan veri türlerinin sıralanabilen bir forma dönüştürülmesi gerekir. Örneğin, yönetilen dizeler, sıralanmadan önce dize nesnelerine dönüştürülmesi gerektiğinden blittable olmayan türlerdir.  
  
 Aşağıdaki tabloda, <xref:System> ad alanından blittable olmayan türler listelenmektedir. Statik bir yönteme veya bir sınıf örneğine başvuran veri yapıları olan [Temsilciler](default-marshaling-behavior.md#default-marshaling-for-delegates)de blittable değildir.  
  
|Blittable olmayan tür|Açıklama|  
|-------------------------|-----------------|  
|[System. Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|C stili bir diziye veya `SAFEARRAY`öğesine dönüştürür.|  
|[System. Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))|1, 2 veya 4 baytlık bir değere 1 veya-1 ile `true` dönüştürür.|  
|[System. Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))|Unicode veya ANSI karaktere dönüştürür.|  
|[System. Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))|Sınıf arabirimine dönüştürür.|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|Bir varyanta veya arabirime dönüştürür.|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|C stili bir diziye veya `SAFEARRAY`öğesine dönüştürür.|  
|[System. String](../../../docs/framework/interop/default-marshaling-for-strings.md)|Null bir başvuruya veya BSTR 'ye bir dizeye dönüştürür.|  
|[System. ValueType](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))|Sabit bellek düzenine sahip bir yapıya dönüştürür.|  
|[System. Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|C stili bir diziye veya `SAFEARRAY`öğesine dönüştürür.|  
  
 Sınıf ve nesne türleri yalnızca COM birlikte çalışma tarafından desteklenir. Visual Basic, C#ve C++içindeki karşılık gelen türler Için bkz. [sınıf kitaplığına genel bakış](../../standard/class-library-overview.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Varsayılan Hazırlama Davranışı](../../../docs/framework/interop/default-marshaling-behavior.md)
