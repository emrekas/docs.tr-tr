---
title: 'Nasıl yapılır: Uygulama başlatma ve gönderme tuş vuruşları (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 9519fd85177d5d2adf97b54652c19330954edadf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815972"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="47a93-102">Nasıl yapılır: Uygulama başlatma ve gönderme tuş vuruşları (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47a93-102">How to: Start an Application and Send it Keystrokes (Visual Basic)</span></span>
<span data-ttu-id="47a93-103">Bu örnekte `Shell` hesaplayıcı uygulamayı başlatmak için işlevi ve ardından tuş vuruşları kullanarak göndererek iki sayıyı çarpar `My.Computer.Keyboard.SendKeys` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="47a93-103">This example uses the `Shell` function to start the calculator application and then multiplies two numbers by sending keystrokes using the `My.Computer.Keyboard.SendKeys` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47a93-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="47a93-104">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]  
  
## <a name="robust-programming"></a><span data-ttu-id="47a93-105">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="47a93-105">Robust Programming</span></span>  
 <span data-ttu-id="47a93-106">A <xref:System.ArgumentException> istenen işlem tanımlayıcısına sahip bir uygulama bulunamazsa özel durum oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="47a93-106">A <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="47a93-107">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="47a93-107">.NET Framework Security</span></span>  
 <span data-ttu-id="47a93-108">Çağrı `Shell` işlevi, tam güven gerektirir (<xref:System.Security.SecurityException> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="47a93-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a93-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="47a93-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
