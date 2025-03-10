---
title: -addmodule (C# derleyici seçenekleri)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: f2fae0be3ba958dc9776ed253c178933e4f76024
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69607039"
---
# <a name="-addmodule-c-compiler-options"></a>-addmodule (C# derleyici seçenekleri)
Bu seçenek, target: Module anahtarı geçerli derlemeye ile oluşturulmuş bir modül ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a>Arguments  
 `file`, `file2`  
 Meta veri içeren bir çıkış dosyası. Dosya, bütünleştirilmiş kod bildirimi içeremez. Birden fazla dosyayı içeri aktarmak için, dosya adlarını virgülle veya noktalı virgülle ayırın.  
  
## <a name="remarks"></a>Açıklamalar  
 **-Addmodule** ile eklenen tüm modüller, çalışma zamanında çıkış dosyası ile aynı dizinde olmalıdır. Diğer bir deyişle, derleme zamanında herhangi bir dizinde bir modül belirtebilirsiniz, ancak modülün çalışma zamanında uygulama dizininde olması gerekir. Modül, çalışma zamanında uygulama dizininde değilse, bir <xref:System.TypeLoadException>alırsınız.  
  
 `file`bütünleştirilmiş kod içeremez. Örneğin, çıkış dosyası [-target: Module](./target-module-compiler-option.md)ile oluşturulduysa, meta verileri **-addmodule**ile içeri aktarılabilir.  
  
 Çıkış dosyası **-target: Module**dışında bir **-target** seçeneği ile oluşturulduysa, meta verileri **-addmodule** ile içeri aktarılamaz ancak [-Reference](./reference-compiler-option.md)ile içeri aktarılabilir.  
  
 Bu derleyici seçeneği Visual Studio 'da kullanılamaz; bir proje bir modüle başvuramaz. Ayrıca, bu derleyici seçeneği program aracılığıyla değiştirilemez.  
  
## <a name="example"></a>Örnek  
 Kaynak dosyasını `input.cs` derleyin, ve ' `metad1.netmodule` `metad2.netmodule` dan meta verileri ekleyin `out.exe`:  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Derleyici Seçenekleri](./index.md)
- [Proje ve Çözüm Özelliklerini Yönetme](/visualstudio/ide/managing-project-and-solution-properties)
- [Çok Dosyalı Bütünleştirilmiş Kodlar](../../../framework/app-domains/multifile-assemblies.md)
- [Nasıl yapılır: Çoklu dosya derlemesi oluşturma](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
