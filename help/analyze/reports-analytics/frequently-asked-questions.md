---
description: Fornecem sugestões para a solução de problemas e respostas a algumas das perguntas mais frequentes sobre o Analytics.
keywords: Troubleshooting Analytics
title: Perguntas frequentes
uuid: 285b0ea4-aa07-4d39-a74f-37b1d02d19f1
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Perguntas frequentes

Fornecem sugestões para a solução de problemas e respostas a algumas das perguntas mais frequentes sobre o Analytics para Reports &amp; Analytics. Para perguntas frequentes sobre implementação, consulte as [Perguntas frequentes](/help/implement/faq.md) no guia do usuário de Implementação.

**Minha conta foi bloqueada, como posso desbloqueá-la?**

Para reativar uma conta, entre em contato com um administrador em sua organização. Consulte também [Solução de problemas de logon com o Adobe Analytics](/help/technotes/troubleshoot-login.md) no guia do usuário de Technotes.

**Por que vejo um relatório em branco mesmo sabendo que os dados são coletados?**

Há vários itens a serem verificados para solucionar problemas de dados do relatório:

* Verifique as métricas usadas: alguns relatórios são padronizados como Receita no Reports &amp; Analytics. Verifique se a métrica que você está visualizando é relevante para o relatório.
* Verificar o intervalo de datas: os intervalos de datas, especialmente os que estão além da política de retenção de dados da organização, não podem retornar dados. Verifique se o intervalo de datas está definido corretamente.
* Verificar filtros internos de URL: alguns relatórios de fontes de tráfego não funcionam até que você defina corretamente os filtros internos de URL.

**Por que alguns relatórios estão ausentes no menu de navegação?**

Todos os relatórios ausentes em um menu normalmente são provenientes de permissões restritas ou personalização de menu. Entre em contato com um administrador de produto em sua organização para garantir que você tenha acesso a todas as dimensões e métricas necessárias e que a estrutura de menu de um conjunto de relatórios não tenha sido personalizada.

**Por que alguns valores extensos estão cortados?**

Quase todas as variáveis no Adobe Analytics têm um limite de caracteres. O Nome da página tem um limite de 100 caracteres, enquanto as variáveis de conversão personalizadas (eVars) têm um limite de 255 caracteres. A Adobe recomenda garantir que os valores enviados à Adobe sejam concisos para evitar o truncamento.

**Por que vejo um atraso significativo nos relatórios?**

Os Relatórios em tempo real possibilitam que algumas métricas de tráfego sejam disponibilizadas em minutos, ao mesmo tempo em que conversão e outros dados com processamento intensivo geralmente são disponibilizados após 30-90 minutos. Embora a plataforma da Experience Cloud seja avançada, há algumas situações que podem resultar em atrasos de relatórios. Esse atraso é conhecido como latência. Consulte [Latência](/help/technotes/latency.md) no guia do usuário de Technotes para obter mais informações.

**Por que não posso ver a versão do dispositivo em iPhones?**

Os dispositivos da Apple relatam a versão do firmware na sequência de agente do usuário, e não a versão do dispositivo. É difícil determinar a versão do dispositivo iPhone usando as informações disponíveis para o Adobe Analytics. Consulte [Comparação das versões do dispositivo iPhone](https://helpx.adobe.com/br/analytics/kb/comparing-iphone-device-versions.html) na Base de conhecimento do Analytics para obter mais informações.

**Por que os totais na parte inferior do meu relatório não correspondem quando eu somo os valores?**

Muitas vezes, os valores de dimensão podem ser aplicados em vários lugares, por exemplo, visitas que abrangem meia-noite ou vários produtos pertencentes a um único pedido. O valor da dimensão é reportado em todos os itens de linha aplicáveis, mas é desduplicado no total do relatório. Consulte [Comparar a soma dos itens de linha ao total do relatório](https://helpx.adobe.com/br/analytics/kb/sum-line-items-different-from-total.html) na Base de conhecimento do Analytics para obter mais informações.

**Como posso excluir dados de um endereço IP específico no conjunto de relatórios?**

É possível eliminar dados de atividades internas do site, como testes do site e uso pelos funcionários, de seus relatórios de Esse recurso permite que você e seus colegas visitem seu site sem distorcer os dados de tráfego. Consulte [Excluir por endereço IP](/help/admin/admin/exclude-ip.md) no guia do usuário de Administração para obter mais informações.

**É possível excluir um conjunto de relatórios?**

Não é possível excluir um conjunto de relatórios. No entanto, um conjunto de relatórios pode ser ocultado em todas as exibições no Adobe Analytics. Observe que as chamadas do servidor enviadas para um conjunto de relatórios oculto ainda contam para o limite mensal de contratos. Consulte [Ocultar conjuntos de relatórios](/help/admin/company/c-hide-report-suites.md) no guia do usuário de Administração para obter mais informações.

**Ao usar a segmentação, qual contêiner devo usar? Exibição de página, visita ou visitante?**

O contêiner de segmento usado depende da amplitude com que você deseja capturar os dados. Os contêineres de exibição de página trazem somente ocorrências que correspondem aos critérios de segmento, úteis para filtrar as partes irrelevantes das visitas. Os contêineres de visita trazem todas as ocorrências de uma visita em que uma ou mais ocorrências corresponderam aos critérios de segmento, úteis para analisar as sessões em geral. Os contêineres de visitante trazem todas as visitas em que uma ocorrência correspondeu aos critérios do segmento, úteis para analisar as pessoas. Como analista, você determina qual contêiner de segmento é a melhor escolha. Consulte [Visão geral de segmentação](/help/components/c-segmentation/seg-overview.md) no guia do usuário de Componentes para obter mais informações.

**Por que meu segmento não está aparecendo no Data Warehouse?**

Devido à arquitetura de processamento exclusiva do Data Warehouse, a plataforma não é otimizada para lidar com alguns tipos de dados, como definição de caminho. Consulte [Compatibilidade de segmentos do Data Warehouse](/help/components/c-segmentation/seg-reference/seg-compatibility.md) no guia do usuário de Componentes para obter mais informações.
