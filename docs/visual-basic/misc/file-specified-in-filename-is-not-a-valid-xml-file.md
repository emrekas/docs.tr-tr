---
title: Dosya adında belirtilen dosya geçerli bir XML dosyası değil.
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: ffa39653c20127bb6af5e85654fee940a191fe5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603537"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>Dosya adında belirtilen dosya geçerli bir XML dosyası değil.
Girdiğiniz dosya adı geçerli bir XML dosyası değil. İzin verilen yapısı ve bir XML belgesinin içeriğini belirtmek için bir belge türü tanımı (DTD'nin), Microsoft XML verileri azaltılmış (XDR) şema veya bir XML Şeması Tanım Dili (XSD) şemaya kullanabilirsiniz. XSD şemaları XML dilbilgisi sistemlerinde belirtmek için tercih edilen yolu olan [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].

> [!NOTE]
>  Visual Studio'nun önceki bazı sürümlerinde **XML Tasarımcısı** türü belirtilmiş veri kümeleri ve XML şema Tasarımcısı. **XML Tasarımcısı** XML şema dosyalarını oluşturmak ve düzenlemek için hala kullanılabilir. Ancak, Visual Studio 2012'de, oluşturma ve düzenleme türü belirtilmiş datasets için tasarımcı olan **veri kümesi Tasarımcısı**. Daha fazla bilgi için [oluşturma ve yazılan veri kümelerini düzenleme](/visualstudio/data-tools/creating-and-editing-typed-datasets).

## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

-   Doğru dosya adı sağlayarak denetleyin.

-   Belirtilen dosya içine kontrol etmek istediğiniz XML dosyası yükleyerek geçerli XML içerdiğinden denetleyin **XML Tasarımcısı**. Gelen **XML** menüsünü tıklatın **doğrulamak XML**. Hatalar görüntülenir **görev listesi**.

-   XML dosyası ilişkili bir XML şeması varsa, öğeleri tanımlanmış bir yapı içinde görünür ve tek tek öğelerine içeriğini belirtilen şemada bildirilen veri türleri için uygun olduğunu denetleyin.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml>
- [Nasıl yapılır: Dosya yollarını ayrıştırma](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)