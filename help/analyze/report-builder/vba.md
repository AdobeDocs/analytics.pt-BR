---
title: Macros do Visual Basic no Report Builder
description: Expanda a funcionalidade de pastas de trabalho do Excel e do Report Builder usando VBA.
feature: Report Builder
role: Profissional de negócios, Administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 98%

---


# Macros do Visual Basic no Report Builder

As macros VBA, também conhecidas como macros do Visual Basic, permitem manipular pastas de trabalho de maneiras que o Microsoft Excel não é capaz. O Visual Basic tem acesso à pasta de trabalho, ao Excel e até mesmo ao Windows.

A Adobe aceita três métodos de API do Report Builder. Verifique se a versão mais recente do Report Builder está instalada e faça logon antes de executar uma macro.

>[!IMPORTANT]
>
>Por motivos de segurança, não é possível agendar uma pasta de trabalho que contenha uma macro

## `RefreshAllReportBuilderRequests()`

A macro `RefreshAllReportBuilderRequests()` atualiza todas as solicitações do Report Builder na pasta de trabalho ativa. Ela é iniciada chamando o suplemento COM do Report Builder por meio de sua ID de produto e, em seguida, chama o comando da API `RefreshAllRequests()`:

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

A macro `RefreshAllReportBuilderRequestsInActiveWorksheet()` atualiza todas as solicitações do Report Builder na planilha ativa. A chamada de API `RefreshWorksheetRequests()` usa um objeto de planilha como argumento. Você pode usar esta chamada para qualquer planilha que contenha solicitações do Report Builder:

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

A macro `RefreshAllReportBuilderRequestsInCellsRange()` atualiza todas as solicitações do Report Builder cujos resultados da célula se cruzam com o intervalo de células especificado. O intervalo de células usado neste exemplo aponta para o intervalo `B1:B54` da planilha “Dados” na pasta de trabalho ativa. A expressão de intervalo aceita todas as expressões de intervalo do Excel compatíveis:

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
