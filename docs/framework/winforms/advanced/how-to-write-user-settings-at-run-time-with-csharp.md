---
title: 'Nasıl yapılır: Çalışma zamanında ile kullanıcı ayarlarını yazmaC#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: a62bf540ebdc383f26bd4aed760b2562437047aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560951"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="c2424-102">Nasıl yapılır: Çalışma zamanında ile kullanıcı ayarlarını yazmaC#</span><span class="sxs-lookup"><span data-stu-id="c2424-102">How To: Write User Settings at Run Time with C#</span></span> #
<span data-ttu-id="c2424-103">Uygulama kapsamlı ayarlar salt okunurdur ve yalnızca tasarım zamanında ya da uygulama oturumları arasında .config dosyasını değiştirerek değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="c2424-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="c2424-104">Herhangi bir özelliğin değerini değiştirmek gibi kullanıcı kapsamlı ayarları ancak çalışma zamanında yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="c2424-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="c2424-105">Yeni değer, uygulama oturum süresi boyunca devam ettirir.</span><span class="sxs-lookup"><span data-stu-id="c2424-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="c2424-106">Ayarları kaydetme yöntemini çağırarak uygulama oturumları arasında yapılan değişiklikleri kalıcı hale getirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c2424-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="c2424-107">Nasıl yapılır: Yazma ve çalışma zamanında ile kullanıcı ayarlarını kalıcı yapmaC#</span><span class="sxs-lookup"><span data-stu-id="c2424-107">How To: Write and Persist User Settings at Run Time with C#</span></span>  
  
1.  <span data-ttu-id="c2424-108">Ayar erişmek ve bu örnekte gösterildiği gibi yeni bir değer atayabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="c2424-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  <span data-ttu-id="c2424-109">Uygulama oturumları arasında ayarlarındaki değişiklikler kalıcı hale getirmek istiyorsanız, bu örnekte gösterildiği gibi Save metoduna çağrı:</span><span class="sxs-lookup"><span data-stu-id="c2424-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     <span data-ttu-id="c2424-110">Kullanıcı ayarları kullanıcının yerel gizli uygulama veri klasörünün bir alt dosyasında kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="c2424-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2424-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c2424-111">See also</span></span>
- [<span data-ttu-id="c2424-112">Uygulama Ayarları ve Kullanıcı Ayarlarını Kullanma</span><span class="sxs-lookup"><span data-stu-id="c2424-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [<span data-ttu-id="c2424-113">Nasıl yapılır: Çalışma zamanında ile ayarları okumaC#</span><span class="sxs-lookup"><span data-stu-id="c2424-113">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="c2424-114">Uygulama Ayarlarına Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="c2424-114">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
