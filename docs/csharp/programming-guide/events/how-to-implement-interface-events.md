---
title: 'Nasıl yapılır: Arabirim olaylarını uygulama- C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 574ea9927a22c24c356d84652fd29692c519247b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590510"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a>Nasıl yapılır: Arabirim olaylarını uygulama (C# Programlama Kılavuzu)
Bir [arabirim](../../language-reference/keywords/interface.md) , bir [olayı](../../language-reference/keywords/event.md)bildirebilir. Aşağıdaki örnek, bir sınıfında arabirim olaylarının nasıl uygulanacağını gösterir. Temel olarak kurallar, herhangi bir arabirim yöntemi veya özelliği uygularken olduğu gibidir.  
  
## <a name="to-implement-interface-events-in-a-class"></a>Arabirim olaylarını bir sınıfta uygulamak için  
  
Sınıfınıza olayı bildirin ve uygun alanlarda çağırın.  
  
```csharp
namespace ImplementInterfaceEvents  
{  
    public interface IDrawingObject  
    {  
        event EventHandler ShapeChanged;  
    }  
    public class MyEventArgs : EventArgs   
    {  
        // class members  
    }  
    public class Shape : IDrawingObject  
    {  
        public event EventHandler ShapeChanged;  
        void ChangeShape()  
        {  
            // Do something here before the event…  

            OnShapeChanged(new MyEventArgs(/*arguments*/));  

            // or do something here after the event.   
        }  
        protected virtual void OnShapeChanged(MyEventArgs e)  
        {  
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek, sınıfınızın iki veya daha fazla arabirimden devraldığı daha az yaygın olan durumun nasıl işleneceğini ve her arabirimin aynı ada sahip bir olaya sahip olduğunu gösterir. Bu durumda, en az bir olay için açık bir arabirim uygulamasını sağlamalısınız. Bir olay için açık arabirim uygulama yazdığınızda, `add` ve `remove` olay erişimcilerini de yazmanız gerekir. Bunlar normalde derleyici tarafından sağlanır, ancak bu durumda derleyici bunları sağlayamaz.  
  
Kendi erişimclerinizi sunarak, iki olayın sınıfınıza aynı olay ile mi yoksa farklı olaylara göre mi temsil edileceğini belirtebilirsiniz. Örneğin, olayların arabirim belirtimlerine göre farklı zamanlarda oluşturulması gerekiyorsa, her bir olayı sınıfınıza ayrı bir uygulamayla ilişkilendirebilirsiniz. Aşağıdaki örnekte, aboneler bir `OnDraw` `IShape` veya bir veya bir `IDrawingObject`öğesine şekil başvurusunu kaldırarak hangi olayın alacağını tespit eder.  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../index.md)
- [Olaylar](./index.md)
- [Temsilciler](../delegates/index.md)
- [Belirtik Arabirim Kullanma](../interfaces/explicit-interface-implementation.md)
- [Nasıl yapılır: Türetilmiş sınıflarda temel sınıf olayları oluştur](./how-to-raise-base-class-events-in-derived-classes.md)
