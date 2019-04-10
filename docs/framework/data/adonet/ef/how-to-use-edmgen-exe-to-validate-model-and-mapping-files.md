---
title: 'Nasıl yapılır: EdmGen.exe kullanarak Model ve Eşleme Dosyalarını Doğrulama'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: ac278123e9b0927ba6b2ce07059561e7fbb3a898
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329278"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="b9457-102">Nasıl yapılır: EdmGen.exe kullanarak Model ve Eşleme Dosyalarını Doğrulama</span><span class="sxs-lookup"><span data-stu-id="b9457-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="b9457-103">Bu konu nasıl kullanılacağını gösterir [EDM Oluşturucu (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) model ve eşleme dosyalarını doğrulama aracı.</span><span class="sxs-lookup"><span data-stu-id="b9457-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="b9457-104">Daha fazla bilgi için [varlık veri modeli](../../../../../docs/framework/data/adonet/entity-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="b9457-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="b9457-105">Okul modeli EdmGen.exe kullanarak doğrulamak için</span><span class="sxs-lookup"><span data-stu-id="b9457-105">To validate the School model using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="b9457-106">School veritabanını oluşturun.</span><span class="sxs-lookup"><span data-stu-id="b9457-106">Create the School database.</span></span> <span data-ttu-id="b9457-107">Daha fazla bilgi için [School örnek veritabanını oluşturma](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b9457-107">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="b9457-108">Okul modeli oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b9457-108">Generate the School model.</span></span> <span data-ttu-id="b9457-109">Daha fazla bilgi için [nasıl yapılır: Model ve eşleme dosyalarını üretmek için Edmgen.exe'yi kullanın](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="b9457-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="b9457-110">Komut isteminde satır sonları olmadan aşağıdaki komutu yürütün:</span><span class="sxs-lookup"><span data-stu-id="b9457-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b9457-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b9457-111">See also</span></span>

- [<span data-ttu-id="b9457-112">Nasıl yapılır: El ile bir Entity Framework projesinin yapılandırma</span><span class="sxs-lookup"><span data-stu-id="b9457-112">How to: Manually Configure an Entity Framework Project</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [<span data-ttu-id="b9457-113">ADO.NET Varlık Veri Modeli Araçları</span><span class="sxs-lookup"><span data-stu-id="b9457-113">ADO.NET Entity Data Model Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [<span data-ttu-id="b9457-114">Nasıl yapılır: Sorgu performansını artırmak için görünümleri önceden oluştur</span><span class="sxs-lookup"><span data-stu-id="b9457-114">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [<span data-ttu-id="b9457-115">Nasıl yapılır: EdmGen.exe kullanarak Nesne Katmanı Kodu Oluşturma</span><span class="sxs-lookup"><span data-stu-id="b9457-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
