---
title: Bildirilmiş Öğelere Başvurular (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 16f4fb28ab030ccebed2a8d1b93a3a6c29d075c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501262"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="e13c5-102">Bildirilmiş Öğelere Başvurular (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e13c5-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="e13c5-103">Kodunuz için bildirilen bir öğe başvurduğunda, Visual Basic Derleyicisi, adı uygun bildirimi, başvuru adı eşleşir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="e13c5-104">Aynı ada sahip birden fazla öğe bildirilmişse, bu öğeleri tarafından başvurulan olan denetleyebilirsiniz *uygun* adı.</span><span class="sxs-lookup"><span data-stu-id="e13c5-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="e13c5-105">Derleme adı başvuru adı bildirimi ile eşleştirmeyi dener *kapsamdan*.</span><span class="sxs-lookup"><span data-stu-id="e13c5-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="e13c5-106">Başka bir deyişle, başvuru yapan koda ile başlar ve dışa doğru öğeleri içeren art arda gelen düzeyleri ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="e13c5-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="e13c5-107">Aşağıdaki örnek, aynı ada sahip iki değişken başvuruları gösterir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="e13c5-108">Örnekte iki değişkenler bildirilmektedir, her adlı `totalCount`, kapsamın modülünde farklı düzeylerde `container`.</span><span class="sxs-lookup"><span data-stu-id="e13c5-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="e13c5-109">Zaman yordamı `showCount` görüntüler `totalCount` niteleme olmadan Visual Basic Derleyicisi dar kapsamlı özelliği içindeki yerel bildirim bildirimi başvuruyu çözümler `showCount`.</span><span class="sxs-lookup"><span data-stu-id="e13c5-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="e13c5-110">Ne zaman niteleyen `totalCount` içeren modülü ile `container`, derleyici daha geniş kapsamlı bildirimi başvuruyu çözümler.</span><span class="sxs-lookup"><span data-stu-id="e13c5-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="e13c5-111">Bir öğe adı niteleme</span><span class="sxs-lookup"><span data-stu-id="e13c5-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="e13c5-112">Bu arama işlemi geçersiz kılabilir ve gerekir daha geniş bir kapsamda bildirilen bir ad belirtmek istiyorsanız *uygun* adı ile daha geniş kapsam kapsayıcı öğe.</span><span class="sxs-lookup"><span data-stu-id="e13c5-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="e13c5-113">Bazı durumlarda, kapsayıcı öğe nitelemek olabilir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="e13c5-114">Uygun. hedef öğenin tanımlandığı tanımlayan bilgiler ile kaynak deyiminde önceki adı anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="e13c5-115">Bu bilgiler adlı bir *nitelik dize*.</span><span class="sxs-lookup"><span data-stu-id="e13c5-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="e13c5-116">Bir içerebilir veya daha fazla ad alanları ve bir modül, sınıf veya yapı.</span><span class="sxs-lookup"><span data-stu-id="e13c5-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="e13c5-117">Nitelik dize adlı modül, sınıf veya yapının hedef öğe içeren belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="e13c5-118">Kapsayıcı başka bir kapsayıcı öğe içinde genellikle bir ad alanı sırayla bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="e13c5-119">Nitelik dizesine birkaç içeren öğeleri dahil etmek gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="e13c5-120">Bildirilen öğe adını nitelendirme tarafından erişmek için</span><span class="sxs-lookup"><span data-stu-id="e13c5-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="e13c5-121">Öğe tanımlanmış konumu belirlenemiyor.</span><span class="sxs-lookup"><span data-stu-id="e13c5-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="e13c5-122">Bu, bir ad veya hatta ad alanları hiyerarşisi içerebilir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="e13c5-123">En düşük düzey ad alanı içinde bir modül, sınıf veya yapı öğe bulunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e13c5-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  <span data-ttu-id="e13c5-124">Hedef öğenin konumuna göre bir nitelenmiş yola belirleyin.</span><span class="sxs-lookup"><span data-stu-id="e13c5-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="e13c5-125">En üst düzey ad alanı ile devam etmek için en düşük düzey ad alanı ve modül, sınıf veya hedef öğe içeren yapı ile bitmelidir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="e13c5-126">Yolun her öğeyi takip eden öğe içermelidir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="e13c5-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="e13c5-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="e13c5-128">Nitelik dize hedef öğe için hazırlayın.</span><span class="sxs-lookup"><span data-stu-id="e13c5-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="e13c5-129">Bir nokta koyun (`.`) sonra her öğenin yolu.</span><span class="sxs-lookup"><span data-stu-id="e13c5-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="e13c5-130">Uygulamanızı her öğe nitelik dizenizi erişiminiz olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e13c5-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="e13c5-131">İfade veya normal bir şekilde hedef öğeye başvuran atama ifadesi yazın.</span><span class="sxs-lookup"><span data-stu-id="e13c5-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="e13c5-132">Hedef öğe adı nitelik dizesiyle koyun.</span><span class="sxs-lookup"><span data-stu-id="e13c5-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="e13c5-133">Ad, dönem hemen izlemelidir (`.`) modülü, sınıf veya öğeyi içeren yapı izler.</span><span class="sxs-lookup"><span data-stu-id="e13c5-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="e13c5-134">Derleyici nitelik dizesi için hedef öğe başvurusu eşleşebilir açık ve anlaşılır bir bildirimi bulmak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="e13c5-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="e13c5-135">Uygulamanız aynı ada sahip birden fazla programlama öğesine erişimi varsa ad başvuru nitelemek olabilir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="e13c5-136">Örneğin, <xref:System.Windows.Forms> ve <xref:System.Web.UI.WebControls> her iki ad alanları içeren bir `Label` sınıfı (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> ve <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="e13c5-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="e13c5-137">Uygulamanız hem de kullanıyorsa veya kendi tanımlıyorsa `Label` sınıfı, farklı ayırdetmek `Label` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="e13c5-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="e13c5-138">Değişken bildiriminde içe veya ad alanı diğer adı içerir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="e13c5-139">Aşağıdaki örnek, içeri aktarma diğer ad kullanır.</span><span class="sxs-lookup"><span data-stu-id="e13c5-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="e13c5-140">Diğer içeren öğeleri üyeleri</span><span class="sxs-lookup"><span data-stu-id="e13c5-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="e13c5-141">Paylaşılmayan başka bir sınıf veya yapı üyesi kullandığınızda, önce bir değişkenin veya ifadenin sınıfın veya yapının örneğine işaret eden üye adıyla nitelemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="e13c5-142">Aşağıdaki örnekte, `demoClass` adlı bir sınıfın bir örneği `class1`.</span><span class="sxs-lookup"><span data-stu-id="e13c5-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="e13c5-143">Sınıf adı olmayan bir üye nitelemek için kullanamazsınız [paylaşılan](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="e13c5-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="e13c5-144">Öncelikle bir nesne değişkeninin örneği oluşturmanız gerekir (Bu durumda `demoClass`) ve değişken adıyla başvurun.</span><span class="sxs-lookup"><span data-stu-id="e13c5-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="e13c5-145">Bir sınıf veya yapı varsa bir `Shared` üye bu üyenin sınıf veya yapı adı veya bir değişkeni veya bir örneğine işaret eden ifade uygun.</span><span class="sxs-lookup"><span data-stu-id="e13c5-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="e13c5-146">Ayrı bir örneğinin bir modül yok ve tüm üyeleri `Shared` varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="e13c5-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="e13c5-147">Bu nedenle, modül ada sahip bir modül üye nitelendirin.</span><span class="sxs-lookup"><span data-stu-id="e13c5-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="e13c5-148">Aşağıdaki örnek, tam modülü üye yordamlarına yönelik başvuruları gösterir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="e13c5-149">İki örnek bildirir `Sub` yordamları, hem adlandırılmış `perform`, bir projede farklı modül içinde.</span><span class="sxs-lookup"><span data-stu-id="e13c5-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="e13c5-150">Her biri kendi modül içinde nitelik olmadan belirtilebilir ancak başka bir yerde gelen başvurulan nitelenmiş olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e13c5-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="e13c5-151">En son başvurusunun çünkü `module3` uygun değil `perform`, derleyici bu başvurusu çözümlenemiyor.</span><span class="sxs-lookup"><span data-stu-id="e13c5-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="e13c5-152">Proje başvuruları</span><span class="sxs-lookup"><span data-stu-id="e13c5-152">References to Projects</span></span>  
 <span data-ttu-id="e13c5-153">Kullanılacak [genel](../../../../visual-basic/language-reference/modifiers/public.md) başka bir projede tanımlanan öğeleri, ilk ayarlamalısınız bir *başvuru* projenin derleme veya tür kitaplığına.</span><span class="sxs-lookup"><span data-stu-id="e13c5-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="e13c5-154">Bir başvuru ayarlamak için tıklayın **Başvuru Ekle** üzerinde **proje** menü veya kullanım [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) derleyici komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="e13c5-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="e13c5-155">Örneğin, XML nesne modeli kullanabilirsiniz [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e13c5-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e13c5-156">Bir başvuru ayarlamanız <xref:System.Xml> ad alanı, bildirme ve herhangi bir alt sınıfı gibi kullanma <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e13c5-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="e13c5-157">Aşağıdaki örnekte <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e13c5-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="e13c5-158">Öğeleri içeren içeri aktarma</span><span class="sxs-lookup"><span data-stu-id="e13c5-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="e13c5-159">Kullanabileceğiniz [Imports deyimi (.NET Namespace ve türü)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) için *alma* modüller veya kullanmak istediğiniz sınıfları içeren ad alanları.</span><span class="sxs-lookup"><span data-stu-id="e13c5-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="e13c5-160">Bu, tam adlarını niteleme olmadan bir içeri aktarılan ad alanında tanımlanan öğeler başvurmak sağlar.</span><span class="sxs-lookup"><span data-stu-id="e13c5-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="e13c5-161">Aşağıdaki örnek, içeri aktarmak için önceki örnekte yeniden yazar <xref:System.Xml> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="e13c5-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="e13c5-162">Ayrıca, `Imports` deyimi tanımlayabilirsiniz bir *diğer içeri aktarma* için her bir içeri aktarılan ad alanı.</span><span class="sxs-lookup"><span data-stu-id="e13c5-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="e13c5-163">Bu, kaynak kodu daha kısa ve okunması kolay hale getirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e13c5-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="e13c5-164">Aşağıdaki örnek, önceki örneğin yeniden yazar `xD` için bir diğer ad olarak <xref:System.Xml> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="e13c5-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="e13c5-165">`Imports` Deyimi yapmaz öğeleri diğer projelerden uygulamanız için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="e13c5-166">Diğer bir deyişle, bir başvuru ayarlama yer almaz.</span><span class="sxs-lookup"><span data-stu-id="e13c5-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="e13c5-167">Yalnızca bir ad alanı alma, o ad alanında tanımlanan adlar nitelemek için gereksinimini ortadan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="e13c5-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="e13c5-168">Ayrıca `Imports` modülleri, sınıflar, yapılar ve sabit listeleri içeri aktarma deyimi.</span><span class="sxs-lookup"><span data-stu-id="e13c5-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="e13c5-169">Daha sonra içeri aktarılan tür öğeleri nitelik olmadan üyeleri de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e13c5-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="e13c5-170">Ancak, sınıfları ve yapıları bir değişken veya sınıf veya yapının örneği için değerlendirilen bir ifade ile paylaşılmayan üyelerinin her zaman nitelemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="e13c5-171">Adlandırma kuralları</span><span class="sxs-lookup"><span data-stu-id="e13c5-171">Naming Guidelines</span></span>  
 <span data-ttu-id="e13c5-172">Aynı ada sahip iki veya daha fazla programlama öğeleri tanımlarken bir *ad belirsizliği* derleyici bir başvuru adı çözümlemeye çalışırken neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="e13c5-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="e13c5-173">Kapsam içinde birden çok bir tanım ise veya hiçbir tanımı kapsamları dahilinde olması durumunda, çözümlenemeyen başvurudur.</span><span class="sxs-lookup"><span data-stu-id="e13c5-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="e13c5-174">Örneğin, "Tam başvuru örnek" Bu Yardım sayfasında bakın.</span><span class="sxs-lookup"><span data-stu-id="e13c5-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="e13c5-175">Tüm öğeleri benzersiz adlar sağlayarak ad belirsizliği önleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e13c5-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="e13c5-176">Daha sonra bir ad alanı, modül veya sınıfı adıyla nitelemeniz gerek kalmadan herhangi bir öğeye başvuru yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e13c5-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="e13c5-177">Ayrıca, yanlışlıkla yanlış öğesine başvuran olasılığını de azaltır.</span><span class="sxs-lookup"><span data-stu-id="e13c5-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="e13c5-178">Gölgeleme</span><span class="sxs-lookup"><span data-stu-id="e13c5-178">Shadowing</span></span>  
 <span data-ttu-id="e13c5-179">Bunlardan biri, iki programlama öğeleri aynı adı paylaşan, gizleyebilirsiniz, veya *gölge*, diğerinde.</span><span class="sxs-lookup"><span data-stu-id="e13c5-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="e13c5-180">Gölgeli öğe için başvuru kullanılabilir değil; Bunun yerine, kodunuzu gölgeli öğe adı kullandığında, Visual Basic Derleyicisi, gölgelendirme öğesine çözümler.</span><span class="sxs-lookup"><span data-stu-id="e13c5-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="e13c5-181">Örnekleri içeren daha ayrıntılı bir açıklaması için bkz: [Visual Basic'de gölgeleme](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="e13c5-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e13c5-182">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e13c5-182">See also</span></span>
- [<span data-ttu-id="e13c5-183">Bildirilen Öğe Adları</span><span class="sxs-lookup"><span data-stu-id="e13c5-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="e13c5-184">Bildirilen Öğe Özellikleri</span><span class="sxs-lookup"><span data-stu-id="e13c5-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="e13c5-185">Proje ve Çözüm Özelliklerini Yönetme</span><span class="sxs-lookup"><span data-stu-id="e13c5-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="e13c5-186">Değişkenler</span><span class="sxs-lookup"><span data-stu-id="e13c5-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="e13c5-187">Imports Deyimi (.NET Ad Alanı ve Türü)</span><span class="sxs-lookup"><span data-stu-id="e13c5-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="e13c5-188">New İşleci</span><span class="sxs-lookup"><span data-stu-id="e13c5-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="e13c5-189">Public</span><span class="sxs-lookup"><span data-stu-id="e13c5-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
