---
title: 'Nasıl yapılır: Yazdırma Kuyruklarının Alt Kümesini Numaralandırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: e1cbd9e7332a5e021e1cf9fba75f6d21ae01582b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558572"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Nasıl yapılır: Yazdırma Kuyruklarının Alt Kümesini Numaralandırma
Belirli özelliklere sahip yazıcıların listesini oluşturmak için olduğu yazıcıların şirket genelindeki bir ayar kümesini yönetme, bilgi teknolojisi (BT) uzmanları tarafından karşılaşılan yaygın bir durumdur. Bu işlev tarafından sağlanan <xref:System.Printing.PrintServer.GetPrintQueues%2A> yöntemi bir <xref:System.Printing.PrintServer> nesne ve <xref:System.Printing.EnumeratedPrintQueueTypes> sabit listesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, bir dizi listelemek istediğiniz yazdırma sıralarını özelliklerini belirten bayrakları oluşturarak kodu başlar. Bu örnekte, yazdırma sunucusunda yerel olarak yüklenir ve paylaşılan yazdırma sıraları için arıyoruz. <xref:System.Printing.EnumeratedPrintQueueTypes> Numaralandırma birçok diğer olanaklar sağlar.  
  
 Ardından kod oluşturur bir <xref:System.Printing.LocalPrintServer> türetilmiş bir sınıf nesnesi <xref:System.Printing.PrintServer>. Yerel yazdırma sunucusu, uygulamanın çalıştığı bilgisayardır.  
  
 Son önemli adım dizisine geçirmektir <xref:System.Printing.PrintServer.GetPrintQueues%2A> yöntemi.  
  
 Son olarak, sonuçları kullanıcıya gösterilir.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Bu örnek sağlayarak genişletilebiliyordu `foreach` her bir yazdırma sırası daha da incelemek döngü filtreleme. Örneğin, iki taraflı yazdırma döngüyle tarafından desteklemeyen yazıcıları her yazıcı sırasının ekran <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> yöntemi ve çift yönlü baskı varlığını test döndürülen değer.  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [WPF'deki Belgeler](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [Yazdırmaya Genel Bakış](../../../../docs/framework/wpf/advanced/printing-overview.md)
- [Microsoft XPS Belge Yazıcısı](https://go.microsoft.com/fwlink/?LinkId=147319)
