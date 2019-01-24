---
title: Deyim bir satır dışında blok sona &#39;varsa&#39; deyimi
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 78fe136acbd09e202b1daeb16dd540cf42ada390
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574722"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>Deyim bir satır dışında blok sona &#39;varsa&#39; deyimi
Tek satırlı `If` deyimi biri olan virgülle (:) ayırarak çeşitli deyimleri içeren bir `End` deyim için bir denetim bloğu tek satır dışında `If`. Tek satırlı `If` deyimleri kullanmayın `End If` deyimi.  
  
 **Hata Kimliği:** BC32005  
  
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Tek satırlı taşıma `If` içeren denetim bloğu dışında bir deyim `End If` deyimi.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [If...Then...Else Deyimi](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
