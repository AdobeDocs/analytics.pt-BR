---
title: Macros do Visual Basic no Report Builder
description: Expanda a funcionalidade de pastas de trabalho e Report Builder do Excel usando o VBA.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Macros do Visual Basic no Report Builder

As macros VBA, também conhecidas como macros do Visual Basic, permitem manipular pastas de trabalho de maneiras que o Microsoft Excel não pode usar sozinho. O Visual Basic tem acesso à pasta de trabalho, ao Excel e até mesmo ao Windows.

Adobe suporta três métodos de API de Report Builder. Verifique se a versão mais recente do Construtor de relatórios está instalada e faça logon antes de executar qualquer macros.

>[!IMPORTANT]
>
>Por motivos de segurança, não é possível agendar uma pasta de trabalho que contenha uma macro.

## `RefreshAllReportBuilderRequests()`

The `RefreshAllReportBuilderRequests()` macro refreshes all Report Builder requests in the active workbook. Ele é start chamando o Report Builder COM Add-in por meio de sua ID de produto e, em seguida, chama o comando da `RefreshAllRequests()` API:

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

The `RefreshAllReportBuilderRequestsInActiveWorksheet()` macro refreshes all Report Builder requests in the active worksheet. A chamada de `RefreshWorksheetRequests()` API usa um objeto de planilha como argumento. Você pode usar esta chamada para qualquer planilha que contenha solicitações de Report Builder:

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

The `RefreshAllReportBuilderRequestsInCellsRange()` macro refreshes all Report Builder requests whose cell outputs intersect the specified range of cells. O intervalo de células usado neste exemplo aponta para o intervalo `B1:B54` da planilha &quot;Dados&quot; na pasta de trabalho ativa. A expressão de intervalo suporta todas as expressões de intervalo do Excel suportadas:

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
