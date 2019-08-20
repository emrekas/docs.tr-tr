---
title: 'Nasıl yapılır: Ifade ağaçlarını değiştirme (C#)'
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: 7875cf1ccca8866cc87ebec80701ad77ad2bea2d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595063"
---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="0ba06-102">Nasıl yapılır: Ifade ağaçlarını değiştirme (C#)</span><span class="sxs-lookup"><span data-stu-id="0ba06-102">How to: Modify Expression Trees (C#)</span></span>
<span data-ttu-id="0ba06-103">Bu konu başlığı altında, bir ifade ağacının nasıl değiştirileceği gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="0ba06-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="0ba06-104">İfade ağaçları sabittir ve bu, doğrudan değiştirilemediği anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="0ba06-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="0ba06-105">Bir ifade ağacını değiştirmek için, var olan bir ifade ağacının bir kopyasını oluşturmanız ve kopyayı oluşturduğunuzda gerekli değişiklikleri yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="0ba06-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="0ba06-106">Sınıfını, <xref:System.Linq.Expressions.ExpressionVisitor> var olan bir ifade ağacında çapraz geçiş yapmak ve bulduğu her düğümü kopyalamak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0ba06-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="0ba06-107">Bir ifade ağacını değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="0ba06-107">To modify an expression tree</span></span>  
  
1. <span data-ttu-id="0ba06-108">Yeni bir **konsol uygulaması** projesi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="0ba06-108">Create a new **Console Application** project.</span></span>  
  
2. <span data-ttu-id="0ba06-109">Ad`System.Linq.Expressions` alanı `using` için dosyasına bir yönerge ekleyin.</span><span class="sxs-lookup"><span data-stu-id="0ba06-109">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3. <span data-ttu-id="0ba06-110">`AndAlsoModifier` Sınıfını projenize ekleyin.</span><span class="sxs-lookup"><span data-stu-id="0ba06-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```csharp  
    public class AndAlsoModifier : ExpressionVisitor  
    {  
        public Expression Modify(Expression expression)  
        {  
            return Visit(expression);  
        }  
  
        protected override Expression VisitBinary(BinaryExpression b)  
        {  
            if (b.NodeType == ExpressionType.AndAlso)  
            {  
                Expression left = this.Visit(b.Left);  
                Expression right = this.Visit(b.Right);  
  
                // Make this binary expression an OrElse operation instead of an AndAlso operation.  
                return Expression.MakeBinary(ExpressionType.OrElse, left, right, b.IsLiftedToNull, b.Method);  
            }  
  
            return base.VisitBinary(b);  
        }  
    }  
    ```  
  
     <span data-ttu-id="0ba06-111">Bu sınıf <xref:System.Linq.Expressions.ExpressionVisitor> sınıfını devralır ve koşullu `AND` işlemleri temsil eden ifadeleri değiştirmek için özelleştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="0ba06-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="0ba06-112">Bu işlemleri koşullu `AND` sunucudan koşullu `OR`olarak değiştirir.</span><span class="sxs-lookup"><span data-stu-id="0ba06-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="0ba06-113">Bunu yapmak için, koşullu <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> `AND` ifadeler ikili ifadeler olarak temsil edildiği için sınıf temel tür yöntemini geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="0ba06-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="0ba06-114">Yönteminde, kendisine geçirilen ifade koşullu `AND` bir işlemi temsil ediyorsa, kod koşullu `OR` işleci `AND` içeren yeni bir ifade oluşturur `VisitBinary` işlecinde.</span><span class="sxs-lookup"><span data-stu-id="0ba06-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="0ba06-115">Geçirilen `VisitBinary` ifade koşullu `AND` bir işlemi temsil ediyorsa, yöntemi temel sınıf uygulamasına erteler.</span><span class="sxs-lookup"><span data-stu-id="0ba06-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="0ba06-116">Temel sınıf yöntemleri, geçirilen ifade ağaçları gibi düğümleri oluşturur, ancak düğümlerin alt ağaçları, ziyaretçi tarafından yinelemeli olarak üretilen ifade ağaçları ile değiştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="0ba06-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4. <span data-ttu-id="0ba06-117">Ad`System.Linq.Expressions` alanı `using` için dosyasına bir yönerge ekleyin.</span><span class="sxs-lookup"><span data-stu-id="0ba06-117">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5. <span data-ttu-id="0ba06-118">Program.cs dosyasındaki `Main` yöntemine kod ekleyerek bir ifade ağacı oluşturun ve bunu değiştirecek yönteme geçirin.</span><span class="sxs-lookup"><span data-stu-id="0ba06-118">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```csharp  
    Expression<Func<string, bool>> expr = name => name.Length > 10 && name.StartsWith("G");  
    Console.WriteLine(expr);  
  
    AndAlsoModifier treeModifier = new AndAlsoModifier();  
    Expression modifiedExpr = treeModifier.Modify((Expression) expr);  
  
    Console.WriteLine(modifiedExpr);  
  
    /*  This code produces the following output:  
  
        name => ((name.Length > 10) && name.StartsWith("G"))  
        name => ((name.Length > 10) || name.StartsWith("G"))  
    */  
    ```  
  
     <span data-ttu-id="0ba06-119">Kod, koşullu `AND` bir işlem içeren bir ifade oluşturur.</span><span class="sxs-lookup"><span data-stu-id="0ba06-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="0ba06-120">Daha sonra `AndAlsoModifier` sınıfın bir örneğini oluşturur ve bu sınıfın `Modify` yöntemine ifadeyi geçirir.</span><span class="sxs-lookup"><span data-stu-id="0ba06-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="0ba06-121">Hem özgün hem de değiştirilen ifade ağaçları değişikliği göstermek için çıktılardır.</span><span class="sxs-lookup"><span data-stu-id="0ba06-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6. <span data-ttu-id="0ba06-122">Uygulamayı derleyin ve çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="0ba06-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ba06-123">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0ba06-123">See also</span></span>

- [<span data-ttu-id="0ba06-124">Nasıl yapılır: Ifade ağaçlarını yürütme (C#)</span><span class="sxs-lookup"><span data-stu-id="0ba06-124">How to: Execute Expression Trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="0ba06-125">İfade ağaçları (C#)</span><span class="sxs-lookup"><span data-stu-id="0ba06-125">Expression Trees (C#)</span></span>](./index.md)
