---
description: Opções de calendário em outro modelo que não o Gregoriano. As opções incluem os modelos de calendário 4-4-5, 4-5-4 e 5-4-4, todos usados como padrão para o setor de varejo. Os relatórios também oferecem um calendário completamente personalizável que você mesmo pode configurar.
title: Personalizar calendário
feature: Admin Tools
exl-id: 2196c7b7-7183-43a8-bb91-5a1e479819d4
role: Admin
TQID: https://experienceleague.adobe.com/14PcXGRnv3ab-D2NaRAs4-pgiDYk4OnMnKCfNB2uEbc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: e44bec7e-8653-4d5b-b53e-60b1ae7c3475
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 563
ht-degree: 40%

---

# Personalizar calendário

Opções de calendário em outro modelo que não o Gregoriano. As opções incluem os modelos de calendário 4-4-5, 4-5-4 e 5-4-4, todos usados como padrão para o setor de varejo. Além disso, os relatórios oferecem uma opção para um calendário completamente personalizável que você mesmo pode configurar.

**[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Personalizar calendário]**

>[!CAUTION]
>
>Alterar o calendário resulta em alterações na maneira como os dados são processados (ou seja, a definição semanal e mensal de visitantes únicos). Quando a definição do calendário de semanas e meses muda, os dados históricos não são alterados. Essa configuração também afeta segmentos com base em intervalos de datas.

Você pode usar o calendário para definir o primeiro dia da semana e ano, ou usar um estilo de calendário de varejo diferente. Os formatos de calendário são usados para várias finalidades, incluindo comparação de vendas e padronização de previsão, análise de custo de folha de pagamento ou regulamento de contagem de inventário físico. Por exemplo, o setor de varejo usa o calendário contábil 4-5-4 para dar suporte às necessidades específicas da temporada de vendas para o setor de varejo. Cada um dos formatos de calendário é descrito abaixo.

## Personalizar descrições de calendário {#section_B0D224DACB914A378902A4E0E1234889}

| Calendário | Descrição |
|--- |--- |
| Calendário gregoriano | Usa o formato de calendário tradicional (janeiro a dezembro, com 30 ou 31 dias e um número variável de semanas em cada mês). |
| Calendário Gregoriano Modificado | Usa o Calendário gregoriano tradicional, mas permite selecionar o primeiro mês do ano e o primeiro dia da semana. |
| 4-5-4 Calendário fiscal | Divide cada mês pelo número de semanas no mês. Janeiro tem quatro semanas, e assim por diante. A National Retail Federation usa o formato de calendário 4-5-4. |
| Calendário personalizado | Oferece três formatos com base no número de semanas em cada mês. O número de semanas em cada mês depende do primeiro dia do ano selecionado.  Um ano tem 52 semanas. Divida isso em 4 trimestres e você terá 13 semanas por trimestre. Mas há 3 meses em um trimestre. O número 13 não é divisível por três, dessa forma você acaba colocando uma semana extra em um dos meses, de forma que seja sempre consistente.<ul><li>5/4/4 significa que o primeiro mês do trimestre recebe a semana extra. 4/5/4 significa que o segundo mês do trimestre recebe a semana extra, etc. No calendário 5-4-4, a 53ª semana é adicionada ao último trimestre do ano.</li><li>4-5-4:January tem quatro semanas, fevereiro tem cinco semanas, março tem quatro semanas e assim por diante.</li><li>4-4-5: janeiro possui quatro semanas, fevereiro quatro, março cinco e assim por diante.</li><li>5-4-4: janeiro tem cinco semanas, fevereiro tem quatro, março tem quatro, e assim em diante.</li></ul> |

>[!NOTE]
>Essas opções de calendário são compatíveis com todas as ferramentas do Adobe Analytics (Analysis Workspace, Report Builder, Activity Map), exceto o Data Warehouse. Data Warehouse oferece suporte total apenas ao calendário gregoriano. Ao escolher um calendário não gregoriano, o Data Warehouse usará o intervalo de datas esperado do calendário não gregoriano, no entanto, os detalhamentos de dia/semana/mês nas linhas do relatório podem não ser o esperado de um calendário não gregoriano.
