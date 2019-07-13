---
ms.openlocfilehash: 38dd0b33202b8e8f1708ebec689333bd5367c93f
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857543"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="f296f-101">TextBlock denetimi üst IsEnabled özelliğinin değiştirilmesi tüm alt denetimler etkiler</span><span class="sxs-lookup"><span data-stu-id="f296f-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f296f-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="f296f-102">Details</span></span>|<span data-ttu-id="f296f-103">.NET Framework 4.6.2, değiştirme ile başlayarak <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> üst öğesinin özellik bir <xref:System.Windows.Controls.TextBlock?displayProperty=name> denetimi etkiler (örneğin, köprüler ve düğmeler) tüm alt denetimler <xref:System.Windows.Controls.TextBlock?displayProperty=name> denetimi. İçinde .NET Framework 4.6.1 ve önceki sürümlerle denetleyen bir <xref:System.Windows.Controls.TextBlock?displayProperty=name> her zaman durumunu yansıtmıyor <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> özelliği <xref:System.Windows.Controls.TextBlock?displayProperty=name> üst.</span><span class="sxs-lookup"><span data-stu-id="f296f-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> parent.</span></span>|
|<span data-ttu-id="f296f-104">Öneri</span><span class="sxs-lookup"><span data-stu-id="f296f-104">Suggestion</span></span>|<span data-ttu-id="f296f-105">Yok.</span><span class="sxs-lookup"><span data-stu-id="f296f-105">None.</span></span> <span data-ttu-id="f296f-106">Bu değişiklik içindeki denetimlerin yönelik beklenen davranışın uyan bir <xref:System.Windows.Controls.TextBlock?displayProperty=name> denetimi.</span><span class="sxs-lookup"><span data-stu-id="f296f-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.</span></span>|
|<span data-ttu-id="f296f-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="f296f-107">Scope</span></span>|<span data-ttu-id="f296f-108">Küçük</span><span class="sxs-lookup"><span data-stu-id="f296f-108">Minor</span></span>|
|<span data-ttu-id="f296f-109">Version</span><span class="sxs-lookup"><span data-stu-id="f296f-109">Version</span></span>|<span data-ttu-id="f296f-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="f296f-110">4.6.2</span></span>|
|<span data-ttu-id="f296f-111">Type</span><span class="sxs-lookup"><span data-stu-id="f296f-111">Type</span></span>|<span data-ttu-id="f296f-112">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="f296f-112">Runtime</span></span>|
|<span data-ttu-id="f296f-113">Etkilenen API’ler</span><span class="sxs-lookup"><span data-stu-id="f296f-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|

