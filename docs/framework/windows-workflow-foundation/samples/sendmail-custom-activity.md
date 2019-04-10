---
title: SendMail Özel Etkinliği
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: 89252098402deee991ea01b8e76082a5f4b8c389
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321867"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="a36b0-102">SendMail Özel Etkinliği</span><span class="sxs-lookup"><span data-stu-id="a36b0-102">SendMail Custom Activity</span></span>
<span data-ttu-id="a36b0-103">Bu örnek, türetilen özel etkinlik oluşturma işlemini gösterir <xref:System.Activities.AsyncCodeActivity> bir iş akışı uygulaması içinde kullanmak için SMTP kullanarak posta göndermek için.</span><span class="sxs-lookup"><span data-stu-id="a36b0-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="a36b0-104">Özel Etkinlik özelliklerini kullanan <xref:System.Net.Mail.SmtpClient> zaman uyumsuz olarak e-posta gönderin ve kimlik doğrulaması içeren e-posta göndermek için.</span><span class="sxs-lookup"><span data-stu-id="a36b0-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="a36b0-105">Test modu, belirteç değiştirme, dosya şablonları ve test bırakma yolu gibi bazı son kullanıcı özellikler de sağlar.</span><span class="sxs-lookup"><span data-stu-id="a36b0-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="a36b0-106">Aşağıdaki tabloda bağımsız değişkenleri için ayrıntıları `SendMail` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="a36b0-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="a36b0-107">Ad</span><span class="sxs-lookup"><span data-stu-id="a36b0-107">Name</span></span>|<span data-ttu-id="a36b0-108">Tür</span><span class="sxs-lookup"><span data-stu-id="a36b0-108">Type</span></span>|<span data-ttu-id="a36b0-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a36b0-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a36b0-110">Ana bilgisayar</span><span class="sxs-lookup"><span data-stu-id="a36b0-110">Host</span></span>|<span data-ttu-id="a36b0-111">Dize</span><span class="sxs-lookup"><span data-stu-id="a36b0-111">String</span></span>|<span data-ttu-id="a36b0-112">Hostitel SMTP sunucu adresi.</span><span class="sxs-lookup"><span data-stu-id="a36b0-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="a36b0-113">Bağlantı Noktası</span><span class="sxs-lookup"><span data-stu-id="a36b0-113">Port</span></span>|<span data-ttu-id="a36b0-114">Dize</span><span class="sxs-lookup"><span data-stu-id="a36b0-114">String</span></span>|<span data-ttu-id="a36b0-115">Konak SMTP hizmetinin bağlantı noktası.</span><span class="sxs-lookup"><span data-stu-id="a36b0-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="a36b0-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="a36b0-116">EnableSsl</span></span>|<span data-ttu-id="a36b0-117">bool</span><span class="sxs-lookup"><span data-stu-id="a36b0-117">bool</span></span>|<span data-ttu-id="a36b0-118">Belirtir olup olmadığını <xref:System.Net.Mail.SmtpClient> Güvenli Yuva Katmanı (SSL) bağlantıyı şifrelemek için kullanır.</span><span class="sxs-lookup"><span data-stu-id="a36b0-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="a36b0-119">UserName</span><span class="sxs-lookup"><span data-stu-id="a36b0-119">UserName</span></span>|<span data-ttu-id="a36b0-120">Dize</span><span class="sxs-lookup"><span data-stu-id="a36b0-120">String</span></span>|<span data-ttu-id="a36b0-121">Kullanıcı adı, gönderenin kimliğini doğrulamak için kimlik bilgilerini ayarlayın <xref:System.Net.Mail.SmtpClient.Credentials%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="a36b0-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="a36b0-122">Parola</span><span class="sxs-lookup"><span data-stu-id="a36b0-122">Password</span></span>|<span data-ttu-id="a36b0-123">Dize</span><span class="sxs-lookup"><span data-stu-id="a36b0-123">String</span></span>|<span data-ttu-id="a36b0-124">Gönderenin kimliğini doğrulamak için kimlik bilgilerini ayarlayın parola <xref:System.Net.Mail.SmtpClient.Credentials%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="a36b0-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="a36b0-125">Özne</span><span class="sxs-lookup"><span data-stu-id="a36b0-125">Subject</span></span>|<xref:System.Activities.InArgument%601><span data-ttu-id="a36b0-126">\<dize ></span><span class="sxs-lookup"><span data-stu-id="a36b0-126">\<string></span></span>|<span data-ttu-id="a36b0-127">İletinin konusu.</span><span class="sxs-lookup"><span data-stu-id="a36b0-127">Subject of the message.</span></span>|  
|<span data-ttu-id="a36b0-128">Gövde</span><span class="sxs-lookup"><span data-stu-id="a36b0-128">Body</span></span>|<xref:System.Activities.InArgument%601><span data-ttu-id="a36b0-129">\<dize ></span><span class="sxs-lookup"><span data-stu-id="a36b0-129">\<string></span></span>|<span data-ttu-id="a36b0-130">İletinin gövdesi.</span><span class="sxs-lookup"><span data-stu-id="a36b0-130">Body of the message.</span></span>|  
|<span data-ttu-id="a36b0-131">Ekler</span><span class="sxs-lookup"><span data-stu-id="a36b0-131">Attachments</span></span>|<xref:System.Activities.InArgument%601><span data-ttu-id="a36b0-132">\<dize ></span><span class="sxs-lookup"><span data-stu-id="a36b0-132">\<string></span></span>|<span data-ttu-id="a36b0-133">Bu e-posta iletisine ekli veri depolamak için kullanılan ek koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="a36b0-133">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="a36b0-134">Başlangıç</span><span class="sxs-lookup"><span data-stu-id="a36b0-134">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="a36b0-135">Bu e-posta iletisi için adres.</span><span class="sxs-lookup"><span data-stu-id="a36b0-135">From address for this email message.</span></span>|  
|<span data-ttu-id="a36b0-136">Bitiş</span><span class="sxs-lookup"><span data-stu-id="a36b0-136">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="a36b0-137">Bu e-posta iletisinin alıcıları içeren adres koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="a36b0-137">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="a36b0-138">CC</span><span class="sxs-lookup"><span data-stu-id="a36b0-138">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="a36b0-139">Bilgi (CC) alıcılarını bu eposta iletisi için içeren koleksiyon adresi.</span><span class="sxs-lookup"><span data-stu-id="a36b0-139">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="a36b0-140">GİZLİ</span><span class="sxs-lookup"><span data-stu-id="a36b0-140">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="a36b0-141">Bu e-posta iletisi için gizli kopya (gizli) alıcıları içeren adres koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="a36b0-141">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="a36b0-142">Belirteçler</span><span class="sxs-lookup"><span data-stu-id="a36b0-142">Tokens</span></span>|<xref:System.Activities.InArgument%601><span data-ttu-id="a36b0-143">< IDictionary\<dize, dize >></span><span class="sxs-lookup"><span data-stu-id="a36b0-143"><IDictionary\<string, string>></span></span>|<span data-ttu-id="a36b0-144">Belirteçleri gövdesinde değiştirin.</span><span class="sxs-lookup"><span data-stu-id="a36b0-144">Tokens to replace in the body.</span></span> <span data-ttu-id="a36b0-145">Bu özellik, kullanıcıların daha sonra bu özelliği kullanarak verilen belirteçleri ile değiştirilebilir daha gövdesinde bazı değerleri belirtmesine izin verir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-145">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="a36b0-146">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="a36b0-146">BodyTemplateFilePath</span></span>|<span data-ttu-id="a36b0-147">Dize</span><span class="sxs-lookup"><span data-stu-id="a36b0-147">String</span></span>|<span data-ttu-id="a36b0-148">Gövdesi için bir şablon yolu.</span><span class="sxs-lookup"><span data-stu-id="a36b0-148">Path of a template for the body.</span></span> <span data-ttu-id="a36b0-149">`SendMail` Etkinliği, bu dosyanın içeriğini kendi gövdesi özelliğine kopyalar.</span><span class="sxs-lookup"><span data-stu-id="a36b0-149">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="a36b0-150">Şablon belirteçleri özelliğinin içeriğine göre değiştirilir belirteçlerini içerebilir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-150">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="a36b0-151">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="a36b0-151">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="a36b0-152">Bu özelliği ayarlandığında, tüm e-postaları içinde belirtilen adrese gönderilir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-152">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="a36b0-153">Bu özellik, iş akışları test ederken kullanılması amaçlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="a36b0-153">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="a36b0-154">Örneğin, emin olmak istediğinizde tüm e-postaları gerçek alıcıya gönderim olmadan gönderilir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-154">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="a36b0-155">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="a36b0-155">TestDropPath</span></span>|<span data-ttu-id="a36b0-156">Dize</span><span class="sxs-lookup"><span data-stu-id="a36b0-156">String</span></span>|<span data-ttu-id="a36b0-157">Bu özelliği ayarlandığında, tüm e-postaları da belirtilen dosyasında kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-157">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="a36b0-158">Bu özellik, test veya giden e-posta içeriğini ve biçimini uygun olduğunu emin olmak için iş akışlarında hata ayıklama yaparken kullanılmak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="a36b0-158">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="a36b0-159">Çözüm içeriği</span><span class="sxs-lookup"><span data-stu-id="a36b0-159">Solution Contents</span></span>  
 <span data-ttu-id="a36b0-160">Çözüm iki proje içerir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-160">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="a36b0-161">Project</span><span class="sxs-lookup"><span data-stu-id="a36b0-161">Project</span></span>|<span data-ttu-id="a36b0-162">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a36b0-162">Description</span></span>|<span data-ttu-id="a36b0-163">Önemli dosya</span><span class="sxs-lookup"><span data-stu-id="a36b0-163">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="a36b0-164">SendMail</span><span class="sxs-lookup"><span data-stu-id="a36b0-164">SendMail</span></span>|<span data-ttu-id="a36b0-165">SendMail etkinliği</span><span class="sxs-lookup"><span data-stu-id="a36b0-165">The SendMail activity</span></span>|<span data-ttu-id="a36b0-166">1.  SendMail.cs: ana etkinlik uygulama</span><span class="sxs-lookup"><span data-stu-id="a36b0-166">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="a36b0-167">2.  SendMailDesigner.xaml ve SendMailDesigner.xaml.cs: SendMail etkinliğinin Tasarımcısı</span><span class="sxs-lookup"><span data-stu-id="a36b0-167">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="a36b0-168">3.  MailTemplateBody.htm: gönderilecek e-posta şablonu.</span><span class="sxs-lookup"><span data-stu-id="a36b0-168">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="a36b0-169">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="a36b0-169">SendMailTestClient</span></span>|<span data-ttu-id="a36b0-170">SendMail etkinlik test etmek için istemci.</span><span class="sxs-lookup"><span data-stu-id="a36b0-170">Client to test the SendMail activity.</span></span>  <span data-ttu-id="a36b0-171">Bu proje SendMail etkinlik çağrılırken, iki yolunu gösterir: bildirimli ve programlı olarak.</span><span class="sxs-lookup"><span data-stu-id="a36b0-171">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="a36b0-172">1.  Sequence1.XAML: SendMail etkinlik çağıran iş akışı.</span><span class="sxs-lookup"><span data-stu-id="a36b0-172">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="a36b0-173">2.  Program.cs: Sıra1 çağırır ve aynı zamanda program aracılığıyla SendMail kullanan bir iş akışı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="a36b0-173">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="a36b0-174">SendMail etkinlik başka bir yapılandırma</span><span class="sxs-lookup"><span data-stu-id="a36b0-174">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="a36b0-175">Örnekte gösterilmese, kullanıcılar ayrıca yapılandırma SendMail etkinliğin gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-175">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="a36b0-176">Sonraki üç bölümde nasıl yapıldığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-176">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="a36b0-177">Gövdesinde belirtilen belirteçleri kullanarak bir e-posta gönderme</span><span class="sxs-lookup"><span data-stu-id="a36b0-177">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="a36b0-178">Bu kod parçacığı, nasıl gövdesinde e-posta belirteçleri ile gönderebileceğiniz gösterilir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-178">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="a36b0-179">Gövde özelliğinde belirteçlerin nasıl sağlanan dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="a36b0-179">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="a36b0-180">Bu belirteçler için değerler belirteçleri özelliğine sağlanır.</span><span class="sxs-lookup"><span data-stu-id="a36b0-180">Values for those tokens are provided to the tokens property.</span></span>  
  
