---
title: 'Nasıl yapılır: Windows Forms DataGrid Denetimiyle Girişi Doğrulama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: dc8c8f157e6673c1bddc68bfb511683e6d2b99be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796480"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="d199c-102">Nasıl yapılır: Windows Forms DataGrid Denetimiyle Girişi Doğrulama</span><span class="sxs-lookup"><span data-stu-id="d199c-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="d199c-103"><xref:System.Windows.Forms.DataGridView> Denetimi değiştirir ve işlevsellik ekler <xref:System.Windows.Forms.DataGrid> denetler; ancak, <xref:System.Windows.Forms.DataGrid> denetim korunur geriye dönük uyumluluk ve gelecekte kullanım için seçerseniz.</span><span class="sxs-lookup"><span data-stu-id="d199c-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="d199c-104">Daha fazla bilgi için [farklar arasında Windows Forms DataGridView ve DataGrid denetimleri](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="d199c-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="d199c-105">İki tür giriş doğrulaması Windows Forms'da kullanılabilen <xref:System.Windows.Forms.DataGrid> denetimi.</span><span class="sxs-lookup"><span data-stu-id="d199c-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="d199c-106">Kullanıcı bir kabul edilebilir veri türü tamsayı, örneğin bir dizeye hücre için bir değer girmeyi denerse yeni geçersiz bir değer eski değer ile değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="d199c-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="d199c-107">Bu tür bir giriş doğrulama otomatik olarak yapılır ve özelleştirilemez.</span><span class="sxs-lookup"><span data-stu-id="d199c-107">This kind of input validation is done automatically and cannot be customized.</span></span>

<span data-ttu-id="d199c-108">Bir giriş doğrulama türünü kabul edilemez tüm verileri, örneğin 0 değerinde büyüktür veya eşittir 1 ya da uygun olmayan bir dize olmalıdır. bir alan reddetmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d199c-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="d199c-109">Bu veri kümesi için bir olay işleyicisi yazarak yapılır <xref:System.Data.DataTable.ColumnChanging> veya <xref:System.Data.DataTable.RowChanging> olay.</span><span class="sxs-lookup"><span data-stu-id="d199c-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="d199c-110">Kullanan aşağıdaki örnekte <xref:System.Data.DataTable.ColumnChanging> olay "Product" sütunu için özellikle izin verilmeyen kabul edilemez değeri olduğundan.</span><span class="sxs-lookup"><span data-stu-id="d199c-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="d199c-111">Kullanabileceğinize <xref:System.Data.DataTable.RowChanging> bir "Bitiş tarihi" sütunun değeri "StartDate" sütun ile aynı satırdaki daha olduğunu denetlemek için olay.</span><span class="sxs-lookup"><span data-stu-id="d199c-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>

## <a name="to-validate-user-input"></a><span data-ttu-id="d199c-112">Kullanıcı girişini doğrulamak için</span><span class="sxs-lookup"><span data-stu-id="d199c-112">To validate user input</span></span>

1. <span data-ttu-id="d199c-113">İşlemek için kod yazma <xref:System.Data.DataTable.ColumnChanging> uygun tablosu için olay.</span><span class="sxs-lookup"><span data-stu-id="d199c-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="d199c-114">Uygun olmayan giriş algılandığında, çağrı <xref:System.Data.DataRow.SetColumnError%2A> yöntemi <xref:System.Data.DataRow> nesne.</span><span class="sxs-lookup"><span data-stu-id="d199c-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
             e.Row.SetColumnError(e.Column, "Product cannot be " & _
             CType(badValue, String))
          End If
       End If
    End Sub
    ```

    ```csharp
    //Handle column changing events on the Customers table
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {

       //Only check for errors in the Product column
       if (e.Column.ColumnName.Equals("Product")) {

          //Do not allow "Automobile" as a product
          if (e.ProposedValue.Equals("Automobile")) {
             object badValue = e.ProposedValue;
             e.ProposedValue = "Bad Data";
             e.Row.RowError = "The Product column contains an error";
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);
          }
       }
    }
    ```

2. <span data-ttu-id="d199c-115">Olay işleyicisi olaya bağlayın.</span><span class="sxs-lookup"><span data-stu-id="d199c-115">Connect the event handler to the event.</span></span>

    <span data-ttu-id="d199c-116">Yere aşağıdaki kod içinde ya da formun <xref:System.Windows.Forms.Form.Load> olay ya da kendi Oluşturucu.</span><span class="sxs-lookup"><span data-stu-id="d199c-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>

    ```vb
    ' Assumes the grid is bound to a dataset called customersDataSet1
    ' with a table called Customers.
    ' Put this code in the form's Load event or its constructor.
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging
    ```

    ```csharp
    // Assumes the grid is bound to a dataset called customersDataSet1
    // with a table called Customers.
    // Put this code in the form's Load event or its constructor.
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);
    ```

## <a name="see-also"></a><span data-ttu-id="d199c-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d199c-117">See also</span></span>

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="d199c-118">DataGrid Denetimi</span><span class="sxs-lookup"><span data-stu-id="d199c-118">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
