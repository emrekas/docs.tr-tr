---
title: 'Nasıl yapılır: Aynı türde birden fazla belirteç kullanma'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
ms.openlocfilehash: 40fc95c905f8923b8aaf2c97fb9dc2b937dfb06f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691356"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a>Nasıl yapılır: Aynı türde birden fazla belirteç kullanma
-   İçinde [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, belirtilen her türlü istemci iletisi yalnızca kapsanan bir belirteç. Artık istemci iletileri birden çok belirteç türü içerebilir. Bu konuda, bir istemci iletiye aynı türde birden çok belirteç gösterilmektedir.  
  
-   Bu şekilde bir hizmet yapılandıramazsınız Not: hizmet yalnızca bir destekleme belirteci içerebilir.  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a>Aynı türde birden fazla belirteç kullanmak için  
  
1.  Doldurulacak bir boş bağlama öğesi koleksiyonu oluşturun.  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  Oluşturma bir <xref:System.ServiceModel.Channels.SecurityBindingElement> çağırarak <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  Oluşturma bir <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> koleksiyonu.  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  SAML belirteçlerini koleksiyona ekleyin.  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  Koleksiyona ekleme <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  Bağlama öğeleri bağlama öğesi koleksiyona ekleyin.  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  Bağlama öğesi koleksiyonundan oluşturulan yeni bir özel bağlama döndürür.  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a>Örnek  
 Yukarıdaki yordamı tarafından tanımlanan tüm yöntemi verilmiştir.  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Güvenlik mimarisi](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
