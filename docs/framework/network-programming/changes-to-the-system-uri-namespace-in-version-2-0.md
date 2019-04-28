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
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a><span data-ttu-id="b9431-102">System.Uri ad 2.0 sürümündeki değişiklikler</span><span class="sxs-lookup"><span data-stu-id="b9431-102">Changes to the System.Uri namespace in version 2.0</span></span>

<span data-ttu-id="b9431-103">Birkaç değişiklik yapılmıştır <xref:System.Uri?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b9431-103">Several changes were made to the <xref:System.Uri?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="b9431-104">Bu değişiklikler yanlış davranışa sabit, artırılmış kullanılabilirlik ve Gelişmiş Güvenlik.</span><span class="sxs-lookup"><span data-stu-id="b9431-104">These changes fixed incorrect behavior, enhanced usability, and enhanced security.</span></span>

## <a name="obsolete-and-deprecated-members"></a><span data-ttu-id="b9431-105">Artık kullanılmıyor ve kullanım dışı bırakılan üyeleri</span><span class="sxs-lookup"><span data-stu-id="b9431-105">Obsolete and deprecated Members</span></span>

 <span data-ttu-id="b9431-106">Oluşturucular:</span><span class="sxs-lookup"><span data-stu-id="b9431-106">Constructors:</span></span>

- <span data-ttu-id="b9431-107">Sahip tüm oluşturucular bir `dontEscape` parametresi.</span><span class="sxs-lookup"><span data-stu-id="b9431-107">All constructors that have a `dontEscape` parameter.</span></span>

 <span data-ttu-id="b9431-108">Yöntemleri:</span><span class="sxs-lookup"><span data-stu-id="b9431-108">Methods:</span></span>

- <xref:System.Uri.CheckSecurity%2A>

- <xref:System.Uri.Escape%2A>

- <xref:System.Uri.Canonicalize%2A>

- <xref:System.Uri.Parse%2A>

- <xref:System.Uri.IsReservedCharacter%2A>

- <xref:System.Uri.IsBadFileSystemCharacter%2A>

- <xref:System.Uri.IsExcludedCharacter%2A>

- <xref:System.Uri.EscapeString%2A>

## <a name="changes"></a><span data-ttu-id="b9431-109">Değişiklikler</span><span class="sxs-lookup"><span data-stu-id="b9431-109">Changes</span></span>

- <span data-ttu-id="b9431-110">(Dosya, ftp ve diğerleri), sorgu parçası olmayan bilinen URI düzenleri için '?' karakteri, her zaman Atlanan ve başlangıcı olarak kabul edilmez bir <xref:System.Uri.Query%2A> bölümü.</span><span class="sxs-lookup"><span data-stu-id="b9431-110">For URI schemes that are known to not have a query part (file, ftp, and others), the '?' character is always escaped and is not considered the beginning of a <xref:System.Uri.Query%2A> part.</span></span>

- <span data-ttu-id="b9431-111">Örtük dosya URI'ler için (form `c:\directory\file@name.txt`), parça karakter ('#') tam unescaping istenen sürece her zaman kaçırılmışsa veya <xref:System.Uri.LocalPath%2A> olduğu `true`.</span><span class="sxs-lookup"><span data-stu-id="b9431-111">For implicit file URIs (of the form `c:\directory\file@name.txt`), the fragment character ('#') is always escaped unless full unescaping is requested or <xref:System.Uri.LocalPath%2A> is `true`.</span></span>

- <span data-ttu-id="b9431-112">UNC ana bilgisayar adı desteği kaldırıldı; Uluslararası ana bilgisayar adları temsil eden IDN belirtimi benimsenen.</span><span class="sxs-lookup"><span data-stu-id="b9431-112">UNC hostname support was removed; the IDN specification for representing international hostnames was adopted.</span></span>

