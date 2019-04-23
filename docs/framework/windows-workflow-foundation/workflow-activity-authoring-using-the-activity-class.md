---
title: Etkinlik sınıfını kullanarak iş akışı etkinliği yazma
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 1bec10b6ae9fb43319cfb6acbf59133e1acca09c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770781"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="12656-102">Etkinlik sınıfını kullanarak iş akışı etkinliği yazma</span><span class="sxs-lookup"><span data-stu-id="12656-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="12656-103">Windows Workflow Foundation (WF) kullanarak bir etkinlik oluşturmak için en temel yolu [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] öğesinden devralınan bir sınıf oluşturmak <xref:System.Activities.Activity> işlevselliği birleştirerek özel oluşturan etkinlikler veya etkinlikten [yerleşik Etkinlik Kitaplığı](net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="12656-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="12656-104">Bu konu, iki ileti konsola bir etkinlik oluşturma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="12656-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="12656-105">Etkinlik Tasarımcısı'nı kullanarak özel bir etkinlik oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="12656-105">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="12656-106">Visual Studio 2012'yi açın.</span><span class="sxs-lookup"><span data-stu-id="12656-106">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="12656-107">Dosya, yeni, proje'i seçin.</span><span class="sxs-lookup"><span data-stu-id="12656-107">Select File, New, Project.</span></span> <span data-ttu-id="12656-108">Seçin **Workflow 4.0** altında **Visual C#** içinde **proje türleri** penceresi ve select **v2010** düğümü.</span><span class="sxs-lookup"><span data-stu-id="12656-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="12656-109">Seçin **etkinlik Kitaplığı** içinde **şablonları** penceresi.</span><span class="sxs-lookup"><span data-stu-id="12656-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="12656-110">Yeni Proje HelloActivity adı.</span><span class="sxs-lookup"><span data-stu-id="12656-110">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="12656-111">Yeni Etkinlik açın.</span><span class="sxs-lookup"><span data-stu-id="12656-111">Open the new activity.</span></span>  <span data-ttu-id="12656-112">Sürükleme bir <xref:System.Activities.Statements.Sequence> Tasarımcı yüzeyine araç kutusundan.</span><span class="sxs-lookup"><span data-stu-id="12656-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="12656-113">Sürükleme bir <xref:System.Activities.Statements.WriteLine> etkinliğini <xref:System.Activities.Statements.Sequence> etkinlik.</span><span class="sxs-lookup"><span data-stu-id="12656-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="12656-114">Girin `"Hello World"` (teklifler ile) içine **metin** alan.</span><span class="sxs-lookup"><span data-stu-id="12656-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="12656-115">İkinci sürükleyin <xref:System.Activities.Statements.WriteLine> etkinliğini <xref:System.Activities.Statements.Sequence> ilki aşağıda bir etkinlik.</span><span class="sxs-lookup"><span data-stu-id="12656-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="12656-116">Girin `"Goodbye"` (teklifler ile) içine **metin** alan.</span><span class="sxs-lookup"><span data-stu-id="12656-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
