---
title: İş akışı tasarım deneyimini özelleştirme
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 87b49b025cfb27812933511b76c5a024cde4995a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680318"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="25561-102">İş akışı tasarım deneyimini özelleştirme</span><span class="sxs-lookup"><span data-stu-id="25561-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="25561-103">Özel etkinlikler tasarlama ve yeniden barındırma senaryolarında [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] içinde önemli ölçüde basitleştirilmiştir [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25561-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="25561-104">Geliştirme ve dağıtım artık daha kolay ve daha esnektir.</span><span class="sxs-lookup"><span data-stu-id="25561-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="25561-105">Anahtar altyapısal değişikliği, Windows Presentation Foundation (WPF) üzerine yeni etkinlik Tasarımcısı programlama modeli yerleşik olarak eklenmesidir.</span><span class="sxs-lookup"><span data-stu-id="25561-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="25561-106">Bu etkinlik tasarımcıları bildirimli olarak tanımlamanızı ve barındırma olanağı verir [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] diğer uygulamalarda ile karşılaştırmalı kolay.</span><span class="sxs-lookup"><span data-stu-id="25561-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="25561-107">Yeniden barındırma, IntelliSense ya da bir Basitleştirilmiş ifade etki alanı desteklemek için özel ifade düzenleyicisini geliştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="25561-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="25561-108">Windows Communication Foundation (WCF) ile tümleştirme, iş akışı hizmet kullanımı ile daha sorunsuz hale geldi.</span><span class="sxs-lookup"><span data-stu-id="25561-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="25561-109">Özel Etkinlik tasarımcıları ve modeli öğe ağacı, tasarım zamanı yeniden barındırılan iş akışı tasarımcıları deneyimler geliştirmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="25561-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="25561-110">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="25561-110">In This Section</span></span>

 [<span data-ttu-id="25561-111">Özel Etkinlik Tasarımcıları ve Şablonları Kullanma</span><span class="sxs-lookup"><span data-stu-id="25561-111">Using Custom Activity Designers and Templates</span></span>](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="25561-112">Yeni özel etkinlik tasarımcıları ve şablonları nasıl oluşturulacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="25561-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="25561-113">İş Akışı Tasarımcısını Yeniden Barındırma</span><span class="sxs-lookup"><span data-stu-id="25561-113">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)

 <span data-ttu-id="25561-114">Yeniden barındırma açıklar [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] Visual Studio ve doğrulama hataları görüntülemek nasıl dışında.</span><span class="sxs-lookup"><span data-stu-id="25561-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="25561-115">Özel İfade Düzenleyicisi Kullanma</span><span class="sxs-lookup"><span data-stu-id="25561-115">Using a Custom Expression Editor</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)

 <span data-ttu-id="25561-116">Visual Studio 2010 dışında yeniden barındırılan iş akışı tasarımcıları ile kullanılacak özel ifade düzenleyicisini uygulanacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="25561-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="25561-117">Başvuru</span><span class="sxs-lookup"><span data-stu-id="25561-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="25561-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="25561-118">See also</span></span>

- [<span data-ttu-id="25561-119">Windows Workflow Foundation’ı Genişletme</span><span class="sxs-lookup"><span data-stu-id="25561-119">Extending Windows Workflow Foundation</span></span>](../../../docs/framework/windows-workflow-foundation/extend.md)
- [<span data-ttu-id="25561-120">Tasarımcı</span><span class="sxs-lookup"><span data-stu-id="25561-120">Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer.md)
- [<span data-ttu-id="25561-121">Özel Etkinlik Tasarımcıları</span><span class="sxs-lookup"><span data-stu-id="25561-121">Custom Activity Designers</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)
- [<span data-ttu-id="25561-122">Tasarımcıyı Yeniden Barındırma</span><span class="sxs-lookup"><span data-stu-id="25561-122">Designer ReHosting</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)