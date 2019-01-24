---
title: 'Derlemeler ve Genel Derleme Önbelleği (C#)'
ms.date: 07/20/2015
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
---
# <a name="assemblies-and-the-global-assembly-cache-c"></a>Derlemeler ve Genel Derleme Önbelleği (C#)
Derlemeler dağıtım, sürüm denetimi, yeniden kullanma, aktivasyon kapsamı ve güvenlik izinleri için temel birimini oluşturur bir. AĞ tabanlı bir uygulama. Derlemeler, bir yürütülebilir (.exe) dosya veya dinamik bağlantı kitaplığı (.dll) dosyası biçiminde ve .NET Framework'ün yapı taşlarıdır. Bunlar, ortak dil çalışma zamanı tür uygulamalarına dikkat etmeniz gereken bilgileri sağlar. Derleme türleri ve mantıksal bir işlevsellik birimi oluşturacak ve birlikte çalışmak üzere tasarlanan kaynakları koleksiyonu olarak düşünebilirsiniz.  
  
 Derlemeler, bir veya daha fazla modül içerebilir. Örneğin, daha büyük projeleri birden fazla bireysel geliştiriciler ayrı modüllerde, tek bir derleme oluşturmak için bir araya tüm gelecek iş şekilde planlı. Modüller hakkında daha fazla bilgi için Ek Yardım konusuna [nasıl yapılır: Bir çoklu dosya derlemesi oluşturmak](../../../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md).  
  
 Derlemeleri, aşağıdaki özelliklere sahiptir:  
  
-   Derlemeleri, .exe veya .dll dosyaları olarak uygulanır.  
  
-   Bir derlemeyi genel derleme önbelleğinde koyarak uygulamalar arasında paylaşabilirsiniz. Derlemeleri güçlü-genel derleme önbelleğinde bulunan önce adlandırılması gerekir. Daha fazla bilgi için [Strong-Named derlemeleri](../../../../../docs/framework/app-domains/strong-named-assemblies.md).  
  
-   Derlemeleri, yalnızca gerekli olduğunda belleğe yüklenir. Kullanılmazlar, bunlar yüklü değildir. Başka bir deyişle, derlemeleri daha büyük projeler kaynakları yönetmek için etkili bir yol olabilir.  
  
-   Yansıma kullanarak program aracılığıyla bir derlemeyle ilgili bilgiler elde edebilirsiniz. Daha fazla bilgi için [yansıma (C#)](../../../../csharp/programming-guide/concepts/reflection.md).  
  
-   Yalnızca incelemek için bir derlemeyi yüklemek istiyorsanız, bir yöntem gibi kullanın <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>.  
  
## <a name="assembly-manifest"></a>Derleme Bildirimi  
 Her derleme içinde var olan bir *derleme bildirimi*. Benzer şekilde bir içindekiler tablosu, derleme bildirimi aşağıdakileri içerir:  
  
-   Derlemenin kimliğini (adı ve sürümü).  
  
-   Diğer tüm derlemeyi oluşturan, örneğin, .exe veya .dll dosyası, dayandığını oluşturduğunuz herhangi bir derleme dosyaların veya hatta bit eşlem ya da Benioku dosyaları tanımlayan bir dosya tablosu.  
  
-   Bir *derleme başvurusu listesi*, tüm dış bağımlılıkları listesi verilmiştir: .dll veya diğer dosyaları uygulama gereksinimlerinizi başkası tarafından oluşturulmuş olabilir. Derleme başvuruları, genel ve özel nesnelere başvurular içerir. Genel nesneler, genel derleme önbelleği, diğer uygulamalar için de kullanılabilir olan bir alan olarak yer alır. Özel nesneleri aynı düzeyde olarak veya uygulamanızı yüklendiği dizinin altında ya da bir dizin olmalıdır.  
  
 Derlemeleri içeriği, sürümleri ve bağımlılıkları hakkında bilgi içerdiğinden, C# ile oluşturduğunuz uygulamaların düzgün çalışması için Windows kayıt defteri değerlerini güvenmeyin. Derlemeler .dll çakışmalarını azaltmak ve daha güvenilir ve kolay dağıtmak uygulamalarınızı. Çoğu durumda, yüklediğiniz bir. Hedef bilgisayarın dosyaları kopyalama powershell'inizi yazarak NET tabanlı uygulama.  
  
 Daha fazla bilgi için [derleme bildirimi](../../../../../docs/framework/app-domains/assembly-manifest.md).  
  
## <a name="adding-a-reference-to-an-assembly"></a>Bir derlemeye bir başvuru ekleme  
 Bir derlemeyi kullanması için buna bir başvuru eklemeniz gerekir. Ardından, kullandığınız [using yönergesi](../../../../csharp/language-reference/keywords/using-directive.md) için ad alanı kullanmak istediğiniz öğeleri seçin. Bir derlemeye başvuru ve içeri aktarıldıktan sonra tüm erişilebilir sınıfları, özellikleri, yöntemleri ve diğer üyeleri, ad alanları kodlarını kaynak dosyanıza bir parçası değilmiş gibi uygulamanızda kullanılabilir.  
  
 C# ' ta aynı derlemenin iki sürümü de tek bir uygulama kullanabilirsiniz. Daha fazla bilgi için [extern diğer adı](../../../../csharp/language-reference/keywords/extern-alias.md).  
  
## <a name="creating-an-assembly"></a>Bir derleme oluşturma  
 Tıklayarak uygulamanızı derleyin **derleme** üzerinde **derleme** menüsünden veya komut satırı derleyicisini kullanarak komut satırından derleme. Komut satırı derlemeleri oluşturma hakkında daha fazla ayrıntı için bkz [oluşturma ile komut satırı csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  
  
> [!NOTE]
>  Visual Studio'da bir derlemeyi derlemek için **derleme** menüsünde **yapı**.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../../../../csharp/programming-guide/index.md)
- [Ortak Dil Çalışma Zamanı Modülündeki Bütünleştirilmiş Kodlar](../../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [Arkadaş derlemeler (C#)](friend-assemblies.md)
- [Nasıl yapılır: Bir derlemeyi başka uygulamalarla paylaşma (C#)](how-to-share-an-assembly-with-other-applications.md)
- [Nasıl yapılır: Yükleme ve yüklemelerini kaldırma derlemeleri (C#)](how-to-load-and-unload-assemblies.md)
- [Nasıl yapılır: Bir dosyanın derleme olup olmadığını belirleme (C#)](how-to-determine-if-a-file-is-an-assembly.md)
- [Nasıl yapılır: Komut satırını kullanarak derlemeler oluşturma ve kullanma (C#)](how-to-create-and-use-assemblies-using-the-command-line.md)
- [İzlenecek yol: Yönetilen derlemeler Visual Studio'da türler katıştırma (C#)](walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)
- [İzlenecek yol: Visual Studio'da Microsoft Office derlemelerinden tür bilgilerini katıştırma (C#)](walkthrough-embedding-type-information-from-microsoft-office-assemblies.md)
