---
ms.openlocfilehash: e8fcd496b9c1921753ad0e1c2632f29bc5036956
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802465"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>ArgumentOutOfRangeException DataGridCellsPanel.BringIndexIntoView oluşturur

|   |   |
|---|---|
|Ayrıntılar|<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> Sütun sanallaştırma etkinleştirilmiş ancak sütun genişliklerini henüz karar olduğunda zaman uyumsuz olarak çalışır.  Zaman uyumsuz iş gerçekleşmeden önce sütunları kaldırılırsa bir <xref:System.ArgumentOutOfRangeException?displayProperty=name> ortaya çıkabilir.|
|Öneri|Aşağıdakilerden herhangi biri:<ol><li>.NET Framework 4.7 yükseltin.</li><li>En son hizmet düzeltme eki için .NET Framework 4.6.2 yükleyin.</li><li>Zaman uyumsuz yanıt kadar sütunları kaldırmayı önlemek <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> tamamlandı.</li></ol>|
|Kapsam|Kenar|
|Sürüm|4.6.2|
|Tür|Çalışma zamanı|
|Etkilenen API’ler|<ul><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|

