---
description: As classificações numéricas 2 oferecem métricas personalizadas e flexíveis que podem ser importadas para a Adobe Experience Cloud por meio do importador.
seo-description: As classificações numéricas 2 oferecem métricas personalizadas e flexíveis que podem ser importadas para a Adobe Experience Cloud por meio do importador.
seo-title: Visão geral das classificações numéricas 2
solution: Analytics
subtopic: Classificações
title: Visão geral das classificações numéricas 2
topic: Ferramentas administrativas
uuid: cbea7cd1-3a92-4e9d-b671-646e9add1ee6
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Visão geral das classificações numéricas 2

As classificações numéricas 2 oferecem métricas personalizadas e flexíveis que podem ser importadas para a Adobe Experience Cloud por meio do importador.

>[!IMPORTANT]
>
>A capacidade de importar classificações Numérico 2 e Ativadas por data foi removida da base de código. Essa alteração será aplicada na Versão de manutenção de julho de 2019. Se você tiver colunas Numéricas ou Ativadas por data no arquivo de importação, essas células serão ignoradas silenciosamente e todos os outros dados nesse arquivo serão importados normalmente. As classificações existentes ainda podem ser exportadas por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

>[!NOTE]
>
>Na versão de 10 de maio de 2018 da Analytics Maintenance, a Adobe começou a limitar a funcionalidade de classificações numéricas e ativadas por data. Esses tipos de classificações foram removidos das interfaces Admin e Importador de classificações. Nenhuma classificação numérica ou habilitada por data pode ser adicionada. As classificações existentes ainda podem ser gerenciadas (atualizadas, excluídas) por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

Uma maneira comum de usar as classificações numéricas 2 é para variáveis numéricas que mudam ao longo do tempo para itens diferentes, como o custo dos bens vendidos. Na administração, você pode criar classificações na página [!UICONTROL Classificação da conversão] e usar o importador para exportar um arquivo, efetuar auditorias e importar o arquivo de volta para a Adobe. Após importar os dados, é possível usar a classificação numérica ao criar métricas calculadas.

>[!IMPORTANT]
>
>A Analysis Workspace e a Análise ad hoc não suportam classificações numéricas 2.

A tabela a seguir ilustra a diferença entre os tipos de classificação:

| RECURSO | TEXTO | NUMÉRICO 1,0 | NUMÉRICO 2,0 |
|---|---|---|---|
| Exibe como um relatório | Sim | Não | Não |
| Pode ser usado como uma métrica | Não | Sim | Sim |
| Pode ser criado no relatório de base | Sim | Não | Sim |
| Calculado com base em eventos | Não | Sim | Sim |
| Múltiplas linhas por chave | Não | Não | Sim |
| Pode ter valores diferentes para períodos de tempo diferentes | Não | Não | Sim |
| Pode ser usado em métricas calculadas | Não | Sim | Sim |

