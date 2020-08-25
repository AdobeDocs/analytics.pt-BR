---
title: Solução de problemas de presença de dados
description: Saiba quais etapas você pode seguir quando não vir dados em relatórios.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 4%

---


# Solução de problemas de presença de dados

No Analysis Workspace, algumas configurações de projeto retornam zero linhas. Em Relatórios e análises, exibir determinados relatórios retorna a seguinte mensagem:

**&quot;Não há dados para os critérios selecionados.&quot;**

Use as seguintes etapas para determinar por que um relatório não mostra os dados.

## Os dados existem, mas são filtrados

Seu conjunto de relatórios contém dados, mas os componentes específicos usados no relatório filtros todos os dados.

* **Segmentos**: Os segmentos podem facilmente impedir que todos os dados apareçam em um relatório. Verifique todas as definições de segmento e remova todos os segmentos para ver se um segmento está fazendo com que seus dados não apareçam.
* **Métricas**: Verifique se as métricas corretas foram usadas. Altere a métrica para [Ocorrências](/help/components/metrics/occurrences.md) para garantir que ela não seja o contribuidor para um relatório sem dados.
* **Intervalos** de datas: Os intervalos de datas muito distantes no passado ou no futuro não retornam dados. A política [de retenção de](data-retention.md) dados de sua organização determina a distância em que os dados históricos são mantidos.
* **Filtros**: Remova todos os filtros de pesquisa do relatório.

## Os dados não existem

Se não houver segmentos, a métrica será Ocorrências, o intervalo de datas será o mês atual e não haverá filtros de pesquisa, verifique o seguinte:

* **Verifique o conjunto** de relatórios: Verifique se você está em um conjunto de relatórios que contém dados. Muitas organizações têm conjuntos de relatórios novos, de teste ou de desenvolvimento que normalmente não contêm muitos dados.
* **Latência**: Se estiver visualizando dados recentes, os dados podem estar atrasados. Consulte [Latência](latency.md) para obter mais informações.
* **Validar coleta** de dados: Navegue até a propriedade da Web que seu conjunto de relatórios deve rastrear e abra o depurador de [Adobe](https://docs.adobe.com/content/help/pt-BR/debugger/using/experience-cloud-debugger.html). Certifique-se de que uma solicitação de imagem do Analytics esteja presente ao carregar uma página. Se você vir uma solicitação de imagem, verifique se ela usa a ID correta do conjunto de relatórios, se inclui um [currencyCode](/help/implement/vars/config-vars/currencycode.md)válido e se o suporte [a](/help/implement/vars/page-vars/timestamp.md) carimbo de data e hora corresponde entre a solicitação de imagem e o conjunto de relatórios.
