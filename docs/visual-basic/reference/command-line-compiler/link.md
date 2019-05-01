---
title: -bağlantı (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
ms.openlocfilehash: d8451a028def44ec7d5b629a1c0749321684e4d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789044"
---
# <a name="-link-visual-basic"></a>-bağlantı (Visual Basic)
Derleyici COM tür bilgilerini belirli derlemelerde şu anda derleme proje kullanılabilir hale getirmek neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
-link:fileList  
' -or-  
-l:fileList  
```  
  
## <a name="arguments"></a>Arguments  
  
|Terim|Tanım|  
|---|---|  
|`fileList`|Gerekli. Derleme dosya adlarının virgülle ayrılmış liste. Dosya adı boşluk içeriyorsa adı tırnak içine alın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `-link` Seçeneği, gömülü tür bilgileri içeren bir uygulama dağıtmanıza olanak sağlar. Uygulama, daha sonra bir çalışma zamanı derlemesindeki gömülü tür bilgileri, çalışma zamanı derlemeye bir başvuruda gerek kalmadan uygulayan türler kullanabilirsiniz. Çeşitli çalışma zamanı derleme sürümleri yayımladıysanız, gömülü tür bilgileri içeren uygulama derlenmesi gerek kalmadan çeşitli sürümleriyle çalışabilir. Bir örnek için bkz [izlenecek yol: Yönetilen derlemeler türler katıştırma](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md).  
  
 Kullanarak `-link` COM birlikte çalışma ile çalışırken seçenek özellikle yararlıdır. Uygulamanız artık hedef bilgisayarda birincil birlikte çalışma derlemesi (PIA) gerektirmemesi için COM türlerini ekleyebilir. `-link` Başvurulan birlikte çalışma bütünleştirilmiş kod içine ortaya çıkan derlenmiş kodu COM tür bilgilerini katıştırma derleyici seçeneği bildirir. COM türü (GUID) CLSID değeri tarafından tanımlanır. Sonuç olarak, uygulamanızı aynı COM türlerini aynı CLSID değerlerle yüklü olduğu bir hedef bilgisayarda çalıştırabilirsiniz. Microsoft Office otomatikleştirmek uygulamaların iyi bir örnektir. Office gibi uygulamalarda, genellikle aynı CLSID değeri farklı sürümler arasında tutmak olduğundan, uygulamanızı başvurulan COM türlerini uzun olarak .NET Framework 4 veya daha sonra hedef bilgisayarda yüklü olduğundan ve yöntemler, özellikler, uygulamanızın kullandığı gibi kullanabilirsiniz veya Başvurulan COM türlerini dahil edilen olaylar.  
  
 `-link` Seçeneği yalnızca arabirimleri, yapılar ve temsilciler ekler. COM sınıfları ekleme desteklenmiyor.  
  
> [!NOTE]
>  Kodunuzda katıştırılmış bir COM türün örneğini oluşturduğunuzda, uygun arabirimini kullanarak örneği oluşturmanız gerekir. Coclass'ı kullanarak katıştırılmış bir COM tür örneği oluşturulmaya çalışılırken bir hata oluşur.  
  
 Ayarlanacak `-link` seçeneğini Visual Studio'da ve bir bütünleştirilmiş kod Başvurusu Ekle `Embed Interop Types` özelliğini **true**. İçin varsayılan `Embed Interop Types` özelliği **false**.  
  
 Bir COM derlemesine (bütünleştirilmiş kod: A) bağlarsanız kendisi başka bir COM derlemesine (derleme B) başvuruda, aşağıdakilerden biri doğruysa, derleme B bağlamak de:  
  
- Bir derlemeden bir tür bir tür tarafından devralındığında veya derleme B'deki bir arabirim uygular.  
  
- Bir alan, özelliği, olay veya dönüş türü veya parametresi türü derleme b olan yöntemi çağrılır.  
  
 Kullanım [- LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) için bir veya daha fazla, derleme başvuruları bulunduğu dizini belirtin.  
  
 Gibi [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) derleyici seçeneği `-link` derleyici seçeneği başvuru sık kullanılan nezahrnovat yanıt dosyası kullanan [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] derlemeler. Kullanma [- noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) nezahrnovat dosyasını kullanmak için derleyicinin istemiyorsanız derleyici seçeneği.  
  
 Kısa formunu da `-link` olduğu `-l`.  
  
## <a name="generics-and-embedded-types"></a>Genel türler ve gömülü türleri  
 Aşağıdaki bölümlerde, genel türleri kullanarak birlikte çalışma türlerini katıştır uygulamalarda sınırlamaları açıklanmaktadır.  
  
### <a name="generic-interfaces"></a>Genel Arabirimler  
 Gömülü birlikte çalışma derlemesi genel arabirimler kullanılamaz. Bu, aşağıdaki örnekte gösterilir.  
  
 [!code-vb[VbLinkCompiler#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#1)]  
  
### <a name="types-that-have-generic-parameters"></a>Genel parametre türleri  
 Genel parametre türü bir birlikte çalışma derlemesi katıştırılmış türleri, dış bütünleştirilmiş koddan tür olan kullanılamaz. Bu kısıtlama, arabirimler için geçerli değildir. Örneğin, düşünün <xref:Microsoft.Office.Interop.Excel.Range> tanımlanan arabirimi <xref:Microsoft.Office.Interop.Excel> derleme. Birlikte çalışma türleri bir kitaplığını katıştırır, <xref:Microsoft.Office.Interop.Excel> bütünleştirilmiş kod ve türü olan bir parametreye sahip genel bir tür döndüren bir yöntem sunarsa <xref:Microsoft.Office.Interop.Excel.Range> arabirim yöntemi aşağıdaki kod örneğinde gösterildiği gibi genel bir arabirim döndürmelidir.  
  
 [!code-vb[VbLinkCompiler#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#2)]  
[!code-vb[VbLinkCompiler#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#3)]  
[!code-vb[VbLinkCompiler#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#4)]  
  
 Aşağıdaki örnekte, istemci kodu döndüren yöntem çağırabilirsiniz <xref:System.Collections.IList> hatasız genel arabirim.  
  
 [!code-vb[VbLinkCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#5)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını kaynak dosyasını derler `OfficeApp.vb` ve başvuru derlemeleri `COMData1.dll` ve `COMData2.dll` üretmek için `OfficeApp.exe`.  
  
```console  
vbc -link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)
- [İzlenecek yol: Yönetilen derlemelerden türler katıştırma](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [-başvuru (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)
- [Örnek Derleme Komut Satırları](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [COM Birlikte Çalışma'ya Giriş](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
