---
title: Genel arabirimler- C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: 47eba90eba670d2f735c2f5ca24053e23d34e871
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659804"
---
# <a name="generic-interfaces-c-programming-guide"></a>Genel Arabirimler (C# Programlama Kılavuzu)
Genel koleksiyon sınıfları için ya da koleksiyondaki öğeleri temsil eden genel sınıflar için arabirim tanımlamak genellikle yararlıdır. Genel sınıfların tercihi, değer türlerinde kutulamayı ve kutudan çıkarma işlemlerini önlemek <xref:System.IComparable%601> için <xref:System.IComparable>yerine gibi genel arabirimleri kullanmaktır. .NET Framework sınıf kitaplığı, <xref:System.Collections.Generic> ad alanındaki koleksiyon sınıflarıyla kullanılmak üzere birkaç genel arabirimi tanımlar.  
  
 Bir arabirim bir tür parametresinde kısıtlama olarak belirtildiğinde, yalnızca arabirimini uygulayan türler kullanılabilir. Aşağıdaki kod örneğinde `GenericList<T>` sınıfından türetilen bir `SortedList<T>` sınıf gösterilmektedir. Daha fazla bilgi için bkz. [Genel türlere giriş](./index.md). `SortedList<T>`kısıtlamayı `where T : IComparable<T>`ekler. Bu, `BubbleSort` içindeki `SortedList<T>` yönteminin List öğelerinde genel <xref:System.IComparable%601.CompareTo%2A> yöntemini kullanmasına olanak sağlar. Bu örnekte, liste öğeleri, uygulayan `Person` `IComparable<Person>`basit bir sınıftır.  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 Birden çok arabirim, tek bir tür üzerinde kısıtlamalar olarak belirtilebilir ve aşağıdaki gibi:  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 Bir arabirim, aşağıdaki gibi birden fazla tür parametresi tanımlayabilir:  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 Sınıflar için uygulanan devralma kuralları arabirimler için de geçerlidir:  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 Genel arabirim değişken karşıtı ise genel arabirimler, genel olmayan arabirimlerden devralınabilir, bu da yalnızca kendi tür parametresini dönüş değeri olarak kullanır. <xref:System.Collections.Generic.IEnumerable%601> .NET Framework sınıf kitaplığında öğesinden <xref:System.Collections.IEnumerable> devralır çünkü <xref:System.Collections.Generic.IEnumerable%601> yalnızca öğesinin `T` <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> dönüş değerinde ve <xref:System.Collections.Generic.IEnumerator%601.Current%2A> özellik alıcısı içinde kullanılır.  
  
 Somut sınıflar, aşağıdaki gibi kapalı oluşturulmuş arabirimler uygulayabilir:  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 Genel sınıflar, sınıf parametresi listesi arabirimin gerektirdiği tüm bağımsız değişkenleri aşağıdaki şekilde sağladığı sürece genel arabirimleri veya kapalı oluşturulmuş arabirimleri uygulayabilir:  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 Yöntem aşırı yüklemesini denetleyen kurallar, genel sınıflar, genel yapılar veya genel arabirimler içindeki yöntemler için aynıdır. Daha fazla bilgi için bkz. [Genel yöntemler](./generic-methods.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../index.md)
- [Genel Türlere Giriş](./index.md)
- [interface](../../language-reference/keywords/interface.md)
- [Genel Türler](../../../standard/generics/index.md)
