---
title: XamlName Dilbilgisi
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 642ca16142bdfe78a40ddf4e6a3a79ce6a8a4985
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58031608"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="f0e7f-102">XamlName Dilbilgisi</span><span class="sxs-lookup"><span data-stu-id="f0e7f-102">XamlName Grammar</span></span>
<span data-ttu-id="f0e7f-103">XamlName dilbilgisi kolaylık olması için burada tekrar üretilmektedir XAML dil belirtimi [MS-XAML], tanımlanan belirli bir dil bilgisi olur.</span><span class="sxs-lookup"><span data-stu-id="f0e7f-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="f0e7f-104">XAML belirtiminden</span><span class="sxs-lookup"><span data-stu-id="f0e7f-104">From the XAML Specification</span></span>  
 <span data-ttu-id="f0e7f-105">[MS-XAML] belirtimi türleri ve özellikler için kullanılan yasal sembolik tanımlayıcıları kümesini tanımlamak için XamlName dilbilgisi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="f0e7f-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="f0e7f-106">XamlName aşağıdaki dilbilgisi uymalıdır türü olan değerleri dize:</span><span class="sxs-lookup"><span data-stu-id="f0e7f-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="f0e7f-107">Aşağıdaki genel kategori değerleri Unicode karakter veritabanında tanımlanan varsayılır</span><span class="sxs-lookup"><span data-stu-id="f0e7f-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 <span data-ttu-id="f0e7f-108">İkinci özelliği için kullanılan DottedXamlName dilbilgisi, XAML tanımlar ve olay uygun başvuruları ve üyeleri için ve ayrıca bağlı.</span><span class="sxs-lookup"><span data-stu-id="f0e7f-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="f0e7f-109">Daha fazla bilgi için <xref:System.Windows.DependencyProperty> ve [XAML genel bakış (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="f0e7f-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="f0e7f-110">DottedXamlName aşağıdaki dilbilgisi uymalıdır türü olan değerleri dize:</span><span class="sxs-lookup"><span data-stu-id="f0e7f-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="f0e7f-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f0e7f-111">Remarks</span></span>  
 <span data-ttu-id="f0e7f-112">Tam belirtimi için bkz: [ \[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="f0e7f-112">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
