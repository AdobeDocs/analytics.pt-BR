---
description: Exibe o tráfego da página da Web e classifica as visualizações da página em tempo real. Oferece dados acionáveis para basear suas decisões comerciais.
title: Visão geral do relatório em tempo real
topic-fix: Reports
feature: Real-time
exl-id: 056235bc-42ea-4118-aa54-bc7666044fe3
source-git-commit: 20093692327f555bfd78d99b2ec03146a5f2b181
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 89%

---

# Visão geral do relatório em tempo real

O relatório em tempo real exibe o tráfego da página da Web e classifica as visualizações da página em tempo real. Oferece dados acionáveis para basear suas decisões comerciais.

>[!NOTE]
>
>O relatório Tempo real não requer implementações ou marcações adicionais. Ele impulsiona sua implantação já existente do Adobe Analytics. Para configurar relatórios em tempo real, consulte [Configuração de relatórios em tempo real](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md).

## Acessar relatórios em tempo real

1. No Adobe Analytics, selecione a guia [!UICONTROL **Espaço de trabalho**].

1. No lado esquerdo da página, em **[!UICONTROL Modelos]**, selecione [!UICONTROL **Modelos do Adobe**].

1. Selecione [!UICONTROL **Envolvimento**] > **[!UICONTROL Tempo real]**.

## Entender os relatórios em tempo real

O Tempo real responde as seguintes questões: Quais são os assuntos mais falados do meu site, e por quê? Permite que você, enquanto profissional de marketing, possa responder de maneira rápida e gerenciar ativamente o desempenho de seu conteúdo de marketing e de suas campanhas. Os dados em tempo real relatados possui menos de dois minutos de latência e é atualizado automaticamente em um intervalo de um em um minuto.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/report-realtime.png)

O painel inclui as métricas de alta frequência do Adobe Analytics e as análises do site da Web para reportar visualmente o tráfego e as visualizações de notícias dinâmicas e sites de varejo na página. A análise em tempo real entende as tendências em seus dados de minuto a minuto, segundos após o início da coleta. Coleciona e envia dados para uma interface que é atualizada automaticamente, através da correlação em tempo real, do rastreamento de conteúdo e da conversão.

Dois dos cenários de utilização mais recorrentes incluem editores que gostariam de promover/rebaixar histórias para alterações de atividade do usuário, e profissionais de marketing que gostariam de rastrear o lançamento de uma nova linha de produto.

Como Administrador, você pode

* Criar até três relatórios em tempo real para cada conjunto de relatórios, utilizando dimensões e métricas existentes. Utiliza as dimensões secundárias para correlacionar com (ou separar) a dimensão primária.
* Adicionar três dimensões (ou classificações) por relatório (uma primária e duas secundárias), além de uma métrica de site inteiro.
* Utiliza qualquer evento personalizado, evento de carrinho de compras ou instância.
* Exibir até duas horas de dados do histórico em tempo real e modificar essa configuração:

   * Últimos 15 minutos: granularidade de um minuto
   * Últimos 30 minutos: granularidade de um minuto
   * Última hora: granularidade de dois minutos
   * Últimas duas horas: granularidade de quatro minutos

* Por exemplo, compare os valores da semana anterior aos do último ano (bem como o total do dia).

Lembre-se que as eVars (métricas de conversão) não são suportadas, uma vez que não há conceito de persistência. Você pode selecionar métricas de conversão, mas elas funcionarão apenas se definidas na mesma página que a(s) dimensão(ões). Para obter mais informações, consulte a mensagem de aviso capturada em [Configurando Relatórios em Tempo Real](/help/components/c-real-time-reporting/t-realtime-admin.md).

A configuração e a exibição dos relatórios em tempo real está restrita aos Administradores ou qualquer outro usuário que faça parte dos grupos &quot;Todos os acessos de relatório&quot; e &quot;Relatórios avançados&quot; . Porém, o Tempo real não respeita as permissões. Por exemplo, se você não possui os direitos para visualizar a receita, você não poderá visualizar um relatório em tempo real que inclui dados da mesma.

## Latência dos dados como resultado da configuração A4T {#latency-a4t}

Depois que a integração A4T for habilitada no Adobe [!DNL Target], haverá de 5 a 10 minutos adicionais de latência no Adobe Analytics. O aumento dessa latência permite que os dados do Analytics e do [!DNL Target] sejam armazenados na mesma ocorrência, permitindo dividir os testes por página e seção do site.

Este aumento é refletido em todos os serviços e ferramentas do Adobe Analytics, incluindo a transmissão ao vivo e os relatórios em tempo real e aplicam-se nas seguintes situações:

* Para transmissão ao vivo, relatórios em tempo real e solicitações de API, e dados atuais para variáveis de tráfego, somente as ocorrências com uma ID de dados complementar são atrasadas.
* Para os dados atuais sobre as métricas de conversão, dados finalizados e feeds de dados, todos os hits são atrasados de 5 a 7 minutos.

Esteja ciente de que o aumento da latência começa após a implementação do Identity Service, mesmo que essa integração não tenha sido integralmente implementada.
