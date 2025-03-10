---
title: Managed Extensibility Framework (MEF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Managed Extensibility Framework, overview
- MEF, overview
ms.assetid: 6c61b4ec-c6df-4651-80f1-4854f8b14dde
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fc66837dc31dc1697bcb4ad6dddfb57bfb99bd4
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68434093"
---
# <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)

Bu konu, .NET Framework 4 ' te tanıtılan Managed Extensibility Framework genel bir bakış sağlar.

<a name="what_is_mef"></a>
## <a name="what-is-mef"></a>MEF nedir?

Managed Extensibility Framework veya MEF, hafif, Genişletilebilir uygulamalar oluşturmaya yönelik bir kitaplıktır. Uygulama geliştiricilerinin yapılandırma gerekmeden uzantıları bulmasına ve kullanmasına olanak tanır. Ayrıca, uzantı geliştiricilerinin kodu kolayca kapsüllemeyi ve kırarak sabit bağımlılıklara engel olmasını sağlar. MEF, uzantıların uygulamalar içinde yeniden kullanılmasına izin verir, ancak uygulamalar arasında da kullanılabilir.

<a name="the_problem_of_extensibility"></a>
## <a name="the-problem-of-extensibility"></a>Genişletilebilirlik sorunu
 Genişletilebilirlik için destek sağlaması gereken büyük bir uygulamanın mimarı olduğunu düşünün. Uygulamanızın büyük olasılıkla çok sayıda küçük bileşen içermesi ve bunları oluşturup çalıştırmasından sorumlu olması gerekir.

 Soruna en basit yaklaşım, bileşenleri uygulamanıza kaynak kodu olarak dahil etmek ve doğrudan kodunuzda çağırmak olur. Bu bir dizi belirgin sakıncalar içerir. En önemlisi, kaynak kodu değiştirmeden yeni bileşenler, örneğin bir Web uygulaması gibi kabul edilebilir olabilecek bir kısıtlama, ancak bir istemci uygulamasında kullanılamaz. Benzer şekilde sorunlu olarak, bileşenler için kaynak koda erişiminiz olmayabilir, çünkü bunlar üçüncü taraflar tarafından geliştirilip aynı nedenden dolayı sizinkilerle erişime izin vermezsiniz.

 Daha karmaşık bir yaklaşım, uygulama ve bileşenleri arasında ayrılmasına izin vermek için bir uzantı noktası veya arabirim sağlamaktır. Bu model altında, bir bileşenin uygulayabileceği bir arabirim ve uygulamanızla etkileşime geçmesini sağlamak için bir API sağlayabilirsiniz. Bu, kaynak kodu erişimi gerektirme sorununu çözer, ancak yine de kendi zorluklarıyla karşılaşmıştır.

 Uygulamanın, bileşenleri bulmak için herhangi bir kapasitesi olmadığından, yine de hangi bileşenlerin kullanılabilir olduğunu ve yüklenmesi gerektiğini açıkça söylemelidir. Bu, genellikle bir yapılandırma dosyasına kullanılabilir bileşenleri açıkça kaydederek gerçekleştirilir. Bu, bileşenlerin doğru olduğu anlamına gelir. Bu, özellikle son kullanıcı ise, güncellemeyi yapması beklenen geliştiriciden değil, bir bakım sorunu haline gelir.

 Ayrıca, bileşenler, uygulamanın kendisinin rigidly tanımlı kanalları dışında birbiriyle iletişim kurabiliyor. Uygulama mimarı belirli bir iletişim gereksinimini tahmin etmez, genellikle olanaksızdır.

 Son olarak, bileşen geliştiricileri, uygulamadıkları arabirimi içeren derlemenin bir sabit bağımlılığını kabul etmelidir. Bu, bir bileşenin birden fazla uygulamada kullanılmasını zorlaştırıyor ve bileşenler için bir test çerçevesi oluştururken da sorun oluşturabilir.

<a name="what_mef_provides"></a>
## <a name="what-mef-provides"></a>MEF 'in sağladığı
 MEF, kullanılabilir bileşenlerin bu açık kaydı yerine, bunları *kompozisyon*aracılığıyla örtülü olarak keşfetmenin bir yolunu sağlar. *Bölüm*adı VERILEN bir MEF bileşeni, bildirimli olarak hem bağımlılıklarını ( *içeri aktarmalar*olarak bilinir) hem de kullanılabilir özellikleri ( *dışarı aktarma*olarak bilinir) belirler. Bir bölüm oluşturulduğunda, MEF bileşim altyapısı, diğer bölümlerden kullanılabilir olan içeri aktarmalarını karşılar.

 Bu yaklaşım, önceki bölümde ele alınan sorunları çözer. MEF parçaları, yeteneklerini bildirimli olarak belirttiğinden, çalışma zamanında keşfedilir ve bu da bir uygulamanın sabit kodlanmış başvurular veya fragel yapılandırma dosyaları olmadan parçalar tarafından kullanılabilmesini sağlayabilir. MEF, uygulamaların onları örneklemeden veya derlemeleri yüklemeden, meta verilerine göre parçalar bulmasına ve incelemesine olanak sağlar. Sonuç olarak, uzantıların ne zaman ve nasıl yükleneceğini dikkatle belirtmeniz gerekmez.

 Bir bölüm, belirtilen dışarı aktarımlarının yanı sıra içeri aktarmaları belirtebilir ve diğer parçalar tarafından doldurulur. Bu, parçalar arasında iletişimi yalnızca mümkün değildir ancak kolay bir kod düzenleme olanağı sağlar. Örneğin, birçok bileşen için ortak hizmetler ayrı bir bölüme ayrılabilir ve kolayca değiştirilebilir veya değiştirilebilir.

 MEF modeli belirli bir uygulama derlemesinde sabit bağımlılık gerektirmediğinden, uzantıların uygulamadan uygulamaya yeniden kullanılmasına izin verir. Bu Ayrıca, uzantı bileşenlerini test etmek için uygulamadan bağımsız bir test bandı geliştirmeyi kolaylaştırır.

 MEF kullanılarak yazılan genişletilebilir bir uygulama, uzantı bileşenleriyle doldurulabilecek bir içeri aktarma bildirir ve uygulama hizmetlerini uzantılara sunmak için dışarı aktarmaları de bildirebilir. Her uzantı bileşeni bir dışarı aktarma bildirir ve içeri aktarmaları de bildirebilir. Bu şekilde, uzantı bileşenleri otomatik olarak genişletilebilir.

<a name="where_is_mef_available"></a>
## <a name="where-is-mef-available"></a>MEF nerede kullanılabilir?
 MEF .NET Framework 4 ' ün ayrılmaz bir parçasıdır ve .NET Framework kullanıldığı her yerde kullanılabilir. Windows Forms, WPF veya başka herhangi bir teknolojiyi kullanıp kullandıklarından veya ASP.NET kullanan sunucu uygulamalarında MEF 'i istemci uygulamalarınızda kullanabilirsiniz.

<a name="mef_and_maf"></a>
## <a name="mef-and-maf"></a>MEF ve MAF
 .NET Framework önceki sürümleri, uygulamaların uzantıları yalıtmasına ve yönetmesine olanak tanımak için tasarlanan yönetilen eklenti çerçevesini (MAF) kullanıma sunmuştur. MAF 'nin odağı MEF 'ten biraz daha yüksek düzeydeyse, MEF 'in odağı keşfedilebilirlik, genişletilebilirlik ve taşınabilirlik üzerinde olduğunda, uzantı yalıtımı ve derleme yükleme ve kaldırma üzerinde yoğunlaşmaktadır. İki çerçeve sorunsuz bir şekilde çalışır ve tek bir uygulama her ikisinin de avantajlarından yararlanabilir.

<a name="simplecalculator_an_example_application"></a>

## <a name="simplecalculator-an-example-application"></a>'In Örnek bir uygulama

MEF 'in neler yapabileceğini görmenin en basit yolu basit bir MEF uygulaması derlemenize olanak sağlar. Bu örnekte, SimpleCalculator adlı çok basit bir Hesaplayıcı oluşturacaksınız. SimpleCalculator 'ın amacı, "5 + 3" veya "6-2" biçimindeki temel aritmetik komutları kabul eden bir konsol uygulaması oluşturmaktır ve doğru yanıtları döndürür. MEF kullanarak, uygulama kodunu değiştirmeden yeni işleçler ekleyebileceksiniz.

Bu örneğe ilişkin tüm kodu indirmek için bkz. [SimpleCalculator örneği](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).

> [!NOTE]
> SimpleCalculator 'ın amacı, kullanımı için gerçekçi bir senaryo sağlamak yerine MEF 'in kavramlarını ve sözdizimini göstermektir. MEF 'in gücünden en fazla faydalanabilir uygulamalar SimpleCalculator 'dan daha karmaşıktır. Daha kapsamlı örnekler için GitHub 'daki [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) bakın.

- Başlamak için, Visual Studio 'da yeni bir konsol uygulaması projesi oluşturun ve bunu `SimpleCalculator`adlandırın.

- MEF 'in bulunduğu System. ComponentModel. Composition derlemesine bir başvuru ekleyin.

- System. ComponentModel. Composition ve System. `Imports` ComponentModel `using` . Composition. Hosting için Module1. vb veya program.cs ve Add ya da deyimlerini açın. Bu iki ad alanı, genişletilebilir bir uygulama geliştirmek için ihtiyacınız olan MEF türlerini içerir.

- Visual Basic kullanıyorsanız, `Public` anahtar sözcüğünü `Module1` modülünü bildiren satıra ekleyin.

<a name="composition_container_and_catalogs"></a>

## <a name="composition-container-and-catalogs"></a>Birleşim kapsayıcısı ve kataloglar

MEF bileşim modelinin çekirdeği, kullanılabilir tüm parçaları içeren ve kompozisyonu gerçekleştiren *bileşim kapsayıcısıdır*. Bileşim dışarı aktarmalar için içeri aktarmaların eşleştirmesinin eşleşmesine sahiptir. Birleşim kapsayıcısının en yaygın türü ' dir <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>ve bunu SimpleCalculator için kullanacaksınız.

Visual Basic kullanıyorsanız, Module1. vb ' de adlı `Program`bir ortak sınıf ekleyin.

Aşağıdaki satırı `Program` , Module1. vb veya program.cs içindeki sınıfa ekleyin:

```vb
Dim _container As CompositionContainer
```

```csharp
private CompositionContainer _container;
```

Bu bölümde bulunan bölümleri saptamak için, bileşim kapsayıcıları bir *kataloğu*kullanır. Katalog, bazı kaynaklardan bulunan kullanılabilir bölümleri oluşturan bir nesnedir. MEF, sağlanan bir türden, bir derlemeden veya bir dizinden parçalar bulmaya yönelik kataloglar sağlar. Uygulama geliştiricileri, Web hizmeti gibi diğer kaynaklardan parçaları saptamak için kolayca yeni kataloglar oluşturabilir.

`Program` Sınıfına aşağıdaki oluşturucuyu ekleyin:

```vb
Public Sub New()
    ' An aggregate catalog that combines multiple catalogs.
     Dim catalog = New AggregateCatalog()

    ' Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(New AssemblyCatalog(GetType(Program).Assembly))

    ' Create the CompositionContainer with the parts in the catalog.
    _container = New CompositionContainer(catalog)

    ' Fill the imports of this object.
    Try
        _container.ComposeParts(Me)
    Catch ex As CompositionException
        Console.WriteLine(ex.ToString)
    End Try
End Sub
```

```csharp
private Program()
{
    // An aggregate catalog that combines multiple catalogs.
    var catalog = new AggregateCatalog();
    // Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(new AssemblyCatalog(typeof(Program).Assembly));

    // Create the CompositionContainer with the parts in the catalog.
    _container = new CompositionContainer(catalog);

    // Fill the imports of this object.
    try
    {
        this._container.ComposeParts(this);
    }
    catch (CompositionException compositionException)
    {
        Console.WriteLine(compositionException.ToString());
   }
}
```

Çağrısı <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> , bileşim kapsayıcısına belirli bir parçalar kümesi oluşturmasını söyler, bu durumda geçerli `Program`örneği. Ancak, doldurulacak bir içeri aktarma `Program` işlemi olmadığından, bu noktada hiçbir şey gerçekleşmeyecektir.

<a name="imports_and_exports_with_attributes"></a>
## <a name="imports-and-exports-with-attributes"></a>Özniteliklerle içeri ve dışarı aktarmalar
 İlk olarak, `Program` bir Hesaplayıcı içeri aktarmalısınız. Bu işlem `Program`, hesap makinesinin mantığındaki konsol girişi ve çıktısı gibi kullanıcı arabirimi sorunlarının ayrılmasını sağlar.

 `Program` Sınıfına aşağıdaki kodu ekleyin:

```vb
<Import(GetType(ICalculator))>
Public Property calculator As ICalculator
```

```csharp
[Import(typeof(ICalculator))]
public ICalculator calculator;
```

 `calculator` Nesnenin bildiriminin olağandışı olmadığına, ancak <xref:System.ComponentModel.Composition.ImportAttribute> özniteliğiyle birlikte tasarlandığına dikkat edin. Bu öznitelik bir içeri aktarma işlemi olduğunu bildirir; diğer bir deyişle, nesne oluşturulduğunda bileşim motoru tarafından doldurulur.

 Her içeri aktarma işlemi bir *sözleşmeye*sahiptir ve bu, ile eşleştirileceği dışarı aktarmaları belirler. Sözleşme açıkça belirtilen bir dize olabilir veya bu durumda arabirim `ICalculator`, belırlı bir türden MEF tarafından otomatik olarak oluşturulabilir. Eşleşen bir sözleşmeyle belirtilen tüm dışarı aktarma işlemi bu içeri aktarmayı karşılar. `calculator` Nesnenin türü aslında `ICalculator`olduğunda, bu gerekli değildir. Sözleşme, içeri aktarma nesnesinin türünden bağımsızdır. (Bu durumda, `typeof(ICalculator)`' yi bırakabilirsiniz. MEF, açıkça belirtmediğiniz takdirde, sözleşmenin içeri aktarma türüne göre otomatik olarak kabul edilir.)

 Bu çok basit arabirimi modüle veya `SimpleCalculator` ad alanına ekleyin:

```vb
Public Interface ICalculator
    Function Calculate(ByVal input As String) As String
End Interface
```

```csharp
public interface ICalculator
{
    String Calculate(String input);
}
```

 Tanımladığınıza `ICalculator`göre, onu uygulayan bir sınıfa ihtiyacınız vardır. Aşağıdaki sınıfı modüle veya `SimpleCalculator` ad alanına ekleyin:

```vb
<Export(GetType(ICalculator))>
Public Class MySimpleCalculator
   Implements ICalculator

End Class
```

```csharp
[Export(typeof(ICalculator))]
class MySimpleCalculator : ICalculator
{

}
```

 İçeri aktarma `Program`ile eşleşecek dışarı aktarma aşağıda verilmiştir. Dışarı aktarmanın içeri aktarma ile eşleşmesi için, dışarı aktarmanın aynı sözleşmeye sahip olması gerekir. ' A dayalı `typeof(MySimpleCalculator)` bir sözleşme altında dışa aktarma bir uyumsuzluk üretecektir ve içeri aktarma doldurulmaz; sözleşmenin tam olarak eşleşmesi gerekir.

 Bileşim kapsayıcısı Bu derlemede bulunan tüm bölümlerle doldurulduğundan, `MySimpleCalculator` bölüm kullanılabilir olacaktır. İçin `Program` Oluşturucu `Program` nesne üzerinde kompozisyon gerçekleştirdiğinde, içeri aktarma işlemi bu amaçla oluşturulacak bir `MySimpleCalculator` nesne ile doldurulur.

 Kullanıcı arabirimi katmanının (`Program`) başka herhangi bir şeyi bilmeleri gerekmez. Bu nedenle, `Main` yönteminde Kullanıcı arabirimi mantığının geri kalanını doldurabilirsiniz.

 `Main` Yöntemine aşağıdaki kodu ekleyin:

```vb
Sub Main()
    ' Composition is performed in the constructor.
    Dim p As New Program()
    Dim s As String
    Console.WriteLine("Enter Command:")
    While (True)
        s = Console.ReadLine()
        Console.WriteLine(p.calculator.Calculate(s))
    End While
End Sub
```

```csharp
static void Main(string[] args)
{
    // Composition is performed in the constructor.
    var p = new Program();
    String s;
    Console.WriteLine("Enter Command:");
    while (true)
    {
        s = Console.ReadLine();
        Console.WriteLine(p.calculator.Calculate(s));
    }
}
```

 Bu kod, bir giriş satırını okur ve sonuç `Calculate` `ICalculator` üzerinde öğesine çağrı yaparak konsola geri yazar. Bu, ihtiyacınız olan tüm kodlarda `Program`bulunur. Çalışmanın tüm geri kalanı parçalar halinde olur.

<a name="further_imports_and_importmany"></a>
## <a name="further-imports-and-importmany"></a>Daha fazla Içeri aktarmalar ve ImportMany
 SimpleCalculator 'ın Genişletilebilir olması için, işlem listesini içeri aktarması gerekir. Sıradan <xref:System.ComponentModel.Composition.ImportAttribute> bir öznitelik bir ve yalnızca bir <xref:System.ComponentModel.Composition.ExportAttribute>ile doldurulur. Birden fazla kullanılabilir varsa, bileşim altyapısı bir hata üretir. Herhangi bir sayıda dışarı aktarma tarafından doldurulabilecek bir içeri aktarma oluşturmak için, <xref:System.ComponentModel.Composition.ImportManyAttribute> özniteliğini kullanabilirsiniz.

 `MySimpleCalculator` Sınıfına aşağıdaki Operations özelliğini ekleyin:

```vb
<ImportMany()>
Public Property operations As IEnumerable(Of Lazy(Of IOperation, IOperationData))
```

```csharp
[ImportMany]
IEnumerable<Lazy<IOperation, IOperationData>> operations;
```

 <xref:System.Lazy%602>, dışarı aktarmalar için dolaylı başvuruları tutmak üzere MEF tarafından sağlanmış bir türdür. Burada dışa aktarılmış nesnenin kendisinin yanı sıra dışarı *aktarma meta verilerini*veya dışarı aktarılmış nesneyi açıklayan bilgileri de alırsınız. Her <xref:System.Lazy%602> biri, `IOperation` gerçek bir işlemi temsil eden bir nesne ve meta `IOperationData` verilerini temsil eden bir nesnesi içerir.

 Aşağıdaki basit arabirimleri modüle veya `SimpleCalculator` ad alanına ekleyin:

```vb
Public Interface IOperation
    Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer
End Interface

Public Interface IOperationData
    ReadOnly Property Symbol As Char
End Interface
```

```csharp
public interface IOperation
{
     int Operate(int left, int right);
}

public interface IOperationData
{
    Char Symbol { get; }
}
```

 Bu durumda, her bir işlemin meta verileri +,-, * gibi bir işlemi temsil eden simgedir. Ek işlemi kullanılabilir hale getirmek için modüle veya `SimpleCalculator` ad alanına aşağıdaki sınıfı ekleyin:

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "+"c)>
Public Class Add
    Implements IOperation

    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate
        Return left + right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '+')]
