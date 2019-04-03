---
title: Error deyimi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 8ac7cee2f9959bc75df165d00d3a0a67e1dd9af0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837539"
---
# <a name="error-statement"></a>Error Deyimi
Bir hatanın oluşum benzetimini yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Bölümler  
 `errornumber`  
 Gerekli. Herhangi bir geçerli hata sayı olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `Error` Deyimi, geriye dönük uyumluluk için desteklenir. Özellikle, nesneleri oluştururken yeni kodda, kullanın `Err` nesnenin `Raise` çalışma zamanı hataları oluşturmasına yöntemi.  
  
 Varsa `errornumber` tanımlanan `Error` ifade, sonra özelliklerini hata işleyicisini çağırır `Err` nesne, aşağıdaki varsayılan değerler atanır:  
  
|Özellik|Değer|  
|--------------|-----------|  
|`Number`|Bağımsız değişkeni olarak belirtilen değeri `Error` deyimi. Herhangi bir geçerli hata sayı olabilir.|  
|`Source`|Geçerli Visual Basic projesi adı.|  
|`Description`|Dize ifadesi dönüş değerine karşılık gelen `Error` işlevi için belirtilen `Number`, bu dizenin varsa. Dize mevcut değilse `Description` sıfır uzunlukta bir dize içerir ("").|  
|`HelpFile`|Tam sürücü yolu ve uygun Visual Basic Yardım dosyasının dosya adı.|  
|`HelpContext`|Visual Basic uygun Yardım dosyası hata karşılık gelen için bir bağlam kimliği `Number` özelliği.|  
|`LastDLLError`|Sıfır.|  
  
 Hiçbir hata işleyicisi yok veya etkinse, bir hata iletisi oluşturulur ve gelen görüntülenen `Err` nesne özellikleri.  
  
> [!NOTE]
>  Bazı Visual Basic ana bilgisayar uygulamalarını nesneler oluşturamaz. Sınıflar ve nesneler oluşturabilir olup olmadığını belirlemek için konak uygulamanızın belgelerine bakın.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `Error` hata numarası 11 oluşturulacak deyimi.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Derleme:** Visual Basic Çalışma Zamanı Kitaplığı (Microsoft.VisualBasic.dll içinde)  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [On Error Deyimi](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Resume Deyimi](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Hata İletileri](../../../visual-basic/language-reference/error-messages/index.md)
