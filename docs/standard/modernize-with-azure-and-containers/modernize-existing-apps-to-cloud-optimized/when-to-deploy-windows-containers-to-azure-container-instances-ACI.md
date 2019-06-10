---
title: Azure Container Instances'a (ACI) Windows kapsayıcıları dağıtma zamanı
description: Azure Bulut ve Windows kapsayıcıları ile mevcut .NET uygulamalarını modernleştirme | Azure Container Instances'a (ACI) Windows kapsayıcıları dağıtma zamanı
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758586"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Azure Container Instances'a (ACI) Windows kapsayıcıları dağıtma zamanı

Ana değer önerisi hemen kapsayıcılar için uygulamayı dağıtmak ve bu ortamı sürdürmeniz gerekmez olan Azure Container Instances, yükseltmek/yama uygulamak temel işletim sistemi veya tüm saydam olan VM'ler ihtiyacınız yoksa ve yalnızca dağıtma kullanıma hazır bir ortam kapsayıcılarına.

ACI kullanmak istediğiniz zaman senaryoları ve nedeni, Azure Vm'leri kapsayıcılar ile aslında kullandığınızda yönelik temel senaryolar için benzer, Azure Container Instances kullanılarak için ana senaryolar şunlardır:

- **Geliştirme/Test senaryoları**
- **Görev Otomasyonu**
- **CI/CD aracıları**
- **Küçük/ölçek toplu işleme**
- **Basit web uygulamaları**

Basit web apps senaryosu için ACI adil bir senaryodur ancak ACI kapsayıcı görüntüsü başına tek bir kapsayıcı örneği yalnızca olabileceği için yüksek oranda kullanılabilir olmaz ve yalnızca ölçeklenebilirlik sınırlı olduğunu dikkate alın.

Ancak, yalnızca tek bir container Instances sağladığından ACI altyapı bile edildiği durumlarda, Windows Server normal Azure Vm'lerle karşılaştırıldığında çok büyük bir avantajı yoktur. ACI, şirket içinde tutulan bir ortama yalnızca kapsayıcıları dağıtın ve yalnızca bu kapsayıcılar için ücret ödersiniz. Burada, sanal makineleri ile kapsayıcıları kullanıyor olabilecek çoğu senaryo için bir çok daha iyi platformu, bu nedenle korumak/güncelleştirme/düzeltme eki için Vm'leri, gerekmez. ACI kullanarak oldukça kolaydır, yalnızca bir kapsayıcı dağıtma, kapsayıcıları dağıttığınız yalnızca bir sanal makine ortamınızı oluşturmaya gerek yoktur.

Azure Container Instances'a (ACI) başlıca avantajları şunlardır:

- Kapsayıcıları, sunucu yönetmeye gerek kalmadan çalıştırın
- İsteğe bağlı kapsayıcılarla çevikliği artırın
- Bulutta hiç olmadığı kadar kolay ve hızlı kapsayıcılar dağıtma — tek bir komutla.
- Hiper yönetici yalıtımı ile uygulamaları güvenli hale getirin

Kısacası, ACI ile uygulamaları hızlı sanal makineler yönetmeden veya yeni araçlar öğrenmek zorunda kalmadan geliştirebilirsiniz. Yalnızca uygulamanızda, bir kapsayıcı içinde bulutta olduğu.

> [!div class="step-by-step"]
> [Önceki](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [İleri](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
