---
title: XAML’den Yükleme
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: 5a3b3673812c0b5500a13ae9ce79ce8206aa4834
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772862"
---
# <a name="load-from-xaml"></a><span data-ttu-id="e5582-102">XAML’den Yükleme</span><span class="sxs-lookup"><span data-stu-id="e5582-102">Load From XAML</span></span>
<span data-ttu-id="e5582-103">Bu örnek nasıl XamlBuildTask aracı çalıştırmak zorunda kalmadan bir XAML iş akışı dinamik olarak yükleneceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="e5582-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="e5582-104">Bunun yerine, örnek çağırır <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e5582-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="e5582-105">Örnek kullanarak XAML iş akışları yükleyen bir Windows Presentation Foundation (WPF) istemci uygulamasıdır <xref:System.Activities.XamlIntegration.ActivityXamlServices> sınıfı ve bunları yürütür.</span><span class="sxs-lookup"><span data-stu-id="e5582-105">The sample is a Windows Presentation Foundation (WPF) client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="e5582-106">Kullanılarak yüklenmiş sonra <xref:System.Activities.XamlIntegration.ActivityXamlServices> sınıfı, bir <xref:System.Activities.DynamicActivity%601> , yürütülebilir döndürülür.</span><span class="sxs-lookup"><span data-stu-id="e5582-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="e5582-107">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="e5582-107">To use this sample</span></span>

1. <span data-ttu-id="e5582-108">Visual Studio 2010 kullanarak LoadFromXAML.sln çözüm dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="e5582-108">Using Visual Studio 2010, open the LoadFromXAML.sln solution file.</span></span>

2. <span data-ttu-id="e5582-109">Çözümü derlemek için CTRL + SHIFT + B tuşlarına basın.</span><span class="sxs-lookup"><span data-stu-id="e5582-109">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="e5582-110">Çözümü çalıştırmak için CTRL + F5 tuşlarına basın.</span><span class="sxs-lookup"><span data-stu-id="e5582-110">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="e5582-111">Örnekler, makinenizde zaten yüklü.</span><span class="sxs-lookup"><span data-stu-id="e5582-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e5582-112">Devam etmeden önce şu (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="e5582-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e5582-113">Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="e5582-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e5582-114">Bu örnek, şu dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="e5582-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`