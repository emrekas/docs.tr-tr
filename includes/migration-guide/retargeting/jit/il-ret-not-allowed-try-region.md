---
ms.openlocfilehash: 060da3ebc60057554fd572bd2569652afee6bd0f
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804480"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a>IL ret deneyin bölgede izin verilmiyor

|   |   |
|---|---|
|Ayrıntılar|JIT64 tam zamanında derleyici, bir IL yönergesi bir try bölgede ret (.NET Framework 4. 6'içinde kullanılan) Ryujıt izin vermez. Bir try bölgeden döndüren ECMA-335 belirtimine göre izin verilmez ve bu tür IL bilinen hiçbir yönetilen derleyici oluşturur. Bununla birlikte, yansıma kullanarak oluşturulursa JIT64 derleyici böyle IL yürütecek gösterin.|
|Öneri|Bir uygulama bir try bölgede ret opcode içeren IL oluşturuyorsa, uygulama .NET Framework 4. 5'i eski JIT kullanın ve bu kesmesinden kaçınılmasını sağlar hedefleyebilir. Alternatif olarak, oluşturulan IL sonra deneyin bölge döndürmek için güncelleştirilebilir.|
|Kapsam|Kenar|
|Sürüm|4.6|
|Tür|Yeniden Hedefleme|

