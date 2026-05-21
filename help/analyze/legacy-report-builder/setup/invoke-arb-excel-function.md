---
description: Saiba como usar o Microsoft Excel com funções do Report Builder sem acessar a interface do usuário do Report Builder.
title: Saiba como usar o Microsoft Excel com funções do Report Builder
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
TQID: https://experienceleague.adobe.com/cgDjTqGH0KzSrpg66sRfF8Kf81Q-WDwSWJ-OBvJK8DM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 23%

---

# Usar funções do Report Builder com o Microsoft Excel

{{legacy-arb}}

Você pode usar as funções do Report Builder para acessar a funcionalidade sem acessar a interface do usuário do Report Builder.

Por exemplo, para atualizar automaticamente solicitações do Report Builder com filtros de entrada com base em dados transferidos para o Excel de outras fontes, use a cadeia de caracteres RefreshRequestsInCellsRange(..) função. Todas as chamadas são assíncronas, retornam imediatamente e não aguardam a execução completa.

**Requisitos**

* O Report Builder 5.0 (ou posterior) é necessário.

A tabela a seguir lista as funções expostas.

| Nome da função | Tipo | Descrição |
|:---| --- | ---|
| AsyncRefreshAll() | string | Atualiza todas as solicitações do Report Builder presentes em uma pasta de trabalho. |
| AsyncRefreshRange(cadeia de caracteres rangeAddressInA1Format) | string | Atualiza todas as solicitações do Report Builder presentes no endereço do intervalo de células especificado (uma expressão de cadeia de caracteres que representa um intervalo de células no formato A1, por exemplo &quot;Sheet1!A2:A10&quot;). |
| AsyncRefreshRangeAltTextParam() | string | Atualiza todas as solicitações do Report Builder presentes no intervalo de células especificado que é passado para Texto alternativo do Controle de formulários da Ms. |
| AsyncRefreshActiveWorksheet() | string | Atualiza todas as solicitações do Report Builder presentes na planilha ativa. |
| AsyncRefreshWorksheet(nomePlanilhaCadeiaDeCaracteres) | string | Atualiza todas as solicitações do Report Builder presentes na planilha especificada (o nome da planilha como aparece na guia). |
| AsyncRefreshWorksheetAltTextParam(); | string | Atualiza todas as solicitações do Report Builder presentes no nome da planilha específica que foi passada para Texto alternativo do Controle de formulários da Ms |
| string GetLastRunStatus() | string | Retorna uma string que descreve o status da última execução. |

Para acessar as funções do Report Builder, vá para **[!UICONTROL Fórmulas]** > **[!UICONTROL Inserir função]**. Use o campo de pesquisa para procurar uma função ou selecione uma categoria para listar as funções nessa categoria.

![Captura de tela mostrando a janela Inserir Função com a lista de categorias expandida.](assets/arb_functions.png)

## Exemplo {#section_034311081C8D4D7AA9275C1435A087CD}

O exemplo a seguir mostra *Se o valor na célula P5 for texto ou estiver em branco, atualize o intervalo na célula P9*.

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## Usar funções do Report Builder com controle de formato {#section_26123090B5BD49748C8D8ED7A1C5ED84}

Você pode atribuir uma macro a um controle criado e esse controle pode ser uma função que atualiza uma solicitação da pasta de trabalho. Por exemplo, a função AsyncRefreshActiveWorksheet atualizará todas as solicitações em uma planilha. No entanto, às vezes, convém atualizar apenas determinadas solicitações.

1. Defina o parâmetro de macro.
1. Clique com o botão direito no controle e selecione **[!UICONTROL Atribuir Macro]**.
1. Insira o nome da função Report Builder (sem parâmetros ou parênteses).

![Captura de tela mostrando a janela Atribuir Macro.](assets/assign_macro.png)

## Passar parâmetros para funções do Report Builder usando controle de formato {#section_ECCA1F4990D244619DFD79138064CEF0}

Duas funções que usam um parâmetro podem ser usadas com o Controle de formato. Você deve usar o campo **Texto alternativo:**:

* AsyncRefreshRange(cadeia de caracteres rangeAddressInA1Format)
* AsyncRefreshWorksheet(nomePlanilhaCadeiaDeCaracteres)

Para passar parâmetros para funções do Report Builder usando o controle de formato

1. Clique com o botão direito no controle e selecione **[!UICONTROL Controle de formato]**.

   ![Captura de tela mostrando o Controle de Formato selecionado.](assets/format_control.png)

1. Clique na guia **[!UICONTROL Alt Text]**.

   ![Captura de tela mostrando a guia Texto Alternativo e o campo Texto Alternativo:.](assets/alt_text.png)

1. Em **[!UICONTROL Texto alternativo]**, insira o intervalo de células que você deseja atualizar.
1. Abra a lista de parâmetros do Report Builder em **[!UICONTROL Fórmulas]** > **[!UICONTROL Inserir Função]**> **[!UICONTROL Adobe.ReportBuilder.Bridge]**.

1. Selecione uma das duas funções que terminam com AltTextParam e clique em **[!UICONTROL OK]**.