- <span data-ttu-id="b9431-113"><xref:System.Uri.LocalPath%2A> her zaman tamamen atlanmayan bir dize döndürür.</span><span class="sxs-lookup"><span data-stu-id="b9431-113"><xref:System.Uri.LocalPath%2A> always returns a completely unescaped string.</span></span>

- <span data-ttu-id="b9431-114"><xref:System.Uri.ToString%2A> bir kaçış '%', unescape değil '?', veya '#' karakteri.</span><span class="sxs-lookup"><span data-stu-id="b9431-114"><xref:System.Uri.ToString%2A> does not unescape an escaped '%', '?', or '#' character.</span></span>

- <span data-ttu-id="b9431-115"><xref:System.Uri.Equals%2A> artık <xref:System.Uri.Query%2A> yapılan eşitlik kontrolüne bölümünde.</span><span class="sxs-lookup"><span data-stu-id="b9431-115"><xref:System.Uri.Equals%2A> now includes the <xref:System.Uri.Query%2A> part in the equality check.</span></span>

- <span data-ttu-id="b9431-116">İşleçleri "=="ve"! =" geçersiz kılınacak ve bağlantılı <xref:System.Uri.Equals%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="b9431-116">Operators "==" and "!=" are overridden and linked to the <xref:System.Uri.Equals%2A> method.</span></span>

- <span data-ttu-id="b9431-117"><xref:System.Uri.IsLoopback%2A> Şimdi, tutarlı sonuçlar üretir.</span><span class="sxs-lookup"><span data-stu-id="b9431-117"><xref:System.Uri.IsLoopback%2A> now produces consistent results.</span></span>

- <span data-ttu-id="b9431-118">URI "`file:///path`" artık veri dönüştürülür `file://path`.</span><span class="sxs-lookup"><span data-stu-id="b9431-118">The URI "`file:///path`" is no longer translated into `file://path`.</span></span>

- <span data-ttu-id="b9431-119">"#", artık bir konak adı Sonlandırıcı kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="b9431-119">"#" is now recognized as a host name terminator.</span></span> <span data-ttu-id="b9431-120">Diğer bir deyişle, `http://contoso.com#fragment` artık dönüştürülür `http://contoso.com/#fragment`.</span><span class="sxs-lookup"><span data-stu-id="b9431-120">That is, `http://contoso.com#fragment` is now converted to `http://contoso.com/#fragment`.</span></span>

- <span data-ttu-id="b9431-121">Taban URI ile bir parça birleştirilirken bir hata düzeltildi.</span><span class="sxs-lookup"><span data-stu-id="b9431-121">A bug when combining a base URI with a fragment has been fixed.</span></span>

- <span data-ttu-id="b9431-122">Bir hatada <xref:System.Uri.HostNameType%2A> sabittir.</span><span class="sxs-lookup"><span data-stu-id="b9431-122">A bug in <xref:System.Uri.HostNameType%2A> is fixed.</span></span>

- <span data-ttu-id="b9431-123">NNTP ayrıştırılırken bir hata düzeltildi.</span><span class="sxs-lookup"><span data-stu-id="b9431-123">A bug in NNTP parsing is fixed.</span></span>

- <span data-ttu-id="b9431-124">Bir URI biçiminde HTTP:contoso.com artık bir ayrıştırma özel durumu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b9431-124">A URI of the form HTTP:contoso.com now throws a parsing exception.</span></span>

- <span data-ttu-id="b9431-125">Framework doğru bir Uri kullanıcı bilgileri işler.</span><span class="sxs-lookup"><span data-stu-id="b9431-125">The Framework correctly handles userinfo in a URI.</span></span>

- <span data-ttu-id="b9431-126">Bozuk URI yukarıda kök dosya sistemine çapraz olamaz, URI yolu sıkıştırma sabittir.</span><span class="sxs-lookup"><span data-stu-id="b9431-126">URI path compression is fixed so that a broken URI cannot traverse the file system above the root.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9431-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b9431-127">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
