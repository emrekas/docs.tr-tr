---
title: 'Nasıl yapılır: Özel yerleşim altyapısı uygulama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- layout engines [Windows Forms], custom
- TableLayoutPanel control [Windows Forms], layout engine
- layout engines [Windows Forms], implementing
- FlowLayoutPanel control [Windows Forms], layout engine
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
ms.openlocfilehash: ac3817e8acfb249050b64f0a9ee8d082c933917b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517168"
---
# <a name="how-to-implement-a-custom-layout-engine"></a>Nasıl yapılır: Özel yerleşim altyapısı uygulama
Aşağıdaki kod örneği, bir basit bir akış düzeni gerçekleştiren özel yerleşim altyapısı oluşturma işlemini gösterir. Adlı bir panel denetimi uygular `DemoFlowPanel`, hangi geçersiz kılmaları <xref:System.Windows.Forms.Control.LayoutEngine%2A> bir örneğini sağlamak için özellik `DemoFlowLayout` sınıfı.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Forms.Layout.LayoutEngine>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=nameWithType>
