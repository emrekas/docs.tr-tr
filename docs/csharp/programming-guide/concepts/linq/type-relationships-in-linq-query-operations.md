---
title: LINQ Sorgu İşlemlerinde Tür İlişkileri (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- inferring type information [LINQ in C#]
- data sources [LINQ in C#], type relationships
- queries [LINQ in C#], type relationships
- relationships [LINQ in C#]
- type relationships [LINQ in C#]
- variable relationships [LINQ in C#]
- type information inferred [LINQ in C#]
- data transformations [LINQ in C#]
- LINQ [C#], type relationships
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
ms.openlocfilehash: 42519a74be1bd6934bc7a3304d154321697d128c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591014"
---
# <a name="type-relationships-in-linq-query-operations-c"></a>LINQ Sorgu İşlemlerinde Tür İlişkileri (C#)
Sorguları etkili bir şekilde yazmak için, bir bütün sorgu işlemindeki değişkenlerin türlerinin birbirleriyle ilişkisini anlamalısınız. Bu ilişkileri anladıysanız, belgelerde [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] örnekleri ve kod örneklerini daha kolay anlarsınız. Ayrıca, değişkenler, kullanılarak `var`örtük olarak yazıldığında ne olduğunu anlamış olursunuz.  
  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]sorgu işlemleri veri kaynağında, sorgunun kendisinde ve sorgu yürütmesinde kesin olarak türdedir. Sorgudaki değişkenlerin türü, veri kaynağındaki öğelerin türüyle ve `foreach` deyimdeki yineleme değişkeni türüyle uyumlu olmalıdır). Bu güçlü yazma, tür hatalarının Kullanıcı tarafından karşılaşmadan önce düzeltilebilecekleri derleme zamanında yakalanmasını güvence altına alır.  
  
 Bu tür ilişkilerini göstermek için, aşağıdaki örneklerin çoğu tüm değişkenler için açık yazma kullanır. Son örnek, [var](../../../language-reference/keywords/var.md)kullanarak örtük yazma kullandığınızda bile aynı ilkelerin nasıl uygulanacağını gösterir.  
  
## <a name="queries-that-do-not-transform-the-source-data"></a>Kaynak verileri dönüştürmeksizin sorgular  
 Aşağıdaki çizimde, verilerde dönüştürme [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] gerçekleştirmeyen bir nesneler sorgu işlemi gösterilmektedir. Kaynak bir dize dizisi içerir ve sorgu çıktısı da dizeler dizisidir.  
  
 ![LINQ sorgusundaki veri türlerinin ilişkisini gösteren diyagram.](./media/type-relationships-in-linq-query-operations/linq-query-data-type-relation.png)  
  
1. Veri kaynağının tür bağımsız değişkeni, Aralık değişkeninin türünü belirler.  
  
2. Seçilen nesnenin türü, sorgu değişkeninin türünü belirler. İşte `name` bir dize. Bu nedenle, sorgu değişkeni bir `IEnumerable<string>`.  
  
3. Sorgu değişkeni, `foreach` ifadesinde tekrarlanıyor. Sorgu değişkeni bir dizeler dizisi olduğundan, yineleme değişkeni de bir dizedir.  
  
## <a name="queries-that-transform-the-source-data"></a>Kaynak verileri dönüştüren sorgular  
 Aşağıdaki çizimde, verilerde basit [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] bir dönüşüm gerçekleştiren bir sorgu işlemi gösterilmektedir. Sorgu, giriş olarak bir dizi `Customer` nesne alır ve `Name` yalnızca sonuç içindeki özelliği seçer. `Name` Bir dize olduğundan, sorgu çıktı olarak bir dize dizisi üretir.  
  
 ![Veri türünü dönüştüren bir sorgu gösteren diyagram.](./media/type-relationships-in-linq-query-operations/linq-query-transform-data-type.png)  
  
1. Veri kaynağının tür bağımsız değişkeni, Aralık değişkeninin türünü belirler.  
  
2. İfade, `Name` tüm`Customer` nesne yerine özelliği döndürür. `select` Bir dize olduğundan, `custNameQuery` `Customer`öğesinin tür bağımsız değişkeni değildir. `string` `Name`  
  
3. Bir dize dizisi olduğundan `foreach` , döngünün yineleme değişkeni de bir `string`olmalıdır. `custNameQuery`  
  
 Aşağıdaki çizimde biraz daha karmaşık bir dönüştürme gösterilmektedir. İfade, özgün `Customer` nesnenin yalnızca iki üyesini yakalayan bir anonim tür döndürür. `select`  
  
 ![Veri türünü dönüştüren daha karmaşık bir sorgu gösteren diyagram.](./media/type-relationships-in-linq-query-operations/linq-complex-query-transform-data-type.png)  
  
1. Veri kaynağının tür bağımsız değişkeni her zaman sorgudaki aralık değişkeninin türüdür.  
  
2. İfade anonim bir tür oluşturduğundan, sorgu değişkeninin kullanılarak `var`örtük olarak yazılması gerekir. `select`  
  
3. Sorgu değişkeninin türü örtük olduğundan, `foreach` döngüdeki yineleme değişkeni de örtük olmalıdır.  
  
## <a name="letting-the-compiler-infer-type-information"></a>Derleyicinin tür bilgilerini çıkarmalarına izin verme  
 Bir sorgu işlemindeki tür ilişkilerini anlamanız gerekse de, derleyicinin tüm işleri gerçekleştirmesini sağlamak için seçeneğiniz vardır. [Var](../../../language-reference/keywords/var.md) anahtar sözcüğü, bir sorgu işlemindeki herhangi bir yerel değişken için kullanılabilir. Aşağıdaki çizim, daha önce açıklanan örnek numarası 2 ' ye benzer. Ancak, derleyici sorgu işlemindeki her değişken için güçlü tür sağlar.  
  
 ![Türü örtük olarak yazılan tür akışını gösteren diyagram.](./media/type-relationships-in-linq-query-operations/linq-type-flow-implicit-typing.png)  
  
 Hakkında `var`daha fazla bilgi için bkz. [örtülü olarak yazılan yerel değişkenler](../../classes-and-structs/implicitly-typed-local-variables.md).  
