---
title: ad alanı anahtar sözcüğü - C# başvurusu
ms.custom: seoapril2019
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 4859c361b3321c1144204f63896152694f6ac5c9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148765"
---
# <a name="namespace-c-reference"></a>namespace (C# Başvurusu)

`namespace` Anahtar sözcüğü, bir dizi ilgili nesneleri içeren bir kapsamı bildirmek için kullanılır. Kod öğelerini düzenlemek ve genel olarak benzersiz türleri oluşturmak için bir ad kullanabilirsiniz.

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a>Açıklamalar

Ad alanı içinde sıfır veya daha fazla türlerinden birini bildirebilirsiniz:

- başka bir ad alanı

- [sınıf](class.md)

- [arabirim](interface.md)

- [struct ](struct.md)

- [enum](enum.md)

- [temsilci](delegate.md)

Açıkça bir C# kaynak dosyası içinde bir ad alanı bildirimini olsun veya olmasın, derleyici varsayılan bir ad alanı ekler. Bazen genel ad alanı adlandırılır, bu adlandırılmamış ad, her bir dosyanın yok. Genel ad alanındaki herhangi bir tanımlayıcı adlandırılmış bir ad alanında kullanılabilir.

Ad alanları, örtük olarak genel erişimi vardır ve bu değiştirilebilir değildir. Bir ad alanındaki öğeler atayabilirsiniz erişim değiştiricileri ile ilgili tartışma için bkz: [erişim değiştiricileri](access-modifiers.md).

İki veya daha fazla bildirimlerinde ad alanı tanımlamak mümkündür. Örneğin, aşağıdaki örnekte iki sınıf kapsamında tanımlar `MyCompany` ad alanı:

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir iç içe geçmiş ad alanındaki statik bir yöntemi çağırmak nasıl gösterir.

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a>İlgili kaynaklar

Ad alanlarını kullanma hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Ad Alanları](../../programming-guide/namespaces/index.md)

- [Ad Alanlarını Kullanma](../../programming-guide/namespaces/using-namespaces.md)

- [Nasıl yapılır: Genel Ad Alanı Diğer Adlarını Kullanma](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>C# dili belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [C# Başvurusu](../../language-reference/index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# Anahtar Sözcükleri](index.md)
- [Ad Alanı Anahtar Sözcükleri](namespace-keywords.md)
- [kullanma](using-directive.md)
- [' Using static](using-static.md)