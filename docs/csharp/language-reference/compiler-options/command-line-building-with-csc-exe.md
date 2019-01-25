---
title: Csc.exe ile komut satırı derleme
ms.date: 04/19/2017
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
ms.openlocfilehash: bb8f9ace8f259ece803aa6681ebab90355146380
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661704"
---
# <a name="command-line-build-with-cscexe"></a>Csc.exe ile komut satırı derleme
Yürütülebilir dosyanın adını yazarak C# derleyicisini çağırabilirsiniz (*csc.exe*) bir komut isteminde.

Kullanırsanız **Visual Studio için geliştirici komut istemi** penceresinde tüm gerekli ortam değişkenleri sizin için ayarlanır. Bu araç erişim hakkında daha fazla bilgi için bkz: [Visual Studio için geliştirici komut istemi](../../../framework/tools/developer-command-prompt-for-vs.md) konu. 

Standart bir komut istemi penceresi kullanıyorsanız çağırabilirsiniz önce yolunuzu ayarlamanız gerekir *csc.exe* bilgisayarınızdaki herhangi bir alt dizinden. Ayrıca çalıştırmalısınız *vsvars32.bat* komut satırı yapılarını desteklemek üzere uygun ortam değişkenlerini ayarlamak için. Hakkında daha fazla bilgi için *vsvars32.bat*, bulmak ve çalıştırmak için bkz: hakkında yönergeler dahil olmak üzere [nasıl yapılır: Visual Studio komut satırı için ortam değişkenlerini ayarlama](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).

Yalnızca bir bilgisayarda çalışıyorsanız [!INCLUDE[winsdklong](~/includes/winsdklong-md.md)], C# derleyicisi, kullanabileceğiniz **SDK Komut İstemi**, açtığınız **Microsoft .NET Framework SDK'sı** menü seçeneği.

Ayrıca C# programlarını program aracılığıyla oluşturmak için MSBuild'i kullanabilirsiniz. Daha fazla bilgi için [MSBuild](/visualstudio/msbuild/msbuild).

*Csc.exe* yürütülebilir dosyası genellikle bulunan Microsoft.NET\Framework\\*\<sürüm >* klasörü altında *Windows* Dizin. Bu dosyanın yeri, belirli bir bilgisayarın tam yapılandırmasına bağlı olarak değişebilir. Bilgisayarınızda .NET Framework'ün birden fazla sürümü yüklüyse, bu dosyanın birden fazla sürümünü bulacaksınız. Bu tür yüklemeler hakkında daha fazla bilgi için bkz. [nasıl yapılır: hangi .NET Framework sürümlerinin yüklü olduğunu belirleme](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).

> [!TIP]
>  Visual Studio IDE kullanarak bir proje oluşturduğunuzda, görüntüleyebileceğiniz **csc** komut ve ilgili derleme seçeneklerini de **çıkış** penceresi. Bu bilgileri görüntülemek için yönergeleri izleyin. [nasıl yapılır: Görüntüleme, kaydetme ve yapılandırma derleme günlük dosyalarını](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) günlük verilerinin ayrıntı düzeyini değiştirmek için **Normal** veya **ayrıntılı**. Projenizi yeniden oluşturduktan sonra arama **çıkış** penceresi **csc** C# derleyicisinin çağrısını bulmak için.

 **Bu konudaki**

- [Komut satırı sözdizimi için kurallar](#rules-for-command-line-syntax-for-the-c-compiler)

- [Örnek komut satırları](#sample-command-lines-for-the-c-compiler)

- [C# Derleyici ve C++ Derleyici çıkışını arasındaki farklar](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a>Komut satırı sözdizimi C# derleyicisi için kurallar

İşletim sistemi komut satırında belirtilen bağımsız değişkenler yorumlarken C# derleyici aşağıdaki kuralları kullanır:

- Bağımsız değişkenler bir boşluk veya sekme olduğu boşluk tarafından ayrılmış.

- İnceltme işareti (^) bir kaçış karakteri veya sınırlayıcı olarak tanınmıyor. İşletim sistemindeki komut satırı ayrıştırıcı tarafından karakter için geçirilmeden önce işlenir `argv` programı dizisi.

- Çift tırnak işaretleri ("dize") arasına bir dize içinde bulunan boşluk bağımsız olarak tek bir bağımsız değişken olarak yorumlanır. Tırnak işaretli dize bağımsız değişkeni eklenebilir.

- Çift tırnak işareti öncesinde bir ters eğik çizgi (\\") bir değişmez değer çift tırnak işareti karakteri (") yorumlanır.

- Ters eğik çizgi, başka bir deyişle, bunlar hemen çift tırnak işareti koyun sürece yorumlanır.

- Çift tırnak işareti ters eğik çizgi sayıda izlediyseniz, bir ters eğik çizgi yerleştirecek `argv` dizisi için her çift ters eğik çizgi ve çift tırnak işareti, dize ayırıcı olarak yorumlanır.

- Çift tırnak işareti ters eğik çizgi tek sayıda izlediyseniz, bir ters eğik çizgi yerleştirecek `argv` dizisi için her çift ters eğik çizgi ve çift tırnak işareti "kaçış" kalan ters eğik çizgi. Bu sabit değeri çift tırnak içinde eklenecek işareti (") neden `argv`.

## <a name="sample-command-lines-for-the-c-compiler"></a>C# derleyicisi için örnek komut satırları

- Derleme *File.cs* üretme *File.exe*:

```console
csc File.cs 
```

- Derleme *File.cs* üretme *File.dll*:

```console
csc -target:library File.cs
```

- Derleme *File.cs* ve oluşturan *My.exe*:

```console
csc -out:My.exe File.cs
```

- Tüm C# dosyaları geçerli dizine iyileştirmeler derler ve hata ayıklama sembolünü tanımlar. Çıktı *File2.exe*:

```console
csc -define:DEBUG -optimize -out:File2.exe *.cs
```

- Tüm C# dosyalarında hata ayıklama sürümü geçerli dizindeki derler *File2.dll*. Logo ve uyarı görüntülenir:

```console
csc -target:library -out:File2.dll -warn:0 -nologo -debug *.cs
```

- Tüm C# dosyaları geçerli dizine derler *Something.xyz* (DLL):

```console
csc -target:library -out:Something.xyz *.cs
```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a>C# Derleyici ve C++ Derleyici çıkışını arasındaki farklar
Hiçbir nesne vardır (*.obj*) dosyaları oluşturan C# derleyicisini çağırma işleminin sonucu olarak; çıktı dosyaları doğrudan oluşturulur. Bunun bir sonucu olarak C# derleyicisinin bir bağlayıcı gerekmez.

## <a name="see-also"></a>Ayrıca bkz.

- [C# Derleyici Seçenekleri](../../../csharp/language-reference/compiler-options/index.md)
- [Alfabetik Listelenmiş C# Derleyici Seçenekleri](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)
- [Kategorilere Göre Listelenen C# Derleyici Seçenekleri](../../../csharp/language-reference/compiler-options/listed-by-category.md)
- [Ana() ve Komut Satırı Bağımsız Değişkenleri](../../../csharp/programming-guide/main-and-command-args/index.md)
- [Komut Satırı Bağımsız Değişkenleri](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)
- [Nasıl yapılır: Komut satırı bağımsız değişkenlerini görüntüleme](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [Nasıl yapılır: Erişim foreach kullanarak komut satırı bağımsız değişkenleri](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
- [Ana() Dönüş Değerleri](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
