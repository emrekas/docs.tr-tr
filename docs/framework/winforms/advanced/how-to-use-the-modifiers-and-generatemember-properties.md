---
title: 'Nasıl yapılır: Değiştiricileri ve GenerateMember Özelliklerini Kullanma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 6194ef288bd43267c2b00fa6d7c6250e90b37c75
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322647"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="26d5b-102">Nasıl yapılır: Değiştiricileri ve GenerateMember Özelliklerini Kullanma</span><span class="sxs-lookup"><span data-stu-id="26d5b-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="26d5b-103">Bir Windows formunda bir bileşen yerleştirdiğinizde, iki özellik tasarım ortamı tarafından sağlanan: `GenerateMember` ve `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="26d5b-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="26d5b-104">`GenerateMember` Özellik belirtir, Windows Form Tasarımcısı ' bileşeni için bir üye değişkeni oluşturur.</span><span class="sxs-lookup"><span data-stu-id="26d5b-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="26d5b-105">`Modifiers` Özelliğidir, bu üye değişkenine atanan erişim değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="26d5b-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="26d5b-106">Varsa değerini `GenerateMember` özelliği `false`, değerini `Modifiers` özelliğinin hiçbir etkisi.</span><span class="sxs-lookup"><span data-stu-id="26d5b-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26d5b-107">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="26d5b-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="26d5b-108">Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="26d5b-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="26d5b-109">Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="26d5b-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="26d5b-110">Bir bileşen form üyesi olup olmadığını belirlemek için</span><span class="sxs-lookup"><span data-stu-id="26d5b-110">To specify whether a component is a member of the form</span></span>  
  
1. <span data-ttu-id="26d5b-111">Windows Form Tasarımcısı'nda formunuza açın.</span><span class="sxs-lookup"><span data-stu-id="26d5b-111">In the Windows Forms Designer, open your form.</span></span>  
  
2. <span data-ttu-id="26d5b-112">Açık **araç kutusu**ve üç form üzerinde yerleştirmek <xref:System.Windows.Forms.Button> kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="26d5b-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3. <span data-ttu-id="26d5b-113">Ayarlama `GenerateMember` ve `Modifiers` özellikleri her <xref:System.Windows.Forms.Button> aşağıdaki tabloya göre denetimi.</span><span class="sxs-lookup"><span data-stu-id="26d5b-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="26d5b-114">Düğme adı</span><span class="sxs-lookup"><span data-stu-id="26d5b-114">Button name</span></span>|<span data-ttu-id="26d5b-115">GenerateMember değeri</span><span class="sxs-lookup"><span data-stu-id="26d5b-115">GenerateMember value</span></span>|<span data-ttu-id="26d5b-116">Değiştiriciler değeri</span><span class="sxs-lookup"><span data-stu-id="26d5b-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="26d5b-117">Değişiklik yok</span><span class="sxs-lookup"><span data-stu-id="26d5b-117">No change</span></span>|  
  
4. <span data-ttu-id="26d5b-118">Çözümü oluşturun.</span><span class="sxs-lookup"><span data-stu-id="26d5b-118">Build the solution.</span></span>  
  
5. <span data-ttu-id="26d5b-119">İçinde **Çözüm Gezgini**, tıklayın **tüm dosyaları göster** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="26d5b-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6. <span data-ttu-id="26d5b-120">Açık **Form1** düğümünü ve **Kod Düzenleyicisi**açın **Form1.Designer.vb** veya **Form1.Designer.cs** dosya.</span><span class="sxs-lookup"><span data-stu-id="26d5b-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="26d5b-121">Bu dosya Windows Forms Tasarımcısı tarafından yayılan kod içerir.</span><span class="sxs-lookup"><span data-stu-id="26d5b-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7. <span data-ttu-id="26d5b-122">Üç düğme için bildirimler bulun.</span><span class="sxs-lookup"><span data-stu-id="26d5b-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="26d5b-123">Aşağıdaki kod örneği tarafından belirtilen farklar gösterilmektedir `GenerateMember` ve `Modifiers` özellikleri.</span><span class="sxs-lookup"><span data-stu-id="26d5b-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="26d5b-124">Varsayılan olarak, Windows Form Tasarımcısı atar `private` (`Friend` Visual Basic) değiştirici gibi kapsayıcı denetimlere <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="26d5b-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="26d5b-125">Varsa tabanınızı <xref:System.Windows.Forms.UserControl> veya <xref:System.Windows.Forms.Form> bir kapsayıcı denetimi sahip devralınan denetimler ve formları yeni alt öğe kabul etmez.</span><span class="sxs-lookup"><span data-stu-id="26d5b-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="26d5b-126">Temel bir kapsayıcı denetimin değiştiricisini çözümüdür `protected` veya `public`.</span><span class="sxs-lookup"><span data-stu-id="26d5b-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d5b-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="26d5b-127">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="26d5b-128">Windows Forms Görsel Devralma</span><span class="sxs-lookup"><span data-stu-id="26d5b-128">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="26d5b-129">İzlenecek yol: Görsel Devralmayı Gösterme</span><span class="sxs-lookup"><span data-stu-id="26d5b-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="26d5b-130">Nasıl yapılır: Windows Formlarını Devralma</span><span class="sxs-lookup"><span data-stu-id="26d5b-130">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
