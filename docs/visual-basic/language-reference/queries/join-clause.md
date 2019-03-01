---
title: Join Tümcesi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: 1a2ec42adb4c41c33cb9e1c09822795c81e3a728
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971305"
---
# <a name="join-clause-visual-basic"></a>Join Tümcesi (Visual Basic)
İki koleksiyonu tek bir koleksiyon halinde birleştirir. Birleştirme işlemi anahtarların eşleşmesi temeline göre ve kullandığı `Equals` işleci.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>Bölümler  
 `element`  
 Gerekli. Denetim değişkeni birleştirilen koleksiyonu.  
  
 `collection`  
 Gerekli. Sol tarafında belirtilen toplama ile birleştirmek için koleksiyon `Join` işleci. A `Join` yan tümcesi iç içe geçirilemez başka `Join` yan tümcesi veya bir `Group Join` yan tümcesi.  
  
 `joinClause`  
 İsteğe bağlı. Bir veya daha fazla ek `Join` daha da fazla yan tümce sorgu daraltın.  
  
 `groupJoinClause`  
 İsteğe bağlı. Bir veya daha fazla ek `Group Join` daha da fazla yan tümce sorgu daraltın.  
  
 `key1` `Equals` `key2`  
 Gerekli. Birleştirilen koleksiyonlar için anahtarları tanımlar. Kullanmalısınız `Equals` birleştirilen koleksiyonları'ndaki anahtarları Karşılaştırılacak işleci. Birleştirme koşulları kullanarak birleştirebilirsiniz `And` birden çok anahtar tanımlamak için işleci. `key1` sol tarafındaki koleksiyondan olmalıdır `Join` işleci. `key2` sağ alt tarafında koleksiyondan olmalıdır `Join` işleci.  
  
 Birleşim koşulunda kullanılan anahtarları koleksiyonundan birden fazla öğe içeren ifadeler olabilir. Ancak, her anahtar ifadesi yalnızca kendi ilgili koleksiyondaki öğeler içerebilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `Join` Yan tümcesi birleştirilen koleksiyonları anahtar değerlerinden eşleşmesi temeline göre iki koleksiyon birleştirir. Sonuçta elde edilen koleksiyon değerleri sol tarafında belirtilen koleksiyondaki herhangi bir birleşimini içerebilir `Join` işleci ile tanımlanan koleksiyonu `Join` yan tümcesi. Sorgu tarafından koşulu için belirtilen sonuç döndürür `Equals` işleci karşılanıyorsa. Bunun eşdeğeri olan bir `INNER JOIN` SQL.  
  
 Birden çok kullanabileceğiniz `Join` tek bir koleksiyon iki veya daha fazla koleksiyonlara katılmak için bir sorgu yan tümcelerinde.  
  
 Koleksiyonları olmadan birleştirmek için örtük bir birleşim gerçekleştirebileceğiniz `Join` yan tümcesi. Bunu yapmak için birden çok dahil `In` yan tümcelerinde, `From` yan tümcesini belirtin bir `Where` birleştirme için kullanmak istediğiniz anahtarları tanımlayan yan tümcesi.  
  
 Kullanabileceğiniz `Group Join` koleksiyonları tek bir hiyerarşik koleksiyon halinde birleştirmek için yan tümcesi. Bu benzer bir `LEFT OUTER JOIN` SQL.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, müşterilerin listesini siparişlerini ile birleştirmek için örtük bir birleşim gerçekleştirir.  
  
 [!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği iki koleksiyonu kullanarak birleştirir `Join` yan tümcesi.  
  
 [!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]  
  
 Bu örnekte, aşağıdakine benzer bir çıktı oluşturur:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği iki koleksiyonu kullanarak birleştirir `Join` iki anahtar sütunlarıyla yan tümcesi.  
  
 [!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]  
  
 Örneğin, aşağıdakine benzer bir çıktı oluşturur:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Visual Basic'de LINQ'e giriş](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Sorgular](../../../visual-basic/language-reference/queries/index.md)
- [Select Yan Tümcesi](../../../visual-basic/language-reference/queries/select-clause.md)
- [From Yan Tümcesi](../../../visual-basic/language-reference/queries/from-clause.md)
- [Group Join Yan Tümcesi](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Where Yan Tümcesi](../../../visual-basic/language-reference/queries/where-clause.md)
