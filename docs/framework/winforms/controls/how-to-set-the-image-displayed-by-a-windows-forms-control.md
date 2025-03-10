---
title: 'Nasıl yapılır: Windows Forms Denetimi Tarafından Görüntülenen Resmi Ayarlama'
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: b1b1dbbb50c3b19cf8d8a7d7030d0bc168afb6a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666196"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Nasıl yapılır: Windows Forms denetimi tarafından gösterilecek resmi ayarlama

Birçok Windows Forms denetimi görüntü görüntüleyebilir. Bu görüntüler, Kaydet komutunu gösteren bir düğmedeki disket simgesi gibi denetimin amacını açıklığa kavuşturacak simgeler olabilir. Alternatif olarak, simgeler istediğiniz görünümü ve davranışı denetlemek için arka plan görüntüleri olabilir.

## <a name="programmatic"></a>Programatik

Denetimin `Image` veya `BackgroundImage` özelliğini türünde<xref:System.Drawing.Image>bir nesne olarak ayarlayın. Genellikle, <xref:System.Drawing.Image.FromFile%2A> yöntemini kullanarak görüntüyü bir dosyadan yüklersiniz.

Aşağıdaki kod örneğinde, görüntü konumu için ayarlanan yol **Resimlerim** klasörüdür. Windows işletim sistemini çalıştıran bilgisayarların çoğu bu dizini içerir. Bu Ayrıca, en az sistem erişim düzeylerine sahip kullanıcıların uygulamayı güvenle çalıştırmasına olanak sağlar. Aşağıdaki kod örneği, bir <xref:System.Windows.Forms.PictureBox> denetim eklenmiş bir formunuza sahip olmanızı gerektirir.

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a>Tasarımcı

1. Visual Studio 'nun **Özellikler** penceresinde, denetimin **görüntüsünü** veya **BackgroundImage** özelliğini seçin ve ardından Seç ' i göstermek için üç nokta (![Visual Studio](./media/visual-studio-ellipsis-button.png)'da üç nokta düğmesini) seçin  **Kaynak** iletişim kutusu.

2. Göstermek istediğiniz görüntüyü seçin.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
