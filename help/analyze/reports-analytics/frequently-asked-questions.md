---
description: Fornecem sugestões para a solução de problemas e respostas a algumas das perguntas mais frequentes sobre o Analytics.
keywords: Solução de problemas do Analytics
seo-description: Fornecem sugestões para a solução de problemas e respostas a algumas das perguntas mais frequentes sobre o Analytics.
seo-title: Perguntas frequentes
title: Perguntas frequentes
uuid: 285 b 0 ea 4-aa 07-4 d 39-a 74 f -37 b 1 d 02 d 19 f 1
translation-type: tm+mt
source-git-commit: fd1e2f1789ed9c8c31c89f0e7b6b7b2dd3ee114d

---


# Perguntas frequentes

Fornece sugestões e solução de problemas para algumas das perguntas mais frequentes do Analytics sobre Relatórios e análises. For frequently asked implementation questions, see the [FAQ](../../implement/faq.md) in the Implement user guide.

**Minha conta foi bloqueada; como faço para desbloqueá-la?**

Para reativar uma conta, entre em contato com um administrador em sua organização. See also [Troubleshoot login issues with Adobe Analytics](../../technotes/troubleshoot-login.md) in the Technotes user guide.

**Por que vejo um relatório em branco mesmo que eu saiba que os dados são coletados?**

Há várias coisas a serem verificadas para resolver os dados do relatório:

* Verifique as métricas usadas: Alguns relatórios assumem como padrão a Receita no Relatórios e análises. Verifique se a métrica exibida é relevante para o relatório.
* Verifique o intervalo de datas: Os intervalos de datas, especialmente aqueles além da política de retenção de dados da organização, não podem retornar dados. Verifique se o intervalo de datas está definido corretamente.
* Verificar filtros internos de URL: Alguns relatórios de fontes de tráfego não funcionam até que você defina corretamente os filtros internos de URL.

**Por que alguns relatórios estão ausentes no menu de navegação?**

Os relatórios ausentes com mais frequência são originados de permissões restritas ou personalização de menu. Entre em contato com um administrador de produto na organização para garantir que você tenha acesso a todas as dimensões e métricas necessárias e que a estrutura de menu de um conjunto de relatórios não tenha sido personalizada.

**Por que alguns valores longos estão cortados?**

Quase todas as variáveis no Adobe Analytics têm um limite de caracteres. O Nome da página tem um limite de 100 caracteres, enquanto as variáveis de conversão personalizadas (evars) têm um limite de 255 caracteres. A Adobe recomenda garantir que os valores enviados para a Adobe sejam concisos para evitar truncamento.

**Por que vejo um atraso importante no relatório?**

Os relatórios em tempo real permitem que algumas métricas de tráfego fiquem disponíveis em minutos, ao passo que a conversão e outros dados com processamento intensivo geralmente ficam disponíveis dentro de 30a 90 minutos. Embora a plataforma da Experience Cloud seja avançada, há algumas situações que podem resultar em atrasos de relatórios. Esse atraso é conhecido como latência. See [Latency](../../technotes/latency.md) in the Technotes user guide for more information.

**Por que não consigo ver a versão do dispositivo em iphones?**

Os dispositivos Apple relatam sua versão do firmware na sequência do agente do usuário, e não na versão do dispositivo. É difícil determinar a versão do dispositivo iphone usando as informações disponíveis para o Adobe Analytics. See [Comparing iPhone device versions](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) in the Analytics KB for more information.

**Por que os totais na parte inferior do meu relatório não correspondem quando eu somo os valores?**

Geralmente, os valores de dimensão podem ser aplicados em vários lugares; por exemplo, visitas que abrangem meia-noite ou vários produtos pertencentes a um único pedido. O valor da dimensão é relatado em todos os itens de linha aplicáveis, mas é desduplicado no total do relatório. See [Compare sum of line items to report total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) in the Analytics KB for more information.

**Como posso excluir dados de um endereço IP específico no conjunto de relatórios?**

É possível eliminar dados de atividades internas do site, como testes do site e uso pelos funcionários, de seus relatórios de Esse recurso permite que você e seus colegas visitem seu site sem distorcer os dados de tráfego. See [Exclude by IP Address](../../admin/admin/exclude-ip.md) in the Admin user guide for more information.

**É possível excluir um conjunto de relatórios?**

Não é possível excluir um conjunto de relatórios. No entanto, um conjunto de relatórios pode ficar oculto em todas as exibições do Adobe Analytics. Observe que as chamadas do servidor enviadas para um conjunto de relatórios oculto ainda contam para o limite mensal de contrato. See [Hide report suites](../../admin/company/c-hide-report-suites.md) in the Admin user guide for more information.

**Ao usar a segmentação, qual contêiner devo usar? Page view, visit, or visitor?**

O contêiner de segmento usado é de acordo com a amplitude de uma captura de dados. Os contêineres de exibição de página apenas resultam em ocorrências que correspondem aos critérios do segmento, úteis para filtrar partes irrelevantes das visitas. Os contêineres de visita trazem todas as ocorrências de uma visita em que um ou mais hits correspondiam aos critérios do segmento, úteis para examinar sessões em geral. Os contêineres de Visitante incluem todas as visitas nas quais uma ocorrência correspondeu aos critérios do segmento, útil para analisar pessoas. É sua escolha como analista para determinar qual contêiner de segmento é melhor para usar. See [Segmentation overview](../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

**Por que meu segmento não está sendo exibido no Data Warehouse?**

Devido à arquitetura de processamento exclusiva do Data Warehouse, a plataforma não é otimizada para lidar com alguns tipos de dados, como definição de caminho. See [Data Warehouse segment compatibility](../../components/c-segmentation/seg-reference/seg-compatibility.md) in the Components user guide for more information.
