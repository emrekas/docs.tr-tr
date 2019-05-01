---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924715"
---
# <a name="1006---workflowapplicationunhandledexception"></a>1006 - WorkflowApplicationUnhandledException
## <a name="properties"></a>Özellikler  
  
|||  
|-|-|  
|Kimlik|1006|  
|anahtar sözcükler|WFRuntime|  
|Düzey|Hata|  
|Kanal|Microsoft Windows uygulaması sunucu-uygulamalar/hata ayıklama|  
  
## <a name="description"></a>Açıklama  
 Bir iş akışı uygulaması işlenmeyen bir özel durumla karşılaştı gösterir.  
  
## <a name="message"></a>İleti  
 WorkflowInstance ID: '%1' işlenmeyen bir özel durumla karşılaştı.  Özel durum '%2', DisplayName etkinliğinden kaynaklanan: '%3'.  Aşağıdaki işlem yapılmayacak: %4.  
  
## <a name="details"></a>Ayrıntılar  
  
|Veri öğesi adı|Veri öğesi türü|Açıklama|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceID|`xs:string`|İş akışı örnek kimliği|  
|Özel Durum|`xs:string`|Özel durum için özel durum ayrıntıları|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.|
