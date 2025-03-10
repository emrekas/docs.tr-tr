---
title: 'Nasıl yapılır: Windows Forms Denetimleri için Erişim Tuşları Oluşturma'
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: ccec8bba9e01cbaa7bfef841af68a0fcaa720b90
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658375"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Nasıl yapılır: Windows Forms denetimleri için erişim tuşları oluşturma

*Erişim tuşu* , bir menü, menü öğesi veya düğme gibi bir denetimin etiketi içindeki altı çizili bir karakterdir. Bir erişim anahtarı ile Kullanıcı, önceden tanımlanmış erişim anahtarı ile birlikte alt tuşuna basarak bir düğmeyi "tıklaedebilir". Örneğin, bir düğme bir formu yazdırmak için bir yordam çalıştırıyorsa ve bu nedenle `Text` özelliği "Yazdır" olarak ayarlanırsa, "p" harfinden önce bir ampersan eklemek "p" harfinin çalışma zamanında düğme metninde altı çizili olmasına neden olur. Kullanıcı, alt + P tuşlarına basarak düğmeyle ilişkili komutu çalıştırabilir.

Odak alamayan denetimler erişim anahtarlarına sahip olamaz.

## <a name="programmatic"></a>Programatik

`Text` Özelliği, kısayol olacak harften önce bir ve işareti (&) içeren bir dizeye ayarlayın.

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

```cpp
// Set the letter "P" as an access key.
button1->Text = "&Print";
```

> [!NOTE]
> Bir e-posta kutusunda bir erişim anahtarı oluşturmadan bir ve işareti kullanmak için, iki ve işaretleri (& &) dahil edin. Başlıkta tek bir ve işareti görüntülenmediğinde, hiçbir karakter altı çizili değildir.

## <a name="designer"></a>Tasarımcı

Visual Studio 'nun **Özellikler** penceresinde, **metin** özelliğini, erişim tuşu olacak harften önce bir ve işareti (' & ') içeren bir dizeye ayarlayın. Örneğin, "P" harfini erişim anahtarı olarak ayarlamak için **& Yazdır**yazın.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.Button>
- [Nasıl yapılır: Windows Forms Düğme Tıklamalarına Yanıt verme](how-to-respond-to-windows-forms-button-clicks.md)
- [Nasıl yapılır: Windows Forms denetimi tarafından görünen metni ayarlama](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Ayrı Windows Forms Denetimlerini Etiketleme ve Kısayollarını Sunma](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
