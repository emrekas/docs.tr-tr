---
title: For döngüsü denetim değişkeni olarak bildirilen dizi başlangıç boyutuyla bildirilemez
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: bee3bcd3701945f5cf77f6761defc8be77acf49f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935388"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>For döngüsü denetim değişkeni olarak bildirilen dizi başlangıç boyutuyla bildirilemez
A `For Each` döngü kullanan bir dizi olarak kendi *öğesi* yineleme değişkeni, ancak bu diziyi başlatır.  
  
 Aşağıdaki deyimleri nasıl bu hatayı oluşturulacağını gösterir.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 İlk `For Each` deyimdir erişim öğeleri doğru şekilde `arrayList`. İkinci `For Each` deyimi bu hata oluşturur.  
  
 **Hata Kimliği:** BC32039  
  
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
- Başlatma bildirimden kaldırmak *öğesi* yineleme değişkeni.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [For...Next Deyimi](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Diziler](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Koleksiyonlar](../../../standard/collections/index.md)
