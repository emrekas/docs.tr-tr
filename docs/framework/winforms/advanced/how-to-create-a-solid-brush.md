---
title: 'Nasıl yapılır: Düz Fırça Oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: ed9ec1f52b41c83b3cc6e36dedf97f1c00db42e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213447"
---
# <a name="how-to-create-a-solid-brush"></a>Nasıl yapılır: Düz Fırça Oluşturma
Bu örnekte bir <xref:System.Drawing.SolidBrush> tarafından kullanılabilen bir nesne bir <xref:System.Drawing.Graphics> şekilleri doldurmak için nesne.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Bunları kullanmayı bitirdikten sonra çağırmalıdır <xref:System.IDisposable.Dispose%2A> fırça nesneleri gibi sistem kaynaklarının kullanılmasına nesneler üzerinde.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [Grafik Programlamaya Başlarken](getting-started-with-graphics-programming.md)
- [GDI+'da Fırçalar ve Dolgulu Şekiller](brushes-and-filled-shapes-in-gdi.md)
- [Şekilleri Doldurmak için Fırça Kullanma](using-a-brush-to-fill-shapes.md)
