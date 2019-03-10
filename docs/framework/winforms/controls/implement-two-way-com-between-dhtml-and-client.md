---
title: 'Nasıl yapılır: DHTML koduyla istemci uygulaması kodu arasında iki yönlü iletişim uygulamak'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.ObjectForScripting
- WebBrowser.Document
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- communications [Windows Forms], DHTML and client applications
- examples [Windows Forms], WebBrowser control
- WebBrowser control [Windows Forms], communication between DHTML and client application
- DHTML [Windows Forms], embedding in Windows Forms
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
ms.openlocfilehash: 52928b11ce3577a1fb6d218b4a74b986f5fe8d1e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710270"
---
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a>Nasıl yapılır: DHTML koduyla istemci uygulaması kodu arasında iki yönlü iletişim uygulamak
Kullanabileceğiniz <xref:System.Windows.Forms.WebBrowser> denetimi mevcut dinamik HTML (DHTML) Web uygulama kodu Windows Forms istemci uygulamalarınıza ekleyin. Bu, önemli geliştirme süresini DHTML tabanlı denetimler oluşturma yatırım yapmış ve mevcut kodu yeniden yazmak zorunda kalmadan Windows formlarının zengin kullanıcı arabirimi özelliklerinden yararlanan istediğinizde kullanışlıdır.  
  
 <xref:System.Windows.Forms.WebBrowser> Denetimi Web sayfasına komut dosyası kodunuzda, istemci uygulaması kodu arasında iki yönlü iletişim uygulamanıza olanak tanır <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> ve <xref:System.Windows.Forms.WebBrowser.Document%2A> özellikleri. Buna ek olarak, yapılandırabileceğiniz <xref:System.Windows.Forms.WebBrowser> Web denetimleri, diğer denetimleri, uygulamanın formunuzda, DHTML geliştirdikleri gizleme ile sorunsuz bir şekilde blend göstermelerini sağlayın. Sorunsuz bir şekilde denetimleri karıştırmak için görsel stil ve arka plan rengi formun kalanını eşleşen ve kullanmak görüntülenen sayfa biçimlendirme <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>, ve <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> standart tarayıcı özellikleri devre dışı bırakmak için özellikleri.  
  
### <a name="to-embed-dhtml-in-your-windows-forms-application"></a>Windows Forms uygulaması'nda DHTML eklemek için  
  
1.  Ayarlama <xref:System.Windows.Forms.WebBrowser> denetimin <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> özelliğini `false` önlemek için <xref:System.Windows.Forms.WebBrowser> sürüklediğinizde bırakılan dosyaları açma denetimi.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]  
  
2.  Denetimin ayarlamak <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> özelliğini `false` önlemek için <xref:System.Windows.Forms.WebBrowser> denetiminin kullanıcı tıkladığında, kısayol menüsünü görüntüleme.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]  
  
3.  Denetimin ayarlamak <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> özelliğini `false` önlemek için <xref:System.Windows.Forms.WebBrowser> kısayol tuşları için yanıt denetimi.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]  
  
4.  Ayarlama <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> formun Oluşturucusu bir özellik veya <xref:System.Windows.Forms.Form.Load> olay işleyicisi.  
  
     Aşağıdaki kod, betik oluşturma nesne için form sınıfı kullanır.  
  
    > [!NOTE]
    >  Bileşen Nesne Modeli (COM) komut dosyası nesnesi erişebilir olması gerekir. Formunuza COM görünür hale getirmek için ekleme <xref:System.Runtime.InteropServices.ComVisibleAttribute> form sınıfı özniteliği.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]  
  
5.  Genel Özellikler veya yöntemler, uygulama kodunuzda betik kodunuzun kullanacağı uygulayın.  
  
     Örneğin, betik oluşturma nesne için form sınıfı kullanırsanız, form sınıfa aşağıdaki kodu ekleyin.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]  
  
6.  Kullanım `window.external` genel özellikleri ve yöntemleri belirtilen nesnenin erişmek için komut dosyası kodunuzda bir nesne.  
  
     Aşağıdaki HTML kod bir düğmeyi tıklatın betik oluşturma nesne üzerinde bir yöntemi çağırmak nasıl gösterir. Bu kodu denetimin kullanarak yükleyen bir HTML belgesi gövde öğesinin içine kopyalayın <xref:System.Windows.Forms.WebBrowser.Navigate%2A> yöntemi veya denetimin atadığınız <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> özelliği.  
  
    ```  
    <button onclick="window.external.Test('called from script code')">  
        call client code from script code  
    </button>  
    ```  
  
7.  Betik kodunuzu uygulama kodunuzun kullanacağı işlevleri uygulayın.  
  
     Aşağıdaki HTML BETİK öğesi, bir örnek işlevi sağlar. Bu kodu denetimin kullanarak yükleyen bir HTML belgesi baş öğesinin içine kopyalayın <xref:System.Windows.Forms.WebBrowser.Navigate%2A> yöntemi veya denetimin atadığınız <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> özelliği.  
  
    ```  
    <script>  
    function test(message) {   
        alert(message);   
    }  
    </script>  
    ```  
  
8.  Kullanım <xref:System.Windows.Forms.WebBrowser.Document%2A> betik kodu istemci uygulama kodunuz içinden erişmek için özelliği.  
  
     Örneğin, aşağıdaki kod bir düğme ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]  
  
9. Hata ayıklama, DHTML işiniz bittiğinde, denetimin ayarlamak <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> özelliğini `true` önlemek için <xref:System.Windows.Forms.WebBrowser> betik kodu sorunlar için hata iletileri görüntülenmesini denetim.  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bu özellik anlamak için kullanabileceğiniz bir uygulama sağlar. HTML kod yüklendiği <xref:System.Windows.Forms.WebBrowser> aracılığıyla kontrol <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> özelliği yerine ayrı bir HTML dosyasından yükleniyor.  
  
 [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod gerektirir:  
  
-   Sistem ve System.Windows.Forms öğelerini derlemelerine başvurular.  
  
 Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>
- [WebBrowser Denetimi](webbrowser-control-windows-forms.md)
