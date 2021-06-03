---
title: Solução de problemas de presença de dados
description: Saiba quais etapas você pode seguir quando não visualiza dados em relatórios.
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 4%

---


# Solução de problemas de presença de dados

No Analysis Workspace, algumas configurações de projeto retornam zero linhas. Em Reports &amp; Analytics, visualizar determinados relatórios retorna a seguinte mensagem:

**&quot;Não há dados para os critérios selecionados.&quot;**

Use as etapas a seguir para determinar por que um relatório não mostra dados.

## Os dados existem, mas são filtrados

Seu conjunto de relatórios contém dados, mas os componentes específicos usados no relatório filtram todos os dados.

* **Segmentos**: Os segmentos podem facilmente impedir que todos os dados apareçam em um relatório. Verifique todas as definições de segmento e remova todos os segmentos para ver se um segmento está fazendo com que seus dados não apareçam.
* **Métricas**: Verifique se as métricas corretas foram usadas. Altere a métrica para [Ocorrências](/help/components/metrics/occurrences.md) para garantir que a métrica não seja o contribuidor de um relatório sem dados.
* **Intervalos** de datas: Intervalos de datas muito distantes no passado ou em qualquer momento no futuro não retornam dados. A [política de retenção de dados](data-retention.md) de sua organização determina o tempo limite em que os dados retrospectivos são mantidos.
* **Filtros**: Remova todos os filtros de pesquisa do relatório.

## Os dados não existem

Se não houver segmentos, a métrica será Ocorrências, o intervalo de datas será o mês atual e não haverá filtros de pesquisa, verifique o seguinte:

* **Verifique o conjunto** de relatórios: Verifique se você está em um conjunto de relatórios que contém dados. Muitas organizações têm conjuntos de relatórios novos, de teste ou de desenvolvimento que normalmente não contêm muitos dados.
* **Latência**: Ao visualizar dados recentes, os dados podem estar atrasados. Consulte [Latência](latency.md) para obter mais informações.
* **Validar a coleta** de dados: Navegue até a propriedade da Web que seu conjunto de relatórios deve rastrear e abra o  [Adobe Debugger](https://docs.adobe.com/content/help/pt-BR/experience-cloud/user-guides/home.translate.html). Certifique-se de que uma solicitação de imagem do Analytics esteja presente ao carregar uma página. Se você vir uma solicitação de imagem, verifique se ela usa a ID de conjunto de relatórios correta, se inclui um [currencyCode](/help/implement/vars/config-vars/currencycode.md) válido e se [suporte ao carimbo de data e hora](/help/implement/vars/page-vars/timestamp.md) corresponde entre a solicitação de imagem e o conjunto de relatórios.
