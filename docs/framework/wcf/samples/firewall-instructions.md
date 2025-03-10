---
title: Güvenlik Duvarı Yönergeleri
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: 2c07d17ebb6bbefa78d12bb128e354112311891a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044945"
---
# <a name="firewall-instructions"></a>Güvenlik Duvarı Yönergeleri
Windows Communication Foundation (WCF) örneklerinin çalışabilmesi için güvenlik duvarındaki çeşitli bağlantı noktalarını veya programları etkinleştirmeniz gerekir. Örneklerin birçoğu 8000-8003 aralığındaki bağlantı noktalarını ve bağlantı noktası 9000 ' yi kullanarak iletişim kurar. Güvenlik Duvarı varsayılan olarak açıktır ve bu bağlantı noktalarına erişimi engeller. Örneklere yönelik güvenlik duvarını etkinleştirmek için, gereksinimlerinize ve güvenlik ortamınıza bağlı olarak aşağıdaki yordamlardan birini yapın:  
  
- Seçenek 1: Çalıştırırken örnekleri etkileşimli olarak etkinleştirin. Güvenlik Duvarı yapılandırmanızda hiçbir değişiklik yapmayın ve örnekleri oluşturmaya ve çalıştırmaya devam edin. Bir örnek çalıştırıldığında, bir **Windows Güvenlik Uyarısı** iletişim kutusu görüntülenir. Söz konusu örnek program, engeli kaldırılmış bir listeye etkileşimli olarak eklenebilir. Bu yordamla, örneği yeniden başlatmanız gerekebilir.  
  
- Seçenek 2: Örnek programları önceden etkinleştirin. **Windows Güvenlik Duvarı Denetim Masası** uygulamasını başlatın ve çalıştırmayı planladığınız örnek programları etkinleştirin. Yürütülebilir dosyaların mevcut olması için önce programları derlemeniz gerekir. Daha ayrıntılı yönergeleri aşağıdaki yordamda bulabilirsiniz.  
  
- Seçenek 3: Bir bağlantı noktası aralığını önceden etkinleştirin. **Windows Güvenlik Duvarı** **Denetim Masası** uygulamasını başlatın ve örnekler tarafından kullanılan 80, 443, 8000-8003 ve 9000 bağlantı noktalarını etkinleştirin. Daha ayrıntılı yönergeleri aşağıdaki yordamda bulabilirsiniz. Bu seçenek, yalnızca örnekleri değil, herhangi bir programın bu bağlantı noktalarını kullanmasına izin verdiğinden, diğerlerinden daha az güvenlidir.  
  
 Hangi yordamın kullanılacağı konusunda emin değilseniz, ilk seçeneği belirleyin. Başka bir satıcıdan güvenlik duvarı çalıştırıyorsanız, benzer değişiklikler yapmanız gerekebilir.  
  
> [!IMPORTANT]
> Güvenlik duvarı yapılandırmanızı değiştirmek güvenliği etkiler. Yaptığınız değişiklikleri kaydetmeniz ve örneklerle çalışmayı bitirdiğinizde onları kaldırmanız önerilir.  
  
### <a name="to-enable-samples-programs-in-advance"></a>Örnek programları önceden etkinleştirmek için  
  
1. Örneği oluşturun.  
  
2. **Başlat**' a tıklayın, **Çalıştır**' a `firewall.cpl`tıklayın ve yazın. Bu, **Windows Güvenlik Duvarı Denetim Masası** uygulamasını açar.  
  
    > [!NOTE]
    > Windows Güvenlik Duvarı üzerinden iletişim kurmayı gerektiren örnekleri çalıştırmak için güvenlik duvarı ayarlarını değiştirme izninizin olması gerekir. Bazı güvenlik duvarı ayarları kullanılamaz durumdaysa ve bilgisayarınız bir etki alanına bağlıysa, sistem yöneticiniz bu ayarları grup ilkesi aracılığıyla denetliyor olabilir.  
  
