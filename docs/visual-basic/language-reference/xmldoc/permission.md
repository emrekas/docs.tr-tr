---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: a8914e6d8fbce3e99ff92d9e4968e85a0f0ad7d5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263647"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="67f6d-102">\<izni > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67f6d-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="67f6d-103">Üye için gerekli izni belirtir.</span><span class="sxs-lookup"><span data-stu-id="67f6d-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f6d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="67f6d-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67f6d-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="67f6d-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="67f6d-106">Bir üye veya geçerli derleme ortamdan çağrılacak kullanılabilir alan başvuru.</span><span class="sxs-lookup"><span data-stu-id="67f6d-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="67f6d-107">Derleyici belirli kod öğesi var. çevirir olup olmadığını denetler ve `member` kurallı öğesi adı ' % s'çıkış XML dosyası.</span><span class="sxs-lookup"><span data-stu-id="67f6d-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="67f6d-108">İçine `member` tırnak işaretleri ("").</span><span class="sxs-lookup"><span data-stu-id="67f6d-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="67f6d-109">Üye erişimi açıklaması.</span><span class="sxs-lookup"><span data-stu-id="67f6d-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67f6d-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="67f6d-110">Remarks</span></span>  
 <span data-ttu-id="67f6d-111">Kullanım `<permission>` üyenin erişim belgelemek için etiket.</span><span class="sxs-lookup"><span data-stu-id="67f6d-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="67f6d-112">Kullanım <xref:System.Security.PermissionSet> sınıfın üyesi erişimi belirtin.</span><span class="sxs-lookup"><span data-stu-id="67f6d-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="67f6d-113">Derleme [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) işlem belgeleri açıklamaları için bir dosya için.</span><span class="sxs-lookup"><span data-stu-id="67f6d-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67f6d-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="67f6d-114">Example</span></span>  
 <span data-ttu-id="67f6d-115">Bu örnekte `<permission>` açıklayan için etiket <xref:System.Security.Permissions.FileIOPermission> gerektirdiği `ReadFile` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="67f6d-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="67f6d-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="67f6d-116">See also</span></span>
- [<span data-ttu-id="67f6d-117">XML Açıklama Etiketleri</span><span class="sxs-lookup"><span data-stu-id="67f6d-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
