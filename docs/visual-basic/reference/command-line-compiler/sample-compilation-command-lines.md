---
title: Örnek Derleme Komut Satırları (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: b7879c23bc64269c793c21b61b84d6f0fd4bdc24
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046287"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Örnek derleme komut satırları (Visual Basic)

Visual Studio içinden Visual Basic programları derlemeye alternatif olarak, çalıştırılabilir (. exe) dosyalar veya dinamik bağlantı kitaplığı (. dll) dosyaları oluşturmak için komut satırından derleme yapabilirsiniz.

Visual Basic komut satırı derleyicisi, giriş ve çıkış dosyalarını, derlemeleri ve hata ayıklama ve Önişlemci seçeneklerini denetleyen tam bir seçenek kümesini destekler. Her seçenek, iki değiştirilebilir formda mevcuttur: `-option` ve. `/option` Bu belgede yalnızca `-option` form gösterilmektedir.

Aşağıdaki tabloda, kendi kullanımı için değiştirebileceğiniz bazı örnek komut satırları listelenmektedir.

|Bitiş|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------|---------|
|Dosya. vb dosyasını derleyin ve File. exe oluşturun|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|File. vb dosyasını derleyin ve File. dll dosyasını oluşturun|`vbc -target:library File.vb`|
|Dosya. vb 'yi derleyin ve My. exe dosyasını oluşturun|`vbc -out:My.exe File.vb`|
|File. vb derleyin ve hem bir kitaplık hem de File. dll adlı bir başvuru derlemesi oluşturun|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Geçerli dizindeki tüm Visual Basic dosyalarını, iyileştirmeler açık ve `DEBUG` tanımlanan sembolle derleyin, dosya2. exe dosyasını üretir|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|Logo veya uyarıları görüntülemeden dosya2. dll ' nin hata ayıklama sürümünü üreten geçerli dizindeki tüm Visual Basic dosyalarını derleyin|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|Geçerli dizindeki tüm Visual Basic dosyalarını bir. dll dosyasına derle|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> Visual Studio IDE kullanarak bir proje oluşturduğunuzda, ilişkili **vbc** komutuyla ilgili bilgileri çıkış penceresinde derleyici seçenekleriyle birlikte görüntüleyebilirsiniz. Bu bilgileri göstermek için, [Seçenekler Iletişim kutusu, projeler ve çözümler ' i açın ve çalıştırın](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), sonra **MSBuild proje yapı çıkış ayrıntı** düzeyini **normal** veya daha yüksek ayrıntı düzeyi olarak ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)
- [Koşullu Derleme](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
