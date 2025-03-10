---
title: 'Örnek: Veri Bağlama Sırasında Özel Durum İşleme'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5be728cbeb0c3378bb35765787b299167069f57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910618"
---
# <a name="example-handling-exceptions-when-binding-data"></a>Örnek: Veri Bağlama Sırasında Özel Durum İşleme
> [!NOTE]
> Bu konu, yayın öncesi yazılım olan .NET Native geliştirici önizlemesine başvurur. Önizlemeyi [Microsoft Connect Web sitesinden](https://go.microsoft.com/fwlink/?LinkId=394611) indirebilirsiniz (kayıt gerekir).  
  
 Aşağıdaki örnek, .NET Native araç zinciri ile derlenen bir uygulama verileri bağlamayı denediğinde oluşan bir [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) özel durumunun nasıl çözümlendiğini gösterir. Özel durum bilgileri aşağıda verilmiştir:  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:   
App.ViewModels.MainPageVM  
```  
  
 İlişkili çağrı yığını aşağıda verilmiştir:  
  
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
  
## <a name="what-was-the-app-doing"></a>Uygulama ne yapıyor?  
 Yığının tabanında, <xref:Windows.UI.Xaml?displayProperty=nameWithType> ad alanındaki Çerçeveler XAML işleme altyapısının çalıştığını gösterir.   <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> Yönteminin kullanımı, meta verileri kaldırılmış olan türdeki bir özelliğin değerinin yansıma tabanlı bir aramasını gösterir.  
  
 Meta veri yönergesini sağlamanın ilk adımı, özelliklerinin tümünün erişilebilir olması için `serialize` türün meta verilerini eklemektir:  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a>Bu yalıtılmış bir durumdur mi?  
 Bu senaryoda, veri bağlamasında bir tane `ViewModel`için eksik meta veriler varsa, diğerleri de olabilir.  Kod, uygulamanın görünüm modellerinin `App.ViewModels` ad alanında yer aldığı bir şekilde yapılandırılmış ise, daha genel bir çalışma zamanı yönergesi kullanabilirsiniz:  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a>Kod, yansıma kullanmadan yeniden yazılabilir mi?  
 Veri bağlama yansıma yoğun olduğundan, yansımayı önlemek için kodun değiştirilmesi uygun değildir.  
  
 Ancak, araç zincirinin derleme zamanında doğru türle `ViewModel` Özellik bağlamalarını ilişkilendirebilmesi ve bir çalışma zamanı yönergesi kullanmadan meta verileri tutması için XAML sayfasına belirtmek için bazı yollar vardır.  Örneğin, özelliğini özelliklerine uygulayabilirsiniz <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> . Bu, XAML derleyicisinin gerekli arama bilgilerini oluşturmasına ve default. RD. xml dosyasında bir çalışma zamanı yönergesi gerektirmesine neden olur.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Başlarken](../../../docs/framework/net-native/getting-started-with-net-native.md)
- [Örnek: Dinamik programlama sorunlarını giderme](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)
