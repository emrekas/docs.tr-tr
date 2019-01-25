---
title: WCF Güvenliğinde Şifreleme Çevikliği
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: a97f0b908d3c4d2e14fb55ec21371322dc740e47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668905"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="f16e5-102">WCF Güvenliğinde Şifreleme Çevikliği</span><span class="sxs-lookup"><span data-stu-id="f16e5-102">Cryptographic Agility in WCF Security</span></span>
<span data-ttu-id="f16e5-103">Bu örnek, bir Windows Communication Foundation (WCF) istemci ve hizmet şifreleme ve Çevik bir uygulama sağlamak için bir standart/özel algoritması belirtin gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="f16e5-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="f16e5-104">Örnek, aşağıdaki projelerin oluşur:</span><span class="sxs-lookup"><span data-stu-id="f16e5-104">The sample is composed of the following projects:</span></span>

 <span data-ttu-id="f16e5-105">Bu, uygulayan şirket içinde barındırılan bir WCF hizmeti hizmet `ICalculator` arabirim ve uç noktayı kullanarak güvenliğini sağlar <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> güvenli oturum ve güvenilir oturum devre dışı.</span><span class="sxs-lookup"><span data-stu-id="f16e5-105">Service This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> with secure session and reliable session disabled.</span></span> <span data-ttu-id="f16e5-106">Özel bir hizmet tanımlar `SecurityAlgorithmSuite` ileti güvenliği için kullanılacak şifreleme algoritmalarını belirlemek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="f16e5-106">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

 <span data-ttu-id="f16e5-107">İstemci başarılı kimlik doğrulamasından sonra hizmete erişen bir WCFclient budur.</span><span class="sxs-lookup"><span data-stu-id="f16e5-107">Client This is a WCFclient that accesses the service after successful authentication.</span></span> <span data-ttu-id="f16e5-108">Tarafından sunulan işlemleri çağırır `ICalculator` arabirim ve hizmet tarafından uygulanır.</span><span class="sxs-lookup"><span data-stu-id="f16e5-108">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="f16e5-109">İstemci Ayrıca, aynı özel tanımlar `SecurityAlgorithmSuite` ileti güvenliği için kullanılacak şifreleme algoritmalarını belirlemek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="f16e5-109">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

### <a name="to-use-this-sample"></a><span data-ttu-id="f16e5-110">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="f16e5-110">To use this sample</span></span>

1.  <span data-ttu-id="f16e5-111">Visual Studio 2012'de CryptoAgility.sln çözümü açın.</span><span class="sxs-lookup"><span data-stu-id="f16e5-111">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2.  <span data-ttu-id="f16e5-112">Çözümü derlemek için CTRL + SHIFT + B tuşlarına basın.</span><span class="sxs-lookup"><span data-stu-id="f16e5-112">Press CTRL+SHIFT+B to build the solution.</span></span>

3.  <span data-ttu-id="f16e5-113">Açık [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] \WCF\Basic\Security\CryptoAgility\Service\bin dizine gidin ve service.exe sağ tıklatıp seçerek service.exe dosyasını yönetici ayrıcalıklarıyla çalıştırın **yönetici olarak çalıştır**.</span><span class="sxs-lookup"><span data-stu-id="f16e5-113">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4.  <span data-ttu-id="f16e5-114">\WCF\Basic\Security\CryptoAgility\Client\bin dizine gidin ve normalde client.exe dosyasını çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="f16e5-114">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="f16e5-115">Örnekler, makinenizde zaten yüklü.</span><span class="sxs-lookup"><span data-stu-id="f16e5-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f16e5-116">Devam etmeden önce şu (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="f16e5-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f16e5-117">Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="f16e5-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f16e5-118">Bu örnek, şu dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="f16e5-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a><span data-ttu-id="f16e5-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f16e5-119">See also</span></span>
- [<span data-ttu-id="f16e5-120">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="f16e5-120">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
