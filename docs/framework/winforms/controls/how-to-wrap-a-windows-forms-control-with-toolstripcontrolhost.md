---
title: 'Nasıl yapılır: ToolStripControlHost ile bir Windows Forms denetimini kaydırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStrip control [Windows Forms], wrapping controls
- toolbars [Windows Forms], wrapping controls
- ToolStrip control [Windows Forms], hosting controls
ms.assetid: e2ce4990-661d-4882-a116-8a9eb575dc84
ms.openlocfilehash: 2836991d1bb2c5808894050665c3e22a7ed6e0ef
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261339"
---
# <a name="how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost"></a><span data-ttu-id="309d7-102">Nasıl yapılır: ToolStripControlHost ile bir Windows Forms denetimini kaydırma</span><span class="sxs-lookup"><span data-stu-id="309d7-102">How to: Wrap a Windows Forms Control with ToolStripControlHost</span></span>
<span data-ttu-id="309d7-103"><xref:System.Windows.Forms.ToolStripControlHost> kullanarak isteğe bağlı Windows Forms denetimleri barındırma sağlamak üzere tasarlanmış <xref:System.Windows.Forms.ToolStripControlHost> Oluşturucusu veya genişleterek <xref:System.Windows.Forms.ToolStripControlHost> kendisi.</span><span class="sxs-lookup"><span data-stu-id="309d7-103"><xref:System.Windows.Forms.ToolStripControlHost> is designed to enable hosting of arbitrary Windows Forms controls by using the <xref:System.Windows.Forms.ToolStripControlHost> constructor or by extending <xref:System.Windows.Forms.ToolStripControlHost> itself.</span></span> <span data-ttu-id="309d7-104">Genişleterek denetimini kaydırma daha kolaydır <xref:System.Windows.Forms.ToolStripControlHost> ve uygulama özellikleri ve sık kullanıma sunma yöntemleri kullanılan özellikleri ve yöntemleri denetimi.</span><span class="sxs-lookup"><span data-stu-id="309d7-104">It is easier to wrap the control by extending <xref:System.Windows.Forms.ToolStripControlHost> and implementing properties and methods that expose frequently used properties and methods of the control.</span></span> <span data-ttu-id="309d7-105">Denetim olaylarını da getirebilir <xref:System.Windows.Forms.ToolStripControlHost> düzeyi.</span><span class="sxs-lookup"><span data-stu-id="309d7-105">You can also expose events for the control at the <xref:System.Windows.Forms.ToolStripControlHost> level.</span></span>  
  
### <a name="to-host-a-control-in-a-toolstripcontrolhost-by-derivation"></a><span data-ttu-id="309d7-106">Bir denetimde bir ToolStripControlHost göre türetme barındırmak için</span><span class="sxs-lookup"><span data-stu-id="309d7-106">To host a control in a ToolStripControlHost by derivation</span></span>  
  
1.  <span data-ttu-id="309d7-107">Genişletme <xref:System.Windows.Forms.ToolStripControlHost>.</span><span class="sxs-lookup"><span data-stu-id="309d7-107">Extend <xref:System.Windows.Forms.ToolStripControlHost>.</span></span> <span data-ttu-id="309d7-108">Temel sınıf oluşturucusu geçirme istenen denetiminde çağıran bir varsayılan oluşturucu uygulayın.</span><span class="sxs-lookup"><span data-stu-id="309d7-108">Implement a default constructor that calls the base class constructor passing in the desired control.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#10)]  
  
2.  <span data-ttu-id="309d7-109">Sarmalanan denetimi aynı türden bir özelliği bildirme ve dönüş `Control` doğru özelliğin erişimci denetiminde türü olarak.</span><span class="sxs-lookup"><span data-stu-id="309d7-109">Declare a property of the same type as the wrapped control and return `Control` as the correct type of control in the property's accessor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#11)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#11)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#11)]  
  
3.  <span data-ttu-id="309d7-110">Expose diğer sık özellikleri ve yöntemleri Sarmalanan denetimin özellikleri ve yöntemleri genişletilmiş sınıfı ile kullanılır.</span><span class="sxs-lookup"><span data-stu-id="309d7-110">Expose other frequently used properties and methods of the wrapped control with properties and methods in the extended class.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#12)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#12)]  
  
4.  <span data-ttu-id="309d7-111">İsteğe bağlı olarak, geçersiz kılma <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A>, ve <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> yöntemleri ve kullanıma sunmak istediğiniz denetim olayları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="309d7-111">Optionally, override the <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A>, and <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> methods and add the control events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#16](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#16)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#16)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#16)]  
  
5.  <span data-ttu-id="309d7-112">Gerekli sarmalama kullanıma sunmak istediğiniz olayları sağlar.</span><span class="sxs-lookup"><span data-stu-id="309d7-112">Provide the necessary wrapping for the events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#17](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#17)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#17)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="309d7-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="309d7-113">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ToolStripControlHost#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#13)]
 [!code-csharp[System.Windows.Forms.ToolStripControlHost#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#13)]
 [!code-vb[System.Windows.Forms.ToolStripControlHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#13)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="309d7-114">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="309d7-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="309d7-115">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="309d7-115">This example requires:</span></span>  
  
-   <span data-ttu-id="309d7-116">Sistem ve System.Windows.Forms öğelerini derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="309d7-116">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="309d7-117">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="309d7-117">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="309d7-118">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="309d7-118">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="309d7-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="309d7-119">See also</span></span>
- <xref:System.Windows.Forms.ToolStripControlHost>
- [<span data-ttu-id="309d7-120">ToolStrip Denetimine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="309d7-120">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="309d7-121">ToolStrip Denetim, Mimarisi</span><span class="sxs-lookup"><span data-stu-id="309d7-121">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [<span data-ttu-id="309d7-122">ToolStrip Teknoloji Özeti</span><span class="sxs-lookup"><span data-stu-id="309d7-122">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
