---
title: 'Nasıl yapılır: Tasarımcı Kullanarak Windows Forms Denetimlerini BindingSource Bileşeni ile Bağlama'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 180fafa9ace5927fd84ec5dc0a1b2a342f771efd
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040026"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>Nasıl yapılır: Tasarımcı Kullanarak Windows Forms Denetimlerini BindingSource Bileşeni ile Bağlama
Formunuza denetimler ekledikten ve uygulamanız için Kullanıcı arabirimini belirledikten sonra, denetimleri bir veri kaynağına bağlayabilirsiniz, böylece çalışma zamanında kullanıcılar uygulamayla ilgili verileri değiştirebilir ve kaydedebilir.

 Windows Forms denetimleri veya denetim dizilerini, form ve veri kaynağı denetimleri arasında köprü olarak kullanarak <xref:System.Windows.Forms.BindingSource> kolayca gerçekleştirilebilir.

 Form üzerindeki bir veya daha fazla denetim verilere bağlanabilir; Aşağıdaki yordamda bir <xref:System.Windows.Forms.TextBox> denetim bir veri kaynağına bağlanır.

 Yordamı gerçekleştirmek için bir veritabanından türetilmiş bir veri kaynağına bağlayacağınız varsayılır. Diğer veri mağazalarından veri kaynakları oluşturma hakkında daha fazla bilgi için bkz. [Yeni veri kaynakları ekleme](/visualstudio/data-tools/add-new-data-sources).

## <a name="to-bind-a-control-at-design-time"></a>Tasarım zamanında bir denetimi bağlamak için

1. Formun üzerine <xref:System.Windows.Forms.TextBox> bir denetim sürükleyin.

2. **Özellikler** penceresinde:

    1. **(DataBindings)** düğümünü genişletin.

    2. <xref:System.Windows.Forms.TextBox.Text%2A> Özelliğin yanındaki oka tıklayın.

         **DataSource** Kullanıcı arabirimi tür Düzenleyicisi açılır.

         Bir veri kaynağı daha önce proje veya form için yapılandırıldıysa, görüntülenir.

3. Verilere bağlanmak ve bir veri kaynağı oluşturmak için **proje veri kaynağı Ekle** ' ye tıklayın.

4. **Veri kaynağı Yapılandırma Sihirbazı** 'na hoş geldiniz sayfasında **İleri**' ye tıklayın.

5. **Veri kaynağı türü seç** sayfasında, **veritabanı**' nı seçin.

6. **Veri bağlantınızı seçin** sayfasında, kullanılabilir bağlantılar listesinden bir veri bağlantısı seçin. İstediğiniz veri bağlantınız yoksa yeni bir veri bağlantısı oluşturmak için **Yeni bağlantı** ' yı seçin.

7. **Evet ' i seçin,** bağlantı dizesini uygulama yapılandırma dosyasına kaydetmek için bağlantıyı kaydedin.

8. Uygulamanıza getirmek istediğiniz veritabanı nesnelerini seçin. Bu durumda, <xref:System.Windows.Forms.TextBox> bir tablodaki görüntülenmesini istediğiniz alanı seçin.

9. İsterseniz varsayılan veri kümesi adını değiştirin.

10.           **Son**'a tıklayın.

11. **Özellikler** penceresinde, <xref:System.Windows.Forms.TextBox.Text%2A> özelliğin yanındaki oka tekrar tıklayın. **DataSource** Kullanıcı arabirimi türü düzenleyicisinde, bağlanacak <xref:System.Windows.Forms.TextBox> alanın adını seçin.

     **DataSource** Kullanıcı arabirimi tür Düzenleyicisi kapanır ve veri kümesi <xref:System.Windows.Forms.BindingSource> ve bu veri bağlantısına özgü tablo bağdaştırıcısı formunuza eklenir.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Yeni veri kaynağı ekleme](/visualstudio/data-tools/add-new-data-sources)
- [Veri kaynakları penceresi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
