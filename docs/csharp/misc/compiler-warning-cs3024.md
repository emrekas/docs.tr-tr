---
title: Derleyici Uyarısı CS3024
ms.date: 07/20/2015
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
ms.openlocfilehash: 6147fc1aafc06d7c844cfc39eafebbd737d89610
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69601965"
---
# <a name="compiler-warning-cs3024"></a>Derleyici Uyarısı CS3024
' Type ' kısıtlama türü CLS uyumlu değil.  
  
 Bu uyarı, CLS uyumlu olmayan bir türün genel bir tür kısıtlaması olarak kullanılması, bazı dillerde yazılan kodun genel sınıfınızı kullanmasını olanaksız hale getirecek olduğundan bu uyarıyı yayınlar.  
  
### <a name="to-eliminate-this-warning"></a>Bu uyarıyı kaldırmak için  
  
1. Tür kısıtlaması için CLS uyumlu bir tür kullanın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli konumlarda CS3024 oluşturur:  
  
```csharp  
// cs3024.cs  
// Compile with: /target:library  
 [assembly: System.CLSCompliant(true)]  
  
[type: System.CLSCompliant(false)]  
public class TestClass // CS3024  
{  
    public ushort us;  
}  
[type: System.CLSCompliant(false)]  
public interface ITest // CS3024  
{}  
public interface I<T> where T : TestClass  
{}  
public class TestClass_2<T> where T : ITest  
{}  
public class TestClass_3<T> : I<T> where T : TestClass  
{}  
public class TestClass_4<T> : TestClass_2<T> where T : ITest  
{}  
public class Test  
{  
    public static int Main()  
    {  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Tür Parametrelerindeki Kısıtlamalar](../programming-guide/generics/constraints-on-type-parameters.md)
