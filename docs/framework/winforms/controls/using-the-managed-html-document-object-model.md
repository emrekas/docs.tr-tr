---
title: Yönetilen HTML Belgesi Nesne Modelini Kullanma
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: fe84cabfaabdc14c7dec6cb69653d41b4c6f6416
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590162"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="ff10a-102">Yönetilen HTML Belgesi Nesne Modelini Kullanma</span><span class="sxs-lookup"><span data-stu-id="ff10a-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="ff10a-103">Yönetilen HTML belge nesne modeli (DOM), .NET Framework Internet Explorer tarafından ortaya konan HTML sınıflar için temel bir sarmalayıcı sağlar.</span><span class="sxs-lookup"><span data-stu-id="ff10a-103">The managed HTML document object model (DOM) provides a wrapper based on the .NET Framework for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="ff10a-104">Barındırılan HTML sayfaları işlemek için bu sınıflar kullanma <xref:System.Windows.Forms.WebBrowser> denetimi veya yeni sayfalar baştan oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="ff10a-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff10a-105">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="ff10a-105">In This Section</span></span>  
 [<span data-ttu-id="ff10a-106">Nasıl yapılır: Yönetilen HTML belgesi nesne modeline erişme</span><span class="sxs-lookup"><span data-stu-id="ff10a-106">How to: Access the Managed HTML Document Object Model</span></span>](how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="ff10a-107">Geçerli bir örneğini alma yolları açıklanır <xref:System.Windows.Forms.HtmlDocument> bir Windows Forms uygulamasında veya <xref:System.Windows.Forms.UserControl> Internet Explorer'da barındırılan.</span><span class="sxs-lookup"><span data-stu-id="ff10a-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="ff10a-108">Nasıl yapılır: Yönetilen HTML belgesi nesne modelinde HTML kaynağına erişme</span><span class="sxs-lookup"><span data-stu-id="ff10a-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="ff10a-109">Özgün, değiştirilmemiş HTML kaynağını edinme ve DOM geçerli durumunu yansıtan "canlı" kaynağı elde etme açıklanmaktadır</span><span class="sxs-lookup"><span data-stu-id="ff10a-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="ff10a-110">Nasıl yapılır: Yönetilen HTML belgesi nesne modelinde bir öğedeki stilleri değiştirme</span><span class="sxs-lookup"><span data-stu-id="ff10a-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="ff10a-111">Öğelerin görünümünü kontrol etmek için kullanılan stilleri yönetileceğini açıklar.</span><span class="sxs-lookup"><span data-stu-id="ff10a-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="ff10a-112">Yönetilen HTML Belgesi Nesne Modelindeki Çerçevelere Erişme</span><span class="sxs-lookup"><span data-stu-id="ff10a-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="ff10a-113">Çerçeve ve çerçeve kümesi nedir ve DOM çerçevesinin nasıl açıklar.</span><span class="sxs-lookup"><span data-stu-id="ff10a-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="ff10a-114">Yönetilen HTML Belgesi Nesne Modelinde Gösterilmeyen Öğelere Erişme</span><span class="sxs-lookup"><span data-stu-id="ff10a-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="ff10a-115">Temel alınan DOM yönetilen eşdeğeri olmayan üyelere erişim açıklar.</span><span class="sxs-lookup"><span data-stu-id="ff10a-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ff10a-116">Başvuru</span><span class="sxs-lookup"><span data-stu-id="ff10a-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="ff10a-117">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="ff10a-117">Related Sections</span></span>  
 [<span data-ttu-id="ff10a-118">WebBrowser Denetimi</span><span class="sxs-lookup"><span data-stu-id="ff10a-118">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)  
