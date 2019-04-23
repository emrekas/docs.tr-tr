---
title: x:ClassModifier Yönergesi
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: fdbc69634e86992e71cfccdc080829b6b45f963c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100945"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier Yönergesi
XAML derlemesi davranışı değiştirir, `x:Class` de sağlanır. Kısmi oluşturmak yerine özellikle `class` olan bir `Public` erişim düzeyi (varsayılan), sağlanan `x:Class` ile oluşturulan bir `NotPublic` erişim düzeyi. Bu davranış, sınıf oluşturulmuş derlemeler için erişim düzeyi etkiler.  
  
## <a name="xaml-attribute-usage"></a>XAML Öznitelik Kullanımı  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML Değerleri  
  
|||  
|-|-|  
|*NotPublic*|Tam dizeyi belirtmek için geçirilecek <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> karşı <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , kullandığınız arka plan kod programlama diline bağlı olarak değişir. Açıklamalara bakın.|  
  
## <a name="dependencies"></a>Bağımlılıklar  
 [x: Class](x-class-directive.md) de aynı öğede sağlanması gerekir ve bu öğe bir sayfa kök öğesi olması gerekir. Daha fazla bilgi için [ \[MS-XAML\] bölümü 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Açıklamalar  
 Değerini `x:ClassModifier` programlama dili tarafından kullanım .NET Framework XAML hizmetlerinde değişir. Her bir dilin nasıl uyguladığını kullanılacak dize bağlıdır, <xref:System.CodeDom.Compiler.CodeDomProvider> ve döndürür anlamı tanımlamak için tür dönüştürücüleri <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ve <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, ve bu dilin büyük küçük harfe duyarlı olup olmadığını.  
  
-   C#, belirlemek üzere iletilecek dizeyi <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> olduğu `internal`.  
  
-   Microsoft Visual Basic .NET, atamak için geçirilecek dize için <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> olduğu `Friend`.  
  
-   İçin [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], XAML derleme destekleyen hiçbir hedef var; Bu nedenle geçirilecek değer belirtilmemiş.  
  
 Belirtebilirsiniz <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` C# ' ta, `Public` Visual Basic'te); ancak belirtme <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> çünkü seyrek yapılan <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> zaten varsayılan davranıştır.  
  
 Diğer değerler eşdeğer kullanıcı kod ile erişim düzeyi kısıtlamaları gibi `private` C# ' ta ilgili olmayan `x:ClassModifier` çünkü iç içe geçmiş sınıf başvuruları XAML içinde desteklenmez ve bu nedenle, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> değiştiricisi, aynı etkiye sahiptir.  
  
## <a name="security-notes"></a>Güvenlik notları  
 Erişim düzeyi bildirilen `x:ClassModifier` yorumu belirli çerçeveleri ve yeteneklerini hala tabidir. WPF yüklemek ve türleri örneği için özellikleri içerir burada `x:ClassModifier` olduğu `internal`, bu sınıfı bir WPF kaynaktan bir URI başvuru paketi aracılığıyla başvurulur. Bu durumda ve diğerleri gibi diğer çerçeveler tarafından uygulanan, söz konusu kümelerdeki potansiyel olarak, özel olarak üzerinde güvenmeyin `x:ClassModifier` olası tüm oluşturmada engellemeye çalışır.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [x:Class Yönergesi](x-class-directive.md)
- [Arka Plan Kod ve WPF İçindeki XAML](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier Yönergesi](x-fieldmodifier-directive.md)
- [Güvenlik (WPF)](../wpf/security-wpf.md)
- [WPF'den System.Xaml'e Geçirilen Türler](types-migrated-from-wpf-to-system-xaml.md)
