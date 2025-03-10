---
title: LINQ ile Veri Dönüştürmeler (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: f042042f36e373ec05e8f0f15c14027463653578
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924310"
---
# <a name="data-transformations-with-linq-c"></a>LINQ ile Veri Dönüştürmeler (C#)
[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]yalnızca verileri alma hakkında değildir. Ayrıca, verileri dönüştürmek için güçlü bir araçtır. Bir [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgu kullanarak, giriş olarak bir kaynak sırası kullanabilir ve yeni bir çıkış sırası oluşturmak için bunu birçok şekilde değiştirebilirsiniz. Sıralamayı sıralama ve gruplama yoluyla öğeleri değiştirmeden değiştirebilirsiniz. Ancak, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorguların en güçlü özelliği yeni türler oluşturma olanağıdır. Bu, [Select](../../../language-reference/keywords/select-clause.md) yan tümcesinde gerçekleştirilir. Örneğin, aşağıdaki görevleri gerçekleştirebilirsiniz:  
  
- Birden çok giriş dizisini yeni bir türe sahip tek bir çıkış dizisinde birleştirin.  
  
- Öğeleri, kaynak dizideki her öğenin yalnızca bir veya birkaç özelliklerinden oluşan çıkış dizileri oluşturun.  
  
- Öğeleri, kaynak verilerde gerçekleştirilen işlemlerin sonuçlarından oluşan çıkış dizileri oluşturun.  
  
- Çıkış dizilerini farklı biçimde oluşturun. Örneğin, verileri SQL satırlarından veya metin dosyalarından XML 'e dönüştürebilirsiniz.  
  
 Bunlar yalnızca birkaç örnektir. Tabii ki, bu dönüşümler aynı sorgudaki çeşitli şekillerde birleştirilebilir. Ayrıca, bir sorgunun çıkış sırası yeni bir sorgu için giriş sırası olarak kullanılabilir.  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a>Birden Çok Girdiyi Bir Çıkış Sırasına Katma  
 Birden fazla giriş dizisinin [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] öğelerini içeren bir çıkış sırası oluşturmak için bir sorgu kullanabilirsiniz. Aşağıdaki örnek, iki bellek içi veri yapısının nasıl birleştirileceğini gösterir, ancak aynı ilkeler XML veya SQL veya veri kümesi kaynaklarından verileri birleştirmek için uygulanabilir. Aşağıdaki iki sınıf türünü varsayın:  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 Aşağıdaki örnekte sorgu gösterilmektedir:  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 Daha fazla bilgi için bkz. [JOIN yan tümcesi](../../../language-reference/keywords/join-clause.md) ve [Select yan tümcesi](../../../language-reference/keywords/select-clause.md).  
  
## <a name="selecting-a-subset-of-each-source-element"></a>Her Kaynak Öğesinin alt kümesini seçme  
 Kaynak dizideki her bir öğenin alt kümesini seçmek için iki temel yol vardır:  
  
1. Kaynak öğenin yalnızca bir üyesini seçmek için, nokta işlemini kullanın. Aşağıdaki örnekte, bir `Customer` nesnesinin adlı `City`bir dize de dahil olmak üzere birkaç ortak özellik içerdiğini varsayın. Yürütüldüğünde, bu sorgu dizelerin çıkış dizisini üretir.  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. Kaynak öğeden birden fazla özellik içeren öğeler oluşturmak için, bir nesne başlatıcısını adlandırılmış bir nesne veya anonim bir türle birlikte kullanabilirsiniz. Aşağıdaki örnek, her `Customer` bir öğeden iki özelliği kapsüllemek için anonim bir türün kullanımını gösterir:  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Daha fazla bilgi için bkz. [nesne ve koleksiyon başlatıcıları](../../classes-and-structs/object-and-collection-initializers.md) ve [anonim türler](../../classes-and-structs/anonymous-types.md).  
  
## <a name="transforming-in-memory-objects-into-xml"></a>Bellek İçi Nesneleri XML'e dönüştürme  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]sorgular, bellek içi veri yapıları, SQL veritabanları, ADO.NET veri kümeleri ve XML akışları veya belgeler arasında veri dönüştürmeyi kolaylaştırır. Aşağıdaki örnek, bellek içi veri yapısındaki nesneleri XML öğelerine dönüştürür.  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 Kod aşağıdaki XML çıktısını üretir:  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 Daha fazla bilgi için bkz. [XML ağaçlarını oluşturma C# (LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md).  
  
## <a name="performing-operations-on-source-elements"></a>Kaynak Öğeler Üzerinde İşlemler Gerçekleştirme  
 Çıkış sırası, kaynak dizisinden herhangi bir öğe veya öğe özelliği içermeyebilir. Çıktı bunun yerine, kaynak öğeleri giriş bağımsız değişkenleri olarak kullanılarak hesaplanan bir değer dizisi olabilir. Aşağıdaki basit sorgu, yürütüldüğü zaman, değerleri türündeki `double`öğelerin kaynak dizisine göre hesaplamayı temsil eden bir dize dizisi verir.  
  
> [!NOTE]
> Sorgu başka bir etki alanına çevrilecektir sorgu ifadelerinde çağırma yöntemi desteklenmez. Örneğin, SQL Server için bir bağlam olmadığından sıradan C# bir yöntem [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] çağrılamaz. Ancak, saklı yordamları yöntemlere eşleyebilir ve bunları çağırabilirsiniz. Daha fazla bilgi için bkz. [saklı yordamlar](../../../../framework/data/adonet/sql/linq/stored-procedures.md).  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Dil ile tümleşik sorgu (LINQ) (C#)](./index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)
- [LINQ to XML (C#)](./linq-to-xml-overview.md)
- [LINQ sorgu Ifadeleri](../../linq-query-expressions/index.md)
- [select yan tümcesi](../../../language-reference/keywords/select-clause.md)
