---
title: 'Nasıl yapılır: Windows Form devralma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 29b32cd91cefe80f2f0a331f901fcabe55aa9c60
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558988"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="137c0-102">Nasıl yapılır: Windows Form devralma</span><span class="sxs-lookup"><span data-stu-id="137c0-102">How to: Inherit Windows Forms</span></span>
<span data-ttu-id="137c0-103">Temel forms devralarak yeni Windows form oluşturmaya, ihtiyaç duyduğunuz her zaman bir form tamamen yeniden işlemine geçmeden çabalarınıza çoğaltmak için kullanışlı bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="137c0-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>  
  
 <span data-ttu-id="137c0-104">Formları kullanarak tasarım zaman devralma hakkında daha fazla bilgi için **devralma Seçici** iletişim kutusu ve görsel olarak güvenlik düzeyleri arasında ayrım yapmak nasıl devralınan denetimler için bkz: [nasıl yapılır: Devralma Seçici iletişim kutusunu kullanarak form devralma](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="137c0-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>  
  
 <span data-ttu-id="137c0-105">**Not** bir formdan devralmak için dosya veya ad alanı, formu içeren bir yürütülebilir dosya veya DLL yerleştirilmiştir gerekir.</span><span class="sxs-lookup"><span data-stu-id="137c0-105">**Note** In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="137c0-106">Projeyi oluşturmak için Seç **derleme** gelen **derleme** menüsü.</span><span class="sxs-lookup"><span data-stu-id="137c0-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="137c0-107">Ayrıca, formun devralan sınıf için bir ad alanına başvuru eklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="137c0-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span> <span data-ttu-id="137c0-108">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="137c0-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="137c0-109">Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="137c0-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="137c0-110">Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="137c0-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-inherit-a-form-programmatically"></a><span data-ttu-id="137c0-111">Bir form programlı olarak devralmak için</span><span class="sxs-lookup"><span data-stu-id="137c0-111">To inherit a form programmatically</span></span>  
  
1.  <span data-ttu-id="137c0-112">Sınıfınızda, devralınan istediğiniz formu içeren ad alanı bir başvuru ekleyin.</span><span class="sxs-lookup"><span data-stu-id="137c0-112">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>  
  
2.  <span data-ttu-id="137c0-113">Sınıf tanımında devralmak için forma bir başvuru ekleyin.</span><span class="sxs-lookup"><span data-stu-id="137c0-113">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="137c0-114">Başvuru formun taban form adını ardından bir nokta içeren ad alanı içermelidir.</span><span class="sxs-lookup"><span data-stu-id="137c0-114">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 <span data-ttu-id="137c0-115">Forms devralınırken her olay hem temel sınıfını hem de devralınan bir sınıf tarafından işlenmediğinden oluşabilecek sorunları iki kez çağrılan olay işleyicileri ile ilgili göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="137c0-115">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="137c0-116">Bu sorunu önlemek yapma hakkında daha fazla bilgi için bkz. [sorun giderme devralınmış olay işleyicileri Visual Basic'te](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="137c0-116">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="137c0-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="137c0-117">See also</span></span>
- [<span data-ttu-id="137c0-118">Inherits Deyimi</span><span class="sxs-lookup"><span data-stu-id="137c0-118">Inherits Statement</span></span>](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="137c0-119">Imports Deyimi (.NET Ad Alanı ve Türü)</span><span class="sxs-lookup"><span data-stu-id="137c0-119">Imports Statement (.NET Namespace and Type)</span></span>](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="137c0-120">using</span><span class="sxs-lookup"><span data-stu-id="137c0-120">using</span></span>](~/docs/csharp/language-reference/keywords/using.md)
- [<span data-ttu-id="137c0-121">Taban Formun Görünüşünü Değiştirmenin Etkileri</span><span class="sxs-lookup"><span data-stu-id="137c0-121">Effects of Modifying a Base Form's Appearance</span></span>](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="137c0-122">Windows Forms Görsel Devralma</span><span class="sxs-lookup"><span data-stu-id="137c0-122">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
