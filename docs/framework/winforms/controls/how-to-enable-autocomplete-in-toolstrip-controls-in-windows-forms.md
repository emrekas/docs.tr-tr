---
title: "Nasıl yapılır: Windows Forms'ta ToolStrip denetiminde AutoComplete seçeneğini etkinleştirme"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: 48c1d24ce2e966f9c078593655da2bc9d84252c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112118"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>Nasıl yapılır: Windows Forms'ta ToolStrip denetiminde AutoComplete seçeneğini etkinleştirme
Aşağıdaki yordam birleştirir bir <xref:System.Windows.Forms.ToolStripLabel> ile bir <xref:System.Windows.Forms.ToolStripComboBox> , bırakılan öğeleri listesi gibi kısa bir süre önce göstermek için Web siteleri ziyaret edilmedi. Kullanıcı listesindeki öğelerin birinin ilk karakterle eşleşen bir karakter yazdığında, öğenin hemen görüntülenir.  
  
> [!NOTE]
>  Otomatik Tamamlama çalışır `ToolStrip` denetimleri gibi geleneksel denetimlerle birlikte çalışan aynı şekilde <xref:System.Windows.Forms.ComboBox> ve <xref:System.Windows.Forms.TextBox>.  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>ToolStrip denetiminde AutoComplete seçeneğini etkinleştirmek için  
  
1.  Oluşturma bir <xref:System.Windows.Forms.ToolStrip> denetlemek ve öğeleri ekleyin.  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2.  Ayarlama <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> özelliği için birleşik giriş kutusu ve etiket <xref:System.Windows.Forms.ToolStripItemOverflow.Never> böylece liste her zaman formun boyutundan bağımsız olarak kullanılabilir.  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3.  Sözcük öğe koleksiyonuna ekleme <xref:System.Windows.Forms.ToolStripComboBox> denetimi.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4.  Ayarlama <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> özellik birleşik giriş kutusunun <xref:System.Windows.Forms.AutoCompleteMode.Append>.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5.  Ayarlama <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> özellik birleşik giriş kutusunun <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [ToolStrip Denetimine Genel Bakış](toolstrip-control-overview-windows-forms.md)
- [ToolStrip Denetim Mimarisi](toolstrip-control-architecture.md)
- [ToolStrip Teknoloiji Özeti](toolstrip-technology-summary.md)
