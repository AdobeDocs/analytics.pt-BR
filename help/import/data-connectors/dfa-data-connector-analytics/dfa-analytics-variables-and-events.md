---
description: A integração de Conectores de dados do DFA usa variáveis do Analytics para monitorar os resultados de campanha do DFA.
keywords: DFA
seo-description: A integração de Conectores de dados do DFA usa variáveis do Analytics para monitorar os resultados de campanha do DFA.
seo-title: Variáveis e eventos do Analytics
solution: Analytics
title: Variáveis e eventos do Analytics
topic: Conectores de dados
uuid: 8996 cb 58-c 793-4600-99 ef-af 3064642 b 29
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Variáveis e eventos do Analytics{#analytics-variables-and-events}

A integração de Conectores de dados do DFA usa variáveis do Analytics para monitorar os resultados de campanha do DFA.

Além da variável de campanha, você pode usar eventos e eVars do Analytics que fazem sentido para você. Depois de identificar o evento e as eVars para usar com esta integração do DFA, use o Admin Console do Analytics para habilitá-los. As variáveis de integração devem ser habilitadas antes da ativação da integração do DFA. A tabela a seguir descreve as variáveis do Analytics necessárias para a integração do DFA.

| Variável | Nome amigável | Método de preenchimento | Descrição |
|---|---|---|---|
| s.campaign ou eVar | Código de rastreamento de anúncio | Automaticamente preenchido pelo conector de dados para campanhas do DFA. | Rastreia conversões de click-through para todas as campanhas. |
| eVar* | View-through | Automaticamente preenchido pelo VISTA e pelo DFA para as campanhas do DFA. | Rastreia dados de view-through para IDs do DFA. Essa eVar deve ter a mesma expiração da variável *`s.campaign`* variável. Deve ser a mesma variável de conversão identificada na ID do provedor de variáveis (consulte [Atualizar o código de coleta de dados do site](../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)). Verifique se as sub-relações da eVar estão habilitadas. O custo de habilitação desse recurso é parte da taxa de integração dos Conectores de dados. |
| eVar* | Erros de consulta do DFA | (Opcional) Preenchido pelo código de coleta do JavaScript. | Contém um de vários códigos de erros retornados do DFA (consulte a tabela em [Configuração da integração](../dfa-data-connector-analytics/dfa-integration/dfa-integration.md#concept-cf33e1051c73452cbd26e950d0293858) para obter um lista desses códigos de erros). |
| event* | Contagem de view-through | Automaticamente preenchido pelo conector de dados para campanhas do DFA. | Captura o número de vezes que os usuários visualizaram um anúncio, não clicaram nele, mas chegaram ao site. |
| event* | Impressões | Automaticamente preenchido por um feed de dados do DFA. | Rastreia o número de vezes que um anúncio do DFA específico foi veiculado. |
| event* | Cliques | Automaticamente preenchido por um feed de dados do DFA. | Rastreia o número de vezes que os usuários clicaram em um anúncio de banner específico do DFA. Essa métrica pode produzir números diferentes em comparação com a métrica de click-through nativa do Analytics por um de vários motivos. Consulte [Comparação de discrepâncias de métricas](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f) para obter mais informações. |
| event* | Tempos limite do DFA | (Opcional) Preenchido pelo código de coleta do JavaScript. | Conta o número de vezes que o DFA deixa de responder antes de exceder o tempo limite de *`s.maxDelay`*. Isso pode ajudar a determinar se há um problema de implementação do DFA. |
| event* | Custo de mídia do DFA | Automaticamente preenchido por um feed de dados do DFA. | Contém as métricas de custo de mídia que foram inseridas na interface do DFA. Esse recurso deve ser habilitado no DFA para que essas métricas sejam exibidas. |

*Selecione uma eVar ou um evento personalizado não utilizado.
