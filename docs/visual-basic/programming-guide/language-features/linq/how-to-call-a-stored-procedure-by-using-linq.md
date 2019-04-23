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
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="f7357-102">Nasıl yapılır: LINQ (Visual Basic) kullanarak bir saklı yordamı çağırma</span><span class="sxs-lookup"><span data-stu-id="f7357-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="f7357-103">Dil ile tümleşik sorgu (LINQ), veritabanı bilgileri, veritabanı nesneleri gibi depolanan yordamları da dahil olmak üzere erişim kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="f7357-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="f7357-104">Aşağıdaki örnek, bir SQL Server veritabanında bir saklı yordamı çağıran bir uygulama oluşturma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="f7357-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="f7357-105">Örnek veritabanında iki farklı saklı yordam çağırmak nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="f7357-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="f7357-106">Her yordam, bir sorgunun sonuçlarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="f7357-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="f7357-107">Bir yordam giriş parametreleri alır ve diğer yordam parametre almaz.</span><span class="sxs-lookup"><span data-stu-id="f7357-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="f7357-108">Bu konudaki örnekler, Northwind örnek veritabanını kullanır.</span><span class="sxs-lookup"><span data-stu-id="f7357-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="f7357-109">Geliştirme bilgisayarınızda bu veritabanı yoksa Microsoft Download Center'dan gelen indirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7357-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="f7357-110">Yönergeler için [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f7357-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="f7357-111">Bir veritabanına bir bağlantı oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="f7357-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="f7357-112">Visual Studio'da açın **Sunucu Gezgini**/**veritabanı Gezgini** tıklayarak **Sunucu Gezgini**/**veritabanı Explorer** üzerinde **görünümü** menüsü.</span><span class="sxs-lookup"><span data-stu-id="f7357-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="f7357-113">Sağ **veri bağlantıları** içinde **Sunucu Gezgini**/**veritabanı Gezgini** ve ardından **Bağlantı Ekle**.</span><span class="sxs-lookup"><span data-stu-id="f7357-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="f7357-114">Northwind örnek veritabanıyla kurulan geçerli bir bağlantı belirtin.</span><span class="sxs-lookup"><span data-stu-id="f7357-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="f7357-115">LINQ to SQL dosyası içeren bir proje eklemek için</span><span class="sxs-lookup"><span data-stu-id="f7357-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="f7357-116">Visual Studio'da üzerinde **dosya** menüsünde **yeni** ve ardından **proje**.</span><span class="sxs-lookup"><span data-stu-id="f7357-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="f7357-117">Visual Basic seçin **Windows Forms uygulaması** proje türü.</span><span class="sxs-lookup"><span data-stu-id="f7357-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="f7357-118">Üzerinde **proje** menüsünü tıklatın **Yeni Öğe Ekle**.</span><span class="sxs-lookup"><span data-stu-id="f7357-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="f7357-119">Seçin **LINQ to SQL sınıfları** öğe şablonu.</span><span class="sxs-lookup"><span data-stu-id="f7357-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="f7357-120">Dosyayı `northwind.dbml` olarak adlandırın.</span><span class="sxs-lookup"><span data-stu-id="f7357-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="f7357-121">**Ekle**'yi tıklatın.</span><span class="sxs-lookup"><span data-stu-id="f7357-121">Click **Add**.</span></span> <span data-ttu-id="f7357-122">Object Relational Designer (O/R Tasarımcısı) için northwind.dbml dosyası açılır.</span><span class="sxs-lookup"><span data-stu-id="f7357-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="f7357-123">O/R Tasarımcısı için saklı yordamlar eklemek için</span><span class="sxs-lookup"><span data-stu-id="f7357-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="f7357-124">İçinde **Sunucu Gezgini**/**veritabanı Gezgini**, Northwind veritabanına bağlantı genişletin.</span><span class="sxs-lookup"><span data-stu-id="f7357-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="f7357-125">Genişletin **saklı yordamlar** klasör.</span><span class="sxs-lookup"><span data-stu-id="f7357-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="f7357-126">O/R Tasarımcısı kapattıysanız, daha önce eklediğiniz northwind.dbml dosyasına çift tıklayarak açabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7357-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="f7357-127">Tıklayın **yıla göre satış** saklı yordam ve tasarımcısının sağ bölmeye sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="f7357-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="f7357-128">Tıklayın **on en pahalı ürün** saklı yordam, tasarımcının sağ bölmeye sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="f7357-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="f7357-129">Değişikliklerinizi kaydetmek ve Tasarımcısı'nı kapatın.</span><span class="sxs-lookup"><span data-stu-id="f7357-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="f7357-130">Projenizi kaydedin.</span><span class="sxs-lookup"><span data-stu-id="f7357-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="f7357-131">Saklı yordamları sonuçlarını görüntülemek için kod eklemek için</span><span class="sxs-lookup"><span data-stu-id="f7357-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="f7357-132">Gelen **araç kutusu**, sürükleyin bir <xref:System.Windows.Forms.DataGridView> Form1 projeniz için varsayılan Windows Form denetimi.</span><span class="sxs-lookup"><span data-stu-id="f7357-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="f7357-133">Form1 kod eklemek için çift tıklayın, `Load` olay.</span><span class="sxs-lookup"><span data-stu-id="f7357-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="f7357-134">Tasarımcı saklı yordamlar için O/R Tasarımcısı eklendiğinde, eklenen bir <xref:System.Data.Linq.DataContext> projeniz için nesne.</span><span class="sxs-lookup"><span data-stu-id="f7357-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="f7357-135">Bu nesne, bu yordamları erişmek için gereken kodu içerir.</span><span class="sxs-lookup"><span data-stu-id="f7357-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="f7357-136"><xref:System.Data.Linq.DataContext> Nesne proje adı için bir .dbml dosyası adına bağlı.</span><span class="sxs-lookup"><span data-stu-id="f7357-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="f7357-137">Bu proje için <xref:System.Data.Linq.DataContext> nesne adlı `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="f7357-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="f7357-138">Bir örneği oluşturabilir <xref:System.Data.Linq.DataContext> , kodu ve çağrı O/R tasarımcısı tarafından belirtilen saklı yordam yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="f7357-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="f7357-139">Bağlanacak <xref:System.Windows.Forms.DataGridView> nesnesini çağırarak hemen yürütme için sorguyu zorlamak sahip olabileceğiniz <xref:System.Linq.Enumerable.ToList%2A> saklı yordam sonuçlarında yöntemi.</span><span class="sxs-lookup"><span data-stu-id="f7357-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="f7357-140">Aşağıdaki kodu ekleyin `Load` veri Bağlamınızı yöntemler olarak kullanıma sunulan saklı yordamlardan birini çağrılacak olay.</span><span class="sxs-lookup"><span data-stu-id="f7357-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="f7357-141">Projenizi çalıştırma ve sonuçları görüntülemek için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="f7357-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7357-142">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f7357-142">See also</span></span>

- [<span data-ttu-id="f7357-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="f7357-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="f7357-144">Sorgular</span><span class="sxs-lookup"><span data-stu-id="f7357-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="f7357-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f7357-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="f7357-146">DataContext Metotları (O/R Tasarımcısı)</span><span class="sxs-lookup"><span data-stu-id="f7357-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="f7357-147">Nasıl yapılır: Güncelleştirme, ekleme ve silme işlemleri gerçekleştirmek için saklı yordamlar atama (O/R Tasarımcısı)</span><span class="sxs-lookup"><span data-stu-id="f7357-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
