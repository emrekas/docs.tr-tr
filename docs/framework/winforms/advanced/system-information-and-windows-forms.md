---
title: Sistem Bilgileri ve Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: d8efb783fcb5bcbe9c4ee99bc784e27a1aebb0cf
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707670"
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="9fbc0-102">Sistem Bilgileri ve Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9fbc0-102">System Information and Windows Forms</span></span>
<span data-ttu-id="9fbc0-103">Bazen kodunuzda kararlar için uygulamanızın çalıştığı bilgisayar hakkında bilgi toplamak gereklidir.</span><span class="sxs-lookup"><span data-stu-id="9fbc0-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="9fbc0-104">Örneğin, yalnızca belirli bir ağ etki alanına bağlı olduğunda geçerli olan bir işleve sahip olabilir; Bu durumda, etki alanı belirlemek ve etki alanı mevcut değilse işlev devre dışı bırakmak için bir yol gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fbc0-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="9fbc0-105">Windows Forms uygulamaları kullanabilir <xref:System.Windows.Forms.SystemInformation> çalışma zamanında bir bilgisayar hakkında birkaç belirlemek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="9fbc0-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="9fbc0-106">Aşağıdaki örneği kullanarak göstermektedir <xref:System.Windows.Forms.SystemInformation> alınacak sınıfı <xref:System.Windows.Forms.SystemInformation.UserName%2A> ve <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="9fbc0-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 <span data-ttu-id="9fbc0-107">Tüm üyeleri <xref:System.Windows.Forms.SystemInformation> sınıfı salt okunur; bir kullanıcının ayarlarına değişiklik yapamazsınız.</span><span class="sxs-lookup"><span data-stu-id="9fbc0-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="9fbc0-108">Her şeyi döndüren bilgi bilgisayara bağlı monitör sayısı 100'den fazla üye sınıfı yok (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) için Windows Gezgini'nde simgeler aralığını (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> ve <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span><span class="sxs-lookup"><span data-stu-id="9fbc0-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="9fbc0-109">Bazı üyeleri daha kullanışlı <xref:System.Windows.Forms.SystemInformation> sınıfını içeren <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, ve <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span><span class="sxs-lookup"><span data-stu-id="9fbc0-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fbc0-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9fbc0-110">See also</span></span>
- <xref:System.Windows.Forms.SystemInformation>
- [<span data-ttu-id="9fbc0-111">Windows Forms'ta Güç Yönetimi</span><span class="sxs-lookup"><span data-stu-id="9fbc0-111">Power Management in Windows Forms</span></span>](power-management-in-windows-forms.md)
