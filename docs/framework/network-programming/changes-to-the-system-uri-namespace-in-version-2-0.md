---
title: System.Uri ad 2.0 sürümündeki değişiklikler
ms.date: 03/30/2017
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
ms.openlocfilehash: 987010b8367069e8089df3f809d23f258bb68f2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61642769"
---
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a>System.Uri ad 2.0 sürümündeki değişiklikler

Birkaç değişiklik yapılmıştır <xref:System.Uri?displayProperty=nameWithType> sınıfı. Bu değişiklikler yanlış davranışa sabit, artırılmış kullanılabilirlik ve Gelişmiş Güvenlik.

## <a name="obsolete-and-deprecated-members"></a>Artık kullanılmıyor ve kullanım dışı bırakılan üyeleri

 Oluşturucular:

- Sahip tüm oluşturucular bir `dontEscape` parametresi.

 Yöntemleri:

- <xref:System.Uri.CheckSecurity%2A>

- <xref:System.Uri.Escape%2A>

- <xref:System.Uri.Canonicalize%2A>

- <xref:System.Uri.Parse%2A>

- <xref:System.Uri.IsReservedCharacter%2A>

- <xref:System.Uri.IsBadFileSystemCharacter%2A>

- <xref:System.Uri.IsExcludedCharacter%2A>

- <xref:System.Uri.EscapeString%2A>

## <a name="changes"></a>Değişiklikler

- (Dosya, ftp ve diğerleri), sorgu parçası olmayan bilinen URI düzenleri için '?' karakteri, her zaman Atlanan ve başlangıcı olarak kabul edilmez bir <xref:System.Uri.Query%2A> bölümü.

- Örtük dosya URI'ler için (form `c:\directory\file@name.txt`), parça karakter ('#') tam unescaping istenen sürece her zaman kaçırılmışsa veya <xref:System.Uri.LocalPath%2A> olduğu `true`.

- UNC ana bilgisayar adı desteği kaldırıldı; Uluslararası ana bilgisayar adları temsil eden IDN belirtimi benimsenen.

- <xref:System.Uri.LocalPath%2A> her zaman tamamen atlanmayan bir dize döndürür.

- <xref:System.Uri.ToString%2A> bir kaçış '%', unescape değil '?', veya '#' karakteri.

- <xref:System.Uri.Equals%2A> artık <xref:System.Uri.Query%2A> yapılan eşitlik kontrolüne bölümünde.

- İşleçleri "=="ve"! =" geçersiz kılınacak ve bağlantılı <xref:System.Uri.Equals%2A> yöntemi.

- <xref:System.Uri.IsLoopback%2A> Şimdi, tutarlı sonuçlar üretir.

- URI "`file:///path`" artık veri dönüştürülür `file://path`.

- "#", artık bir konak adı Sonlandırıcı kabul edilir. Diğer bir deyişle, `http://contoso.com#fragment` artık dönüştürülür `http://contoso.com/#fragment`.

- Taban URI ile bir parça birleştirilirken bir hata düzeltildi.

- Bir hatada <xref:System.Uri.HostNameType%2A> sabittir.

- NNTP ayrıştırılırken bir hata düzeltildi.

- Bir URI biçiminde HTTP:contoso.com artık bir ayrıştırma özel durumu oluşturur.

- Framework doğru bir Uri kullanıcı bilgileri işler.

- Bozuk URI yukarıda kök dosya sistemine çapraz olamaz, URI yolu sıkıştırma sabittir.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Uri?displayProperty=nameWithType>
