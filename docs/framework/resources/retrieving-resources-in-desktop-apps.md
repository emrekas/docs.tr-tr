---
title: Masaüstü Uygulamalarında Kaynakları Alma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- resource files, deploying
- resource files, packaging
- application resources, packaging
- localization
- versioning satellite assemblies
- retrieving localized resources
- application resources, deploying
- packaging application resources
- versioning resources
- translating resources into languages
- localizing resources
ms.assetid: eca16922-1c46-4f68-aefe-e7a12283641f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33bc0ecb4b7d20f0df96486c046e06fc4cf0e7ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941465"
---
# <a name="retrieving-resources-in-desktop-apps"></a>Masaüstü Uygulamalarında Kaynakları Alma
.NET Framework masaüstü uygulamalarında yerelleştirilmiş kaynaklarla çalışırken, ana bütünleştirilmiş kod ile varsayılan veya nötr kültür için kaynakları en iyi şekilde paketleyip uygulamanızın desteklediği her dil ya da kültür için ayrı bir uydu derlemesi oluşturmanız gerekir. Daha sonra, <xref:System.Resources.ResourceManager> adlandırılmış kaynaklara erişmek için sonraki bölümde açıklandığı gibi sınıfını kullanabilirsiniz. Kaynaklarınızı ana derleme ve uydu Derlemeleriyle katıştırmamayı seçerseniz, bu makalenin ilerleyen kısımlarında [kaynakları. resources dosyalarından alma](#from_file) bölümünde açıklandığı gibi doğrudan ikili. resources dosyalarına da erişebilirsiniz.  [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] Uygulamalardaki kaynakları almak için, bkz. Windows Geliştirme Merkezi 'nde [Windows Mağazası uygulamalarında kaynakları oluşturma ve alma](https://go.microsoft.com/fwlink/p/?LinkID=241674) .  
  
<a name="from_assembly"></a>   
## <a name="retrieving-resources-from-assemblies"></a>Derlemelerden kaynakları alma  
 Sınıfı <xref:System.Resources.ResourceManager> , çalışma zamanında kaynaklara erişim sağlar. Dize kaynaklarını almak <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> için yöntemini <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType> ve <xref:System.Resources.ResourceManager.GetStream%2A?displayProperty=nameWithType> dize olmayan kaynakları almak için yöntemini kullanın. Her yöntemin iki aşırı yüklemesi vardır:  
  
- Tek parametresi kaynağın adını içeren bir dize olan aşırı yükleme. Yöntemi, geçerli iş parçacığı kültürü için bu kaynağı almaya çalışır. Daha fazla bilgi için bkz <xref:System.Resources.ResourceManager.GetString%28System.String%29> <xref:System.Resources.ResourceManager.GetObject%28System.String%29>., ve <xref:System.Resources.ResourceManager.GetStream%28System.String%29> yöntemleri.  
  
- İki parametreye sahip bir aşırı yükleme: kaynak adını içeren bir dize ve kaynağı alınacak olan kültürü temsil <xref:System.Globalization.CultureInfo> eden bir nesne. Bu kültür için bir kaynak kümesi bulunamazsa, Kaynak Yöneticisi uygun bir kaynağı almak için geri dönüş kurallarını kullanır. Daha fazla bilgi için bkz <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29> <xref:System.Resources.ResourceManager.GetObject%28System.String%2CSystem.Globalization.CultureInfo%29>., ve <xref:System.Resources.ResourceManager.GetStream%28System.String%2CSystem.Globalization.CultureInfo%29> yöntemleri.  
  
 Resource Manager, uygulamanın kültüre özgü kaynakları nasıl alacağını denetlemek için kaynak geri dönüş işlemini kullanır. Daha fazla bilgi için kaynak [paketleme ve dağıtma](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)konusunun "kaynak geri dönüş işlemi" bölümüne bakın. Bir <xref:System.Resources.ResourceManager> nesneyi örnekleme hakkında daha fazla bilgi için, <xref:System.Resources.ResourceManager> sınıf konusunun "ResourceManager nesnesi örneği oluşturma" bölümüne bakın.  
  
### <a name="retrieving-string-data-an-example"></a>Dize verileri alınıyor: Bir Örnek  
 Aşağıdaki örnek, geçerli UI <xref:System.Resources.ResourceManager.GetString%28System.String%29> kültürünün dize kaynaklarını almak için yöntemini çağırır. Bu, Fransızca (Fransa) ve Rusça (Rusya) kültürleri için Ingilizce (Birleşik Devletler) kültürün ve yerelleştirilmiş kaynakların bağımsız bir dize kaynağını içerir. Aşağıdaki Ingilizce (Birleşik Devletler) kaynağı dizeler. txt adlı bir dosyadır:  
  
```  
TimeHeader=The current time is  
```  
  
 Fransızca (Fransa) kaynağı Strings.fr-FR. txt adlı bir dosyadır:  
  
```  
TimeHeader=L'heure actuelle est  
```  
  
 Rusça (Rusya) kaynağı Strings.ru-RU-txt adlı bir dosyadır:  
  
```  
TimeHeader=Текущее время —  
```  
  
 Bu örneğin, kodun C# sürümü ve Visual Basic sürümü Için GetString. vb adlı bir dosyada bulunan kaynak kodu, dört kültürlerin adını içeren bir dize dizisi tanımlar: kaynakların bulunduğu üç kültür kullanılabilir ve Ispanyolca (Ispanya) kültürü. Beş kez yürütülen bir döngü, <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> bu kültürlerin birini rastgele seçer ve ve <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> özelliklerine atar. Daha sonra, yerelleştirilmiş <xref:System.Resources.ResourceManager.GetString%28System.String%29> dizeyi almak için yöntemini çağırır, bu da günün saati ile birlikte görüntülenir.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/getstring.cs#3)]
 [!code-vb[Conceptual.Resources.Retrieving#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/getstring.vb#3)]  
  
 Aşağıdaki Batch (. bat) dosyası örneği derler ve uygun dizinlerde uydu derlemeleri oluşturur. Komutları C# dil ve derleyici için verilmiştir. Visual Basic için, olarak `csc` değiştirin `vbc`ve öğesini olarak `GetString.cs` `GetString.vb`değiştirin.  
  
```  
resgen strings.txt  
csc GetString.cs -resource:strings.resources  
  
resgen strings.fr-FR.txt  
md fr-FR  
al -embed:strings.fr-FR.resources -culture:fr-FR -out:fr-FR\GetString.resources.dll  
  
resgen strings.ru-RU.txt  
md ru-RU  
al -embed:strings.ru-RU.resources -culture:ru-RU -out:ru-RU\GetString.resources.dll  
```  
  
 Geçerli UI kültürü Ispanyolca (Ispanya) olduğunda, Ispanyolca Dil kaynakları kullanılamadığından ve Ingilizce 'nin varsayılan kültür olduğu için, örneğin Ingilizce dil kaynaklarını görüntülediğini unutmayın.  
  
### <a name="retrieving-object-data-two-examples"></a>Nesne verileri alınıyor: İki örnek  
 Nesne verilerini almak için <xref:System.Resources.ResourceManager.GetObject%2A> ve <xref:System.Resources.ResourceManager.GetStream%2A> yöntemlerini kullanabilirsiniz. Buna temel veri türleri, serileştirilebilir nesneler ve ikili biçimde (görüntüler gibi) depolanan nesneler dahildir.  
  
 Aşağıdaki örnek, bir uygulamanın <xref:System.Resources.ResourceManager.GetStream%28System.String%29> açılış giriş penceresinde kullanılan bir bit eşlemi almak için yöntemini kullanır. CreateResources.cs (for C#) veya createreso,. Visual Basic vb adlı bir dosyada bulunan aşağıdaki kaynak kodu, serileştirilmiş görüntüyü içeren bir. resx dosyası üretir. Bu durumda, görüntü, SplashScreen. jpg adlı bir dosyadan yüklenir. kendi görüntünüzü yerine koymak için dosya adını değiştirebilirsiniz.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/createresources.cs#4)]
 [!code-vb[Conceptual.Resources.Retrieving#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/createresources.vb#4)]  
  
 Aşağıdaki kod, kaynağı alır ve görüntüyü bir <xref:System.Windows.Forms.PictureBox> denetimde görüntüler.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/getstream.cs#5)]
 [!code-vb[Conceptual.Resources.Retrieving#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/getstream.vb#5)]  
  
 C# Örneği oluşturmak için aşağıdaki toplu iş dosyasını kullanabilirsiniz. Visual Basic için, olarak `csc` `vbc`değiştirin ve kaynak kod dosyasının `.cs` uzantısını olarak `.vb`değiştirin.  
  
```  
csc CreateResources.cs  
CreateResources  
  
resgen AppResources.resx  
  
csc GetStream.cs -resource:AppResources.resources  
```  
  
 Aşağıdaki örnek, özel bir <xref:System.Resources.ResourceManager.GetObject%28System.String%29?displayProperty=nameWithType> nesnenin serisini kaldırmak için yöntemini kullanır. Örnek, adlı `PersonTable`aşağıdaki yapıyı tanımlayan, UIElements.cs adlı bir kaynak kod dosyası (Visual Basic için UIElements. vb) içerir. Bu yapının tablo sütunlarının yerelleştirilmiş adlarını görüntüleyen bir genel tablo görüntüleme yordamı tarafından kullanılması amaçlanmıştır. `PersonTable` Yapının <xref:System.SerializableAttribute> özniteliğiyle işaretlendiğini unutmayın.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example.cs#6)]
 [!code-vb[Conceptual.Resources.Retrieving#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example.vb#6)]  
  
 CreateResources.cs adlı bir dosyadan aşağıdaki kod (Visual Basic için createresolenebilir. vb), bir tablo başlığı ve `PersonTable` bir nesne için yerelleştirilmiş bir uygulama için bilgi içeren bir nesnesi olan UIResources. resx adlı bir XML kaynak dosyası oluşturur. İngilizce dili.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example1.cs#7)]
 [!code-vb[Conceptual.Resources.Retrieving#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example.vb#7)]  
  
 Aşağıdaki kod, GetObject.cs (GetObject. vb) adlı bir kaynak kod dosyasında, kaynakları alır ve konsola görüntüler.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example2.cs#8)]
 [!code-vb[Conceptual.Resources.Retrieving#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example2.vb#8)]  
  
 Aşağıdaki toplu iş dosyasını yürüterek gerekli kaynak dosya ve derlemeleri oluşturabilir ve uygulamayı çalıştırabilirsiniz. Bir UIElements. `/r` dll başvurusu ile Resgen. exe ' yi, `PersonTable` yapıyla ilgili bilgilere erişebilecek şekilde sağlamak için bu seçeneği kullanmanız gerekir. C#Kullanıyorsanız, `vbc` derleyici adını ile `csc`değiştirin ve `.vb` uzantısını ile `.cs`değiştirin.  
  
```  
vbc -t:library UIElements.vb  
vbc CreateResources.vb -r:UIElements.dll  
CreateResources  
  
resgen UIResources.resx  -r:UIElements.dll  
vbc GetObject.vb -r:UIElements.dll -resource:UIResources.resources  
  
GetObject.exe  
```  
  
## <a name="versioning-support-for-satellite-assemblies"></a>Uydu derlemeleri için sürüm oluşturma desteği  
 Varsayılan olarak, <xref:System.Resources.ResourceManager> nesne istenen kaynakları aldığında, ana derlemenin sürüm numarasıyla eşleşen sürüm numaralarına sahip uydu derlemelerini arar. Bir uygulamayı dağıttıktan sonra, ana derlemeyi veya belirli kaynak uydu derlemelerini güncelleştirmek isteyebilirsiniz. .NET Framework, ana derleme ve uydu derlemelerinin sürümü oluşturma desteği sağlar.  
  
 Özniteliği <xref:System.Resources.SatelliteContractVersionAttribute> , bir ana derleme için sürüm oluşturma desteği sağlar. Bu özniteliğin bir uygulamanın ana derlemesinde belirtilmesi, bir ana derlemeyi, uydu derlemelerini güncelleştirmeden güncellemenize ve yeniden dağıtmanıza olanak sağlar. Ana derlemeyi güncelleştirdikten sonra, ana derlemenin sürüm numarasını artırın, ancak uydu sözleşmesinin sürüm numarasını değiştirmeden bırakın. Resource Manager istenen kaynakları aldığında, bu öznitelik tarafından belirtilen uydu derleme sürümünü yükler.  
  
 Yayımcı ilke derlemeleri, uydu derlemelerinin sürümü oluşturma desteği sağlar. Ana derlemeyi güncelleştirmeden bir uydu derlemesini güncelleştirebilir ve yeniden dağıtabilirsiniz. Bir uydu derlemesini güncelleştirdikten sonra, sürüm numarasını artırın ve bir yayımcı ilkesi derlemesi ile gönderin. Yayımcı ilkesi derlemesinde, yeni uydu derlemelerinizin önceki sürümüyle geriye dönük olarak uyumlu olduğunu belirtin. Resource Manager, uydu derlemesinin sürümünü <xref:System.Resources.SatelliteContractVersionAttribute> belirlerken özniteliğini kullanır, ancak derleme yükleyicisi yayımcı ilkesi tarafından belirtilen uydu derleme sürümüne bağlanır. Yayımcı ilke derlemeleri hakkında daha fazla bilgi için bkz. [Yayımcı Ilke dosyası oluşturma](../../../docs/framework/configure-apps/how-to-create-a-publisher-policy.md).  
  
 Tam derleme sürümü oluşturma desteğini etkinleştirmek için, tanımlayıcı adlı derlemeleri [genel derleme önbelleğinde](../../../docs/framework/app-domains/gac.md) dağıtmanız ve uygulama dizininde tanımlayıcı adlara sahip olmayan derlemeler dağıtmanız önerilir. Uygulama dizininde tanımlayıcı adlı derlemeler dağıtmak istiyorsanız, derlemeyi güncelleştirdiğinizde bir uydu derlemesinin sürüm numarasını artırmanız mümkün olmayacaktır. Bunun yerine, mevcut kodu güncelleştirilmiş kodla değiştirdiğiniz ve aynı sürüm numarasını tuttuğunuz yerde bir yerinde güncelleştirme gerçekleştirmeniz gerekir. Örneğin, tam belirtilen derleme adı "myApp. resources, Version = 1.0.0.0, Culture = de, PublicKeyToken = b03f5f11d50a3a" olan bir uydu derlemesinin sürüm 1.0.0.0 sürümünü güncelleştirmek istiyorsanız, bu dosyanın üzerine gelen güncelleştirilmiş myApp. resources. dll aynı, tam olarak belirtilen derleme adı "myApp. resources, Version = 1.0.0.0, Culture = de, PublicKeyToken = b03f5f11d50a3a" ile derlendi. Uydu derleme dosyalarında yerinde güncelleştirme kullanmanın, bir uygulamanın bir uydu derlemesinin sürümünü doğru bir şekilde belirlemesini zorlaştırmadığını unutmayın.  
  
 Derleme sürümü oluşturma hakkında daha fazla bilgi için bkz. [derleme sürümü oluşturma](../../../docs/framework/app-domains/assembly-versioning.md) ve [çalışma zamanının derlemeleri nasıl konumlandırır](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
<a name="from_file"></a>   
## <a name="retrieving-resources-from-resources-files"></a>Kaynakları. resources dosyalarından alma  
 Uydu derlemelerindeki kaynakları dağıtmayabilir ' i tercih ediyorsanız,. resources dosyalarından doğrudan kaynaklara <xref:System.Resources.ResourceManager> erişmek için bir nesne kullanmaya devam edebilirsiniz. Bunu yapmak için. resources dosyalarını doğru olarak dağıtmanız gerekir. Daha sonra, <xref:System.Resources.ResourceManager.CreateFileBasedResourceManager%2A?displayProperty=nameWithType> bir <xref:System.Resources.ResourceManager> nesneyi başlatmak ve tek başına. resources dosyalarını içeren dizini belirtmek için yöntemini kullanırsınız.  
  
### <a name="deploying-resources-files"></a>. Resources dosyalarını dağıtma  
 Bir uygulama derlemesine ve uydu derlemelerine. resources dosyaları eklediğinizde, her uydu derlemesi aynı dosya adına sahiptir, ancak uydu derlemesinin kültürünü yansıtan bir alt dizine yerleştirilir. Buna karşılık,. resources dosyalarından doğrudan kaynaklara eriştiğinizde, tüm. resources dosyalarını, genellikle uygulama dizininin bir alt dizini olacak şekilde tek bir dizine yerleştirebilirsiniz. Uygulamanın varsayılan. resources dosyasının adı, kültürü (örneğin, dizeler. resources) göstergesi olmadan yalnızca bir kök adından oluşur. Yerelleştirilmiş her kültürün kaynakları, adı kök adından ve ardından kültürün (örneğin, dizeler. ja. resources veya strings.de-DE. resources) yer aldığı bir dosyada depolanır. 
 
 Aşağıdaki çizimde, kaynak dosyalarının dizin yapısında nerede bulunacağı gösterilmektedir. Ayrıca,. kaynak dosyaları için adlandırma kuralları sağlar.  

 ![Uygulamanızın ana dizinini gösteren çizim.](./media/retrieving-resources-in-desktop-apps/resource-application-directory.gif)  
  
### <a name="using-the-resource-manager"></a>Kaynak Yöneticisi kullanma  
 Kaynaklarınızı oluşturup uygun dizine yerleştirdikten sonra, <xref:System.Resources.ResourceManager> <xref:System.Resources.ResourceManager.CreateFileBasedResourceManager%28System.String%2CSystem.String%2CSystem.Type%29> yöntemini çağırarak kaynakları kullanmak için bir nesne oluşturun. İlk parametre, uygulamanın varsayılan. resources dosyasının kök adını belirtir (Bu, önceki bölümdeki örnek için "dizeler" olacaktır). İkinci parametre, kaynakların konumunu belirtir (önceki örnek için "kaynaklar"). Üçüncü parametre kullanılacak <xref:System.Resources.ResourceSet> uygulamayı belirtir. Üçüncü parametre ise `null`, varsayılan çalışma zamanı <xref:System.Resources.ResourceSet> kullanılır.  
  
> [!NOTE]
> Tek başına. resources dosyalarını kullanarak ASP.NET uygulamalarını dağıtmayın. Bu, kilitlenme sorunlarına neden olabilir ve XCOPY dağıtımını keser. ASP.NET kaynaklarını uydu Derlemeleriyle dağıtmanızı öneririz. Daha fazla bilgi için bkz. [ASP.NET Web sayfası kaynaklarına genel bakış](https://docs.microsoft.com/previous-versions/aspnet/ms227427(v=vs.100)).  
  
 <xref:System.Resources.ResourceManager> Nesneyi örnekledikten sonra, kaynakları almak için daha <xref:System.Resources.ResourceManager.GetString%2A>önce <xref:System.Resources.ResourceManager.GetObject%2A>anlatıldığı gibi <xref:System.Resources.ResourceManager.GetStream%2A> ,, ve yöntemlerini kullanırsınız. Ancak, kaynakların doğrudan. resources dosyalarından alınması, gömülü kaynakların derlemelerden alıntığından farklıdır. Kaynakları. resources dosyalarından <xref:System.Resources.ResourceManager.GetString%28System.String%29> <xref:System.Resources.ResourceManager.GetObject%28System.String%29>aldığınızda,, ve <xref:System.Resources.ResourceManager.GetStream%28System.String%29> yöntemleri her zaman geçerli kültürden bağımsız olarak varsayılan kültürün kaynaklarını alır. Uygulamanın geçerli kültürünün veya belirli bir kültürün kaynaklarını almak için,, veya <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29> <xref:System.Resources.ResourceManager.GetStream%28System.String%2CSystem.Globalization.CultureInfo%29> yöntemini çağırmanız <xref:System.Resources.ResourceManager.GetObject%28System.String%2CSystem.Globalization.CultureInfo%29>ve kaynakları alınacak olan kültürü belirtmeniz gerekir. Geçerli kültürün kaynaklarını almak için, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> özelliğinin değerini `culture` bağımsız değişken olarak belirtin. Resource Manager kaynakları `culture`alamıyorsa, uygun kaynakları almak için standart kaynak geri dönüş kurallarını kullanır.  
  
### <a name="an-example"></a>Bir Örnek  
 Aşağıdaki örnek, Resource Manager 'ın kaynakları doğrudan. resources dosyalarından nasıl alacağını gösterir. Örnek, Ingilizce (Birleşik Devletler), Fransızca (Fransa) ve Rusça (Rusya) kültürleri için üç metin tabanlı kaynak dosyasından oluşur. İngilizce (Birleşik Devletler), örneğin varsayılan kültürdür. Kaynakları, dizeler. txt adlı aşağıdaki dosyada depolanır:  
  
```  
Greeting=Hello  
Prompt=What is your name?  
```  
  
 Fransızca (Fransa) kültürünün kaynakları, Strings.fr-FR. txt adlı aşağıdaki dosyada depolanır:  
  
```  
Greeting=Bon jour  
Prompt=Comment vous appelez-vous?  
```  
  
 Rusça (Rusya) kültürü için kaynaklar, Strings.ru-RU. txt adlı aşağıdaki dosyada depolanır:  
  
```  
Greeting=Здравствуйте  
Prompt=Как вас зовут?  
```  
  
 Örnek için kaynak kodu aşağıda verilmiştir. Örnek, İngilizce <xref:System.Globalization.CultureInfo> (Birleşik Devletler), İngilizce (Kanada), Fransızca (Fransa) ve Rusça (Rusya) kültürleri için nesneleri örnekleyen ve her bir geçerli kültürü yapan. Yöntemi <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType> daha sonra, uygun kültüre özgü kaynakları <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> almak için `culture` bağımsız değişken olarak özelliğin değerini sağlar.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example3.cs#9)]
 [!code-vb[Conceptual.Resources.Retrieving#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example3.vb#9)]  
  
 Aşağıdaki toplu iş dosyasını C# çalıştırarak örnek sürümünü derleyebilirsiniz. `csc` Visual Basic kullanıyorsanız, ile `vbc`değiştirin ve `.cs` uzantısını ile `.vb`değiştirin.  
  
```  
Md Resources  
Resgen Strings.txt Resources\Strings.resources  
Resgen Strings.fr-FR.txt Resources\Strings.fr-FR.resources  
Resgen Strings.ru-RU.txt Resources\Strings.ru-RU.resources  
  
csc Example.cs  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Resources.ResourceManager>
- [Masaüstü Uygulamalarındaki Kaynaklar](../../../docs/framework/resources/index.md)
- [Kaynakları Paketleme ve Dağıtma](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Çalışma Zamanının Bütünleştirilmiş Kodların Konumunu Bulması](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Windows Mağazası uygulamalarında kaynak oluşturma ve alma](https://go.microsoft.com/fwlink/p/?LinkID=241674)
