---
title: 'Nasıl yapılır: Özel Örnek Deposu Oluşturma'
ms.date: 03/30/2017
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
ms.openlocfilehash: cacee7d95a543525ba031de0cc0636d05fc72fc8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945645"
---
# <a name="how-to-create-a-custom-instance-store"></a>Nasıl yapılır: Özel Örnek Deposu Oluşturma

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] içeren <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, iş akışı verileri kalıcı hale getirmek için SQL Server kullanan bir örnek deposu. Uygulamanız farklı bir veritabanı veya bir dosya sistemi gibi başka bir orta iş akışı verileri kalıcı hale getirmek için gerekli ise bir özel örnek deposu uygulayabilirsiniz. Özet genişleterek bir özel örnek deposu oluşturulan <xref:System.Runtime.DurableInstancing.InstanceStore> sınıfı ve uygulama için gereken yöntemleri uygulamak. Bir özel örnek deposu tam bir uygulama için bkz: [şirket satın alma işlemi](./samples/corporate-purchase-process.md) örnek.

## <a name="implementing-the-begintrycommand-method"></a>BeginTryCommand yöntemi uygulama

<xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> Örnek deposuna Kalıcılık altyapısı tarafından gönderilir. Türünü `command` parametresi hangi komutun yürütülmesini gösterir; Bu parametre aşağıdaki türlerde olabilir:

- <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: Bu komutu kullanırken bir iş akışı kalıcı depolama ortamı için Kalıcılık altyapısı örnek deposuna gönderir. İş akışı kalıcılığı verileri yöntemine sağlanan <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> üyesi `command` parametresi.

- <xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: Depolama ortamından yüklenecek bir iş akışı olduğunda Kalıcılık altyapısı bu komut örnek depoya gönderir. Yüklenecek iş akışı örnek kimliği yöntemine sağlanan `instanceId` parametresinin <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> özelliği `context` parametresi.

- <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: Bu komut örneğine depolamak Kalıcılık altyapısı gönderen bir <xref:System.ServiceModel.Activities.WorkflowServiceHost> kilit sahibi olarak kaydedilmesi gerekir. Örnek kimliği geçerli iş akışı örneği kullanarak mağaza sağlanmalıdır <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> yöntemi `context` parametresi.

     Aşağıdaki kod parçacığı bir özel kilit sahibi atamak için CreateWorkflowOwner komutu uygulamak nasıl gösterir.

    ```csharp
    XName WFInstanceScopeName = XName.Get(scopeName, "<namespace>");
    ...
    CreateWorkflowOwnerCommand createCommand = new CreateWorkflowOwnerCommand()
    {
        InstanceOwnerMetadata =
        {
            { WorkflowHostTypeName, new InstanceValue(WFInstanceScopeName) },
        }
    };
    InstanceHandle ownerHandle = store.CreateInstanceHandle();
    store.DefaultInstanceOwner = store.Execute(
                                   ownerHandle,
                                   createCommand,
                                   TimeSpan.FromSeconds(30)).InstanceOwner;
    childInstance.AddInitialInstanceValues(new Dictionary<XName, object>() { { WorkflowHostTypeName, WFInstanceScopeName } });
    ```

- <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: Örnek deposundan bir kilit sahibi örnek kimliği kaldırılabilir zaman Kalıcılık altyapısı bu komut örnek depoya gönderir. Olduğu gibi <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, uygulama tarafından kilit sahibi kimliği sağlanmalıdır.

     Aşağıdaki kod parçacığını kullanarak bir kilidi serbest bırakma gösterir <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.

    ```csharp
    static void FreeHandleAndDeleteOwner(InstanceStore store, InstanceHandle handle)
    {
        handle.Free();
        handle = store.CreateInstanceHandle(store.DefaultInstanceOwner);
        try
        {
            // We need this sleep so that we dont prematurely delete the owner, we need time to update the database.
            Thread.Sleep(10000);
            store.Execute(handle, new DeleteWorkflowOwnerCommand(), TimeSpan.FromSeconds(10));
        }
        catch (InstancePersistenceCommandException ex) { Log.Inform(ex.Message); }
        catch (InstanceOwnerException ex) { Log.Inform(ex.Message); }
        catch (OperationCanceledException ex) { Log.Inform(ex.Message); }
        catch (Exception ex) { Log.Inform(ex.Message); }
        finally
        {
            handle.Free();
            store.DefaultInstanceOwner = null;
        }
    }
    ```

     Bir alt örneği çalıştırdığınızda bir Try/Catch bloğu içinde yukarıdaki yöntemi çağrılmalıdır.

    ```csharp
    try
    {
        childInstance.Run();
    }
    catch (Exception)
    {
        throw ;
    }
    finally
    {
        FreeHandleAndDeleteOwner(store, ownerHandle);
    }
    ```

