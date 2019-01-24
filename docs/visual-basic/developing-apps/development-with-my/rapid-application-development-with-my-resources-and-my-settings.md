---
title: My.Resources ve My.Settings ile Hızlı Uygulama Geliştirme (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 4150d2f9634045351cb52e02c4f4807e55d118e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717923"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>My.Resources ve My.Settings ile Hızlı Uygulama Geliştirme (Visual Basic)
`My.Resources` Nesne uygulamanın kaynaklara erişim sağlar ve uygulamanız için kaynakları dinamik olarak almanıza olanak tanır.  
  
## <a name="retrieving-resources"></a>Kaynakları Alma  
 Ses dosyaları, simgeler, resimler ve dizeler gibi kaynaklar alınabilir `My.Resources` nesne. Örneğin, uygulamanın kültüre özgü kaynak dosyalara erişebilirsiniz. Aşağıdaki örnekte adlı simgeyi form simgesini ayarlar `Form1Icon` uygulamanın kaynak dosyada depolanır.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 `My.Resources` Nesnesi yalnızca Genel kaynaklar kullanıma sunar. Forms ile ilişkili kaynak dosyalarına erişim sağlamaz. Form kaynaklarını formdan erişmeniz gerekir.  
  
 Benzer şekilde, `My.Settings` nesne uygulamanın ayarlarına erişim sağlar ve dinamik olarak depolamak ve özellik ayarlarını ve uygulamanızın diğer bilgilerini almak sağlar. Daha fazla bilgi için [My.Resources nesnesi](../../../visual-basic/language-reference/objects/my-resources-object.md) ve [My.Settings nesnesi](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
- [My.Resources Nesnesi](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [My.Settings Nesnesi](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Uygulama Ayarlarına Erişme](../../../visual-basic/developing-apps/programming/app-settings/index.md)
