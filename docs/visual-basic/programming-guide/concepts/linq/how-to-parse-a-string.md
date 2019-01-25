---
title: 'Nasıl yapılır: Bir dize (Visual Basic) ayrıştırılamıyor'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 513a82cbed796be42eb8e531ec71221ef0ac267f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652455"
---
# <a name="how-to-parse-a-string-visual-basic"></a>Nasıl yapılır: Bir dize (Visual Basic) ayrıştırılamıyor
Bu konuda, bir XML ağacı oluşturma işlemi gösterilmektedir C#.  
  
## <a name="example"></a>Örnek  
 Kullanarak, Visual Basic'te bir dizeyi ayrıştırmak `XElement.Parse` yöntemi. Ancak, XML değişmez değerleri, XML değişmez değerleri, bir dizedeki XML Ayrıştırma olarak aynı performans cezaları gelen karşılaşmaz çünkü aşağıdaki kodda gösterildiği gibi kullanmak daha verimlidir.  
  
 XML değişmez değerlerini kullanarak, yalnızca kopyalayın ve Visual Basic programınızı XML dosyanızı yapıştırın.  
  
> [!NOTE]
>  Metni ayrıştırma veya bir metin dosyasından bir XML belgesi yüklenirken işlevsel oluşturma verimli değildir. Bir XML ağacı koddan başlatırken, metin ayrıştırmak üzere daha işlevsel oluşturma kullanmak için daha az işlemci zamanı alır.  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Ayrıştırma XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
