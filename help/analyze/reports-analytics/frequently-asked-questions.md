---
description: Fornecem sugestões para a solução de problemas e respostas a algumas das perguntas mais frequentes sobre o Analytics.
keywords: Solução de problemas do Analytics
seo-description: Fornecem sugestões para a solução de problemas e respostas a algumas das perguntas mais frequentes sobre o Analytics.
seo-title: Perguntas frequentes
title: Perguntas frequentes
uuid: 285b0ea4-aa07-4d39-a74f-37b1d02d19f1
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Perguntas frequentes

Fornece respostas e sugestões de solução de problemas para algumas das perguntas mais frequentes do Analytics para Relatórios e análises. Para perguntas frequentes sobre implementação, consulte as [Perguntas frequentes](/help/implement/faq.md) no guia Implementação do usuário.

**Minha conta foi bloqueada. como desbloqueá-lo?**

Para reativar uma conta, entre em contato com um administrador em sua organização. Consulte também [Solução de problemas de logon com o Adobe Analytics](/help/technotes/troubleshoot-login.md) no guia do usuário do Technotes.

**Por que vejo um relatório em branco mesmo sabendo que os dados são coletados?**

Há vários itens a serem verificados para solucionar problemas de dados do relatório:

* Verifique as métricas usadas: Alguns relatórios assumem como padrão a Receita no Relatórios e análises. Verifique se a métrica que você está visualizando é relevante para o relatório.
* Verifique o intervalo de datas: Os intervalos de datas, especialmente aqueles que estão além da política de retenção de dados de sua organização, não podem retornar dados. Verifique se o intervalo de datas está definido corretamente.
* Verificar filtros internos de URL: Alguns relatórios de fontes de tráfego não funcionam até que você defina corretamente os filtros internos de URL.

**Por que alguns relatórios estão faltando no menu de navegação?**

Todos os relatórios ausentes em um menu normalmente são originários de permissões restritas ou personalização de menu. Entre em contato com um administrador de produto em sua organização para garantir que você tenha acesso a todas as dimensões e métricas necessárias e que a estrutura de menu de um conjunto de relatórios não tenha sido personalizada.

**Por que alguns valores longos estão cortados?**

Quase todas as variáveis no Adobe Analytics têm um limite de caracteres. O Nome da página tem um limite de 100 caracteres, enquanto as variáveis de conversão personalizadas (eVars) têm um limite de 255 caracteres. A Adobe recomenda certificar-se de que os valores enviados para a Adobe sejam concisos para evitar truncamento.

**Por que vejo um grande atraso nos relatórios?**

O relatório em tempo real permite que algumas métricas de tráfego estejam disponíveis dentro de minutos, enquanto a conversão e outros dados de processamento intensivo geralmente estão disponíveis dentro de 30 a 90 minutos. Embora a plataforma da Experience Cloud seja avançada, há algumas situações que podem resultar em atrasos de relatórios. Esse atraso é chamado de latência. Consulte [Latência](/help/technotes/latency.md) no guia do usuário do Technotes para obter mais informações.

**Por que não consigo ver a versão do dispositivo em iPhones?**

Os dispositivos Apple reportam sua versão de firmware na sequência do agente do usuário, não na versão do dispositivo. É difícil determinar a versão do dispositivo iPhone usando as informações disponíveis para o Adobe Analytics. Consulte [Comparar versões](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) de dispositivos iPhone na Base de conhecimento do Analytics para obter mais informações.

**Por que os totais na parte inferior do meu relatório não correspondem quando eu somo os valores?**

Os valores de dimensão podem muitas vezes se aplicar em vários lugares; por exemplo, visitas que abrangem meia-noite ou vários produtos pertencentes a um único pedido. O valor da dimensão é reportado em todos os itens de linha aplicáveis, mas é desduplicado no total do relatório. Consulte [Comparar a soma dos itens de linha ao total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) do relatório na Base de conhecimento do Analytics para obter mais informações.

**Como posso excluir dados de um endereço IP específico em meu conjunto de relatórios?**

É possível eliminar dados de atividades internas do site, como testes do site e uso pelos funcionários, de seus relatórios de Esse recurso permite que você e seus colegas visitem seu site sem distorcer os dados de tráfego. Consulte [Excluir por endereço](/help/admin/admin/exclude-ip.md) IP no guia do usuário administrativo para obter mais informações.

**É possível excluir um conjunto de relatórios?**

Não é possível excluir um conjunto de relatórios. No entanto, um conjunto de relatórios pode ser ocultado de todas as exibições no Adobe Analytics. Observe que as chamadas de servidor enviadas para um conjunto de relatórios oculto ainda contam para o limite mensal do contrato. Consulte [Ocultar conjuntos](/help/admin/company/c-hide-report-suites.md) de relatórios no Guia do usuário administrativo para obter mais informações.

**Ao usar a segmentação, qual contêiner devo usar? Exibição de página, visita ou visitante?**

O contêiner de segmento usado depende da amplitude com que você deseja capturar os dados. Os contêineres de exibição de página trazem somente ocorrências que correspondem aos critérios de segmento, úteis para filtrar partes irrelevantes das visitas. Os contêineres de visita trazem todas as ocorrências de uma visita em que uma ou mais ocorrências corresponderam a critérios de segmento, úteis para analisar sessões em geral. Os contêineres de visitante trazem todas as visitas em que uma ocorrência correspondeu aos critérios do segmento, útil para observar as pessoas. É sua escolha como analista para determinar qual contêiner de segmento é melhor para usar. Consulte Visão geral [da](/help/components/c-segmentation/seg-overview.md) segmentação no guia do usuário Componentes para obter mais informações.

**Por que meu segmento não está aparecendo no Data Warehouse?**

Devido à arquitetura de processamento exclusiva do Data Warehouse, a plataforma não é otimizada para lidar com alguns tipos de dados, como definição de caminho. Consulte Compatibilidade [de segmentos do](/help/components/c-segmentation/seg-reference/seg-compatibility.md) Data Warehouse no guia do usuário Componentes para obter mais informações.
