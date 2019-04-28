---
title: 'Nasıl yapılır: Geri Çağırma İşlevlerini Uygulama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0a033e6881f9c0c8741fda26211b0f565762de4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61643094"
---
# <a name="how-to-implement-callback-functions"></a><span data-ttu-id="5116a-102">Nasıl yapılır: Geri Çağırma İşlevlerini Uygulama</span><span class="sxs-lookup"><span data-stu-id="5116a-102">How to: Implement Callback Functions</span></span>
<span data-ttu-id="5116a-103">Aşağıdaki yordam ve örnek platformunu kullanarak yönetilen bir uygulamada nasıl çağırma göstermek, her pencere tanıtıcısı değeri yerel bilgisayarda yazdırabilir.</span><span class="sxs-lookup"><span data-stu-id="5116a-103">The following procedure and example demonstrate how a managed application, using platform invoke, can print the handle value for each window on the local computer.</span></span> <span data-ttu-id="5116a-104">Özellikle, yordam ve örnek kullanım **EnumWindows** işlev için windows ve yönetilen bir geri çağırma işlevi (pencere tanıtıcısı değerini yazdırmak için adlandırılmış geri çağırma işlemini) listesinde ilerleyin.</span><span class="sxs-lookup"><span data-stu-id="5116a-104">Specifically, the procedure and example use the **EnumWindows** function to step through the list of windows and a managed callback function (named CallBack) to print the value of the window handle.</span></span>  
  
### <a name="to-implement-a-callback-function"></a><span data-ttu-id="5116a-105">Bir geri çağırma işlevini uygulamak için</span><span class="sxs-lookup"><span data-stu-id="5116a-105">To implement a callback function</span></span>  
  
1. <span data-ttu-id="5116a-106">İmzası bakın **EnumWindows** başka bir uygulama ile geçmeden önce işlevi.</span><span class="sxs-lookup"><span data-stu-id="5116a-106">Look at the signature for the **EnumWindows** function before going further with the implementation.</span></span> <span data-ttu-id="5116a-107">**EnumWindows** şu imzaya sahip:</span><span class="sxs-lookup"><span data-stu-id="5116a-107">**EnumWindows** has the following signature:</span></span>  
  
    ```  
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)  
    ```  
  
     <span data-ttu-id="5116a-108">Bu işlev bir geri çağırma gerektiren bir ipucudur varlığını **lpEnumFunc** bağımsız değişken.</span><span class="sxs-lookup"><span data-stu-id="5116a-108">One clue that this function requires a callback is the presence of the **lpEnumFunc** argument.</span></span> <span data-ttu-id="5116a-109">Yaygın **lp** (uzun işaretçisi) öneki Sunucusu'yla birlikte **Func** soneki adını almak için bir geri arama işlevine bir işaretçi bağımsız değişkenler.</span><span class="sxs-lookup"><span data-stu-id="5116a-109">It is common to see the **lp** (long pointer) prefix combined with the **Func** suffix in the name of arguments that take a pointer to a callback function.</span></span> <span data-ttu-id="5116a-110">Microsoft Platform SDK'sı Win32 işlevlerini ilgili belgeler için bkz.</span><span class="sxs-lookup"><span data-stu-id="5116a-110">For documentation about Win32 functions, see the Microsoft Platform SDK.</span></span>  
  
2. <span data-ttu-id="5116a-111">Yönetilen bir geri çağırma işlevi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="5116a-111">Create the managed callback function.</span></span> <span data-ttu-id="5116a-112">Örnek adlı bir temsilci türü bildirir `CallBack`, iki bağımsız değişken alır (**hwnd** ve **lparam**).</span><span class="sxs-lookup"><span data-stu-id="5116a-112">The example declares a delegate type, called `CallBack`, which takes two arguments (**hwnd** and **lparam**).</span></span> <span data-ttu-id="5116a-113">İlk bağımsız değişken penceresinde bir işleyicisidir; İkinci bağımsız değişkeni uygulama tarafından tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="5116a-113">The first argument is a handle to the window; the second argument is application-defined.</span></span> <span data-ttu-id="5116a-114">Bu sürümde, her iki değişken tamsayılar olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5116a-114">In this release, both arguments must be integers.</span></span>  
  
     <span data-ttu-id="5116a-115">Geri çağırma işlevleri genellikle başarı ve başarısızlık belirtmek için sıfır belirtmek için sıfır olmayan değerler döndürür.</span><span class="sxs-lookup"><span data-stu-id="5116a-115">Callback functions generally return nonzero values to indicate success and zero to indicate failure.</span></span> <span data-ttu-id="5116a-116">Bu örnek açıkça dönüş değeri ayarlar **true** numaralandırma devam etmek için.</span><span class="sxs-lookup"><span data-stu-id="5116a-116">This example explicitly sets the return value to **true** to continue the enumeration.</span></span>  
  
