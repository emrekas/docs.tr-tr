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
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Nasıl yapılır: Nesne Katmanı kodu üretmek için Edmgen.exe'yi kullanın
Bu konu nasıl kullanılacağını gösterir [EDM Oluşturucu (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) .csdl dosya tabanlı nesne katmanı kodu oluşturmak için aracı.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Okul modelin EdmGen.exe kullanarak bir Visual Basic projesi için nesne katmanı kodu oluşturmak için  
  
1.  School veritabanını oluşturun. Daha fazla bilgi için [School örnek veritabanını oluşturma](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Okul model oluşturmak veya School.csdl dosyasını alın. Daha fazla bilgi için [nasıl yapılır: Model ve eşleme dosyalarını üretmek için Edmgen.exe'yi kullanın](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Komut isteminde satır sonları olmadan aşağıdaki komutu yürütün:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>Okul modelin EdmGen.exe kullanarak bir C# projesi için nesne katmanı kodu oluşturmak için  
  
1.  School veritabanını oluşturun. Daha fazla bilgi için [School örnek veritabanını oluşturma](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Okul model oluşturmak veya School.csdl dosyasını alın. Daha fazla bilgi için [nasıl yapılır: Model ve eşleme dosyalarını üretmek için Edmgen.exe'yi kullanın](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Komut isteminde satır sonları olmadan aşağıdaki komutu yürütün:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Modelleme ve Eşleme](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [Nasıl yapılır: El ile bir Entity Framework projesinin yapılandırma](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)
- [ADO.NET varlık veri modeli araçları](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
- [Nasıl yapılır: Sorgu performansını artırmak için görünümleri önceden oluştur](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)
- [Nasıl yapılır: Model ve eşleme dosyalarını üretmek için Edmgen.exe'yi kullanın](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
