---
description: As classificações numéricas 2 oferecem métricas personalizadas e flexíveis que podem ser importadas para a Adobe Experience Cloud por meio do importador.
subtopic: Classifications
title: Visão geral das classificações numéricas 2
topic: Admin tools
uuid: cbea7cd1-3a92-4e9d-b671-646e9add1ee6
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visão geral das classificações numéricas 2

As classificações numéricas 2 oferecem métricas personalizadas e flexíveis que podem ser importadas para a Adobe Experience Cloud por meio do importador.

>[!IMPORTANT]
>
>A capacidade de importar classificações Numérico 2 e Ativadas por data foi removida da base de código. Essa alteração será aplicada na Versão de manutenção de julho de 2019. Se você tiver colunas Numéricas ou Ativadas por data no arquivo de importação, essas células serão ignoradas silenciosamente e todos os outros dados nesse arquivo serão importados normalmente. As classificações existentes ainda podem ser exportadas por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

>[!NOTE] Na Versão de manutenção do Analytics de 10 de maio de 2018, a Adobe começou a limitar a funcionalidade de classificações numéricas e habilitadas por data. Esses tipos de classificações foram removidos das interfaces Admin e Importador de classificações. Nenhuma nova classificação ativada por data e numérica pode ser adicionada. As classificações existentes ainda podem ser gerenciadas (atualizadas, excluídas) por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

Uma maneira comum de usar classificações numéricas 2 é para variáveis numéricas que mudam ao longo do tempo para itens diferentes, como o custo de bens vendidos. Na administração, você pode criar classificações na [!UICONTROL Conversion Classification] página e, em seguida, usar o importador para exportar um arquivo, fazer edições e importar o arquivo de volta para a Adobe. Depois de importar os dados, você pode usar as classificações numéricas ao criar métricas calculadas.

>[!IMPORTANT]
>
>A Analysis Workspace e a Ad Hoc Analysis não oferecem suporte a classificações Numéricas 2.

A tabela a seguir ilustra as diferenças entre os tipos de classificação:

| RECURSO | TEXTO | NUMÉRICO 1.0 | NUMÉRICO 2.0 |
|---|---|---|---|
| Exibe como um relatório | Sim | Não | Não |
| Pode ser usado como uma métrica | Não | Sim | Sim |
| Pode ser criado no relatório base | Sim | Não | Sim |
| Calculado com base em eventos | Não | Sim | Sim |
| Várias linhas por chave | Não | Não | Sim |
| Pode ter valores diferentes para períodos de tempo diferentes | Não | Não | Sim |
| Pode ser usado em métricas calculadas | Não | Sim | Sim |