3. <span data-ttu-id="5116a-117">Temsilci oluşturmak ve bağımsız değişken olarak geçirin **EnumWindows** işlevi.</span><span class="sxs-lookup"><span data-stu-id="5116a-117">Create a delegate and pass it as an argument to the **EnumWindows** function.</span></span> <span data-ttu-id="5116a-118">Platform çağırma temsilci otomatik olarak tanıdık geri çağırma biçimine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="5116a-118">Platform invoke converts the delegate to a familiar callback format automatically.</span></span>  
  
4. <span data-ttu-id="5116a-119">Geri çağırma işlevi, iş tamamlanmadan önce çöp toplayıcı temsilci kazanmıyor emin olun.</span><span class="sxs-lookup"><span data-stu-id="5116a-119">Ensure that the garbage collector does not reclaim the delegate before the callback function completes its work.</span></span> <span data-ttu-id="5116a-120">Bir temsilci bir parametre olarak geçir veya yapısına bir alan olarak yer alan bir temsilci geçirmek, çağrı süresi boyunca uncollected kalır.</span><span class="sxs-lookup"><span data-stu-id="5116a-120">When you pass a delegate as a parameter, or pass a delegate contained as a field in a structure, it remains uncollected for the duration of the call.</span></span> <span data-ttu-id="5116a-121">Bu nedenle, sabit listesi aşağıdaki örnekte olduğu gibi geri çağırma işlevi işini tamamlayıncaya önce çağrı döndürür ve yönetilen çağıran tarafından başka bir işlem gerektirir.</span><span class="sxs-lookup"><span data-stu-id="5116a-121">So, as is the case in the following enumeration example, the callback function completes its work before the call returns and requires no additional action by the managed caller.</span></span>  
  
     <span data-ttu-id="5116a-122">Eğer, ancak geri çağırma işlevi çağrısı döndürdükten sonra çağrılabilir, yönetilen çağırana geri çağırma işlevi bitene kadar temsilci uncollected kalmasını sağlamak için adımları uygulamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5116a-122">If, however, the callback function can be invoked after the call returns, the managed caller must take steps to ensure that the delegate remains uncollected until the callback function finishes.</span></span> <span data-ttu-id="5116a-123">Çöp toplama engelleme hakkında ayrıntılı bilgi için bkz: [birlikte çalışma hazırlama](../../../docs/framework/interop/interop-marshaling.md) Platform Çağırma ile.</span><span class="sxs-lookup"><span data-stu-id="5116a-123">For detailed information about preventing garbage collection, see [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md) with Platform Invoke.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5116a-124">Örnek</span><span class="sxs-lookup"><span data-stu-id="5116a-124">Example</span></span>  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
  
Public Delegate Function CallBack( _  
hwnd As Integer, lParam As Integer) As Boolean  
  
Public Class EnumReportApp  
  
    Declare Function EnumWindows Lib "user32" ( _  
       x As CallBack, y As Integer) As Integer  
  
    Public Shared Sub Main()  
        EnumWindows(AddressOf EnumReportApp.Report, 0)  
    End Sub 'Main  
  
    Public Shared Function Report(hwnd As Integer, lParam As Integer) _  
    As Boolean  
        Console.Write("Window handle is ")  
        Console.WriteLine(hwnd)  
        Return True  
    End Function 'Report  
End Class 'EnumReportApp  
```  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public delegate bool CallBack(int hwnd, int lParam);  
  
public class EnumReportApp  
{  
    [DllImport("user32")]  
    public static extern int EnumWindows(CallBack x, int y);   
  
    public static void Main()   
    {  
        CallBack myCallBack = new CallBack(EnumReportApp.Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    public static bool Report(int hwnd, int lParam)  
    {   
        Console.Write("Window handle is ");  
        Console.WriteLine(hwnd);  
        return true;  
    }  
}  
```  
  
```cpp  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// A delegate type.  
delegate bool CallBack(int hwnd, int lParam);  
  
// Managed type with the method to call.  
ref class EnumReport  
{  
// Report the window handle.  
public:  
    [DllImport("user32")]  
    static int EnumWindows(CallBack^ x, int y);  
  
    static void Main()  
    {  
        EnumReport^ er = gcnew EnumReport;  
        CallBack^ myCallBack = gcnew CallBack(&EnumReport::Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    static bool Report(int hwnd, int lParam)  
    {  
       Console::Write(L"Window handle is ");  
       Console::WriteLine(hwnd);  
       return true;  
    }  
};  
  
int main()  
{  
    EnumReport::Main();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5116a-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5116a-125">See also</span></span>

- [<span data-ttu-id="5116a-126">Geri Arama İşlevleri</span><span class="sxs-lookup"><span data-stu-id="5116a-126">Callback Functions</span></span>](../../../docs/framework/interop/callback-functions.md)
- [<span data-ttu-id="5116a-127">DLL İşlevini Çağırma</span><span class="sxs-lookup"><span data-stu-id="5116a-127">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