class Add: IOperation
{
    public int Operate(int left, int right)
    {
        return left + right;
    }
}
```

 <xref:System.ComponentModel.Composition.ExportAttribute> Özniteliği daha önce olduğu gibi çalışır. <xref:System.ComponentModel.Composition.ExportMetadataAttribute> Özniteliği, meta verileri bir ad-değer çifti biçiminde bu dışarı aktarmaya iliştirir. Sınıf uyguladığı `IOperation`sırada, uygulayan `IOperationData` bir sınıf açıkça tanımlanmamıştır. `Add` Bunun yerine, bir sınıf, belirtilen meta verilerin adlarına göre özellikler ile MEF tarafından örtülü olarak oluşturulur. (Bu, MEF 'teki meta verilere erişmenin çeşitli yöntemlerinden biridir.)

 MEF 'te birleşim *özyinelemeli*. Açık olan `ICalculator` nesneyi, türü `MySimpleCalculator`olması için bir tanesi içeri aktardınız. `Program` `MySimpleCalculator`, sırasıyla bir `IOperation` nesne koleksiyonu içeri aktarır ve içeri aktarma işlemi oluşturulduğunda, içeri aktarmaların `Program`aynı `MySimpleCalculator` anda doldurulur. `Add` Sınıf daha fazla içeri aktarma bildirmişse, bunun da doldurulması gerekir. Doldurulmamış herhangi bir içeri aktarma işlemi bir bileşim hatası ile sonuçlanır. (Ancak, içeri aktarmaları isteğe bağlı olarak bildirmek veya varsayılan değerleri atamak mümkündür.)

<a name="calculator_logic"></a>
## <a name="calculator-logic"></a>Hesaplayıcı mantığı
 Bu parçalar yerinde olduğunda, her şey Hesaplayıcı mantığının kendisidir. Yöntemini uygulamak için aşağıdaki kodu `MySimpleCalculator` sınıfına ekleyin: `Calculate`

```vb
Public Function Calculate(ByVal input As String) As String Implements ICalculator.Calculate
    Dim left, right As Integer
    Dim operation As Char
    ' Finds the operator.
    Dim fn = FindFirstNonDigit(input)
    If fn < 0 Then
        Return "Could not parse command."
    End If
    operation = input(fn)
    Try
        ' Separate out the operands.
        left = Integer.Parse(input.Substring(0, fn))
        right = Integer.Parse(input.Substring(fn + 1))
    Catch ex As Exception
        Return "Could not parse command."
    End Try
    For Each i As Lazy(Of IOperation, IOperationData) In operations
        If i.Metadata.symbol = operation Then
            Return i.Value.Operate(left, right).ToString()
        End If
    Next
    Return "Operation not found!"
