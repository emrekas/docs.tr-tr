---
title: 'Nasıl yapılır: Bir Windows formdan bip sesi çalma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: b847f2f759667eed5dfb6f9168a5c2fc50909cc3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544516"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="6372a-102">Nasıl yapılır: Bir Windows formdan bip sesi çalma</span><span class="sxs-lookup"><span data-stu-id="6372a-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="6372a-103">Bu örnek, çalışma zamanında bir bip sesi çalar.</span><span class="sxs-lookup"><span data-stu-id="6372a-103">This example plays a beep at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6372a-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="6372a-104">Example</span></span>  
  
```vb  
Public Sub OnePing()  
    Beep()  
End Sub  
```  
  
```csharp  
public void onePing()  
{  
    SystemSounds.Beep.Play();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="6372a-105">Yürütülen ses C# kod örneği tarafından belirlenir <xref:System.Media.SystemSounds.Beep%2A> sistem ses ayarı.</span><span class="sxs-lookup"><span data-stu-id="6372a-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="6372a-106">Daha fazla bilgi için bkz. <xref:System.Media.SystemSounds>.</span><span class="sxs-lookup"><span data-stu-id="6372a-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6372a-107">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="6372a-107">Compiling the Code</span></span>  
 <span data-ttu-id="6372a-108">İçin C#, bu örnek, bir başvuru gerektirir <xref:System.Media?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="6372a-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6372a-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6372a-109">See also</span></span>
- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="6372a-110">Nasıl yapılır: Bir Windows formundan sistem sesi çalma</span><span class="sxs-lookup"><span data-stu-id="6372a-110">How to: Play a System Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="6372a-111">Nasıl yapılır: Bir Windows formdan ses çalma</span><span class="sxs-lookup"><span data-stu-id="6372a-111">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
