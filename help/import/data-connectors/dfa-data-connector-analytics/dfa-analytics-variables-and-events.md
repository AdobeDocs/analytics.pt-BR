---
description: A integração do Data Connectors para DFA usa variáveis do Analytics para monitorar os resultados de campanha do DFA.
keywords: DFA
title: Variáveis e eventos do Analytics
topic: Data connectors
uuid: 8996cb58-c793-4600-99ef-af3064642b29
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Variáveis e eventos do Analytics {#analytics-variables-and-events}

A integração do Data Connectors para DFA usa variáveis do Analytics para monitorar os resultados de campanha do DFA.

Além da variável de campanha, você pode usar eventos e eVars do Analytics que fazem sentido para você. Depois de identificar o evento e as eVars para usar com esta integração do DFA, use o Admin Console do Analytics para habilitá-los. As variáveis de integração devem ser habilitadas antes da ativação da integração do DFA. A tabela a seguir descreve as variáveis do Analytics necessárias para a integração do DFA.

| Variável | Nome amigável | Método de preenchimento | Descrição |
|---|---|---|---|
| s.campaign ou eVar | Código de rastreamento de anúncio | Automaticamente preenchido pelo conector de dados para campanhas do DFA. | Rastreia conversões de click-through para todas as campanhas. |
| eVar* | View-through | Automaticamente preenchido pelo VISTA e pelo DFA para as campanhas do DFA. | Rastreia dados de view-through para IDs do DFA. Essa eVar deve ter a mesma expiração da variável *`s.campaign`*. Deve ser a mesma variável de conversão identificada na ID do provedor da variável. Verifique se as sub-relações da eVar estão habilitadas. O custo de habilitação desse recurso é parte da tarifa de integração dos Data Connectors. |
| eVar* | Erros de consulta do DFA | (Opcional) Preenchido pelo código de coleta do JavaScript. | Contém um dos vários códigos de erro retornados do DFA. |
| evento* | Contagem de view-through | Automaticamente preenchido pelo conector de dados para campanhas do DFA. | Captura o número de vezes que os usuários visualizaram um anúncio, não clicaram nele, mas chegaram ao site. |
| evento* | Impressões | Automaticamente preenchido por um feed de dados do DFA. | Rastreia o número de vezes que um anúncio do DFA específico foi veiculado. |
| evento* | Cliques | Automaticamente preenchido por um feed de dados do DFA. | Rastreia o número de vezes que os usuários clicaram em um anúncio de banner específico do DFA. Essa métrica pode produzir números diferentes em comparação com a métrica de click-through nativa do Analytics por um de vários motivos. Consulte [Comparação de discrepâncias de métricas](/help/import/data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) para obter mais informações. |
| evento* | Tempos limite do DFA | (Opcional) Preenchido pelo código de coleta do JavaScript. | Conta o número de vezes que o DFA deixa de responder antes de exceder o tempo limite de *`s.maxDelay`*. Isso pode ajudar a determinar se há um problema de implementação do DFA. |
| evento* | Custo de mídia do DFA | Automaticamente preenchido por um feed de dados do DFA. | Contém as métricas de custo de mídia que foram inseridas na interface do DFA. Esse recurso deve ser habilitado no DFA para que essas métricas sejam exibidas. |

*Selecione uma eVar ou um evento personalizado não utilizado.
