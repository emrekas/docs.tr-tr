---
title: 'Nasıl yapılır: Bir denetimi görüntüleme araç kutusu öğelerini Seç iletişim kutusu'
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 56dad16b7a0bd8f0e7423b4a70e7173578150cbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520457"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="80189-102">Nasıl yapılır: Bir denetimi görüntüleme araç kutusu öğelerini Seç iletişim kutusu</span><span class="sxs-lookup"><span data-stu-id="80189-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="80189-103">Geliştirin ve denetimleri dağıtmak gibi bu denetimlerin görünmesini isteyebilirsiniz **araç kutusu öğelerini Seç** , sağ tıkladığınızda görüntülenen iletişim kutusunda, **araç kutusu** seçip  **Öğeleri seçmek**.</span><span class="sxs-lookup"><span data-stu-id="80189-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="80189-104">Denetiminiz AssemblyFoldersEx kayıt yordamı kullanarak bu iletişim kutusunda görüntülenecek etkinleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80189-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="80189-105">Denetiminiz araç kutusu öğelerini Seç iletişim kutusunda görüntülemek için</span><span class="sxs-lookup"><span data-stu-id="80189-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="80189-106">Denetim derlemeyi genel derleme önbelleğine yükleyin.</span><span class="sxs-lookup"><span data-stu-id="80189-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="80189-107">Daha fazla bilgi için [nasıl yapılır: Bir derlemeyi genel derleme önbelleğine yükleme](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="80189-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="80189-108">-veya-</span><span class="sxs-lookup"><span data-stu-id="80189-108">-or-</span></span>  
  
-   <span data-ttu-id="80189-109">Denetim ve onun ilişkili tasarım zamanı derlemeleri AssemblyFoldersEx kayıt yordamı kullanarak kaydedin.</span><span class="sxs-lookup"><span data-stu-id="80189-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="80189-110">AssemblyFoldersEx, üçüncü taraf satıcılarla destekledikleri framework'ün her sürümü için yollar depoladığınız bir kayıt defteri konumdur.</span><span class="sxs-lookup"><span data-stu-id="80189-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="80189-111">Tasarım zamanı çözümleme başvuru derlemelerini bulmak için bu kayıt defteri konumuna bakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80189-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="80189-112">Kayıt betiği denetimleri araç kutusunda görünmesini istediğiniz belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80189-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="80189-113">Daha fazla bilgi için [bir özel denetim ve tasarım zamanı derlemeleri (Visual Studio 2013) dağıtma](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span><span class="sxs-lookup"><span data-stu-id="80189-113">For more information, see [Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80189-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="80189-114">See also</span></span>
- [<span data-ttu-id="80189-115">Araç kutusu öğelerini Seç iletişim kutusu (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="80189-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)
- [<span data-ttu-id="80189-116">Özel bir denetim ve tasarım zamanı derlemeleri (Visual Studio 2013) dağıtma</span><span class="sxs-lookup"><span data-stu-id="80189-116">Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)</span></span>](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)
- [<span data-ttu-id="80189-117">Tasarım Zamanında Windows Forms Denetimleri Geliştirme</span><span class="sxs-lookup"><span data-stu-id="80189-117">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="80189-118">Nasıl yapılır: Bir derlemeyi genel derleme önbelleğine yükleme</span><span class="sxs-lookup"><span data-stu-id="80189-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)
- [<span data-ttu-id="80189-119">İzlenecek yol: Otomatik olarak araç kutusunu özel bileşenlerle doldurma</span><span class="sxs-lookup"><span data-stu-id="80189-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
