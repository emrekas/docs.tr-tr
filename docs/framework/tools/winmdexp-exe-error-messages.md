---
title: Winmdexp.exe Hata İletileri
ms.date: 03/30/2017
f1_keywords:
- WME1095
- WME1110
- WME15
- WME1094
- WME1078
- WME1080
- WME1014
- WME1025
- WME1089
- WME1111
- WME1010
- WME1013
- WME1055
- WME1005
- WME1033
- WME1003
- WME1011
- WME1046
- WME0013
- WME1032
- WME1029
- WME1048
- WME1019
- WME1106
- WME0012
- WME1017
- WME1098
- WME1039
- WME20
- WME1006
- WME1088
- WME0004
- WME10
- WME12
- WME0015
- WME0017
- WME1026
- WME1045
- WME1002
- WME1051
- WME1107
- WME1100
- WME1072
- WME1090
- WME1105
- WME1022
- WME11
- WME17
- WME1063
- WME1041
- WME1057
- WME1037
- WME1007
- WME3
- WME1096
- WME0003
- WME0006
- WME1065
- WME1102
- WME1070
- WME1113
- WME1064
- WME1061
- WME1066
- WME1018
- WME1049
- WME1027
- WME1101
- WME1058
- WME0005
- WME1083
- WME1004
- WME1073
- WME1087
- WME1077
- WME19
- WME1086
- WME1085
- WME1040
- WME8
- WME1081
- WME1023
- WME4
- WME1050
- WME7
- WME1091
- WME14
- WME0007
- WME1024
- WME1012
- WME1036
- WME0010
- WME1104
- WME1035
- WME1021
- WME1075
- WME5
- WME13
- WME1074
- WME1028
- WME0014
- WME1030
- WME1008
- WME1052
- WME1079
- WME1054
- WME1093
- WME1042
- WME2
- WME1062
- WME6
- WME1001
- WME0011
- WME16
- WME0001
- WME1020
- WME1084
- WME1103
- WME1092
- WME1
- WME0002
- WME1112
- WME1016
- WME1060
- WME0008
- WME0016
- WME1097
- WME1034
- WME1108
- WME1082
- WME1099
- WME1069
- WME1031
- WME1009
- WME1068
- WME1067
- WME1059
- WME18
- WME1038
- WME0009
- WME1109
- WME1056
- WME1076
- WME1071
- WME1044
- WME1043
- WME1053
- WME1015
- WME1047
- WME9
helpviewer_keywords:
- Winmdexp.exe, error messages
- Windows Runtime Metadata Export Tool, error messages
- error messages, Winmdexp.exe
ms.assetid: 8271973c-deba-47a6-8e5e-04ce63f146ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99fa84b8dea326bc7a32ff4f3c3187acc9883748
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61919405"
---
# <a name="winmdexpexe-error-messages"></a><span data-ttu-id="d614f-102">Winmdexp.exe Hata İletileri</span><span class="sxs-lookup"><span data-stu-id="d614f-102">Winmdexp.exe Error Messages</span></span>
<span data-ttu-id="d614f-103">Yapı işleminin çağırdığı [Winmdexp.exe (Windows çalışma zamanı meta verileri dışarı aktarma aracı)](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md) kullandığınızda  **[!INCLUDE[wrt](../../../includes/wrt-md.md)] bileşen** 2012'de Visual Studio içinde Winmdexp.exe hata iletileri görünecek şekilde şablonu **Hata listesi**.</span><span class="sxs-lookup"><span data-stu-id="d614f-103">The build process calls [Winmdexp.exe (Windows Runtime Metadata Export Tool)](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md) when you use the **[!INCLUDE[wrt](../../../includes/wrt-md.md)] Component** template in Visual Studio 2012, so Winmdexp.exe error messages appear in the **Error List**.</span></span> <span data-ttu-id="d614f-104">Winmdexp.exe çalışır ile derlenmiş bir modülde `/target:winmdobj` seçeneği.</span><span class="sxs-lookup"><span data-stu-id="d614f-104">Winmdexp.exe operates on a module that is compiled with the `/target:winmdobj` option.</span></span> <span data-ttu-id="d614f-105">Giriş olarak derlenmiş bir modül gerektiğinden, derleme başarılı sürece, hata iletileri görünmez.</span><span class="sxs-lookup"><span data-stu-id="d614f-105">Because it requires a compiled module as input, its error messages don't appear unless compilation succeeds.</span></span>  
  
 <span data-ttu-id="d614f-106">Hata iletileri, bunlar rapor hata koşullarını gidermek için gereken tüm bilgileri içerecek şekilde tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="d614f-106">The error messages are designed to contain all the information you need to address the error conditions they report.</span></span> <span data-ttu-id="d614f-107">Ancak, bazı sorunlar iletisinde sığmayacak kadar çok daha fazla bilgi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="d614f-107">However, some problems require more information than will fit in the message.</span></span> <span data-ttu-id="d614f-108">Ek bilgiler bulabilirsiniz [tanılama Windows çalışma zamanı bileşeni hata koşulları](https://go.microsoft.com/fwlink/p/?LinkId=251127) Windows geliştirme Merkezi'nde.</span><span class="sxs-lookup"><span data-stu-id="d614f-108">You can find additional information in [Diagnosing Windows Runtime component error conditions](https://go.microsoft.com/fwlink/p/?LinkId=251127) in the Windows Dev Center.</span></span>  
  
 <span data-ttu-id="d614f-109">Hata bu makalede ele alınmamıştır ve ileti sorunu gidermek için yeterli bilgi içermiyor düşünüyorsanız, lütfen bu makalede geri bildirim bağlantısını kullanın ve hata iletisini içerir.</span><span class="sxs-lookup"><span data-stu-id="d614f-109">If your error is not discussed in that article, and you feel that the message doesn't contain sufficient information to address the issue, please use the feedback link in that article and include the error message.</span></span> <span data-ttu-id="d614f-110">Bir hata, alternatif olarak, dosya [Microsoft Connect Web sitesi](https://go.microsoft.com/fwlink/p/?LinkId=251130).</span><span class="sxs-lookup"><span data-stu-id="d614f-110">Alternatively, you can file a bug at the [Microsoft Connect website](https://go.microsoft.com/fwlink/p/?LinkId=251130).</span></span> <span data-ttu-id="d614f-111">Ayrıca daha fazla bilgi için bakabilirsiniz [Microsoft Forums](https://go.microsoft.com/fwlink/p/?LinkId=251129).</span><span class="sxs-lookup"><span data-stu-id="d614f-111">You can also look for more information on the [Microsoft Forums](https://go.microsoft.com/fwlink/p/?LinkId=251129).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d614f-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d614f-112">See also</span></span>

- [<span data-ttu-id="d614f-113">Winmdexp.exe (Windows Çalışma Zamanı Meta Veri Dışarı Aktarma Aracı)</span><span class="sxs-lookup"><span data-stu-id="d614f-113">Winmdexp.exe (Windows Runtime Metadata Export Tool)</span></span>](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md)
- [<span data-ttu-id="d614f-114">Windows çalışma zamanı bileşeni hata durumları tanılama</span><span class="sxs-lookup"><span data-stu-id="d614f-114">Diagnosing Windows Runtime component error conditions</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=251127)