```html  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="a36b0-181">Şablon kullanarak bir e-posta gönderme</span><span class="sxs-lookup"><span data-stu-id="a36b0-181">Sending an email using a template</span></span>  
 <span data-ttu-id="a36b0-182">Bu kod parçacığı gövdesinde bir şablon belirteçleri kullanarak bir e-posta gönderme işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-182">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="a36b0-183">Ayarlarken dikkat `BodyTemplateFilePath` özelliği biz (şablon dosyasının içeriğini gövdesine kopyalanır) gövde özelliği için değer sağlamanız gerekmez.</span><span class="sxs-lookup"><span data-stu-id="a36b0-183">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
```  
new SendMail  
{    
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",   
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="a36b0-184">Modu test e-postalar gönderme</span><span class="sxs-lookup"><span data-stu-id="a36b0-184">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="a36b0-185">Bu kod parçacığı, iki test özelliklerini ayarlama işlemi gösterilmektedir: ayarlayarak `TestMailTo` tüm iletileri gönderilir `john.doe@contoso.con` (bakmadan değerlerinin Kime, bilgi, gizli).</span><span class="sxs-lookup"><span data-stu-id="a36b0-185">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="a36b0-186">TestDropPath ayarlayarak tüm giden e-postaları da sağlanan yolda kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-186">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="a36b0-187">Bu özellikler bağımsız olarak ayarlanabilir (bunlar birbiriyle ilgili olmayan).</span><span class="sxs-lookup"><span data-stu-id="a36b0-187">These properties can be set independently (they are not related).</span></span>  
  
```  
new SendMail  
{    
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a><span data-ttu-id="a36b0-188">Kurulum Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="a36b0-188">Set-Up Instructions</span></span>  
 <span data-ttu-id="a36b0-189">Bu örnek için bir SMTP sunucusuna erişim gereklidir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-189">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="a36b0-190">Bir SMTP sunucusu kurma hakkında daha fazla bilgi için aşağıdaki bağlantılara bakın.</span><span class="sxs-lookup"><span data-stu-id="a36b0-190">For more information about setting up a SMTP server, see the following links.</span></span>  
  
-   [<span data-ttu-id="a36b0-191">Microsoft Technet</span><span class="sxs-lookup"><span data-stu-id="a36b0-191">Microsoft Technet</span></span>](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
-   [<span data-ttu-id="a36b0-192">SMTP Hizmeti (IIS 6.0) yapılandırma</span><span class="sxs-lookup"><span data-stu-id="a36b0-192">Configuring the SMTP Service (IIS 6.0)</span></span>](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
-   [<span data-ttu-id="a36b0-193">IIS 7.0: SMTP e-posta Yapılandır</span><span class="sxs-lookup"><span data-stu-id="a36b0-193">IIS 7.0: Configure SMTP E-Mail</span></span>](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
-   [<span data-ttu-id="a36b0-194">SMTP hizmeti nasıl yüklenir?</span><span class="sxs-lookup"><span data-stu-id="a36b0-194">How to Install the SMTP Service</span></span>](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 <span data-ttu-id="a36b0-195">Üçüncü taraflarca sağlanan SMTP öykünücüsünü indirme için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-195">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="a36b0-196">Bu örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="a36b0-196">To run this sample</span></span>  
  
1. <span data-ttu-id="a36b0-197">Visual Studio 2010 kullanarak SendMail.sln çözüm dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="a36b0-197">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="a36b0-198">Geçerli bir SMTP sunucusuna erişimi olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="a36b0-198">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="a36b0-199">Kurulum yönergelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="a36b0-199">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="a36b0-200">Programı, sunucu adresi ve Kimden ve Kime e-posta adreslerini yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="a36b0-200">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="a36b0-201">Doğru Bu örneği çalıştırmak için ilk ve son e-posta adresi ve SMTP sunucusunun adresini değerini program.CS'de Webhostbuilder'a ve Sequence.xaml yapılandırmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="a36b0-201">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="a36b0-202">Program iki farklı şekilde posta gönderen adresi konumlarının her ikisinde de değiştirmek gerekir</span><span class="sxs-lookup"><span data-stu-id="a36b0-202">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="a36b0-203">Çözümü derlemek için CTRL + SHIFT + B tuşlarına basın.</span><span class="sxs-lookup"><span data-stu-id="a36b0-203">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="a36b0-204">Çözümü çalıştırmak için CTRL + F5 tuşlarına basın.</span><span class="sxs-lookup"><span data-stu-id="a36b0-204">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a36b0-205">Örnekler, makinenizde zaten yüklü.</span><span class="sxs-lookup"><span data-stu-id="a36b0-205">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a36b0-206">Devam etmeden önce şu (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="a36b0-206">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a36b0-207">Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="a36b0-207">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a36b0-208">Bu örnek, şu dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="a36b0-208">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`