---
title: .NET Framework'te Güvenlik Değişiklikleri
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61f9e68bcc554dc3e4a4878e575d3f046a8ef9f5
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378600"
---
# <a name="security-changes-in-the-net-framework"></a>.NET Framework'te Güvenlik Değişiklikleri
En önemli .NET Framework 4. 5'deki güvenlik tanımlayıcı adlandırma değişikliktir. Bkz: [Gelişmiş kesin adlandırma](../../../docs/framework/app-domains/enhanced-strong-naming.md) bu değişikliklerin bir açıklaması için.  
  
 .NET Framework yönetilen uygulamalar için iki katmanlı güvenlik modeli sağlar. [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulamaları, kaynaklara erişimi sınırlayan bir Windows güvenlik kapsayıcısında çalışır. Bu kapsayıcı içinde yönetilen uygulamaların tam olarak güvenilen çalıştırın. Bir kod erişimi güvenliği (CAS) açısından bakıldığında, hiçbir şey yoktur bir geliştirici ayrıcalıklarını yükseltme yapabilirsiniz. Windows tarafından verilen izinler hakkında daha fazla bilgi için bkz. [uygulama yeteneği bildirimleri (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) Windows geliştirme Merkezi'nde. Oluşturma hakkında daha fazla bilgi için bir [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulaması, bakın [C# veya Visual Basic kullanarak ilk Windows Store uygulamasını oluşturma](https://go.microsoft.com/fwlink/?LinkId=230461).
