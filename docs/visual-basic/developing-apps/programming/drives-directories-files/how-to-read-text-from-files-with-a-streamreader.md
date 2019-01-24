---
title: 'Nasıl yapılır: (Visual Basic) StreamReader olan dosyalardaki metni okuma'
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 829b515a6f99799e26da40aa8ee4ed41130dbc20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660066"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a>Nasıl yapılır: (Visual Basic) StreamReader olan dosyalardaki metni okuma
`My.Computer.FileSystem` Nesne açmak için yöntemler sağlar bir <xref:System.IO.TextReader> ve <xref:System.IO.TextWriter>. Bu yöntemler `OpenTextFileWriter` ve `OpenTextFileReader`, seçtiğiniz sürece Intellisense'te görünmez yöntemleri Gelişmiş **tüm** sekmesi.  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a>Bir dosyadan metin okuyucu ile bir satır okunamadı  
  
-   Kullanım `OpenTextFileReader` açmak için yöntemi <xref:System.IO.TextReader>, dosya belirtme. Bu örnek adlı bir dosya açar `testfile.txt`bir satır okur ve satırı bir ileti kutusunda görüntüler.  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Okunan Dosya bir metin dosyası olmalıdır.  
  
 Dosya adına dayanarak dosyanın içeriği ile ilgili kararlar vermeyin. Örneğin, Form1.vb dosyası bir Visual Basic kaynak dosyası olmayabilir.  
  
 Verileri uygulamanızda kullanmadan önce tüm girişleri doğrulayın. Dosyanın içeriği beklendiği gibi olmayabilir ve dosyadan okuma yöntemleri başarısız olabilir.  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 Bir dosyadan okunan, derlemenizin ayrıcalık düzeyi verilen tarafından gerektirir <xref:System.Security.Permissions.FileIOPermission> sınıfı. Kısmi güven bağlamda çalıştırıyorsanız, kod bir özel durum yetersiz ayrıcalıklar nedeniyle fırlatabilir. Daha fazla bilgi için [kod erişimi güvenliği Temelleri](../../../../framework/misc/code-access-security-basics.md). Kullanıcının dosyaya erişimi de olmalıdır. Daha fazla bilgi için [ACL teknolojisine genel bakış](https://msdn.microsoft.com/library/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:System.Windows.Forms.OpenFileDialog>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>
- [SaveFileDialog Bileşeni](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)
- [Dosyalardan Okuma](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
