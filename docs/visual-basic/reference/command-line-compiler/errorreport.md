---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: 5471f0783eee5e2c14cf0f140094d5c292a73756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663264"
---
# <a name="-errorreport"></a>-errorreport

Visual Basic derleyici iç derleyici hatalarını nasıl raporlayacağını belirtir.

## <a name="syntax"></a>Sözdizimi

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, Microsoft Visual Basic ekip için bir Visual Basic derleyici iç hatası (ICE) bildirmek için kullanışlı bir yol sağlar. Varsayılan olarak, derleyici, hiçbir bilgi Microsoft'a gönderir. Ancak, derleyici iç hatayla karşılaşırsanız, bu seçenek hata Microsoft'a bildirmenize olanak tanır. Bu bilgiler, Microsoft mühendisleri nedeni belirlemenize yardımcı olur ve Visual Basic'in sonraki sürümüne artırmanıza yardımcı olabilir.

Bir kullanıcının yeteneğini raporları göndermek için makine ve kullanıcı ilkesi izinlerine bağlıdır.

Aşağıdaki tabloda özetlenmiştir etkisini `-errorreport` seçeneği.

|Seçenek|Davranış|
|---|---|
|`prompt`|Derleyici iç hatası meydana gelirse, derleyici toplanan verileri tam görüntüleyebilmesi için bir iletişim kutusu belirir. Hata raporunda herhangi bir önemli bilgi olup olmadığını belirlemek ve bir karar Microsoft'a gönderilip gönderilmeyeceğini yapın. Göndermeden karar ve makine ve kullanıcı ilke ayarları izin, derleyici verilerini Microsoft'a gönderir.|
|`queue`|Hata raporunu kuyruğa alır. Yönetici ayrıcalıklarıyla oturum açtığınızda, son kez oturum açtıktan sonra herhangi bir hata rapor edebilirsiniz (, üç günde birden çok kez hata raporu göndermek isteyip istemediğiniz değil). Bu varsayılan davranıştır olduğunda `-errorreport` seçeneği belirtilmedi.|
|`send`|Derleyici iç hatası oluşur ve makine ve kullanıcı ilke ayarları izin, derleyici verilerini Microsoft'a gönderir.<br /><br /> Seçenek `-errorreport:send` raporlama tarafından etkinleştirilirse hata bilgileri Microsoft'a otomatik olarak göndermeyi dener [Windows hata bildirimi](/windows/desktop/wer/windows-error-reporting) sistem ayarları. |
|`none`|Derleyici iç hatası oluşursa, toplanmaz ve Microsoft'a gönderilir.|

Derleyici, yığın genellikle bazı kaynak kodu içerir hata anında içeren verileri gönderir. Varsa `-errorreport` ile kullanılan [- bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) kaynak dosyanın tümüne gönderilen seçeneği.

Bu seçenek ile en iyi şekilde kullanılır [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) Microsoft mühendisleri daha kolayca yeniden hata verdiğinden seçeneği.

> [!NOTE]
> `-errorreport` Seçeneği, Visual Studio geliştirme ortamında kullanılabilir değil; yalnızca komut satırından derleme yapılırken kullanılabilir.

## <a name="example"></a>Örnek

Aşağıdaki kod, derleme dener `T2.vb`, ve derleyici bir iç derleyici hatası karşılaşırsa, hata raporunu Microsoft'a göndermek ister.

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)
- [Örnek Derleme Komut Satırları](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
