---
ms.openlocfilehash: 08c16f261338148619de2e484c73046b9d9a6bfe
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761430"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="4dfa8-101">.NET Framework 4.6 4.5.x.x sürüm kendisini kayıt defterinde kaydederken kullanmaz</span><span class="sxs-lookup"><span data-stu-id="4dfa8-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4dfa8-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="4dfa8-102">Details</span></span>|<span data-ttu-id="4dfa8-103">Sürüm anahtarı bir bekleyebileceğiniz gibi kayıt defterinde ayarlayın (adresindeki <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) için .NET Framework 4. 6 '4.6 ile', '4.5' değil başlar.</span><span class="sxs-lookup"><span data-stu-id="4dfa8-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="4dfa8-104">Hangi .NET Framework sürümlerinin bir makinede yüklü olduğunu öğrenmek için bu kayıt defteri anahtarlarını bağımlı uygulamalar, 4.6 mümkün olan yeni bir sürüm olduğunu ve önceki 4.5.x ile uyumlu olan bir serbest anlamak için güncelleştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="4dfa8-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="4dfa8-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="4dfa8-105">Suggestion</span></span>|<span data-ttu-id="4dfa8-106">.NET Framework 4.5 için yoklama uygulamaları güncelleştir 4.5 kayıt defteri anahtarlarını da 4.6 kabul edecek şekilde bakarak yükleyin.</span><span class="sxs-lookup"><span data-stu-id="4dfa8-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="4dfa8-107">Kapsam</span><span class="sxs-lookup"><span data-stu-id="4dfa8-107">Scope</span></span>|<span data-ttu-id="4dfa8-108">Kenar</span><span class="sxs-lookup"><span data-stu-id="4dfa8-108">Edge</span></span>|
|<span data-ttu-id="4dfa8-109">Sürüm</span><span class="sxs-lookup"><span data-stu-id="4dfa8-109">Version</span></span>|<span data-ttu-id="4dfa8-110">4.6</span><span class="sxs-lookup"><span data-stu-id="4dfa8-110">4.6</span></span>|
|<span data-ttu-id="4dfa8-111">Tür</span><span class="sxs-lookup"><span data-stu-id="4dfa8-111">Type</span></span>|<span data-ttu-id="4dfa8-112">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="4dfa8-112">Runtime</span></span>|

