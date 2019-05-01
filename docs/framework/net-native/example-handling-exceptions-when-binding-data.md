---
title: 'Örnek: Veri Bağlama Sırasında Özel Durum İşleme'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25b2117de40bbe7ba36fab028526116fc01ae09b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868549"
---
# <a name="example-handling-exceptions-when-binding-data"></a>Örnek: Veri Bağlama Sırasında Özel Durum İşleme
> [!NOTE]
>  Bu konuda, .NET Native Geliştirici yayın öncesi bir yazılım olan Önizleme, ifade eder. Önizlemesi'nden indirebileceğiniz [Microsoft Connect Web sitesi](https://go.microsoft.com/fwlink/?LinkId=394611) (kayıt gerekir).  
  
 Aşağıdaki örnek nasıl giderileceğini gösterir bir [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) uygulama ile derlendiğinde oluşturulan özel durum [!INCLUDE[net_native](../../../includes/net-native-md.md)] araç zincirinizi veri bağlama dener. Özel durum bilgilerini şu şekildedir:  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:   
App.ViewModels.MainPageVM  
```  
  
 İlişkili çağrı yığını şu şekildedir:  
  
```  
Reflection::Execution::ReflectionDomainSetupImplementation.CreateNonInvokabilityException+0x238  
Reflection::Core::ReflectionDomain.CreateNonInvokabilityException+0x2e  
Reflection::Core::Execution::ExecutionEnvironment.+0x316  
System::Reflection::Runtime::PropertyInfos::RuntimePropertyInfo.GetValue+0x1cb  
System::Reflection::PropertyInfo.GetValue+0x22  
System::Runtime::InteropServices::WindowsRuntime::CustomPropertyImpl.GetValue+0x42  
App!$66_Interop::McgNative.Func_IInspectable_IInspectable+0x158  
App!$66_Interop::McgNative::__vtable_Windows_UI_Xaml_Data__ICustomProperty.GetValue__STUB+0x46  
Windows_UI_Xaml!DirectUI::PropertyProviderPropertyAccess::GetValue+0x3f   
Windows_UI_Xaml!DirectUI::PropertyAccessPathStep::GetValue+0x31   
Windows_UI_Xaml!DirectUI::PropertyPathListener::ConnectPathStep+0x113  
```  
  
## <a name="what-was-the-app-doing"></a>Uygulama neler oldu?  
 Gelen temel yığın çerçevelerini <xref:Windows.UI.Xaml?displayProperty=nameWithType> ad alanı belirtmek XAML işleme altyapısı çalışıyordu.   Kullanımını <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> olan meta veriler temizlendi türünde bir özelliğin değerinin yansıma tabanlı bir arama yöntemi gösterir.  
  
 Meta veri yönergesi sağlayan ilk adımı eklemek için olacaktır `serialize` türü için meta veri özelliklerini tüm erişilebilir olacak şekilde:  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a>Bu, yalıtılmış bir durum mu?  
 Bu senaryoda, veri bağlama tamamlanmamış meta verileri için bir tane varsa `ViewModel`, diğerleri için bir çok olabilir.  Kod, uygulamanın görünüm modelleri tek bir şekilde yapılandırılırsa `App.ViewModels` ad alanı, daha genel bir çalışma zamanı yönerge kullanabilirsiniz:  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a>Kod, yansıma kullanmayı yazılması?  
 Veri bağlama yansıma yoğun olduğundan, yansıma önlemek için kodu değiştirme uygun değildir.  
  
 Ancak, yolu belirtmek için vardır `ViewModel` XAML sayfası araç zincirinizi ilişkilendirebilirsiniz böylece doğru türde özellik bağlamalarla derleme zamanı ve çalışma zamanı yönerge kullanmadan meta verileri tut.  Örneğin, uygulayabilirsiniz <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> öznitelik özellikleri. Bu, XAML derleyicinin arama gerekli bilgileri oluşturmak ve Default.rd.xml dosyasındaki bir çalışma zamanı yönerge gerektiren önler.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Başlarken](../../../docs/framework/net-native/getting-started-with-net-native.md)
- [Örnek: Dinamik programlama sorunlarını giderme](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)
