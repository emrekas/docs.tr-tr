---
title: 'Nasıl yapılır: FlowDocument Sütun Ayırıcı Öznitelikleri Kullanma'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 8693c8973442a5c6e65e64c5c66194c11bbff119
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363793"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="8a211-102">Nasıl yapılır: FlowDocument Sütun Ayırıcı Öznitelikleri Kullanma</span><span class="sxs-lookup"><span data-stu-id="8a211-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="8a211-103">Bu örnek, sütun ayırıcı özelliklerini kullanmayı gösterir. bir <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="8a211-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a211-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="8a211-104">Example</span></span>  
 <span data-ttu-id="8a211-105">Aşağıdaki örnekte tanımlayan bir <xref:System.Windows.Documents.FlowDocument>ve ayarlar <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, ve <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> öznitelikleri.</span><span class="sxs-lookup"><span data-stu-id="8a211-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="8a211-106"><xref:System.Windows.Documents.FlowDocument> Örnek içerik tek bir paragraf içerir.</span><span class="sxs-lookup"><span data-stu-id="8a211-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="8a211-107">Aşağıdaki şekil etkilerini gösterir <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, ve <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> işlenen özniteliklerinde <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="8a211-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="8a211-108">![Ekran: FlowDocument Sütun içi](./media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span><span class="sxs-lookup"><span data-stu-id="8a211-108">![Screenshot: FlowDocument Intra Column](./media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span></span>
