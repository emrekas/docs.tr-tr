---
title: "'<elementname>' eski (Visual Basic Uyarısı)"
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: d7d3d86f89ef3b76e958707dd0be2dce8a3e9bf2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64659814"
---
# <a name="elementname-is-obsolete-visual-basic-warning"></a><span data-ttu-id="7e862-102">'\<elementname >' eski (Visual Basic uyarısı)</span><span class="sxs-lookup"><span data-stu-id="7e862-102">'\<elementname>' is obsolete (Visual Basic Warning)</span></span>
<span data-ttu-id="7e862-103">Bir ifade ile işaretlenmiş bir programlama öğesi erişmeye <xref:System.ObsoleteAttribute> özniteliğini ve bir uyarı olarak değerlendirilecek yönergesi.</span><span class="sxs-lookup"><span data-stu-id="7e862-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>  
  
 <span data-ttu-id="7e862-104">Herhangi bir programlama öğesi artık uygulayarak kullanımda olarak işaretleyebilirsiniz <xref:System.ObsoleteAttribute> ona.</span><span class="sxs-lookup"><span data-stu-id="7e862-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="7e862-105">Bunu yaparsanız özniteliğin ayarlayabilirsiniz <xref:System.ObsoleteAttribute.IsError%2A> ya da özellik `True` veya `False`.</span><span class="sxs-lookup"><span data-stu-id="7e862-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="7e862-106">Ayarlarsanız `True`, derleyici bir hata öğe kullanma girişimi değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="7e862-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="7e862-107">Ayarlarsanız `False`, veya bu izin varsayılan `False`, öğe kullanma girişimi varsa, derleyici bir uyarı verir.</span><span class="sxs-lookup"><span data-stu-id="7e862-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="7e862-108">Varsayılan olarak, bu ileti bir uyarı çünkü <xref:System.ObsoleteAttribute.IsError%2A> özelliği <xref:System.ObsoleteAttribute> olduğu `False`.</span><span class="sxs-lookup"><span data-stu-id="7e862-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="7e862-109">Uyarıları gizleme veya uyarıları hata olarak değerlendirmesini hakkında daha fazla bilgi için bkz. [Visual Basic'teki uyarıları yapılandırma](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7e862-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="7e862-110">**Hata Kimliği:** BC40008</span><span class="sxs-lookup"><span data-stu-id="7e862-110">**Error ID:** BC40008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7e862-111">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="7e862-111">To correct this error</span></span>  
  
- <span data-ttu-id="7e862-112">Kaynak kodu başvuru öğe adı doğru yazım olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="7e862-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e862-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7e862-113">See also</span></span>

- [<span data-ttu-id="7e862-114">Öznitelikler genel bakış</span><span class="sxs-lookup"><span data-stu-id="7e862-114">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
