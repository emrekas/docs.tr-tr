---
title: Özel öznitelikler oluşturma (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: e4b55f92466fde47011937d08c946c9c75ca07b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966327"
---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="ae13f-102">Özel öznitelikler oluşturma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae13f-102">Creating Custom Attributes (Visual Basic)</span></span>
<span data-ttu-id="ae13f-103">Doğrudan veya dolaylı <xref:System.Attribute>olarak sınıfından türetilmiş bir sınıf olan öznitelik sınıfını tanımlayarak kendi özel öznitelerinizi oluşturabilirsiniz. Bu, meta verilerde hızlı ve kolay bir şekilde öznitelik tanımları tanımlamayı sağlar.</span><span class="sxs-lookup"><span data-stu-id="ae13f-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="ae13f-104">Türleri, türünü yazan programcının adıyla etiketlemek istediğinizi varsayalım.</span><span class="sxs-lookup"><span data-stu-id="ae13f-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="ae13f-105">Özel `Author` bir öznitelik sınıfı tanımlayabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="ae13f-105">You might define a custom `Author` attribute class:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="ae13f-106">Sınıf adı özniteliğin adıdır, `Author`.</span><span class="sxs-lookup"><span data-stu-id="ae13f-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="ae13f-107">Öğesinden `System.Attribute`türetilir, bu nedenle özel bir öznitelik sınıfıdır.</span><span class="sxs-lookup"><span data-stu-id="ae13f-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="ae13f-108">Oluşturucunun parametreleri özel özniteliğin konumsal parametreleridir.</span><span class="sxs-lookup"><span data-stu-id="ae13f-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="ae13f-109">Bu örnekte, `name` bir Konumsal parametredir.</span><span class="sxs-lookup"><span data-stu-id="ae13f-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="ae13f-110">Tüm genel okuma/yazma alanları veya özellikleri parametreler olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="ae13f-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="ae13f-111">Bu durumda, `version` tek adlandırılmış parametredir.</span><span class="sxs-lookup"><span data-stu-id="ae13f-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="ae13f-112">Özniteliği yalnızca sınıf ve `AttributeUsage` `Structure` bildirimlerde geçerli `Author` hale getirmek için özniteliğinin kullanımını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="ae13f-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>  
  
 <span data-ttu-id="ae13f-113">Bu yeni özniteliği şu şekilde kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="ae13f-113">You could use this new attribute as follows:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="ae13f-114">`AttributeUsage`, özel bir özniteliği tek `AllowMultiple`kullanımı veya çok kullanımı yapabileceğiniz adlandırılmış bir parametreye sahiptir.</span><span class="sxs-lookup"><span data-stu-id="ae13f-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="ae13f-115">Aşağıdaki kod örneğinde, Multiuse özniteliği oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="ae13f-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 <span data-ttu-id="ae13f-116">Aşağıdaki kod örneğinde, aynı türde birden çok öznitelik bir sınıfa uygulanır.</span><span class="sxs-lookup"><span data-stu-id="ae13f-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
> <span data-ttu-id="ae13f-117">Öznitelik sınıfınız bir özellik içeriyorsa, bu özellik oku-yaz olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="ae13f-117">If your attribute class contains a property, that property must be read-write.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae13f-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ae13f-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="ae13f-119">Visual Basic programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="ae13f-119">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="ae13f-120">Özel Öznitelikler Yazma</span><span class="sxs-lookup"><span data-stu-id="ae13f-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="ae13f-121">Yansıma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae13f-121">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="ae13f-122">Öznitelikler (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae13f-122">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)
- [<span data-ttu-id="ae13f-123">Yansıma kullanarak özniteliklere erişme (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae13f-123">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="ae13f-124">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae13f-124">AttributeUsage (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
