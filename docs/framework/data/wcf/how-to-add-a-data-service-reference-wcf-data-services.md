---
title: 'Nasıl yapılır: Bir veri hizmeti başvurusu (WCF Veri Hizmetleri) ekleme'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: fc1786e1c6102c702374989253cd3ce23e3f7b54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765537"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="cc953-102">Nasıl yapılır: Bir veri hizmeti başvurusu (WCF Data Services) ekleme</span><span class="sxs-lookup"><span data-stu-id="cc953-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="cc953-103">Kullanabileceğiniz **hizmet Başvurusu Ekle** WCF Veri Hizmetleri için bir başvuru eklemek için Visual Studio'da iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="cc953-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="cc953-104">Bu, Visual Studio'da geliştirdiğiniz bir istemci uygulamasında veri hizmeti daha kolay erişmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="cc953-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="cc953-105">Bu yordamı tamamladıktan sonra veri sınıfları, veri hizmetinden alınan meta verileri oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="cc953-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="cc953-106">Daha fazla bilgi için [veri hizmeti istemci kitaplığı oluşturma](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cc953-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="cc953-107">Bir veri hizmeti başvurusu ekleme</span><span class="sxs-lookup"><span data-stu-id="cc953-107">Add a data service reference</span></span>

1. <span data-ttu-id="cc953-108">(İsteğe bağlı) Veri Hizmeti çözümün bir parçası değil ve çalışır durumda değil, veri hizmeti başlatın ve veri hizmeti URI'sini not edin.</span><span class="sxs-lookup"><span data-stu-id="cc953-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="cc953-109">Visual Studio içinde **Çözüm Gezgini**, istemci projeye sağ tıklayın ve ardından **Ekle** > **hizmet başvurusu**.</span><span class="sxs-lookup"><span data-stu-id="cc953-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="cc953-110">Veri Hizmeti geçerli çözümün bir parçası ise, tıklayın **bulma**.</span><span class="sxs-lookup"><span data-stu-id="cc953-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="cc953-111">-veya-</span><span class="sxs-lookup"><span data-stu-id="cc953-111">-or-</span></span>

     <span data-ttu-id="cc953-112">İçinde **adresi** metin kutusuna, veri hizmetinin temel URL'sini yazın gibi `http://localhost:1234/Northwind.svc`ve ardından **Git**.</span><span class="sxs-lookup"><span data-stu-id="cc953-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="cc953-113">**Tamam**’ı seçin.</span><span class="sxs-lookup"><span data-stu-id="cc953-113">Select **OK**.</span></span>

     <span data-ttu-id="cc953-114">Erişebilir ve veri hizmeti kaynaklarına ile etkileşimli veri sınıfları içeren yeni bir kod dosyası projeye eklenir.</span><span class="sxs-lookup"><span data-stu-id="cc953-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc953-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cc953-115">See also</span></span>

- [<span data-ttu-id="cc953-116">Hızlı başlangıç</span><span class="sxs-lookup"><span data-stu-id="cc953-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)