End Function
```

```csharp
public String Calculate(String input)
{
    int left;
    int right;
    char operation;
    // Finds the operator.
    int fn = FindFirstNonDigit(input); 
    if (fn < 0) return "Could not parse command.";

    try
    {
        // Separate out the operands.
        left = int.Parse(input.Substring(0, fn));
        right = int.Parse(input.Substring(fn + 1));
    }
    catch
    {
        return "Could not parse command.";
    }

    operation = input[fn];

    foreach (Lazy<IOperation, IOperationData> i in operations)
    {
        if (i.Metadata.Symbol.Equals(operation)) return i.Value.Operate(left, right).ToString();
    }
    return "Operation Not Found!";
}
```

 İlk adımlar, giriş dizesini sol ve sağ işlenenler ve bir işleç karakteri olarak ayrıştırır. Döngüde, `operations` koleksiyonun her üyesi incelenir. `foreach` Bu nesneler türündedir <xref:System.Lazy%602>ve meta veri değerlerine ve aktarılmış nesnesine sırasıyla <xref:System.Lazy%602.Metadata%2A> özelliği ve <xref:System.Lazy%601.Value%2A> özelliği ile erişilebilir. Bu durumda `Symbol` , `IOperationData` nesnesinin özelliği bir eşleşme olarak bulunursa `Operate` , hesaplayıcı `IOperation` nesnenin yöntemini çağırır ve sonucu döndürür.

 Hesaplayıcıyı tamamlayabilmeniz için bir dizedeki ilk basamak olmayan karakterin konumunu döndüren bir yardımcı yöntemi de gereklidir. `MySimpleCalculator` Sınıfına aşağıdaki yardımcı yöntemi ekleyin:

```vb
Private Function FindFirstNonDigit(ByVal s As String) As Integer
    For i = 0 To s.Length - 1
        If (Not (Char.IsDigit(s(i)))) Then Return i
    Next
    Return -1
