---
title: ImageList Bileşenine Genel Bakış (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ImageList
helpviewer_keywords:
- collection controls [Windows Forms], images
- icon list control
- ImageList component [Windows Forms], about ImageList component
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
ms.openlocfilehash: 9869e647613ccf009954a5d65445947fbced40e7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709854"
---
# <a name="imagelist-component-overview-windows-forms"></a>ImageList Bileşenine Genel Bakış (Windows Forms)

Windows Forms <xref:System.Windows.Forms.ImageList> bileşen denetimleri tarafından görüntülenebilen, görüntüleri depolamak için kullanılır. Görüntü listesi tek, tutarlı bir katalog görüntüleri için kod yazmanıza olanak sağlar. Tarafından görüntülenen görüntüleri döndürme gibi bir <xref:System.Windows.Forms.Button> düğmenin değiştirerek yalnızca denetim <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> veya <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> özelliği. Ayrıca, aynı görüntü listesi birden çok denetimlerle ilişkilendirebilirsiniz. Örneğin, her ikisini de kullanıyorsanız bir <xref:System.Windows.Forms.ListView> denetimi ve bir <xref:System.Windows.Forms.TreeView> denetimi dosyaları, görüntü listesi bir dosyanın simgesini değiştirme aynı listesini görüntülemek için her iki görünümde de görünen için yeni simgesine neden olur.

## <a name="using-imagelist-with-controls"></a>ImageList denetimler ile kullanma

Görüntü listesi olan herhangi bir denetim ile kullanabileceğiniz bir `ImageList` özelliği — veya durumunda <xref:System.Windows.Forms.ListView> denetimi <xref:System.Windows.Forms.ListView.SmallImageList%2A> ve <xref:System.Windows.Forms.ListView.LargeImageList%2A> özellikleri. Görüntü listesi ile ilişkilendirilebilir denetimleri içerir: <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, ve <xref:System.Windows.Forms.Label> kontrol eder. Görüntü listesi denetimi ile ilişkilendirmek için denetimin ayarlamak `ImageList` adını özelliğini <xref:System.Windows.Forms.ImageList> bileşeni.

## <a name="key-properties"></a>Anahtar Özellikler

Anahtar özelliği <xref:System.Windows.Forms.ImageList> bileşeni <xref:System.Windows.Forms.ImageList.Images%2A>, içerir ilişkili bir denetim tarafından kullanılacak resim. Tek tek her görüntü dizini değerini veya anahtarıyla tarafından erişilebilir. <xref:System.Windows.Forms.ImageList.ColorDepth%2A> Özelliği ile görüntüleri işlenen renk sayısını belirler. Görüntüleri tümü aynı boyutta belirlediği görüntülenir <xref:System.Windows.Forms.ImageList.ImageSize%2A> özelliği. Daha büyük görüntüleri uyacak şekilde ayarlanacaktır.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.ImageList>
- [Nasıl yapılır: Windows Forms ImageList bileşeni ile görüntüleri eklemek veya kaldırmak](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)