3. Windows Güvenlik Duvarı aracılığıyla bir programa izin vermek için aşağıdaki işletim özel adımlardan birini doldurun:  
  
    - Windows 7 veya Windows Server 2008 R2 'de **Windows Güvenlik Duvarı üzerinden programa veya özelliğe Izin ver**' e tıklayın. **Ayarları Değiştir**' e tıklayın, **başka bir programa izin verin...** .  
  
    - Veya [!INCLUDE[wv](../../../../includes/wv-md.md)] üzerinde[!INCLUDE[lserver](../../../../includes/lserver-md.md)] **Windows Güvenlik Duvarı üzerinden programa izin ver**' e tıklayın.  
  
4. **Özel durumlar** sekmesinde **Program Ekle**' ye tıklayın.  
  
5. **Araştır** düğmesine tıklayın ve çalıştırmayı planladığınız örneğin çalıştırılabilir dosyasını seçin.  
  
6. Çalıştırmayı planladığınız tüm örneklerin yürütülebilir dosyalarını ekleyinceye kadar 4 ve 5. adımları tekrarlayın.  
  
7. Güvenlik Duvarı uygulamasını kapatmak için **Tamam** ' ı tıklatın.  
  
### <a name="to-enable-a-port-range-in-advance"></a>Bir bağlantı noktası aralığını önceden etkinleştirmek için  
  
1. **Başlat**' a tıklayın, **Çalıştır**' a `firewall.cpl`tıklayın ve yazın. Bu, **Windows Güvenlik Duvarı Denetim Masası** uygulamasını açar.  
  
2. Windows 7 veya Windows Server 2008 R2 'de, aşağıdaki adımları izleyin.  
  
    1. Windows Güvenlik Duvarı penceresinin sol sütununda **Gelişmiş ayarlar** ' a tıklayın.  
  
    2. Sol sütundaki **gelen kurallar** ' a tıklayın.  
  
    3. Sağ sütundaki **yeni kurallar** ' a tıklayın.  
  
    4. **Bağlantı noktasını** seçin ve **İleri**' ye tıklayın.  
  
    5. **TCP** ' yi seçin `8000, 8001, 8002, 8003, 9000, 80, 443` ve **belirli yerel bağlantı noktaları** alanına girin.  
  
    6. **İleri**'ye tıklayın.  
  
    7. **Bağlantıya Izin ver**' i seçin ve **İleri** ' ye tıklayın.  
  
    8. **Etki alanı** ve **özel**' i seçin ve **İleri**' ye tıklayın.  
  
    9. Bu kuralı `WCF-WF 4.0 Samples`adlandırın ve **son**' a tıklayın.  
  
    10. **Giden kuralları** ' na tıklayın ve adımları c-h olarak tekrarlayın.  
  
3. [!INCLUDE[wv](../../../../includes/wv-md.md)] Veya[!INCLUDE[lserver](../../../../includes/lserver-md.md)]üzerinde bu adımları izleyin.  
  
    1. **Windows Güvenlik Duvarı üzerinden programa Izin ver**' e tıklayın.  
  
    2. **Özel durumlar** sekmesinde, **bağlantı noktası Ekle**' ye tıklayın.  
  
    3. Bir ad girin, bağlantı noktası numarası olarak 8000 girin ve **TCP** seçeneğini belirleyin.  
  
    4. **Kapsamı Değiştir** düğmesine tıklayın, yalnızca ağ (alt ağ) seçeneğini belirleyin ve **Tamam**' **a** tıklayın.  
  
    5. 8001, 8002, 8003, 9000, 80 ve 443 bağlantı noktaları için b ile d arasındaki adımları yineleyin.  
  
4. Güvenlik Duvarı uygulamasını kapatmak için **Tamam** ' ı tıklatın.  
  
> [!NOTE]
> Örneklerle çalışmayı bitirdiğinizde tüm güvenlik duvarı özel durumlarını kaldırın. Bunu yapmak için, **Windows Güvenlik Duvarı Denetim Masası** uygulamasını açın ve önceki yordamlar tarafından eklenen tüm programları veya bağlantı noktası girişlerini kaldırın.
