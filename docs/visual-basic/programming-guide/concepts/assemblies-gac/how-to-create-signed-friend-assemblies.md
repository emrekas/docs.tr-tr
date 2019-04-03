---
title: 'Nasıl yapılır: (Visual Basic) imzalı arkadaş derlemeleri oluşturma'
ms.date: 03/14/2018
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
ms.openlocfilehash: 28cbd0c538441978464033df896d69f80a8396a6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836746"
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="ca31e-102">Nasıl yapılır: (Visual Basic) imzalı arkadaş derlemeleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="ca31e-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="ca31e-103">Bu örnek, arkadaş derlemeleri tanımlayıcı adlara sahip derlemeler ile kullanma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="ca31e-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="ca31e-104">İki derleme tanımlayıcı ada gerekir.</span><span class="sxs-lookup"><span data-stu-id="ca31e-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="ca31e-105">Bu örnekte iki derleme, aynı anahtarları kullanmak olsa da, anahtarları farklı iki derlemeler için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ca31e-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="ca31e-106">İmzalı bir derleme ve arkadaş derleme oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="ca31e-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="ca31e-107">Bir komut istemi açın.</span><span class="sxs-lookup"><span data-stu-id="ca31e-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="ca31e-108">Aşağıdaki komut dizisi, tanımlayıcı ad aracı ile bir keyfile oluşturur ve ortak anahtarını görüntülemek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="ca31e-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="ca31e-109">Daha fazla bilgi için [Sn.exe (tanımlayıcı ad aracı)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="ca31e-109">For more information, see [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
    1.  <span data-ttu-id="ca31e-110">Bu örnek için bir tanımlayıcı ad anahtar oluşturun ve FriendAssemblies.snk dosyasında depolar:</span><span class="sxs-lookup"><span data-stu-id="ca31e-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="ca31e-111">FriendAssemblies.snk ortak anahtarı ayıklar ve FriendAssemblies.publickey yerleştirin:</span><span class="sxs-lookup"><span data-stu-id="ca31e-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="ca31e-112">FriendAssemblies.publickey dosyasında depolanan ortak anahtarı görüntüler:</span><span class="sxs-lookup"><span data-stu-id="ca31e-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="ca31e-113">Adlı bir Visual Basic dosyası oluşturma `friend_signed_A` , aşağıdaki kodu içerir.</span><span class="sxs-lookup"><span data-stu-id="ca31e-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="ca31e-114">Kod <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> friend_signed_B arkadaş derleme olarak bildirmek için özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ca31e-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="ca31e-115">Tanımlayıcı ad aracı, her çalıştığında yeni bir ortak anahtar oluşturur.</span><span class="sxs-lookup"><span data-stu-id="ca31e-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="ca31e-116">Bu nedenle, aşağıdaki örnekte gösterildiği gibi ürettiğiniz, ortak anahtar ile ortak anahtar aşağıdaki kodu değiştirmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="ca31e-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  <span data-ttu-id="ca31e-117">Derleme ve aşağıdaki komutu kullanarak friend_signed_A imzalayın.</span><span class="sxs-lookup"><span data-stu-id="ca31e-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```console  
    Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="ca31e-118">Adlı bir Visual Basic dosyası oluşturma `friend_signed_B` ve aşağıdaki kodu içerir.</span><span class="sxs-lookup"><span data-stu-id="ca31e-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="ca31e-119">Friend_signed_A friend_signed_B arkadaş derleme olarak belirttiğinden friend_signed_B kodda erişip `Friend` türleri ve üyeleri friend_signed_A.</span><span class="sxs-lookup"><span data-stu-id="ca31e-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="ca31e-120">Dosya, aşağıdaki kodu içerir.</span><span class="sxs-lookup"><span data-stu-id="ca31e-120">The file contains the following code.</span></span>  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="ca31e-121">Derleme ve aşağıdaki komutu kullanarak friend_signed_B imzalayın.</span><span class="sxs-lookup"><span data-stu-id="ca31e-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```console  
    vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="ca31e-122">Geçirilen friend derleme adı derleyici tarafından oluşturulan bütünleştirilmiş kodun adı eşleşmelidir <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ca31e-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="ca31e-123">Bütünleştirilmiş kod kullanarak açıkça ayarlayabilirsiniz `-out` derleyici seçeneği.</span><span class="sxs-lookup"><span data-stu-id="ca31e-123">You can explicitly set the assembly by using the `-out` compiler option.</span></span> <span data-ttu-id="ca31e-124">Daha fazla bilgi için [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="ca31e-124">For more information, see [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="ca31e-125">Friend_signed_B.exe dosyasını çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="ca31e-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="ca31e-126">Program "Class1.Test" dizesini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="ca31e-126">The program displays the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ca31e-127">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="ca31e-127">.NET Framework Security</span></span>  
 <span data-ttu-id="ca31e-128">Arasındaki benzerlikler vardır <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> özniteliği ve <xref:System.Security.Permissions.StrongNameIdentityPermission> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="ca31e-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="ca31e-129">Ana fark <xref:System.Security.Permissions.StrongNameIdentityPermission> ise kod, belirli bir bölümünü çalıştırmak için güvenlik izinleri talep <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> özniteliği denetimleri görünürlüğünü `Friend` türler ve üyeler.</span><span class="sxs-lookup"><span data-stu-id="ca31e-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca31e-130">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ca31e-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="ca31e-131">.NET’te bütünleştirilmiş kodlar</span><span class="sxs-lookup"><span data-stu-id="ca31e-131">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="ca31e-132">Arkadaş Bütünleştirilmiş Kodları</span><span class="sxs-lookup"><span data-stu-id="ca31e-132">Friend Assemblies</span></span>](../../../../standard/assembly/friend-assemblies.md)
- [<span data-ttu-id="ca31e-133">Nasıl yapılır: (Visual Basic) imzasız arkadaş derlemeleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="ca31e-133">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="ca31e-134">-keyfile</span><span class="sxs-lookup"><span data-stu-id="ca31e-134">-keyfile</span></span>](../../../../visual-basic/reference/command-line-compiler/keyfile.md)
- <span data-ttu-id="ca31e-135">[Sn.exe (tanımlayıcı ad aracı)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="ca31e-135">[Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
- [<span data-ttu-id="ca31e-136">Kesin Adlandırılmış Bütünleştirilmiş Kodlar Oluşturma ve Kullanma</span><span class="sxs-lookup"><span data-stu-id="ca31e-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="ca31e-137">Programlama Kavramları</span><span class="sxs-lookup"><span data-stu-id="ca31e-137">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
