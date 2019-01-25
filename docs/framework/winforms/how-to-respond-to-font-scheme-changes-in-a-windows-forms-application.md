---
title: 'Nasıl yapılır: Bir Windows Forms uygulamasında yazı tipi şeması değişikliklerine yanıt verme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 73a6c20f1790ca4ad1dbe331d693af2331da1ea1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682274"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Nasıl yapılır: Bir Windows Forms uygulamasında yazı tipi şeması değişikliklerine yanıt verme
Windows işletim sistemlerinde, bir kullanıcı, daha büyük veya küçük varsayılan yazı tipini görünür yapmak için sistem genelinde yazı tipi ayarlarını değiştirebilirsiniz. Bu yazı tipi ayarları değiştirmek, ekranlarda metin okuma için daha büyük türü gerektirir ve görme engelli kullanıcılar için kritik öneme sahiptir. Artırmayı veya yazı tipi düzeni değiştiğinde formun ve içerilen tüm metin boyutunu azaltmak için bu değişiklikler tepki vermek için Windows Forms uygulaması ayarlayabilirsiniz. Yazı tipi boyutlarını değişiklikleri dinamik olarak uyum sağlayacak şekilde formunuza istiyorsanız formunuza kod ekleyebilirsiniz.  
  
 Genellikle, Windows Forms tarafından kullanılan varsayılan yazı tipi tarafından döndürülen yazı tipi <xref:Microsoft.Win32> ad alanı çağrısına `GetStockObject(DEFAULT_GUI_FONT)`. Bu çağrı tarafından döndürülen yazı tipi, yalnızca ekran çözünürlüğü değiştiğinde değişir. Aşağıdaki yordamda gösterildiği gibi kodunuzu için varsayılan yazı tipini değiştirmek <xref:System.Drawing.SystemFonts.IconTitleFont%2A> yazı tipi boyutu değişikliklere yanıt vermek için.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Masaüstü yazı tipini kullan ve yazı tipi şeması değişikliklerine yanıt  
  
1.  Formunuza oluşturun ve istediğiniz denetimi ekleyin. Daha fazla bilgi için [nasıl yapılır: Komut satırından bir Windows Forms uygulaması oluşturma](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) ve [Windows Forms'da kullanılacak denetimler](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
2.  Bir başvuru ekleyin <xref:Microsoft.Win32> kodunuzda ad alanı.  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  Oluşturucusu formunuz gerekli olay işleyicilerini yeteneklerinizi ve kullanım form için varsayılan yazı tipini değiştirmek için aşağıdaki kodu ekleyin.  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  Uygulamak için bir işleyici <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> otomatik olarak ölçeklendirmek form neden olan bir olay olduğunda <xref:Microsoft.Win32.UserPreferenceCategory.Window> kategori değişiklikleri.  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  Son olarak, bir işleyici uygulamak <xref:System.Windows.Forms.Form.FormClosing> ayırır olay <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> olay işleyicisi.  
  
     > [!IMPORTANT]
     > Bu kod eklemek için hata, uygulamanızın bellek sızıntısına neden olur.  
  
     [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6.  Derleyin ve kod çalıştırın.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>El ile Windows XP'de yazı tipi düzeni değiştirmek için  
  
1.  Windows Forms uygulamanız çalışırken Windows masaüstüne sağ tıklayın ve seçin **özellikleri** kısayol menüsünden.  
  
2.  İçinde **görüntü özellikleri** iletişim kutusu, tıklayın **Görünüm** sekmesi.  
  
3.  Gelen **yazı tipi boyutu** aşağı açılan liste kutusunda, yeni bir yazı tipi boyutu seçin.  
  
     Form artık Masaüstü yazı tipi düzeni çalışma zamanı değişikliklere tepki verir olduğunu fark edeceksiniz. Kullanıcı değiştiğinde arasında **Normal**, **büyük yazı tipleri**, ve **ek büyük yazı tipleri**, form yazı tipi değiştirir ve doğru şekilde ölçeklendirir.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Bu kod örneğinde constructer bir çağrı içeren `InitializeComponent`, Visual Studio'da yeni bir Windows Forms projesi oluşturduğunuzda tanımlı olduğu. Komut satırında, bir uygulama oluşturuyorsanız bu kod satırını kaldırın.  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [Windows Forms'ta Otomatik Ölçeklendirme](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
