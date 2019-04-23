---
title: 'Nasıl yapılır: LINQ (Visual Basic) kullanarak bir saklı yordamı çağırma'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: af25ebe10681ebb1c346f90afc0291e53224833a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319579"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Nasıl yapılır: LINQ (Visual Basic) kullanarak bir saklı yordamı çağırma
Dil ile tümleşik sorgu (LINQ), veritabanı bilgileri, veritabanı nesneleri gibi depolanan yordamları da dahil olmak üzere erişim kolaylaştırır.  
  
 Aşağıdaki örnek, bir SQL Server veritabanında bir saklı yordamı çağıran bir uygulama oluşturma işlemi gösterilmektedir. Örnek veritabanında iki farklı saklı yordam çağırmak nasıl gösterir. Her yordam, bir sorgunun sonuçlarını döndürür. Bir yordam giriş parametreleri alır ve diğer yordam parametre almaz.  
  
 Bu konudaki örnekler, Northwind örnek veritabanını kullanır. Geliştirme bilgisayarınızda bu veritabanı yoksa Microsoft Download Center'dan gelen indirebilirsiniz. Yönergeler için [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Bir veritabanına bir bağlantı oluşturmak için  
  
1. Visual Studio'da açın **Sunucu Gezgini**/**veritabanı Gezgini** tıklayarak **Sunucu Gezgini**/**veritabanı Explorer** üzerinde **görünümü** menüsü.  
  
2. Sağ **veri bağlantıları** içinde **Sunucu Gezgini**/**veritabanı Gezgini** ve ardından **Bağlantı Ekle**.  
  
3. Northwind örnek veritabanıyla kurulan geçerli bir bağlantı belirtin.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>LINQ to SQL dosyası içeren bir proje eklemek için  
  
1. Visual Studio'da üzerinde **dosya** menüsünde **yeni** ve ardından **proje**. Visual Basic seçin **Windows Forms uygulaması** proje türü.  
  
2. Üzerinde **proje** menüsünü tıklatın **Yeni Öğe Ekle**. Seçin **LINQ to SQL sınıfları** öğe şablonu.  
  
3. Dosyayı `northwind.dbml` olarak adlandırın. **Ekle**'yi tıklatın. Object Relational Designer (O/R Tasarımcısı) için northwind.dbml dosyası açılır.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>O/R Tasarımcısı için saklı yordamlar eklemek için  
  
1. İçinde **Sunucu Gezgini**/**veritabanı Gezgini**, Northwind veritabanına bağlantı genişletin. Genişletin **saklı yordamlar** klasör.  
  
     O/R Tasarımcısı kapattıysanız, daha önce eklediğiniz northwind.dbml dosyasına çift tıklayarak açabilirsiniz.  
  
2. Tıklayın **yıla göre satış** saklı yordam ve tasarımcısının sağ bölmeye sürükleyin. Tıklayın **on en pahalı ürün** saklı yordam, tasarımcının sağ bölmeye sürükleyin.  
  
3. Değişikliklerinizi kaydetmek ve Tasarımcısı'nı kapatın.  
  
4. Projenizi kaydedin.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Saklı yordamları sonuçlarını görüntülemek için kod eklemek için  
  
1. Gelen **araç kutusu**, sürükleyin bir <xref:System.Windows.Forms.DataGridView> Form1 projeniz için varsayılan Windows Form denetimi.  
  
2. Form1 kod eklemek için çift tıklayın, `Load` olay.  
  
3. Tasarımcı saklı yordamlar için O/R Tasarımcısı eklendiğinde, eklenen bir <xref:System.Data.Linq.DataContext> projeniz için nesne. Bu nesne, bu yordamları erişmek için gereken kodu içerir. <xref:System.Data.Linq.DataContext> Nesne proje adı için bir .dbml dosyası adına bağlı. Bu proje için <xref:System.Data.Linq.DataContext> nesne adlı `northwindDataContext`.  
  
     Bir örneği oluşturabilir <xref:System.Data.Linq.DataContext> , kodu ve çağrı O/R tasarımcısı tarafından belirtilen saklı yordam yöntemleri. Bağlanacak <xref:System.Windows.Forms.DataGridView> nesnesini çağırarak hemen yürütme için sorguyu zorlamak sahip olabileceğiniz <xref:System.Linq.Enumerable.ToList%2A> saklı yordam sonuçlarında yöntemi.  
  
     Aşağıdaki kodu ekleyin `Load` veri Bağlamınızı yöntemler olarak kullanıma sunulan saklı yordamlardan birini çağrılacak olay.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. Projenizi çalıştırma ve sonuçları görüntülemek için F5 tuşuna basın.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Sorgular](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext Metotları (O/R Tasarımcısı)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Nasıl yapılır: Güncelleştirme, ekleme ve silme işlemleri gerçekleştirmek için saklı yordamlar atama (O/R Tasarımcısı)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
