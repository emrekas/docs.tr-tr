---
title: UI Otomasyon Güvenliğine Genel Bakış
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: c74f770f917fc3b2a7d3a18c08270745dac68b12
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422430"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="f95bd-102">UI Otomasyon Güvenliğine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="f95bd-102">UI Automation Security Overview</span></span>

> [!NOTE]
> <span data-ttu-id="f95bd-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="f95bd-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f95bd-104">En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f95bd-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>

<span data-ttu-id="f95bd-105">Bu genel bakış için güvenlik modeli açıklanır [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] içinde [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f95bd-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span></span>

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a><span data-ttu-id="f95bd-106">Kullanıcı Hesabı Denetimi</span><span class="sxs-lookup"><span data-stu-id="f95bd-106">User Account Control</span></span>

<span data-ttu-id="f95bd-107">Security'dir önemli odak noktası, [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] ve yenilikleri arasında olması, daha yüksek ayrıcalıklar gerektiren uygulamalar ve hizmetler çalışmasını engellenme olmadan standart (yönetici olmayan) kullanıcı olarak çalıştırmak kullanıcılar için.</span><span class="sxs-lookup"><span data-stu-id="f95bd-107">Security is a major focus of [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>

<span data-ttu-id="f95bd-108">İçinde [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], çoğu uygulama standart veya bir yönetim belirteci ile sağlanır.</span><span class="sxs-lookup"><span data-stu-id="f95bd-108">In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="f95bd-109">Bir uygulama yönetim uygulaması tanımlanamaz, varsayılan olarak standart bir uygulama olarak başlatılır.</span><span class="sxs-lookup"><span data-stu-id="f95bd-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="f95bd-110">Bir uygulama gibi yönetici tanımlanan önce başlatılabilir, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] kullanıcıdan Uygulamayı yükseltilmiş çalıştırmak için bir onay ister.</span><span class="sxs-lookup"><span data-stu-id="f95bd-110">Before an application identified as administrative can be launched, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="f95bd-111">Bir uygulama veya yönetici kimlik bilgileri gerektiren sistem bileşeni çalıştırma izni isteklerini kadar Yöneticiler standart kullanıcı olarak çalıştığından, kullanıcı yerel Administrators grubunun üyesi olsa bile varsayılan olarak onay istemi görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="f95bd-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="f95bd-112">Daha yüksek ayrıcalıklar gerektiren görevler</span><span class="sxs-lookup"><span data-stu-id="f95bd-112">Tasks Requiring Higher Privileges</span></span>

<span data-ttu-id="f95bd-113">Bir kullanıcının yönetici ayrıcalıkları gerektiren bir görevi gerçekleştirmeye çalıştığında [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] kullanıcı devam etmek onay için soran bir iletişim kutusu sunar.</span><span class="sxs-lookup"><span data-stu-id="f95bd-113">When a user attempts to perform a task that requires administrative privileges, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="f95bd-114">Bu iletişim kutusunu, böylece kötü amaçlı yazılım, kullanıcı girişini benzetimi yapamaz çapraz işlem iletişiminden korunur.</span><span class="sxs-lookup"><span data-stu-id="f95bd-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="f95bd-115">Benzer şekilde, masaüstü oturum açma ekranında normalde başka işlemler tarafından erişilemez.</span><span class="sxs-lookup"><span data-stu-id="f95bd-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>

<span data-ttu-id="f95bd-116">UI Otomasyon istemcileri diğer işlemler, belki de daha yüksek bir ayrıcalık düzeyinde çalıştırmak bunlardan bazıları ile iletişim kurması gerekir.</span><span class="sxs-lookup"><span data-stu-id="f95bd-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="f95bd-117">İstemciler ayrıca diğer işlemler için normal olarak görünür olmayan sistem iletişim kutularına erişim gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="f95bd-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="f95bd-118">Bu nedenle, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] istemciler sistem tarafından güvenilir ve özel ayrıcalıklarıyla çalıştırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="f95bd-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>

<span data-ttu-id="f95bd-119">Daha yüksek bir ayrıcalık düzeyinde çalışan uygulamalarla iletişim kurmak için güvenilecek şekilde uygulamaların yeniden imzalanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="f95bd-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a><span data-ttu-id="f95bd-120">Bildirim dosyaları</span><span class="sxs-lookup"><span data-stu-id="f95bd-120">Manifest Files</span></span>

<span data-ttu-id="f95bd-121">Korumalı sistem kullanıcı Arabirimi erişim kazanmak için uygulamaları içeren bir bildirim dosyası ile oluşturulması gereken `uiAccess` özniteliğini `requestedExecutionLevel` , aşağıda gösterildiği gibi etiketleyin:</span><span class="sxs-lookup"><span data-stu-id="f95bd-121">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span></span>

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

<span data-ttu-id="f95bd-122">Değerini `level` bu kodu özniteliği, yalnızca bir örnek verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="f95bd-122">The value of the `level` attribute in this code is an example only.</span></span>

<span data-ttu-id="f95bd-123">`uiAccess` "varsayılan olarak; false" diğer bir deyişle, öznitelik belirtilmezse veya derleme için hiçbir bildirim ise, uygulama korumalı kullanıcı Arabirimi erişmesini mümkün olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="f95bd-123">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span></span>

<span data-ttu-id="f95bd-124">Daha fazla bilgi için [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] bkz: güvenlik, uygulamaları imzalamak ve derleme bildirimleri oluşturma [Geliştirici en iyi ve en az ayrıcalıklı bir ortamda uygulamalar için yönergeler](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480150(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="f95bd-124">For more information on [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] security, on signing applications, and on creating assembly manifests, see [Developer Best Practices and Guidelines for Applications in a Least Privileged Environment](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480150(v=msdn.10)).</span></span>
