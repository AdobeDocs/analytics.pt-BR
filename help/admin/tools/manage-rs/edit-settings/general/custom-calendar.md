---
description: As opções de calendário diferentes do modelo gregoriano. As opções incluem os modelos de calendário 4-4-5, 4-5-4 e 5-4-4, que são usados como padrões para o setor de varejo. Os relatórios também oferecem um calendário completamente personalizável que você mesmo pode configurar.
title: Personalizar calendário
feature: Admin Tools
exl-id: 2196c7b7-7183-43a8-bb91-5a1e479819d4
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 91%

---

# Personalizar calendário

As opções de calendário diferentes do modelo gregoriano. As opções incluem os modelos de calendário 4-4-5, 4-5-4 e 5-4-4, que são usados como padrões para o setor de varejo. Além disso, o relatório oferece uma opção de calendário totalmente personalizável que você mesmo pode configurar.

**[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Personalizar calendário]**

>[!CAUTION]
>
>Alterar o calendário resulta em alterações na maneira como os dados são processados (ou seja, a definição semanal e mensal de visitantes únicos). Quando a definição do calendário de semanas e meses muda, os dados históricos não são alterados. Essa configuração também afeta segmentos com base em intervalos de datas.

Você pode usar o calendário para definir o primeiro dia da semana e ano, ou usar um estilo de calendário de varejo diferente. Os formatos de calendário são usados para várias finalidades, inclusive comparações de vendas e padronização de previsões, análise de custos com folha de pagamento ou regulamento de contagem de inventário físico. Por exemplo, o setor de varejo usa o calendário contábil 4-5-4 em suporte à temporada de vendas característica do setor de varejo. Cada um dos formatos de calendário é descrito abaixo.

## Personalizar descrições de calendário {#section_B0D224DACB914A378902A4E0E1234889}

| Calendário | Descrição |
|--- |--- |
| Calendário Gregoriano | Use o formato de calendário tradicional (janeiro a dezembro com 30 ou 31 dias e um número variável de semanas em cada mês). |
| Calendário Gregoriano Modificado | Usa o calendário gregoriano tradicional, mas permite que você selecione o primeiro mês do ano e o primeiro dia da semana. |
| Calendário de varejo 4-5-4 | Desmembra cada mês pelo número de semanas no mês. Isto é, janeiro tem quatro semanas, e assim por diante. A Federação Nacional do Varejo nos Estados Unidos usa o formato de calendário 4-5-4. |
| Calendário personalizado | Oferece três formatos baseados no número de semanas em cada mês. O número de semanas em cada mês depende do primeiro dia do ano selecionado.  Um ano possui 52 semanas. Divida esse valor por 4 trimestres e você terá 13 semanas por trimestre. Mas há 3 meses em um trimestre. O número 13 não é divisível por três, dessa forma você acaba colocando uma semana extra em um dos meses, de forma que seja sempre consistente.<ul><li>5/4/4 significa que o primeiro mês do trimestre recebe a semana extra. 4/5/4 significa que o segundo mês do trimestre recebe a semana extra, etc. No calendário 5-4-4, a 53ª semana é adicionada ao último trimestre do ano.</li><li>4-5-4:January tem quatro semanas, fevereiro tem cinco semanas, março tem quatro semanas e assim por diante.</li><li>4-4-5: janeiro possui quatro semanas, fevereiro quatro, março cinco e assim por diante.</li><li>5-4-4: janeiro tem cinco semanas, fevereiro tem quatro, março tem quatro, e assim em diante.</li></ul> |

>[!NOTE]
>Essas opções de calendário são compatíveis com todas as ferramentas do Adobe Analytics (Analysis Workspace, Report Builder, Activity Map), exceto o Data Warehouse. Data Warehouse oferece suporte total apenas ao calendário gregoriano. Ao escolher um calendário não gregoriano, o Data Warehouse usará o intervalo de datas esperado do calendário não gregoriano, no entanto, os detalhamentos de dia/semana/mês nas linhas do relatório podem não ser o esperado de um calendário não gregoriano.
