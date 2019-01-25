---
title: 'Nasıl yapılır: UserControl sınıfından devralma'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
ms.openlocfilehash: 4c3f3d6775f3fdf511e59b360d6c356e2d4fabee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532103"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a>Nasıl yapılır: UserControl sınıfından devralma
Özel kod gerektirmeyen bir veya daha fazla Windows Forms denetimleri işlevlerini birleştirmek için oluşturabileceğiniz bir *kullanıcı denetimi*. Kullanıcı denetimleri hızlı denetimi geliştirme birleştirmek, işlevselliği ve özel özellik ve yöntem çok yönlülük standart Windows Forms denetimi. Bir kullanıcı denetimi oluşturma başladığınızda, standart Windows Forms denetimleri yerleştirebilirsiniz görünür Tasarımcısı ile sunulur. Bu denetimler, tüm iç işlevleri yanı sıra görünümünü ve davranışını (Görünüm) standart denetimler korur. Bu denetimler, kullanıcı denetimine oluşturulur, sonra ancak bunlar artık kod kullanılabilir. Kullanıcı denetimi, kendi boyama yapar ve ayrıca temel işlevleri denetimleriyle ilişkili tüm işler.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-user-control"></a>Bir kullanıcı denetimi oluşturmak için  
  
1.  Yeni bir **Windows Denetim Kitaplığı** proje.  
  
     Boş kullanıcı denetimi ile yeni bir Proje oluşturulur.  
  
2.  Sürükleyin denetimlerden **Windows Forms** sekmesinde **araç kutusu** , tasarımcıya.  
  
3.  Bu denetimler konumlandırılır ve son kullanıcı denetimi görünmesini istediğiniz şekilde tasarlanmıştır. Geliştiricilerin bağlı denetimler erişim izin vermek istiyorsanız, bunları ortak olarak bildirmek veya seçmeli olarak bağlı denetimin özelliklerini göstermek. Ayrıntılar için bkz [nasıl yapılır: Bağlı denetimlerin özelliklerini açığa](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).  
  
4.  Herhangi bir özel yöntemler veya denetiminiz birleştirecektir özellikleri uygulayın.  
  
5.  Projeyi oluşturmak ve denetim çalıştırmak için F5 tuşuna basın **UserControl Test kapsayıcısı**. Daha fazla bilgi için [nasıl yapılır: Bir UserControl denetiminin çalışma zamanı davranışını sınama](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Özel Denetim Çeşitleri](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
- [Nasıl yapılır: Denetim sınıfından devralma](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)
- [Nasıl yapılır: Mevcut Windows Formları denetimlerinden devralma](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)
- [Nasıl yapılır: Windows Forms için yazar denetimleri](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)
- [Basic'de devralınmış olay işleyicileri Visual Basic sorunlarını giderme](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Nasıl yapılır: Bir UserControl denetiminin çalışma zamanı davranışını sınama](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)
