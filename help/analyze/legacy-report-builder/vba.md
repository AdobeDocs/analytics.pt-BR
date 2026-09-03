---
title: Como usar macros do Visual Basic no Report Builder
description: Saiba como expandir a funcionalidade de pastas de trabalho do Excel e do Report Builder usando macros VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
TQID: https://experienceleague.adobe.com/RxOpojtJn2vi5uMO8CGzCCm7FcPp4qVwbH-XTEBSRsY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 64%

---

# Macros do Visual Basic no Report Builder

{{legacy-arb}}

As macros do Visual Basic (VBA) fornecem recursos que ajudam a atualizar pastas de trabalho do Excel. O Visual Basic tem acesso à pasta de trabalho, Excel e Windows.

Você deve executar a versão mais recente do Report Builder e fazer logon antes de executar as macros VBA.

>[!IMPORTANT]
>
>Por motivos de segurança, não é possível agendar uma pasta de trabalho que contenha uma macro

O Adobe oferece suporte a três métodos de API do Report Builder.

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
