---
title: "Nasıl yapılır: Nesne Katmanı kodu üretmek için Edmgen.exe'yi kullanın"
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 63542866441cb347362e64b08b5de11bde19d50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654574"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="7b0dc-102">Nasıl yapılır: Nesne Katmanı kodu üretmek için Edmgen.exe'yi kullanın</span><span class="sxs-lookup"><span data-stu-id="7b0dc-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="7b0dc-103">Bu konu nasıl kullanılacağını gösterir [EDM Oluşturucu (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) .csdl dosya tabanlı nesne katmanı kodu oluşturmak için aracı.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="7b0dc-104">Okul modelin EdmGen.exe kullanarak bir Visual Basic projesi için nesne katmanı kodu oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="7b0dc-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="7b0dc-105">School veritabanını oluşturun.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-105">Create the School database.</span></span> <span data-ttu-id="7b0dc-106">Daha fazla bilgi için [School örnek veritabanını oluşturma](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="7b0dc-106">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="7b0dc-107">Okul model oluşturmak veya School.csdl dosyasını alın.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="7b0dc-108">Daha fazla bilgi için [nasıl yapılır: Model ve eşleme dosyalarını üretmek için Edmgen.exe'yi kullanın](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="7b0dc-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="7b0dc-109">Komut isteminde satır sonları olmadan aşağıdaki komutu yürütün:</span><span class="sxs-lookup"><span data-stu-id="7b0dc-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="7b0dc-110">Okul modelin EdmGen.exe kullanarak bir C# projesi için nesne katmanı kodu oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="7b0dc-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="7b0dc-111">School veritabanını oluşturun.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-111">Create the School database.</span></span> <span data-ttu-id="7b0dc-112">Daha fazla bilgi için [School örnek veritabanını oluşturma](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="7b0dc-112">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="7b0dc-113">Okul model oluşturmak veya School.csdl dosyasını alın.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="7b0dc-114">Daha fazla bilgi için [nasıl yapılır: Model ve eşleme dosyalarını üretmek için Edmgen.exe'yi kullanın](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="7b0dc-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="7b0dc-115">Komut isteminde satır sonları olmadan aşağıdaki komutu yürütün:</span><span class="sxs-lookup"><span data-stu-id="7b0dc-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7b0dc-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-116">See also</span></span>
- [<span data-ttu-id="7b0dc-117">Modelleme ve Eşleme</span><span class="sxs-lookup"><span data-stu-id="7b0dc-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="7b0dc-118">Nasıl yapılır: El ile bir Entity Framework projesinin yapılandırma</span><span class="sxs-lookup"><span data-stu-id="7b0dc-118">How to: Manually Configure an Entity Framework Project</span></span>](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)
- [<span data-ttu-id="7b0dc-119">ADO.NET varlık veri modeli araçları</span><span class="sxs-lookup"><span data-stu-id="7b0dc-119">ADO.NET Entity Data Model  Tools</span></span>](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
- [<span data-ttu-id="7b0dc-120">Nasıl yapılır: Sorgu performansını artırmak için görünümleri önceden oluştur</span><span class="sxs-lookup"><span data-stu-id="7b0dc-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)
- [<span data-ttu-id="7b0dc-121">Nasıl yapılır: Model ve eşleme dosyalarını üretmek için Edmgen.exe'yi kullanın</span><span class="sxs-lookup"><span data-stu-id="7b0dc-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
