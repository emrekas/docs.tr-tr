---
title: Kurumsal Hizmetler İşlemsel Bileşenlerini Tümleştirme
ms.date: 03/30/2017
ms.assetid: 05dab277-b8b2-48cf-b40c-826be128b175
ms.openlocfilehash: 33e09eab1d7ad24dc234cfff21e352611e0b2ef9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047041"
---
# <a name="integrating-enterprise-services-transactional-components"></a><span data-ttu-id="a1f1d-102">Kurumsal Hizmetler İşlemsel Bileşenlerini Tümleştirme</span><span class="sxs-lookup"><span data-stu-id="a1f1d-102">Integrating Enterprise Services Transactional Components</span></span>
<span data-ttu-id="a1f1d-103">Windows Communication Foundation (WCF) Hizmetleri ile Kurumsal tümleştirme için otomatik bir mekanizma sağlar (bkz [COM + uygulamaları ile tümleştirme](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)).</span><span class="sxs-lookup"><span data-stu-id="a1f1d-103">Windows Communication Foundation (WCF) provides an automatic mechanism for integrating with Enterprise Services (see [Integrating with COM+ Applications](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)).</span></span> <span data-ttu-id="a1f1d-104">Ancak, dahili olarak Enterprise Hizmetleri içinde bulunan işlem bileşenleri kullanan hizmetleri geliştirmek için esneklik isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-104">However, you may want the flexibility to develop services that internally use transactional components hosted within Enterprise Services.</span></span> <span data-ttu-id="a1f1d-105">WCF işlem özellik oluşturulduğundan <xref:System.Transactions> altyapı, Kurumsal Services'ı WCF ile tümleştirme sürecini arasında birlikte çalışabilirlik belirtmek için aynı <xref:System.Transactions> ve kurumsal açıklandığı gibi hizmetleri [Kurumsal Hizmetler ve COM + işlemleri ile birlikte çalışabilirlik](https://go.microsoft.com/fwlink/?LinkId=94949).</span><span class="sxs-lookup"><span data-stu-id="a1f1d-105">Because the WCF Transactions feature is built on the <xref:System.Transactions> infrastructure, the process for integrating Enterprise Services with WCF is identical to that for specifying interoperability between <xref:System.Transactions> and Enterprise Services, as outlined in [Interoperability with Enterprise Services and COM+ Transactions](https://go.microsoft.com/fwlink/?LinkId=94949).</span></span>  
  
 <span data-ttu-id="a1f1d-106">İstenen akışlı gelen işlem ve COM + bağlamı işlem arasında birlikte çalışabilirlik düzeyini sağlamak için hizmet uygulaması oluşturmanız gerekir bir <xref:System.Transactions.TransactionScope> uygun değerini kullanın ve örnek <xref:System.Transactions.EnterpriseServicesInteropOption> sabit listesi.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-106">To provide the desired level of interoperability between the incoming flowed transaction and the COM+ context transaction, the service implementation must create a <xref:System.Transactions.TransactionScope> instance and use the appropriate value from the <xref:System.Transactions.EnterpriseServicesInteropOption> enumeration.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-service-operation"></a><span data-ttu-id="a1f1d-107">Kurumsal Hizmetler bir hizmet işlemi ile tümleştirme</span><span class="sxs-lookup"><span data-stu-id="a1f1d-107">Integrating Enterprise Services with a Service Operation</span></span>  
 <span data-ttu-id="a1f1d-108">Aşağıdaki kod, oluşturan, izin verilen işlem akışı ile bir işlem gösterir bir <xref:System.Transactions.TransactionScope> ile <xref:System.Transactions.EnterpriseServicesInteropOption.Full> seçeneği.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-108">The following code demonstrates an operation, with Allowed transaction flow, that creates a <xref:System.Transactions.TransactionScope> with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> option.</span></span> <span data-ttu-id="a1f1d-109">Bu senaryoda aşağıdaki koşullar geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="a1f1d-109">The following conditions apply in this scenario:</span></span>  
  
- <span data-ttu-id="a1f1d-110">İstemci bir işlem olursa Enterprise hizmetleri bileşeni için arama da dahil olmak üzere bu işlemi bu işlemin kapsamı içinde yürütülür.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-110">If the client flows a transaction, the operation, including the call to the Enterprise Services component, is executed within the scope of that transaction.</span></span> <span data-ttu-id="a1f1d-111">Kullanarak <xref:System.Transactions.EnterpriseServicesInteropOption.Full> işlem ile eşitlendiğini sağlar <xref:System.EnterpriseServices> anlamına gelir için ortam işlem bağlamı <xref:System.Transactions> ve <xref:System.EnterpriseServices> aynıdır.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-111">Using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the transaction is synchronized with the <xref:System.EnterpriseServices> context, which means that the ambient transaction for <xref:System.Transactions> and the <xref:System.EnterpriseServices> is the same.</span></span>  
  
