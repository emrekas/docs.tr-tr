---
title: Arabirim Özellikleri - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: af80f403942f59d672854c80830e175ef7ebaff5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652195"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="06104-102">Arabirim Özellikleri (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="06104-102">Interface Properties (C# Programming Guide)</span></span>
<span data-ttu-id="06104-103">Özellikleri bildirilebilir bir [arabirimi](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="06104-103">Properties can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="06104-104">Bir arabirim özellik erişimcisi örneği verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="06104-104">The following is an example of an interface property accessor:</span></span>  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 <span data-ttu-id="06104-105">Gövde arabirim özelliği erişimcisine sahip değil.</span><span class="sxs-lookup"><span data-stu-id="06104-105">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="06104-106">Bu nedenle, amacı, erişimci özelliği salt okunur, salt okunur veya sadece yazılabilir olup olmadığını belirtmektir.</span><span class="sxs-lookup"><span data-stu-id="06104-106">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06104-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="06104-107">Example</span></span>  
 <span data-ttu-id="06104-108">Bu örnekte, arabirim `IEmployee` bir okuma-yazma özelliğine sahip `Name`ve salt okunur bir özellik `Counter`.</span><span class="sxs-lookup"><span data-stu-id="06104-108">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="06104-109">Sınıf `Employee` uygulayan `IEmployee` arabirim ve bu iki özellik kullanır.</span><span class="sxs-lookup"><span data-stu-id="06104-109">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="06104-110">Programın adını yeni bir çalışan ve çalışanların geçerli sayısını okur ve çalışan adını ve hesaplanan çalışan sayısını görüntüler.</span><span class="sxs-lookup"><span data-stu-id="06104-110">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>  
  
 <span data-ttu-id="06104-111">Üyesi bildirildiği arabirimde başvuran özelliği tam adını kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="06104-111">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="06104-112">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="06104-112">For example:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 <span data-ttu-id="06104-113">Bu adlandırılır [açık arabirim uygulaması](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="06104-113">This is called [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="06104-114">Örneğin, sınıf `Employee` iki arabirim uygulama `ICitizen` ve `IEmployee` ve her iki arabirimde `Name` özelliği açık arabirim üyesi uygulaması gerekli olacak.</span><span class="sxs-lookup"><span data-stu-id="06104-114">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="06104-115">Diğer bir deyişle, aşağıdaki özellik bildirimi:</span><span class="sxs-lookup"><span data-stu-id="06104-115">That is, the following property declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 <span data-ttu-id="06104-116">uygulayan `Name` özelliği `IEmployee` arabirimi, aşağıdaki bildirim yandan:</span><span class="sxs-lookup"><span data-stu-id="06104-116">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 <span data-ttu-id="06104-117">uygulayan `Name` özelliği `ICitizen` arabirimi.</span><span class="sxs-lookup"><span data-stu-id="06104-117">implements the `Name` property on the `ICitizen` interface.</span></span>  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a><span data-ttu-id="06104-118">Örnek Çıktı</span><span class="sxs-lookup"><span data-stu-id="06104-118">Sample Output</span></span>  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a><span data-ttu-id="06104-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="06104-119">See also</span></span>

- [<span data-ttu-id="06104-120">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="06104-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="06104-121">Özellikler</span><span class="sxs-lookup"><span data-stu-id="06104-121">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="06104-122">Özellikleri Kullanma</span><span class="sxs-lookup"><span data-stu-id="06104-122">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="06104-123">Özellikler ve Dizin Oluşturucular Arasında Karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="06104-123">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="06104-124">Dizin Oluşturucular</span><span class="sxs-lookup"><span data-stu-id="06104-124">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)
- [<span data-ttu-id="06104-125">Arabirimler</span><span class="sxs-lookup"><span data-stu-id="06104-125">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
