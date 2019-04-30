---
title: Genel sınıflar - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
ms.openlocfilehash: 5f898bf342c8596d9dd4cc0b03396aec4dcf545c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61710764"
---
# <a name="generic-classes-c-programming-guide"></a>Genel Sınıflar (C# Programlama Kılavuzu)
Genel sınıflar, belirli veri türüne özgü olmayan işlemler kapsüller. En yaygın Genel sınıflar için bağlantılı liste, karma tabloları, yığınlar, kuyruklar, ağaçlar ve benzeri gibi koleksiyonlar ile kullanılır. Ekleme ve koleksiyondan öğeleri kaldırma gibi işlemler temel olarak aynı şekilde depolanmakta olan veri türünden bağımsız olarak gerçekleştirilir.  
  
 Koleksiyon sınıfları gerektiren çoğu senaryo için önerilen yaklaşım .NET sınıf kitaplığı'nda sağlanan olanları kullanmaktır. Bu sınıflar kullanma hakkında daha fazla bilgi için bkz. [. NET'te genel koleksiyonlar](../../../standard/generics/collections.md).  
  
 Genellikle, varolan bir somut sınıf ile başlayan ve türlerini bir tür parametreleri ile Genelleştirme ve kullanılabilirlik en iyi dengeyi ulaşana kadar aynı anda değiştirme genel sınıflar oluşturun. Genel sınıflarınızı oluştururken önemli noktalar şunlardır:  
  
- İçine genelleştirmek için hangi türlerin tür parametreleri.  
  
     Bir kural, parametreleştirebilirsiniz türlerinin, daha esnek ve yeniden kullanılabilir kodunuzu haline gelir. Ancak, çok fazla Genelleştirme diğer geliştiriciler için okuma veya anlamak zordur kod oluşturabilirsiniz.  
  
- Hangi kısıtlamalar varsa için tür parametreleri uygulamak için (bkz [tür parametrelerindeki kısıtlamalar](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).  
  
     Hala işlemesi gerekir türleri işlemenize olanak sağlayacak en yüksek kısıtlamalara olası uygulamak iyi bir kuraldır. Örneğin, genel, sınıf yalnızca başvuru türleri ile kullanıma yöneliktir biliyorsanız, sınıf kısıtlaması uygulayın. Değer türleri ile sınıfınıza istenmeyen kullanımını engeller ve kullanmanıza olanak tanıyacak `as` işlecinin `T`ve null değerleri için onay.  
  
- Temel sınıflar ve alt sınıfların faktörü genel davranışını belirtir.  
  
     Genel sınıflar temel sınıf olarak hizmet verebilen çünkü aynı tasarım konuları burada geçerli gibi genel olmayan sınıflar. Bu konunun ilerleyen bölümlerinde genel temel sınıflardan devralan hakkında kurallar bakın.  
  
- Bir veya daha fazla genel arabirimi uygulayan verilmeyeceğini belirtir.  
  
     Örneğin, bir genel türler tabanlı koleksiyon öğeleri oluşturmak için kullanılan bir sınıfı tasarlıyorsanız, arabirimi gibi uygulama gerekebilir <xref:System.IComparable%601> burada `T` sınıfınıza türüdür.  
  
 Basit bir genel sınıfın bir örneği için bkz [genel türlere giriş](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 Tür parametreleri ve kısıtlamalar için kuralları, özellikle devralma ve üye erişilebilirliği ile ilgili genel bir sınıf davranışı için birkaç etkiler. Devam etmeden önce bazı terimler anlamanız gerekir. Genel bir sınıf için `Node<T>,` istemci kodu sınıf ya da kapalı bir oluşturulmuş tür oluşturmak için bir tür bağımsız değişkeni belirterek başvurabilir (`Node<int>`). Alternatif olarak, tür parametresi, genel bir temel sınıf belirttiğinizde örneğin belirtilmemiş bırakabilirsiniz, açık bir oluşturma türü oluşturulan (`Node<T>`). Genel sınıflar somut, kapalı oluşturulmuş veya açık oluşturulmuş taban sınıflardan devralınabilir:  
  
 [!code-csharp[csProgGuideGenerics#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#16)]  
  
 Genel olmayan başka bir deyişle, somut, sınıflar devral kapalı oluşturulmuş taban sınıflarına, ancak değil açık oluşturulan sınıflar veya tür parametreleri istemci kodu oluşturmak için gerekli tür bağımsız değişkeni sağlamak için çalışma zamanında hiçbir yolu olmadığından temel sınıf.  
  
 [!code-csharp[csProgGuideGenerics#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#17)]  
  
 Açık oluşturulan türlerinden devraldığına Genel sınıflar türetilen sınıf tarafından paylaşılmayan herhangi bir temel sınıf türü parametre türü bağımsız değişkenler aşağıdaki kodda gösterildiği gibi sağlamanız gerekir:  
  
 [!code-csharp[csProgGuideGenerics#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#18)]  
  
 Açık oluşturulan türlerinden devraldığına Genel sınıflar bir alt kümesi olan kısıtlamaları belirtir veya yaptığından, temel tür kısıtlamalar:  
  
 [!code-csharp[csProgGuideGenerics#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#19)]  
  
 Genel türler birden çok tür parametreleri ve kısıtlamalar, şu şekilde kullanabilirsiniz:  
  
 [!code-csharp[csProgGuideGenerics#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#20)]  
  
 Açık oluşturulan ve kapalı oluşturulan türler, yöntem parametreleri olarak kullanılabilir:  
  
 [!code-csharp[csProgGuideGenerics#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#21)]  
  
 Genel bir sınıf, arabirim uygularsa, bu sınıfın tüm örnekleri o arabirimine çevirebilirsiniz.  
  
 Genel sınıflar değişmez. Diğer bir deyişle, bir giriş parametresi belirtiyorsa bir `List<BaseClass>`, sağlamak çalışırsanız bir derleme zamanı hatası alırsınız bir `List<DerivedClass>`.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Collections.Generic>
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [Genel Türler](../../../csharp/programming-guide/generics/index.md)
- [Numaralandırıcılar durumunu kaydetme](https://blogs.msdn.microsoft.com/wesdyer/2006/01/13/saving-the-state-of-enumerators/)
- [Bir devralma Bulmacanın birinci bölüm](https://blogs.msdn.microsoft.com/ericlippert/2007/07/27/an-inheritance-puzzle-part-one/)
