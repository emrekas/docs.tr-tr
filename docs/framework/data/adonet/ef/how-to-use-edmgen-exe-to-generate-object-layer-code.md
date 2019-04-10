---
title: 'Nasıl yapılır: EdmGen.exe kullanarak Nesne Katmanı Kodu Oluşturma'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 8a39027ee6a5647bbd645f5a38e35d61f7ebbd8e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333411"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="4d6b3-102">Nasıl yapılır: EdmGen.exe kullanarak Nesne Katmanı Kodu Oluşturma</span><span class="sxs-lookup"><span data-stu-id="4d6b3-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="4d6b3-103">Bu konu nasıl kullanılacağını gösterir [EDM Oluşturucu (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) .csdl dosya tabanlı nesne katmanı kodu oluşturmak için aracı.</span><span class="sxs-lookup"><span data-stu-id="4d6b3-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="4d6b3-104">Okul modelin EdmGen.exe kullanarak bir Visual Basic projesi için nesne katmanı kodu oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="4d6b3-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="4d6b3-105">School veritabanını oluşturun.</span><span class="sxs-lookup"><span data-stu-id="4d6b3-105">Create the School database.</span></span> <span data-ttu-id="4d6b3-106">Daha fazla bilgi için [School örnek veritabanını oluşturma](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4d6b3-106">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="4d6b3-107">Okul model oluşturmak veya School.csdl dosyasını alın.</span><span class="sxs-lookup"><span data-stu-id="4d6b3-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="4d6b3-108">Daha fazla bilgi için [nasıl yapılır: Model ve eşleme dosyalarını üretmek için Edmgen.exe'yi kullanın](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="4d6b3-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="4d6b3-109">Komut isteminde satır sonları olmadan aşağıdaki komutu yürütün:</span><span class="sxs-lookup"><span data-stu-id="4d6b3-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="4d6b3-110">Okul modelin EdmGen.exe kullanarak bir C# projesi için nesne katmanı kodu oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="4d6b3-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="4d6b3-111">School veritabanını oluşturun.</span><span class="sxs-lookup"><span data-stu-id="4d6b3-111">Create the School database.</span></span> <span data-ttu-id="4d6b3-112">Daha fazla bilgi için [School örnek veritabanını oluşturma](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4d6b3-112">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="4d6b3-113">Okul model oluşturmak veya School.csdl dosyasını alın.</span><span class="sxs-lookup"><span data-stu-id="4d6b3-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="4d6b3-114">Daha fazla bilgi için [nasıl yapılır: Model ve eşleme dosyalarını üretmek için Edmgen.exe'yi kullanın](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="4d6b3-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="4d6b3-115">Komut isteminde satır sonları olmadan aşağıdaki komutu yürütün:</span><span class="sxs-lookup"><span data-stu-id="4d6b3-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4d6b3-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4d6b3-116">See also</span></span>

- [<span data-ttu-id="4d6b3-117">Modelleme ve Eşleme</span><span class="sxs-lookup"><span data-stu-id="4d6b3-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="4d6b3-118">Nasıl yapılır: El ile bir Entity Framework projesinin yapılandırma</span><span class="sxs-lookup"><span data-stu-id="4d6b3-118">How to: Manually Configure an Entity Framework Project</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [<span data-ttu-id="4d6b3-119">ADO.NET varlık veri modeli araçları</span><span class="sxs-lookup"><span data-stu-id="4d6b3-119">ADO.NET Entity Data Model  Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [<span data-ttu-id="4d6b3-120">Nasıl yapılır: Sorgu performansını artırmak için görünümleri önceden oluştur</span><span class="sxs-lookup"><span data-stu-id="4d6b3-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [<span data-ttu-id="4d6b3-121">Nasıl yapılır: EdmGen.exe kullanarak Model ve Eşleme Dosyaları Oluşturma</span><span class="sxs-lookup"><span data-stu-id="4d6b3-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
