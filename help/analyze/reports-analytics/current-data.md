---
description: A opção Incluir dados atuais do Reports & Analytics permite exibir os dados mais recentes do Analytics, geralmente antes que sejam totalmente processados e finalizados. Os dados atuais exibem a maioria das métricas comuns em minutos, fornecendo dados acionáveis para proporcionar uma tomada de decisão rápida.
subtopic: Current Data
title: Dados atuais
topic: Reports
uuid: 601d3695-be13-4b7f-9df0-de01c8bd64ee
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Dados atuais

A opção Incluir dados atuais do Reports &amp; Analytics permite exibir os dados mais recentes do Analytics, geralmente antes que sejam totalmente processados e finalizados. Os dados atuais exibem a maioria das métricas comuns em minutos, fornecendo dados acionáveis para proporcionar uma tomada de decisão rápida.

É visível como uma opção que faz parte das configurações de um relatório:

![Captura de tela Dados atuais](assets/current_data.png)

Os dados atuais são ativados por padrão em todos os relatórios que os suportam. Se você preferir exibir todas as métricas depois que os dados forem totalmente processados, há várias opções:

* Use a Analysis Workspace, que utiliza dados totalmente processados.
* Clique em &quot;Não&quot; na configuração atual do relatório de dados para usar apenas dados totalmente processados.
* Remova o item de permissão &quot;Dados atuais&quot; de um perfil de produto no Admin Console para impedir que usuários não administradores vejam essa opção. Consulte [itens de permissão das Ferramentas do Analytics](/help/admin/admin-console/permissions/analytics-tools.md) no guia do usuário de Administração para obter mais informações.

Devido à priorização da disponibilidade de dados, os dados atuais não podem ser usados no momento com segmentos, classificações, detalhamentos, definições de caminho e algumas métricas. Se um desses recursos for usado, os dados atuais serão forçados a &quot;Não&quot; no relatório e um aviso amarelo será mostrado explicando por que os dados atuais não estão disponíveis.

![Aviso de dados atuais](assets/current_data_notice.png)

## Latência dos dados atuais comuns

As métricas aparecem em um dos seguintes três intervalos de tempo. Clique no ícone de relógio ao lado da alternância Incluir dados atuais para ver o novo valor de latência atual de cada métrica em um relatório.

| Intervalo de Tempo | Métricas |
| --- | --- |
| Menos de 10 minutos | Instâncias e exibições de página nas variáveis de tráfego |
| Entre 10 e 35 minutos | Eventos de conversão, Instâncias e exibições de página nas variáveis de conversão |
| Entre 45 e 120 minutos | Todos os outros dados, como visitas, visitantes únicos e participação |

Como alguns dados exibidos na visualização de dados atuais não foram completamente processados, você pode ver uma diferença entre valores relatados na visualização de dados atuais e na visualização finalizada. Nos relatórios de tendências, a diferença entre dados normalmente fica dentro de 1%.

## Métricas calculadas

Como é possível criar métricas calculadas por meio de métricas com latência diferente, alguns valores recentes talvez sejam calculados usando dados incompletos na visualização de dados atuais.

Por exemplo, você cria a métrica calculada &quot;Exibições de página por visita&quot; usando a fórmula `Page Views divided by Visits`. As Exibições de página normalmente são exibidas dentro de 10 minutos, e as Visitas normalmente são exibidas dentro de 2 horas, as métricas calculadas dentro dessa janela de latência são calculadas usando métricas incompletas. Se você postar uma nova página que obtém 4000 ocorrências a partir de 4000 visitas diferentes em um intervalo de tempo de 2 horas, a diferença de latência entre essas métricas pode causar cálculos incompletos.

Essa diferença de dados é mais visível ao relatar novos valores ou usar intervalos de tempo curtos. Quando um relatório usa intervalos de dada mais longos, as diferenças de latência que ocorrem nas últimas horas do relatório provavelmente não terão um impacto notório nas métricas calculadas.

Se você tiver calculado métricas que podem ser afetadas por essas diferenças, desative os dados atuais ou use métricas com a mesma janela de latência esperada.

## Relatórios baixados

Quando você faz o download de um relatório com a visualização de dados atuais ativada, o relatório é colocado na fila, gerado e retornado para o navegador. Se os dados forem coletados durante a geração do relatório, esses dados serão exibidos no relatório. Essa janela de tempo pode fazer com que o relatório baixado tenha um pouco mais de dados.
