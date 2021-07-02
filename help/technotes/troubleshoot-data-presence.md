---
title: Solução de problemas de presença de dados
description: Saiba quais etapas seguir quando não é possível ver os dados em relatórios.
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '332'
ht-degree: 100%

---


# Solução de problemas de presença de dados

No Analysis Workspace, algumas configurações de projeto retornam zero linha. No Reports &amp; Analytics, a exibição de determinados relatórios retorna a seguinte mensagem:

**&quot;Não há dados para os critérios selecionados.&quot;**

Use as etapas a seguir para determinar por que um relatório não mostra os dados.

## Os dados existem, mas são filtrados

O conjunto de relatórios contém dados, mas eles são filtrados pelos componentes específicos usados no relatório.

* **Segmentos**: os segmentos podem facilmente impedir todos os dados de serem mostrados em um relatório. Verifique todas as definições de segmento e remova todos os segmentos para ver se um deles está impedindo que os dados sejam mostrados.
* **Métricas**: verifique se as métricas corretas foram usadas. Altere a métrica para [Ocorrências](/help/components/metrics/occurrences.md) para garantir que a métrica não origine um relatório sem dados.
* **Intervalos de datas**: intervalos de datas muito distantes no passado ou em qualquer momento no futuro não retornam dados. A [política de retenção de dados](data-retention.md) de sua organização determina até que ponto os dados antigos são mantidos.
* **Filtros**: remova todos os filtros de pesquisa do relatório.

## Os dados não existem

Se não houver segmentos, a métrica for Ocorrências, o intervalo de datas for o mês atual e não houver filtros de pesquisa, verifique o seguinte:

* **Verificar o conjunto de relatórios**: certifique-se de que está em um conjunto de relatórios que contém dados. Muitas organizações têm conjuntos de relatórios novos, de teste ou de desenvolvimento que normalmente não contêm muitos dados.
* **Latência**: se você estiver exibindo dados recentes, talvez os dados estejam atrasados. Consulte [Latência](latency.md) para obter mais informações.
* **Validar a coleção de dados**: navegue até a propriedade da web que o conjunto de relatórios deve rastrear e abra o [Adobe debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR). Verifique se uma solicitação de imagem do Analytics está presente ao carregar uma página. Se você vir uma solicitação de imagem, verifique se ela usa a ID de conjunto de relatórios correta, se inclui um [currencyCode](/help/implement/vars/config-vars/currencycode.md) válido e se o [suporte de timestamp](/help/implement/vars/page-vars/timestamp.md) corresponde à solicitação de imagem e ao conjunto de relatórios.