- <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: İş akışı örneği anahtarı kullanılarak yüklenmesi için bir iş akışı örneği olduğunda Kalıcılık altyapısı bu komut örnek depoya gönderir. Örnek anahtarı kimliği kullanarak belirlenebilir <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> komut parametresi.

- <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: Kalıcılık altyapısı, örnek deposuna sonra iş akışları yükleyebilir ve bir iş akışı ana bilgisayar oluşturmak için kalıcı iş akışları için etkinleştirme parametresi almak için bu komutu gönderir. Bu komut, örnek deposu oluşturma yanıt altyapısı tarafından gönderilen <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> etkinleştirilebilir bir örneği bulduğunda konağa. Etkinleştirilebilmesi için iş akışlarını olup olmadığını belirlemek için örnek deposuna sorgulanmak.

- <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: Kalıcılık altyapısı, örnek deposuna çalıştırılabilir iş akışı örnekleri yüklemek için bu komutu gönderir. Bu komut, örnek deposu oluşturma yanıt altyapısı tarafından gönderilen <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> çalıştırılabilir bir örneği bulduğunda konağa. Örnek deposuna çalıştırılabilir iş akışları için yoklama. Aşağıdaki kod parçacığını bir örnek deposuna çalıştıran veya etkinleştirilen iş akışları için yoklama gösterir.

    ```csharp
    public void PollForEvents()
    {
        InstanceOwner[] storeOwners = this.GetInstanceOwners();

        foreach (InstanceOwner owner in storeOwners)
        {
            foreach (InstancePersistenceEvent ppEvent in this.GetEvents(owner))
            {
                if (ppEvent.Equals(HasRunnableWorkflowEvent.Value))
                {
                    bool hasRunnable = GetRunnableEvents(this.StoreId, owner.InstanceOwnerId, isActivatable);
                    if (hasRunnable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
                else if(ppEvent.Equals(HasActivatableWorkflowEvent.Value))
                {
                   bool hasActivatable = GetActivatableEvents(this.StoreId, owner.InstanceOwnerId);
                   if (hasActivatable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
            }
        }
    }
    ```

     Yukarıdaki kod parçacığında, örnek deposuna olay yok sorgular ve her biri olup olmadığını belirlemek için inceler bir <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> olay. Bulunması durumunda <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> örnek deposuna bir komut göndermek için ana sinyal için çağrılır. Aşağıdaki kod parçacığı bir işleyici bu komut için uygulanışı gösterilmektedir.

    ```csharp
    If (command is TryLoadRunnableWorkflowCommand)
    {
        Owner owner;
        CheckOwner(context, command.Name, out owner);
        // Checking instance.Owner is like an InstanceLockQueryResult.
        context.QueriedInstanceStore(new InstanceLockQueryResult(context.InstanceView.InstanceId, context.InstanceView.InstanceOwner.InstanceOwnerId));

        XName ownerService = null;
        InstanceValue value;
        Instance runnableInstance = default(Instance);
        bool foundRunnableInstance = false;

        value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, owner.Data);
        if (value != null && value.Value is XName)
        {
            ownerService = (XName)value.Value;
        }

        foreach (KeyValuePair<Guid, Instance> instance in MemoryStore.instances)
        {
            if (instance.Value.Owner != Guid.Empty || instance.Value.Completed)
            {
                continue;
            }

            if (ownerService != null)
            {
                value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, instance.Value.Metadata);
                if (value == null || ((XName)value.Value) != ownerService)
                {
                    continue;
                }
            }

            value = QueryPropertyBag(WorkflowServiceNamespace.SuspendReason, instance.Value.Metadata);
            if (value != null && value.Value != null && value.Value is string)
            {
                continue;
            }

            value = QueryPropertyBag(WorkflowNamespace.Status, instance.Value.Data);
            if (value != null && value.Value is string && ((string)value.Value) == "Executing")
            {
                runnableInstance = instance.Value;
                foundRunnableInstance = true;
            }

            if (!foundRunnableInstance)
            {
                value = QueryPropertyBag(XNamespace.Get("urn:schemas-microsoft-com:System.Activities/4.0/properties").GetName("TimerExpirationTime"), instance.Value.Data);
                if (value != null && value.Value is DateTime && ((DateTime)value.Value) <= DateTime.UtcNow)
                {
                    runnableInstance = instance.Value;
                    foundRunnableInstance = true;
                }
            }

            if (foundRunnableInstance)
            {
                runnableInstance.LockVersion++;
                runnableInstance.Owner = context.InstanceView.InstanceOwner.InstanceOwnerId;
                MemoryStore.instances[instance.Key] = runnableInstance;
                context.BindInstance(instance.Key);
                context.BindAcquiredLock(runnableInstance.LockVersion);

                Dictionary<Guid, IDictionary<XName, InstanceValue>> associatedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                Dictionary<Guid, IDictionary<XName, InstanceValue>> completedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                foreach (KeyValuePair<Guid, Key> keyEntry in MemoryStore.keys)
                {
                if (keyEntry.Value.Instance == context.InstanceView.InstanceId)
                {
                    if (keyEntry.Value.Completed)
                    {
                        completedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                    else
                    {
                        associatedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                }
            }

            context.LoadedInstance(InstanceState.Initialized, DeserializePropertyBag(runnableInstance.Data), DeserializePropertyBag(runnableInstance.Metadata), associatedKeys, completedKeys);
            break;
        }
    }
    ```

    Yukarıdaki kod parçacığında, çalıştırılabilir örnekleri için örnek deposuna arar. Bir örnek bulunursa, yürütme bağlamına bağlı ve yüklenir.