- <span data-ttu-id="a1f1d-112">İstemci bir işlem geçmeyen varsa, <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> için `true` işlemi için yeni bir işlem kapsamı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-112">If the client does not flow a transaction, setting <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> to `true` creates a new transaction scope for the operation.</span></span> <span data-ttu-id="a1f1d-113">Benzer şekilde, kullanarak <xref:System.Transactions.EnterpriseServicesInteropOption.Full> işlemin işlem içinde kullanılan işlem ile aynı olmasını sağlar <xref:System.EnterpriseServices> bileşenin bağlamı.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-113">Similarly, using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the operation’s transaction is the same as the transaction used inside the <xref:System.EnterpriseServices> component's context.</span></span>  
  
 <span data-ttu-id="a1f1d-114">Herhangi bir ek yöntem çağrılarını da aynı işlemin işlem kapsamında oluşur.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-114">Any additional method calls also occur within the scope of the same operation’s transaction.</span></span>  
  
```  
[ServiceContract()]  
public interface ICustomerServiceContract  
{  
   [OperationContract]  
   [TransactionFlow(TransactionFlowOption.Allowed)]  
   void UpdateCustomerNameOperation(int customerID, string newCustomerName);  
}  
  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CustomerService : ICustomerServiceContract  
{  
   [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
   public void UpdateCustomerNameOperation(int customerID, string newCustomerName)  
   {  
   // Create a transaction scope with full ES interop  
      using (TransactionScope ts = new TransactionScope(  
                     TransactionScopeOption.Required,  
                     new TransactionOptions(),  
                     EnterpriseServicesInteropOption.Full))  
      {  
         // Create an Enterprise Services component  
         // Call UpdateCustomer method on an Enterprise Services   
         // component   
  
         // Call UpdateOtherCustomerData method on an Enterprise   
         // Services component   
         ts.Complete();  
      }  
  
      // Do UpdateAdditionalData on an non-Enterprise Services  
      // component  
   }  
}  
```  
  
 <span data-ttu-id="a1f1d-115">Bir işlemin geçerli işlem ve Kurumsal Hizmetler işlemsel bileşenlerini çağrıları arasında eşitleme gereklidir, ardından kullanın <xref:System.Transactions.EnterpriseServicesInteropOption.None> seçeneği örneklerken <xref:System.Transactions.TransactionScope> örneği.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-115">If no synchronization is required between an operation’s current transaction and calls to transactional Enterprise Services components, then use the <xref:System.Transactions.EnterpriseServicesInteropOption.None> option when instantiating the <xref:System.Transactions.TransactionScope> instance.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-client"></a><span data-ttu-id="a1f1d-116">Kurumsal Hizmetler istemcisi ile tümleştirme</span><span class="sxs-lookup"><span data-stu-id="a1f1d-116">Integrating Enterprise Services with a Client</span></span>  
 <span data-ttu-id="a1f1d-117">Aşağıdaki kod, istemci kodu kullanarak gösterir. bir <xref:System.Transactions.TransactionScope> ile örnek <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ayarı.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-117">The following code demonstrates client code using a <xref:System.Transactions.TransactionScope> instance with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> setting.</span></span> <span data-ttu-id="a1f1d-118">Bu senaryoda, Enterprise Hizmetleri bileşenleri çağrılar aynı işlem kapsamında işlem akışı destekleyen hizmet işlemlerine çağrıları oluşur.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-118">In this scenario, calls to service operations that support transaction flow occur within the scope of the same transaction as the calls to Enterprise Services components.</span></span>  
  
```  
static void Main()  
{  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
  
    // Create a transaction scope with full ES interop  
    using (TransactionScope ts = new TransactionScope(  
          TransactionScopeOption.Required,  
          new TransactionOptions(),  
          EnterpriseServicesInteropOption.Full))  
    {  
        // Call Add calculator service operation  
  
        // Create an Enterprise Services component  
  
        // Call UpdateCustomer method on an Enterprise Services   
        // component   
  
        ts.Complete();  
    }  
  
    // Closing the client gracefully closes the connection and   
    // cleans up resources  
    client.Close();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1f1d-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a1f1d-119">See also</span></span>

- [<span data-ttu-id="a1f1d-120">COM+ Uygulamaları ile Tümleştirme</span><span class="sxs-lookup"><span data-stu-id="a1f1d-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="a1f1d-121">COM Uygulamaları ile Tümleştirme</span><span class="sxs-lookup"><span data-stu-id="a1f1d-121">Integrating with COM Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications.md)
