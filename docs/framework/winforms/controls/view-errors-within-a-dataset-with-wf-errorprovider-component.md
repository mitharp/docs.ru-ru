---
title: Как выполнить Просмотр ошибок в наборе данных с помощью компонента ErrorProvider в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 48f333fbae816748813b370bccc559cea2714fa5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694052"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Как выполнить Просмотр ошибок в наборе данных с помощью компонента ErrorProvider в Windows Forms
Можно использовать в Windows Forms <xref:System.Windows.Forms.ErrorProvider> компонента для просмотра ошибок в столбцах набора данных или другом источнике данных. Для <xref:System.Windows.Forms.ErrorProvider> компонент для отображения ошибок данных в форме, оно не обязательно должно непосредственно связаны с элементом управления. После привязки к источнику данных, она может отображать значок ошибки рядом с любой элемент управления, привязанный к тому же источнику данных.  
  
> [!NOTE]
>  Если изменить поставщик ошибок <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> и <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> свойства во время выполнения, следует использовать <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> метод во избежание конфликтов.  
  
### <a name="to-display-data-errors"></a>Для отображения ошибок в данных  
  
1.  Компонент привязки к определенному столбцу в таблице данных.  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  Задайте <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> в форму свойство.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  Установка для позиции текущей записи в строку, содержащую ошибку столбца.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>См. также
- [Общие сведения о компоненте ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)
- [Практическое руководство. Отображение значков ошибок для проверки формы с помощью компонента ErrorProvider в Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
