---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 0463d1b489fdad5e6af2d8eb20a1e68c77f57b4d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254970"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="b4c67-102">\<döndürür > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4c67-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="b4c67-103">Özellik veya işlev dönüş değeri belirtir.</span><span class="sxs-lookup"><span data-stu-id="b4c67-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c67-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b4c67-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4c67-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b4c67-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="b4c67-106">Dönüş değeri bir açıklaması.</span><span class="sxs-lookup"><span data-stu-id="b4c67-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4c67-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b4c67-107">Remarks</span></span>  
 <span data-ttu-id="b4c67-108">Kullanım `<returns>` dönüş değeri tanımlamak bir yöntem bildiriminde yorum etiketi.</span><span class="sxs-lookup"><span data-stu-id="b4c67-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="b4c67-109">Derleme [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) işlem belgeleri açıklamaları için bir dosya için.</span><span class="sxs-lookup"><span data-stu-id="b4c67-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4c67-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="b4c67-110">Example</span></span>  
 <span data-ttu-id="b4c67-111">Bu örnekte `<returns>` ne açıklamak için etiket `DoesRecordExist` işlevi döndürür.</span><span class="sxs-lookup"><span data-stu-id="b4c67-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b4c67-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b4c67-112">See also</span></span>
- [<span data-ttu-id="b4c67-113">XML Açıklama Etiketleri</span><span class="sxs-lookup"><span data-stu-id="b4c67-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
