---
title: 'Nasıl yapılır: Sistem Yazı Tipleri Tuşlarını Kullanma'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: e924f4c14d98380d9f4c0defe27d9f98c3293114
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148934"
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="ea40a-102">Nasıl yapılır: Sistem Yazı Tipleri Tuşlarını Kullanma</span><span class="sxs-lookup"><span data-stu-id="ea40a-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="ea40a-103">Sistem ayarları ile tutarlı, görsel oluşturmak geliştiriciler yardımcı olacak kaynaklar olarak sistem kaynaklarının sistem ölçümlerini sayısını kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="ea40a-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <xref:System.Windows.SystemFonts> <span data-ttu-id="ea40a-104">Sistem yazı tipi değerleri hem değerlere bağlama sistem yazı tipi kaynakları içeren bir sınıf — Örneğin, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> ve <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="ea40a-104">is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="ea40a-105">Sistem yazı tipi ölçümleri statik veya dinamik kaynakları olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ea40a-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="ea40a-106">Yazı tipi ölçüsünün uygulama çalışırken otomatik olarak güncelleştirmek istiyorsanız, bir dinamik kaynak kullanmak çalışır; Aksi takdirde bir statik kaynak kullanın.</span><span class="sxs-lookup"><span data-stu-id="ea40a-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea40a-107">Dinamik kaynaklara sahip anahtar sözcüğü *anahtar* özellik adına eklenir.</span><span class="sxs-lookup"><span data-stu-id="ea40a-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="ea40a-108">Aşağıdaki örnek, bir düğmeye stil veya sistem yazı tipi dinamik kaynaklarına erişmek ve gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="ea40a-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="ea40a-109">Bu [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] örneği oluşturur atayan bir düğme stili <xref:System.Windows.SystemFonts> değerleri.</span><span class="sxs-lookup"><span data-stu-id="ea40a-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea40a-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="ea40a-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="ea40a-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ea40a-111">See also</span></span>

- [<span data-ttu-id="ea40a-112">Sistem Fırçası ile bir Alanı Boyama</span><span class="sxs-lookup"><span data-stu-id="ea40a-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="ea40a-113">SystemParameters Kullanma</span><span class="sxs-lookup"><span data-stu-id="ea40a-113">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="ea40a-114">SystemFonts Kullanma</span><span class="sxs-lookup"><span data-stu-id="ea40a-114">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