End Function
```

```csharp
private int FindFirstNonDigit(string s)
{
    for (int i = 0; i < s.Length; i++)
    {
        if (!(Char.IsDigit(s[i]))) return i;
    }
    return -1;
}
```

 Artık projeyi derleyip çalıştırabilmelisiniz. Visual Basic, `Public` anahtar sözcüğünü öğesine `Module1`eklediğinizden emin olun. Konsol penceresinde, "5 + 3" gibi bir ek işlem yazın ve Hesaplayıcı sonuçları döndürür. "Işlem bulunamadı!" ile ilgili başka bir operatör oluşur İleti.

<a name="extending_simplecalculator_using_a_new_class"></a>
## <a name="extending-simplecalculator-using-a-new-class"></a>Yeni bir sınıf kullanarak SimpleCalculator 'ı genişletme
 Hesap Makinası artık işe yarar, yeni bir işlem eklemek kolaydır. Aşağıdaki sınıfı modüle veya `SimpleCalculator` ad alanına ekleyin:

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "-"c)>
Public Class Subtract
    Implements IOperation

    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate
        Return left - right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '-')]
class Subtract : IOperation
{
    public int Operate(int left, int right)
    {
        return left - right;
    }
}
```

 Projeyi derleyin ve çalıştırın. "5-3" gibi bir çıkarma işlemi yazın. Hesaplayıcı artık çıkarma ve ekleme de desteklemektedir.

