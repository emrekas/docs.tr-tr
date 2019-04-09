---
title: 'Nasıl yapılır: Windows Forms’u Yeniden Boyutlandırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
ms.openlocfilehash: 2da4b7483e92b02360bceb886d84a7f729b84dee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077231"
---
# <a name="how-to-resize-windows-forms"></a><span data-ttu-id="320b4-102">Nasıl yapılır: Windows Forms’u Yeniden Boyutlandırma</span><span class="sxs-lookup"><span data-stu-id="320b4-102">How to: Resize Windows Forms</span></span>
<span data-ttu-id="320b4-103">Windows formunuzda boyutu birkaç şekilde belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="320b4-103">You can specify the size of your Windows Form in several ways.</span></span> <span data-ttu-id="320b4-104">İçin yeni bir değer ayarlayarak hem yüksekliğini hem de formun genişliğine programlama yoluyla değiştirebilirsiniz <xref:System.Windows.Forms.Form.Size%2A> özelliği veya ayarla <xref:System.Windows.Forms.Control.Height%2A> veya <xref:System.Windows.Forms.Control.Width%2A> özellikleri ayrı ayrı.</span><span class="sxs-lookup"><span data-stu-id="320b4-104">You can change both the height and the width of the form programmatically by setting a new value for the <xref:System.Windows.Forms.Form.Size%2A> property, or adjust the <xref:System.Windows.Forms.Control.Height%2A> or <xref:System.Windows.Forms.Control.Width%2A> properties individually.</span></span> <span data-ttu-id="320b4-105">Visual Studio kullanıyorsanız, Windows Forms Tasarımcısı'nı kullanarak boyutunu değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="320b4-105">If you are using Visual Studio, you can change the size using the Windows Forms Designer.</span></span> <span data-ttu-id="320b4-106">Ayrıca bkz: [nasıl yapılır: Tasarımcı kullanarak Windows formlarını yeniden boyutlandır](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="320b4-106">Also see [How to: Resize Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).</span></span>  
  
### <a name="to-resize-a-form-programmatically"></a><span data-ttu-id="320b4-107">Bir form programlı olarak yeniden boyutlandırmak için</span><span class="sxs-lookup"><span data-stu-id="320b4-107">To resize a form programmatically</span></span>  
  
-   <span data-ttu-id="320b4-108">Form boyutunu çalışma zamanında ayarlayarak tanımlarsanız <xref:System.Windows.Forms.Form.Size%2A> formun özelliği.</span><span class="sxs-lookup"><span data-stu-id="320b4-108">Define the size of a form at run time by setting the <xref:System.Windows.Forms.Form.Size%2A> property of the form.</span></span>  
  
     <span data-ttu-id="320b4-109">Aşağıdaki kod örneği, 100 x 100 piksel olarak ayarlayın form boyutunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="320b4-109">The following code example shows the form size set to 100 × 100 pixels.</span></span>  
  
    ```vb  
    Form1.Size = New System.Drawing.Size(100, 100)  
    ```  
  
    ```csharp  
    Form1.Size = new System.Drawing.Size(100, 100);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(100, 100);  
    ```  
  
### <a name="to-change-form-width-and-height-programmatically"></a><span data-ttu-id="320b4-110">Form genişlik ve yükseklik programlı olarak değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="320b4-110">To change form width and height programmatically</span></span>  
  
-   <span data-ttu-id="320b4-111">Sonra <xref:System.Windows.Forms.Form.Size%2A> olan tanımlanmış formu yükseklik veya genişlik kullanarak değiştirmek <xref:System.Windows.Forms.Control.Width%2A> veya <xref:System.Windows.Forms.Control.Height%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="320b4-111">After the <xref:System.Windows.Forms.Form.Size%2A> is defined, change either the form height or width by using the <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="320b4-112">Aşağıdaki kod örneği, yüksekliği sabit kalır ancak formun sol kenardan 300 piksel olarak ayarlayın formun genişliğine gösterir.</span><span class="sxs-lookup"><span data-stu-id="320b4-112">The following code example shows the width of the form set to 300 pixels from the left edge of the form, whereas the height stays constant.</span></span>  
  
    ```vb  
    Form1.Width = 300  
    ```  
  
    ```csharp  
    Form1.Width = 300;  
    ```  
  
    ```cpp  
    Form1->Width = 300;  
    ```  
  
     <span data-ttu-id="320b4-113">-veya-</span><span class="sxs-lookup"><span data-stu-id="320b4-113">-or-</span></span>  
  
     <span data-ttu-id="320b4-114">Değişiklik <xref:System.Drawing.Size.Width%2A> veya <xref:System.Drawing.Size.Height%2A> ayarlayarak <xref:System.Windows.Forms.Form.Size%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="320b4-114">Change <xref:System.Drawing.Size.Width%2A> or <xref:System.Drawing.Size.Height%2A> by setting the <xref:System.Windows.Forms.Form.Size%2A> property.</span></span>  
  
     <span data-ttu-id="320b4-115">Aşağıdaki kod örneğinde gösterildiği gibi ancak bu ayarı yalnızca daha fazla hantal yaklaşımdır <xref:System.Windows.Forms.Control.Width%2A> veya <xref:System.Windows.Forms.Control.Height%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="320b4-115">However, as the following code example shows, this approach is more cumbersome than just setting <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
    ```vb  
    Form1.Size = New Size(300, Form1.Size.Height)  
    ```  
  
    ```csharp  
    Form1.Size = new Size(300, Form1.Size.Height);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(300, Form1->Size.Height);  
    ```  
  
