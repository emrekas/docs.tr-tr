---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 5555f83107a40b40c7f05c7cc5729f721727f67c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793945"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)
Yönetilen kaynağa bağlantı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Gerekli. Derlemeye bağlamak için kaynak dosyası. Dosya adı boşluk içeriyorsa adı tırnak içine alın. ("").  
  
 `identifier`  
 İsteğe bağlı. Kaynağın mantıksal adı. Kaynak yüklemek için kullanılan ad. Varsayılan dosya adıdır. İsteğe bağlı olarak, dosyayı örneğin genel veya özel derleme bildiriminde olup olmadığını belirtebilirsiniz: `-linkres:filename.res,myname.res,public`. Varsayılan olarak, `filename` derleme içinde geneldir.  
  
## <a name="remarks"></a>Açıklamalar  
 `-linkresource` Kullanın; seçeneği değil ekleme kaynak dosyası çıkış dosyasına `-resource` Bunu yapmak için seçeneği.  
  
 `-linkresource` Seçeneği birini gerektirir `-target` dışında seçenekleri `-target:module`.  
  
 Varsa `filename` olduğu bir [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] , örneğin, göre oluşturulmuş kaynak dosyası [Resgen.exe (kaynak dosya oluşturucu)](../../../framework/tools/resgen-exe-resource-file-generator.md) veya geliştirme ortamında üyelerle erişilebileceğini <xref:System.Resources> ad alanı. (Daha fazla bilgi için <xref:System.Resources.ResourceManager>.) Çalışma zamanında diğer kaynaklara erişmek için Şununla yöntemleri kullanan `GetManifestResource` içinde <xref:System.Reflection.Assembly> sınıfı.  
  
 Dosya adı, herhangi bir dosya biçiminde olabilir. Örneğin, böylece genel derleme önbelleğine yüklenebilir ve derlemedeki yönetilen koddan erişilebilir bütünleştirilmiş kodun yerel bir DLL parçası haline getirmek isteyebilirsiniz.  
  
 Kısa formunu da `-linkresource` olduğu `-linkres`.  
  
> [!NOTE]
>  `-linkresource` Seçeneği Visual Studio geliştirme ortamından kullanılamaz; yalnızca komut satırından derleme yaptığınızda kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod derlenir `in.vb` ve kaynak dosyası bağlantılar `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Kaynak (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Örnek Derleme Komut Satırları](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
