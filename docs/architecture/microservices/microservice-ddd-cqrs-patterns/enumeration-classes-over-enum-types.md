---
title: Sabit listesi türleri yerine Sabit Listesi sınıfları kullanma
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmetleri mimarisi | İkinci öğesinin bazı sınırlamalarını çözmenin bir yolu olarak, numaralandırmalar yerine numaralandırma sınıflarını nasıl kullanabileceğinizi ortadan kaldırabilirsiniz.
ms.date: 10/08/2018
ms.openlocfilehash: ba687b700d7a6105baf71aa08a0d888afc9a8ec3
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70296862"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a>Sabit listesi türleri yerine numaralandırma sınıfları kullanın

[Numaralandırmalar](../../../csharp/language-reference/keywords/enum.md) (veya Short için *enum Types* ), bir integral türünün çevresindeki bir ince dil sarmalayıcısıdır. Kapalı bir değer kümesinden bir değeri depolarken, kullanımlarını sınırlamak isteyebilirsiniz. Boyutlara göre sınıflandırma (küçük, orta, büyük) iyi bir örnektir. Denetim akışı veya daha güçlü soyutlamalar için Numaralandırmaların kullanılması [kod kokusu](https://deviq.com/code-smells/)olabilir. Bu kullanım türü, numaralandırmanın değerlerini denetleyen birçok denetim akışı deyimi ile fragla kodu doğurur.

Bunun yerine, nesne yönelimli bir dilin tüm zengin özelliklerini etkinleştiren numaralandırma sınıfları oluşturabilirsiniz.

Ancak, bu önemli bir konu değildir ve birçok durumda kolaylık sağlaması için, tercih ettiğiniz takdirde normal [numaralandırma türlerini](../../../csharp/language-reference/keywords/enum.md) kullanmaya devam edebilirsiniz. Yine de, sabit listesi sınıflarının kullanımı işle ilgili kavramlarla ilgilidir.

## <a name="implement-an-enumeration-base-class"></a>Numaralandırma temel sınıfı uygulama

EShopOnContainers 'daki sıralama mikro hizmeti, aşağıdaki örnekte gösterildiği gibi bir örnek numaralandırma temel sınıf uygulamasını sağlar:

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

    protected Enumeration(int id, string name) 
    {
        Id = id; 
        Name = name; 
    }

    public override string ToString() => Name;

    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public | 
                                         BindingFlags.Static | 
                                         BindingFlags.DeclaredOnly); 

        return fields.Select(f => f.GetValue(null)).Cast<T>();
    }

    public override bool Equals(object obj) 
    {
        var otherValue = obj as Enumeration; 

        if (otherValue == null) 
            return false;

        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);

        return typeMatches && valueMatches;
    }

    public int CompareTo(object other) => Id.CompareTo(((Enumeration)other).Id); 

    // Other utility methods ... 
}
```

Bu sınıfı, aşağıdaki `CardType` `Enumeration` gibi herhangi bir varlık veya değer nesnesinde bir tür olarak kullanabilirsiniz: Sınıfı:

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    public CardType(int id, string name)
        : base(id, name)
    {
    }
}
```

## <a name="additional-resources"></a>Ek kaynaklar

- **Sabit listesinin Evil olması — güncelleştirme** \
  <https://www.planetgeek.ch/2009/07/01/enums-are-evil/>

- **Daniel Hardman. Numaralandırmaların nasıl dağılacağı ve nasıl bulunduğu** \
  <https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/>

- **Jimmy Bogard. Numaralandırma sınıfları** \
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- **Steve Smith. İçindeki sabit listesi alternatifleriC#**  \
  <https://ardalis.com/enum-alternatives-in-c>

- **Enumeration.cs.** EShopOnContainers içindeki temel numaralandırma sınıfı \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- **CardType.cs**. EShopOnContainers içinde örnek numaralandırma sınıfı. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>
    
- **Smartenum**. .NET ' te kesin olarak belirlenmiş daha akıllı numaralandırmalar üretmeye yardımcı olmak için ardın sınıfları. \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
>[Önceki](implement-value-objects.md)İleri
>[](domain-model-layer-validations.md)
