---
title: 'Nasıl yapılır: Nesne Serileştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: a587a132446a5f5d74b2d534b1ca3b93ccca1480
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928980"
---
# <a name="how-to-serialize-an-object"></a>Nasıl yapılır: Nesne Serileştirme
Bir nesneyi serileştirmek için önce sıralanabilir ve ortak özelliklerini ve alanları ayarlamak için olan nesne oluşturun. Bunu yapmak için, XML akışının, akış olarak veya dosya olarak depolanacağı aktarım biçimini belirlemelisiniz. Örneğin, XML akışının kalıcı bir biçimde kaydedilmesi gerekiyorsa, bir <xref:System.IO.FileStream> nesne oluşturun.  
  
> [!NOTE]
> XML serileştirme hakkında daha fazla örnek için bkz. [XML serileştirme örnekleri](../../../docs/standard/serialization/examples-of-xml-serialization.md).  
  
### <a name="to-serialize-an-object"></a>Bir nesneyi serileştirmek için  
  
1. Nesne oluşturun ve kendi ortak alanları ve özelliklerini ayarlayın.  
  
2. Nesnesinin türünü <xref:System.Xml.Serialization.XmlSerializer> kullanarak bir oluşturun. Daha fazla bilgi için bkz <xref:System.Xml.Serialization.XmlSerializer> . sınıf oluşturucuları.  
  
3. Bir xml akışı veya nesnenin ortak özelliklerinin ve alanlarının dosya gösterimini oluşturmak için yönteminiçağırın.<xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> Aşağıdaki örnek, bir dosya oluşturur.  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new   
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [XML Serileştirmeye Giriş](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Nasıl yapılır: Bir nesnenin serisini kaldırma](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