<a name="extending_simplecalculator_using_a_new_assembly"></a>
## <a name="extending-simplecalculator-using-a-new-assembly"></a>Yeni bir derleme kullanarak SimpleCalculator 'ı genişletme
 Kaynak koda sınıflar eklemek yeterince basittir, ancak MEF, bir uygulamanın parçalar için kendi kaynağını göz atabilme olanağı sağlar. Bunu göstermek için, SimpleCalculator ' ı, bir dizini ve kendi derlemesini, parçaları için bir ekleyerek bir <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>Dizin arayacak şekilde değiştirmeniz gerekir.

 SimpleCalculator projesine adlı `Extensions` yeni bir dizin ekleyin. Çözüm düzeyinde değil, proje düzeyine eklediğinizden emin olun. Ardından adlı `ExtendedOperations`çözüme yeni bir sınıf kitaplığı projesi ekleyin. Yeni proje ayrı bir derlemede derlenir.

 ExtendedOperations projesi için proje özellikleri tasarımcısını açın ve **Derle** veya **Derle** sekmesine tıklayın. **Derleme çıkış yolunu** veya **Çıkış yolunu** , SimpleCalculator proje dizinindeki uzantılar dizinine işaret etmek üzere değiştirin (.. \Simplehesapla, Tor\extensions\\).

 Module1. vb veya program.cs içinde, `Program` oluşturucuya aşağıdaki satırı ekleyin:

```vb
catalog.Catalogs.Add(New DirectoryCatalog("C:\SimpleCalculator\SimpleCalculator\Extensions"))
```

```csharp
catalog.Catalogs.Add(new DirectoryCatalog("C:\\SimpleCalculator\\SimpleCalculator\\Extensions"));
```

 Örnek yolu, uzantılar dizininizin yolunu ile değiştirin. (Bu mutlak yol yalnızca hata ayıklama amaçlıdır. Bir üretim uygulamasında göreli bir yol kullanırsınız.) Artık <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> , uzantılar dizinindeki tüm derlemelerde bulunan herhangi bir parçayı bileşim kapsayıcısına ekler.

 ExtendedOperations projesinde, SimpleCalculator ve System. ComponentModel. Composition başvurularını ekleyin. ExtendedOperations sınıf dosyasında, System. ComponentModel. `Imports` Composition için `using` bir veya bir ifade ekleyin. Visual Basic Ayrıca, SimpleCalculator için bir `Imports` ifade ekleyin. Ardından, aşağıdaki sınıfı ExtendedOperations sınıf dosyasına ekleyin:

```vb
<Export(GetType(SimpleCalculator.IOperation))>
<ExportMetadata("Symbol", "%"c)>
Public Class Modulo
    Implements IOperation

    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate
        Return left Mod right
    End Function
End Class
```

