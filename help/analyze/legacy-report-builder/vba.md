---
title: Como usar macros do Visual Basic no Report Builder
description: Saiba como expandir a funcionalidade de pastas de trabalho e Report Builder do Excel usando macros VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 64%

---

# Macros do Visual Basic no Report Builder

As macros do Visual Basic (VBA) fornecem recursos que ajudam a atualizar pastas de trabalho do Excel. O Visual Basic tem acesso à pasta de trabalho, Excel e Windows.

Você deve executar a versão mais recente do Report Builder e fazer logon antes de executar macros VBA.

>[!IMPORTANT]
>
>Por motivos de segurança, não é possível agendar uma pasta de trabalho que contenha uma macro

O Adobe suporta três métodos de API de Report Builder.

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
