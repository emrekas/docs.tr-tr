---
title: cref özniteliği - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: acbf45b5ccd4fcb9cb1c23b843072c2abdeeca25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685951"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="86fbf-102">cref Özniteliği (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="86fbf-102">cref Attribute (C# Programming Guide)</span></span>
<span data-ttu-id="86fbf-103">`cref` Bir XML belgeleri etiketi özniteliğinde "kod başvurusu" anlamına gelir</span><span class="sxs-lookup"><span data-stu-id="86fbf-103">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="86fbf-104">Bu etiket iç metni bir kod öğe türü, yöntemi veya özelliği belirtir.</span><span class="sxs-lookup"><span data-stu-id="86fbf-104">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="86fbf-105">Gibi belgeleri Araçları [Sandcastle](https://github.com/EWSoftware/SHFB) kullanın `cref` köprüler burada türe veya üyeye belgelenen sayfasına otomatik olarak oluşturmak için öznitelikleri.</span><span class="sxs-lookup"><span data-stu-id="86fbf-105">Documentation tools like [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86fbf-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="86fbf-106">Example</span></span>  
 <span data-ttu-id="86fbf-107">Aşağıdaki örnekte gösterildiği `cref` kullanılan öznitelikler [ \<bakın >](../../../csharp/programming-guide/xmldoc/see.md) etiketler.</span><span class="sxs-lookup"><span data-stu-id="86fbf-107">The following example shows `cref` attributes used in [\<see>](../../../csharp/programming-guide/xmldoc/see.md) tags.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#3](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/cref-attribute_1.cs)]  
  
 <span data-ttu-id="86fbf-108">Derlendiğinde, program şu XML dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="86fbf-108">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="86fbf-109">Dikkat `cref` özniteliğini `GetZero` yöntemi, örneğin, dönüştürülmüş derleyicisi tarafından `"M:TestNamespace.TestClass.GetZero"`.</span><span class="sxs-lookup"><span data-stu-id="86fbf-109">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="86fbf-110">"/ M:" ön eki "method" anlamına gelir ve Sandcastle gibi belgeleri araçları tarafından tanınan bir kuraldır.</span><span class="sxs-lookup"><span data-stu-id="86fbf-110">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as Sandcastle.</span></span> <span data-ttu-id="86fbf-111">Ön ekleri tam bir listesi için bkz. [XML dosyasını işleme](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="86fbf-111">For a complete list of prefixes, see [Processing the XML File](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md).</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>CRefTest</name>  
    </assembly>  
    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains cref examples.  
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.#ctor">  
            <summary>  
            This sample shows how to specify the <see cref="T:TestNamespace.TestClass"/> constructor as a cref attribute.   
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.#ctor(System.Int32)">  
            <summary>  
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.#ctor(System.Int32)"/> constructor as a cref attribute.   
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetZero">  
            <summary>  
            The GetZero method.  
            </summary>  
            <example>   
            This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.  
            <code>  
            class TestClass   
            {  
                static int Main()   
                {  
                    return GetZero();  
                }  
            }  
            </code>  
            </example>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">  
            <summary>  
            The GetGenericValue method.  
            </summary>  
            <remarks>   
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.  
            </remarks>  
        </member>  
        <member name="T:TestNamespace.GenericClass`1">  
            <summary>  
            GenericClass.  
            </summary>  
            <remarks>   
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.  
            </remarks>  
        </member>  
    </members>    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains two cref examples.  
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetZero">  
            <summary>  
            The GetZero method.  
            </summary>  
            <example> This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.  
            <code>  
            class TestClass   
            {  
                static int Main()   
                {  
                    return GetZero();  
                }  
            }  
            </code>  
            </example>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">  
            <summary>  
            The GetGenericValue method.  
            </summary>  
            <remarks>   
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.  
            </remarks>  
        </member>  
        <member name="T:TestNamespace.GenericClass`1">  
            <summary>  
            GenericClass.  
            </summary>  
            <remarks>   
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.  
            </remarks>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86fbf-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="86fbf-112">See also</span></span>

- [<span data-ttu-id="86fbf-113">XML Belge Açıklamaları</span><span class="sxs-lookup"><span data-stu-id="86fbf-113">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
- [<span data-ttu-id="86fbf-114">Belge Açıklamaları için Önerilen Etiketler</span><span class="sxs-lookup"><span data-stu-id="86fbf-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
