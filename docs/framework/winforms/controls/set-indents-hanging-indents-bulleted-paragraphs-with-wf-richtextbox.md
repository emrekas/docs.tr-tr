---
title: 'Nasıl yapılır: Windows Forms RichTextBox Denetimi ile Girintileri, Asılı Girintileri ve Madde İşaretli Paragrafları Ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: ef579923ac2b9ea9905a60000d93f6bfc90ed5b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342680"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="98633-102">Nasıl yapılır: Windows Forms RichTextBox Denetimi ile Girintileri, Asılı Girintileri ve Madde İşaretli Paragrafları Ayarlama</span><span class="sxs-lookup"><span data-stu-id="98633-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="98633-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> denetimin görüntülediği metni biçimlendirmek için çok sayıda seçeneği vardır.</span><span class="sxs-lookup"><span data-stu-id="98633-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="98633-104">Madde işaretli listeler olarak ayarlayarak seçili paragrafların biçimlendirebilirsiniz <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="98633-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="98633-105">Ayrıca <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, ve <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> girinti paragraf sol ve sağ kenarları denetimi ve diğer satırlık bir metin ile sol kenarı göre ayarlamak için özellikler.</span><span class="sxs-lookup"><span data-stu-id="98633-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="98633-106">Paragraf madde işaretli liste olarak biçimlendirmek için</span><span class="sxs-lookup"><span data-stu-id="98633-106">To format a paragraph as a bulleted list</span></span>  
  
1. <span data-ttu-id="98633-107">Ayarlama <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> özelliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="98633-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="98633-108">Paragrafın girinti</span><span class="sxs-lookup"><span data-stu-id="98633-108">To indent a paragraph</span></span>  
  
1. <span data-ttu-id="98633-109">Ayarlama <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> metnin sol kenarı ile denetimin sol kenarı arasındaki piksel cinsinden uzaklık temsil eden bir tamsayı özelliği.</span><span class="sxs-lookup"><span data-stu-id="98633-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2. <span data-ttu-id="98633-110">Ayarlama <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> paragraf metni ilk satırının sol kenarı ve sonraki satırları aynı öğenin sol kenarı arasındaki piksel cinsinden uzaklık temsil eden bir tamsayı özelliği.</span><span class="sxs-lookup"><span data-stu-id="98633-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="98633-111">Değerini <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> özelliği ilk satırı sarmalanmış bir paragraf satırlarında için yalnızca uygulanır.</span><span class="sxs-lookup"><span data-stu-id="98633-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3. <span data-ttu-id="98633-112">Ayarlama <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> metnin sağ kenarı ile denetimin sağ kenarı arasındaki piksel cinsinden uzaklığı temsil eden bir tamsayı özelliği.</span><span class="sxs-lookup"><span data-stu-id="98633-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="98633-113">Tüm bu özellikler, seçilen metin ve sonra geçerli ekleme noktasına yazdığınız metni içeren tüm paragrafları etkiler.</span><span class="sxs-lookup"><span data-stu-id="98633-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="98633-114">Örneğin, bir kullanıcı bir paragraf içinde bir sözcük seçer ve ardından girintisini ayarlar yeni ayarları bu sözcüğü içeren tüm paragrafa ve daha sonra seçili paragrafın girilen paragraflara uygulanır.</span><span class="sxs-lookup"><span data-stu-id="98633-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="98633-115">Program aracılığıyla metni seçme hakkında daha fazla bilgi için bkz: <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="98633-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98633-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="98633-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="98633-117">RichTextBox Denetimi</span><span class="sxs-lookup"><span data-stu-id="98633-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="98633-118">Windows Forms'da Kullanılacak Denetimler</span><span class="sxs-lookup"><span data-stu-id="98633-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
