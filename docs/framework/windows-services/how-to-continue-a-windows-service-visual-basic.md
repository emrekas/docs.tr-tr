---
title: 'Nasıl yapılır: Windows Hizmetini Devam Ettirme (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
ms.openlocfilehash: c9a783c0e7df39381ad1d9a8fedd7419605fd241
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935551"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="7612c-102">Nasıl yapılır: Windows Hizmetini Devam Ettirme (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7612c-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="7612c-103">Bu örnek, yerel <xref:System.ServiceProcess.ServiceController> bilgisayarda IIS Yönetim hizmetine devam etmek için bileşenini kullanır.</span><span class="sxs-lookup"><span data-stu-id="7612c-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7612c-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="7612c-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="7612c-105">Bu kod örneği, bir IntelliSense kod parçacığı olarak da kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="7612c-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="7612c-106">Kod parçacığı seçicide, Windows **Işletim sistemi > Windows Hizmetleri**' nde bulunur.</span><span class="sxs-lookup"><span data-stu-id="7612c-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="7612c-107">Daha fazla bilgi için [kod parçacıkları](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="7612c-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7612c-108">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="7612c-108">Compiling the Code</span></span>  
 <span data-ttu-id="7612c-109">Bu örnek şunları gerektirir:</span><span class="sxs-lookup"><span data-stu-id="7612c-109">This example requires:</span></span>  
  
- <span data-ttu-id="7612c-110">System. ServiceProcess. dll dosyasına bir proje başvurusu.</span><span class="sxs-lookup"><span data-stu-id="7612c-110">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="7612c-111"><xref:System.ServiceProcess> Ad alanının üyelerine erişin.</span><span class="sxs-lookup"><span data-stu-id="7612c-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="7612c-112">Kodunuzda üye `Imports` adlarını tam olarak nitedıysanız bir ifade ekleyin.</span><span class="sxs-lookup"><span data-stu-id="7612c-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="7612c-113">Daha fazla bilgi için bkz. [Imports açıklaması (.net ad alanı ve türü)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="7612c-113">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7612c-114">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="7612c-114">Robust Programming</span></span>  
 <span data-ttu-id="7612c-115"><xref:System.ServiceProcess.ServiceController> Sınıfının özelliği, varsayılan olarak yerel bilgisayardır. <xref:System.ServiceProcess.ServiceController.MachineName%2A></span><span class="sxs-lookup"><span data-stu-id="7612c-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="7612c-116">Başka bir bilgisayardaki Windows hizmetlerine başvurmak için, <xref:System.ServiceProcess.ServiceController.MachineName%2A> özelliği bu bilgisayarın adıyla değiştirin.</span><span class="sxs-lookup"><span data-stu-id="7612c-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="7612c-117">Hizmet denetleyicisi <xref:System.ServiceProcess.ServiceController.Continue%2A> <xref:System.ServiceProcess.ServiceControllerStatus.Paused>durumu olana kadar bir hizmette yöntemi çağrılamaz.</span><span class="sxs-lookup"><span data-stu-id="7612c-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="7612c-118">Aşağıdaki koşullar özel bir duruma neden olabilir:</span><span class="sxs-lookup"><span data-stu-id="7612c-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="7612c-119">Hizmet devam ettirilemiyor.</span><span class="sxs-lookup"><span data-stu-id="7612c-119">The service cannot be resumed.</span></span> <span data-ttu-id="7612c-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="7612c-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="7612c-121">Sistem API 'sine erişirken bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="7612c-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="7612c-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="7612c-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7612c-123">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="7612c-123">.NET Framework Security</span></span>  
 <span data-ttu-id="7612c-124">Bilgisayardaki hizmetlerin denetimi, <xref:System.ServiceProcess.ServiceControllerPermissionAccess> <xref:System.ServiceProcess.ServiceControllerPermission> sınıftaki izinleri ayarlamak için sabit listesi kullanılarak kısıtlanabilir.</span><span class="sxs-lookup"><span data-stu-id="7612c-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="7612c-125">Sınıfında<xref:System.Security.Permissions.SecurityPermission> izinleri ayarlamak için <xref:System.Security.Permissions.PermissionState> numaralandırma kullanılarak hizmet bilgilerine erişim kısıtlanabilir.</span><span class="sxs-lookup"><span data-stu-id="7612c-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7612c-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7612c-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [<span data-ttu-id="7612c-127">Nasıl yapılır: Bir Windows hizmetini duraklatma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7612c-127">How to: Pause a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
