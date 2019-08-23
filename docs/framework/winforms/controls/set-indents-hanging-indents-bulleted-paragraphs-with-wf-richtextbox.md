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
ms.openlocfilehash: 9d095e3561cd346e6dbd99d1be7468f6ad5725a6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960450"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="6ec14-102">Nasıl yapılır: Windows Forms RichTextBox Denetimi ile Girintileri, Asılı Girintileri ve Madde İşaretli Paragrafları Ayarlama</span><span class="sxs-lookup"><span data-stu-id="6ec14-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="6ec14-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> denetimi, görüntülediği metni biçimlendirmek için çeşitli seçeneklere sahiptir.</span><span class="sxs-lookup"><span data-stu-id="6ec14-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="6ec14-104"><xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> Özelliği ayarlayarak, Seçili paragrafları madde işaretli listeler olarak biçimlendirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6ec14-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="6ec14-105">Ayrıca <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, ve<xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> özelliklerini, denetimin sol ve sağ kenarlarına ve diğer metin satırlarının sol kenarına göre ayarlamak için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6ec14-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="6ec14-106">Paragrafı madde işaretli liste olarak biçimlendirmek için</span><span class="sxs-lookup"><span data-stu-id="6ec14-106">To format a paragraph as a bulleted list</span></span>  
  
1. <span data-ttu-id="6ec14-107">Ayarlama <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> özelliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="6ec14-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="6ec14-108">Paragrafı girintilemek için</span><span class="sxs-lookup"><span data-stu-id="6ec14-108">To indent a paragraph</span></span>  
  
1. <span data-ttu-id="6ec14-109"><xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> Özelliği, denetimin sol kenarı ve metnin sol kenarı arasındaki mesafeyi temsil eden bir tamsayı olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="6ec14-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2. <span data-ttu-id="6ec14-110"><xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> Özelliği, paragraftaki ilk metin satırının sol kenarı ile aynı paragraftaki sonraki çizgilerin sol kenarı arasındaki mesafeyi temsil eden bir tamsayı olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="6ec14-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="6ec14-111"><xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> Özelliğin değeri yalnızca, ilk satırın altına kaydırılmış olan bir paragraftaki satırlar için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="6ec14-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3. <span data-ttu-id="6ec14-112"><xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> Özelliği, denetimin sağ kenarıyla metnin sağ kenarı arasındaki mesafeyi temsil eden bir tamsayı olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="6ec14-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
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
    > <span data-ttu-id="6ec14-113">Tüm bu özellikler, seçili metni içeren paragrafları ve ayrıca geçerli ekleme noktasının ardından yazılan metni etkiler.</span><span class="sxs-lookup"><span data-stu-id="6ec14-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="6ec14-114">Örneğin, bir Kullanıcı bir paragraf içinde bir kelime seçip Girintiyi ayarladığında, yeni ayarlar, bu sözcüğü içeren tüm paragrafa ve ayrıca seçili paragraftan sonra daha sonra girilmiş olan paragraflara uygulanır.</span><span class="sxs-lookup"><span data-stu-id="6ec14-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="6ec14-115">Program aracılığıyla metin seçme hakkında daha fazla bilgi <xref:System.Windows.Forms.TextBoxBase.Select%2A>için bkz.</span><span class="sxs-lookup"><span data-stu-id="6ec14-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec14-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6ec14-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="6ec14-117">RichTextBox Denetimi</span><span class="sxs-lookup"><span data-stu-id="6ec14-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="6ec14-118">Windows Forms'da Kullanılacak Denetimler</span><span class="sxs-lookup"><span data-stu-id="6ec14-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