```csharp
[Export(typeof(SimpleCalculator.IOperation))]
[ExportMetadata("Symbol", '%')]
public class Mod : SimpleCalculator.IOperation
{
    public int Operate(int left, int right)
    {
        return left % right;
    }
}
```

 Sözleşmenin eşleşmesi için <xref:System.ComponentModel.Composition.ExportAttribute> özniteliğinin ile aynı türde <xref:System.ComponentModel.Composition.ImportAttribute>olması gerektiğini unutmayın.

 Projeyi derleyin ve çalıştırın. Yeni mod (%) sınamasını yapın işlecinde.

<a name="conclusion"></a>
## <a name="conclusion"></a>Sonuç
 Bu konu, MEF 'in temel kavramlarını ele almaktadır.

- Parçalar, kataloglar ve bileşim kapsayıcısı

     Parçalar ve bileşim kapsayıcısı, MEF uygulamasının temel yapı taşlarıdır. Bir bölüm, kendisini içeren veya dahil olmak üzere bir değeri içeri aktaran veya dışarı aktaran herhangi bir nesnedir. Bir katalog, belirli bir kaynaktan bir parçalar koleksiyonu sağlar. Bileşim kapsayıcısı, bir katalog tarafından, dışarı aktarmalar için içeri aktarmalar bağlamayı bağlayan bir katalog tarafından sunulan bölümleri kullanır.

- İçeri aktarmalar ve dışarı aktarmalar

     İçeri ve dışarı aktarmalar, bileşenlerin iletişim kurduğu yoldur. İçeri aktarma ile, bileşen belirli bir değer veya nesne için ihtiyacı belirtir ve bir dışarı aktarma ile bir değerin kullanılabilirliğini belirtir. Her içeri aktarma, sözleşmesi yoluyla dışarı aktarmalar listesi ile eşleştirilir.

<a name="where_do_i_go_now"></a>
## <a name="where-do-i-go-now"></a>Şimdi nereden gidebilirim?
 Bu örneğe ilişkin tüm kodu indirmek için bkz. [SimpleCalculator örneği](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).

 Daha fazla bilgi ve kod örneği için bkz. [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef). MEF türlerinin bir listesi için bkz <xref:System.ComponentModel.Composition?displayProperty=nameWithType> . ad alanı.