### <a name="to-change-form-size-by-increments-programmatically"></a><span data-ttu-id="320b4-116">Form boyutunu artışlarla program aracılığıyla değiştirme</span><span class="sxs-lookup"><span data-stu-id="320b4-116">To change form size by increments programmatically</span></span>  
  
-   <span data-ttu-id="320b4-117">Formun boyutunu artırmak için ayarlanmış <xref:System.Drawing.Size.Width%2A> ve <xref:System.Drawing.Size.Height%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="320b4-117">To increment the size of the form, set the <xref:System.Drawing.Size.Width%2A> and <xref:System.Drawing.Size.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="320b4-118">Aşağıdaki kod örneği, geçerli boyuttan daha geniş 200 piksel olarak formun genişliğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="320b4-118">The following code example shows the width of the form set to 200 pixels wider than the current setting.</span></span>  
  
    ```vb  
    Form1.Width += 200  
    ```  
  
    ```csharp  
    Form1.Width += 200;  
    ```  
  
    ```cpp  
    Form1->Width += 200;  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="320b4-119">Her zaman <xref:System.Drawing.Size.Height%2A> veya <xref:System.Drawing.Size.Width%2A> yükseklik ve genişlik boyutları ayarlayarak aynı anda ayarlamakta olduğunuz sürece, bir form boyutunu değiştirmek için özellik <xref:System.Windows.Forms.Form.Size%2A> yeni bir özellik <xref:System.Drawing.Size> yapısı.</span><span class="sxs-lookup"><span data-stu-id="320b4-119">Always use the <xref:System.Drawing.Size.Height%2A> or <xref:System.Drawing.Size.Width%2A> property to change a dimension of a form, unless you are setting both height and width dimensions at the same time by setting the <xref:System.Windows.Forms.Form.Size%2A> property to a new <xref:System.Drawing.Size> structure.</span></span> <span data-ttu-id="320b4-120"><xref:System.Windows.Forms.Form.Size%2A> Özelliği döndürür bir <xref:System.Drawing.Size> yapısı, bir değer türüdür.</span><span class="sxs-lookup"><span data-stu-id="320b4-120">The <xref:System.Windows.Forms.Form.Size%2A> property returns a <xref:System.Drawing.Size> structure, which is a value type.</span></span> <span data-ttu-id="320b4-121">Bir değer türünün özelliğine yeni bir değer atanamaz.</span><span class="sxs-lookup"><span data-stu-id="320b4-121">You cannot assign a new value to the property of a value type.</span></span> <span data-ttu-id="320b4-122">Bu nedenle, aşağıdaki kod örneği derlemeyecektir.</span><span class="sxs-lookup"><span data-stu-id="320b4-122">Therefore, the following code example will not compile.</span></span>  
  
    ```vb  
    ' NOTE: CODE WILL NOT COMPILE  
    Dim f As New Form()  
    f.Size.Width += 100  
    ```  
  
    ```csharp  
    // NOTE: CODE WILL NOT COMPILE  
    Form f = new Form();  
    f.Size.Width += 100;  
    ```  
  
    ```cpp  
    // NOTE: CODE WILL NOT COMPILE  
    Form^ f = gcnew Form();  
    f->Size->X += 100;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="320b4-123">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="320b4-123">See also</span></span>

- [<span data-ttu-id="320b4-124">Windows Forms'a Başlarken</span><span class="sxs-lookup"><span data-stu-id="320b4-124">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="320b4-125">Windows Forms Uygulamalarını Geliştirme</span><span class="sxs-lookup"><span data-stu-id="320b4-125">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
