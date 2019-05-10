---
title: 'Nasıl yapılır: Windows Forms BindingSource Bileşeni ile ADO.NET Verilerini Sıralama ve Filtreleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: d05cbdf63483c160603ee44f6b507edc2d13b170
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651936"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Nasıl yapılır: Windows Forms BindingSource Bileşeni ile ADO.NET Verilerini Sıralama ve Filtreleme
Sıralama ve filtreleme özelliğini kullanıma sunabileceğiniz <xref:System.Windows.Forms.BindingSource> aracılığıyla denetim <xref:System.Windows.Forms.BindingSource.Sort%2A> ve <xref:System.Windows.Forms.BindingSource.Filter%2A> özellikleri. Temel alınan veri kaynağı olduğunda basit sıralama uygulayabileceğiniz bir <xref:System.ComponentModel.IBindingList>, ve gelişmiş veri kaynağı olduğunda sıralama ve filtreleme uygulayabilirsiniz bir <xref:System.ComponentModel.IBindingListView>. <xref:System.Windows.Forms.BindingSource.Sort%2A> Özelliği gerektiren standart [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] söz dizimi: bir veri kaynağındaki veri sütununun adını temsil eden bir dize tarafından izlenen `ASC` veya `DESC` listesini artan veya azalan olarak sıralanması gerektiğini belirtmek için. Gelişmiş sıralama veya bir virgül ayırıcısına ile her bir sütunun ayrılarak birden çok sütun sıralama ayarlayabilirsiniz. <xref:System.Windows.Forms.BindingSource.Filter%2A> Özelliği bir dize ifadesi alır.  
  
> [!NOTE]
>  Depolama bağlantı dizesi içinde bir parola gibi hassas bilgileri, uygulamanızın güvenliğini etkileyebilir. Windows Kimlik Doğrulaması (tümleşik güvenlik olarak da bilinir) kullanılarak bir veritabanına erişimi denetlemek için daha güvenli bir yoldur. Daha fazla bilgi için [bağlantı bilgilerini koruma](../../data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Verileri BindingSource ile filtreleme  
  
- Ayarlama <xref:System.Windows.Forms.BindingSource.Filter%2A> özelliğini istediğiniz ifade.  
  
     Aşağıdaki kod örneğinde sütun için istediğiniz değere göre ve ardından bir sütun adı bir ifadedir.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Verileri BindingSource ile sıralama  
  
1. Ayarlama <xref:System.Windows.Forms.BindingSource.Sort%2A> özelliğini istediğiniz sütun adından `ASC` veya `DESC` artan veya azalan belirtmek için.  
  
2. Birden çok sütun virgül ile ayırın.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, Northwind örnek veritabanına, Müşteriler tablosundan verileri yükler. bir <xref:System.Windows.Forms.DataGridView> denetlemek, filtreler ve görüntülenen verileri sıralar.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örneği çalıştırmak için kodu içeren bir biçime yapıştırın bir <xref:System.Windows.Forms.BindingSource> adlı `BindingSource1` ve <xref:System.Windows.Forms.DataGridView> adlı `dataGridView1`. Tanıtıcı <xref:System.Windows.Forms.Form.Load> olay formu ve çağrı `InitializeSortedFilteredBindingSource` yük olay işleyicisi yönteminde.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Nasıl yapılır: Örnek veritabanlarını yüklemek](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [BindingSource Bileşeni](bindingsource-component.md)