## <a name="using-a-custom-instance-store"></a>Bir özel örnek deposu kullanma

Bir özel örnek deposu uygulamak için örnek deposuna örneği atamak <xref:System.Activities.WorkflowApplication.InstanceStore%2A>ve uygulama <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> yöntemi. Bkz: [nasıl yapılır: Oluşturma ve uzun çalışan iş akışı çalıştırma](how-to-create-and-run-a-long-running-workflow.md) özellikleri için öğretici.

## <a name="a-sample-instance-store"></a>Bir örnek örnek deposu

Aşağıdaki kod örneği alındığı bir tam örnek deposu uygulaması olan [şirket satın alma işlemi](./samples/corporate-purchase-process.md) örnek. Bu örnek depo, iş akışı verileri XML kullanarak bir dosyaya devam ettirir.

```csharp
using System;
using System.Activities.DurableInstancing;
using System.Collections.Generic;
using System.IO;
using System.Runtime.DurableInstancing;
using System.Runtime.Serialization;
using System.ServiceModel.Persistence;
using System.Xml;
using System.Xml.Linq;

namespace Microsoft.Samples.WF.PurchaseProcess
{

    public class XmlWorkflowInstanceStore : InstanceStore
    {
        Guid ownerInstanceID;

        public XmlWorkflowInstanceStore() : this(Guid.NewGuid())
        {

        }

        public XmlWorkflowInstanceStore(Guid id)
        {
            ownerInstanceID = id;
        }

        //Synchronous version of the Begin/EndTryCommand functions
        protected override bool TryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout)
        {
            return EndTryCommand(BeginTryCommand(context, command, timeout, null, null));
        }

        //The persistence engine will send a variety of commands to the configured InstanceStore,
        //such as CreateWorkflowOwnerCommand, SaveWorkflowCommand, and LoadWorkflowCommand.
        //This method is where we will handle those commands
        protected override IAsyncResult BeginTryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout, AsyncCallback callback, object state)
        {
            IDictionary<XName, InstanceValue> data = null;

            //The CreateWorkflowOwner command instructs the instance store to create a new instance owner bound to the instanace handle
            if (command is CreateWorkflowOwnerCommand)
            {
                context.BindInstanceOwner(ownerInstanceID, Guid.NewGuid());
            }
            //The SaveWorkflow command instructs the instance store to modify the instance bound to the instance handle or an instance key
            else if (command is SaveWorkflowCommand)
            {
                SaveWorkflowCommand saveCommand = (SaveWorkflowCommand)command;
                data = saveCommand.InstanceData;

                Save(data);
            }
            //The LoadWorkflow command instructs the instance store to lock and load the instance bound to the identifier in the instance handle
            else if (command is LoadWorkflowCommand)
            {
                string fileName = IOHelper.GetFileName(this.ownerInstanceID);

                try
                {
                    using (FileStream inputStream = new FileStream(fileName, FileMode.Open))
                    {
                        data = LoadInstanceDataFromFile(inputStream);
                        //load the data into the persistence Context
                        context.LoadedInstance(InstanceState.Initialized, data, null, null, null);
                    }
                }
                catch (Exception exception)
                {
                    throw new PersistenceException(exception.Message);
                }
            }

            return new CompletedAsyncResult<bool>(true, callback, state);
        }

        protected override bool EndTryCommand(IAsyncResult result)
        {
            return CompletedAsyncResult<bool>.End(result);
        }

        //Reads data from xml file and creates a dictionary based off of that.
        IDictionary<XName, InstanceValue> LoadInstanceDataFromFile(Stream inputStream)
        {
            IDictionary<XName, InstanceValue> data = new Dictionary<XName, InstanceValue>();

            NetDataContractSerializer s = new NetDataContractSerializer();

            XmlReader rdr = XmlReader.Create(inputStream);
            XmlDocument doc = new XmlDocument();
            doc.Load(rdr);

            XmlNodeList instances = doc.GetElementsByTagName("InstanceValue");
            foreach (XmlElement instanceElement in instances)
            {
                XmlElement keyElement = (XmlElement)instanceElement.SelectSingleNode("descendant::key");
                XName key = (XName)DeserializeObject(s, keyElement);

                XmlElement valueElement = (XmlElement)instanceElement.SelectSingleNode("descendant::value");
                object value = DeserializeObject(s, valueElement);
                InstanceValue instVal = new InstanceValue(value);

                data.Add(key, instVal);
            }

            return data;
        }

        object DeserializeObject(NetDataContractSerializer serializer, XmlElement element)
        {
            object deserializedObject = null;

            MemoryStream stm = new MemoryStream();
            XmlDictionaryWriter wtr = XmlDictionaryWriter.CreateTextWriter(stm);
            element.WriteContentTo(wtr);
            wtr.Flush();
            stm.Position = 0;

            deserializedObject = serializer.Deserialize(stm);

            return deserializedObject;
        }

        //Saves the persistence data to an xml file.
        void Save(IDictionary<XName, InstanceValue> instanceData)
        {
            string fileName = IOHelper.GetFileName(this.ownerInstanceID);
            XmlDocument doc = new XmlDocument();
            doc.LoadXml("<InstanceValues/>");

            foreach (KeyValuePair<XName,InstanceValue> valPair in instanceData)
            {
                XmlElement newInstance = doc.CreateElement("InstanceValue");

                XmlElement newKey = SerializeObject("key", valPair.Key, doc);
                newInstance.AppendChild(newKey);

                XmlElement newValue = SerializeObject("value", valPair.Value.Value, doc);
                newInstance.AppendChild(newValue);

                doc.DocumentElement.AppendChild(newInstance);
            }
            doc.Save(fileName);
       }

        XmlElement SerializeObject(string elementName, object o, XmlDocument doc)
        {
            NetDataContractSerializer s = new NetDataContractSerializer();
            XmlElement newElement = doc.CreateElement(elementName);
            MemoryStream stm = new MemoryStream();

            s.Serialize(stm, o);
            stm.Position = 0;
            StreamReader rdr = new StreamReader(stm);
            newElement.InnerXml = rdr.ReadToEnd();

            return newElement;
        }
    }
}
```
