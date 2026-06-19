---
title: Visão geral de dimensões
description: Saiba o que são dimensões e como elas são usadas no Adobe Analytics.
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
TQID: https://experienceleague.adobe.com/WypIneraYlrSyIpXv3UQWIFn42A-Dxi0SxeJ2VbeubQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 37%

---

# Visão geral das dimensões

Dimensões são variáveis no Adobe Analytics que normalmente contêm valores de string. As dimensões comuns incluem [Página](page.md), [Domínio de referência](referring-domain.md) ou uma [eVar](evar.md). Por outro lado, as [métricas](../metrics/overview.md) contêm valores numéricos que se vinculam a uma dimensão. Um relatório básico mostra linhas de valores da sequência de caracteres (dimensão) em relação a uma coluna de valores numéricos (métrica).

Por exemplo, se você tiver combinado a dimensão **[!UICONTROL Página]** com a métrica **[!UICONTROL Visitas]**, obterá um relatório classificado que mostra as suas páginas mais visitadas:

| Página | Visitas |
| --- | ---: |
| Página inicial | 800 |
| Página do produto | 500 |
| Página de compra | 100 |

{style="table-layout:fixed"}

Cada dimensão representa uma parte ou uma faceta diferente do site. É possível combinar uma ou mais dessas dimensões com uma ou mais métricas para criar o relatório desejado.

## Adicionar descrições de dimensão

Os administradores do Analytics podem adicionar descrições de dimensões e outros componentes dentro do conjunto de relatórios ou diretamente do Analysis Workspace. Para obter informações sobre como adicionar descrições a dimensões, consulte [Adicionar descrições de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Dimensões removidas

As seguintes dimensões foram removidas. A maioria eram relatórios do Reports &amp; Analytics que não estavam disponíveis no Analysis Workspace. Eles são documentados aqui para referência se você os encontrar nos relatórios herdados ou dados históricos.

* **Hierarquia**: uma dimensão personalizada (`hier1`-`hier5`) usada para capturar a estrutura hierárquica de um site para relatórios. Ela foi removida e não está disponível no Analysis Workspace. Em vez disso, use [eVars](evar.md) e classificações.
* **Página inicial**: um sinalizador que indica se a página atual era a página inicial do navegador do visitante. É uma dimensão herdada sem equivalente moderno devido às práticas modernas de privacidade do navegador.
* **Suporte do JavaScript**: indicou se o navegador do visitante suportava o JavaScript. Uma dimensão herdada que não é mais significativa para a medição moderna.
* **Versão do JavaScript**: relatou a versão do JavaScript para a qual o navegador do visitante deu suporte. Uma dimensão herdada que não é mais coletada.
* **Próxima página**: uma dimensão de definição de caminho que mostra a próxima página que um visitante visualizou. Use a [Visualização de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) no Analysis Workspace para as dimensões de definição de caminho atuais.
* **Página anterior**: uma dimensão de definição de caminho que mostra a página anterior que um visitante visualizou. Use a [Visualização de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) no Analysis Workspace para as dimensões de definição de caminho atuais.
* **Fuso Horário**: o fuso horário do visitante, derivado do deslocamento do carimbo de data/hora nas solicitações de imagem do AppMeasurement. O Web SDK coleta fuso horário usando [`placeContext`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/js/commands/configure/context).
* **Domínio de nível superior**: o domínio de nível superior do ponto de acesso do visitante. Um relatório herdado do Reports &amp; Analytics; use a dimensão [Domínio](domain.md).
* **Número de Página da Visita**: o número de página em uma visita. Um relatório herdado do Reports &amp; Analytics; use a dimensão [Profundidade da ocorrência](hit-depth.md).
* **Estado do Visitante**: relatou o estado dos EUA a partir da variável `s.state`. Foi removido em favor da dimensão [Estados dos EUA](us-states.md), que usa geosegmentação.
