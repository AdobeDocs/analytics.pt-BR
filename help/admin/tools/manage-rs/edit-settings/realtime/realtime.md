---
description: Exibe o tráfego da página da Web e classifica as exibições dela em tempo real. Oferece dados acionáveis para basear suas decisões comerciais.
title: Relatórios em Tempo real
feature: Real-time
exl-id: 267246ba-617f-4284-aaad-d0ace0f6a8cf
TQID: https://experienceleague.adobe.com/SqFAddRYrXCrQyB-LjgsaLWoEQXMLc7hkdgcAcgUdsM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 611
ht-degree: 11%

---

# Relatórios em Tempo real

Exibe o tráfego da página da Web e classifica as exibições dela em tempo real. Oferece dados acionáveis para basear suas decisões comerciais.

>[!NOTE]
>
>O relatório Tempo real não requer implementações ou marcações adicionais. Ele impulsiona sua implantação já existente do Adobe Analytics. Para configurar relatórios em tempo real, consulte [Configuração de relatórios em tempo real](/help/admin/tools/manage-rs/edit-settings/realtime/t-realtime-admin.md).

Para exibir o relatório em tempo real, navegue até:

**[!UICONTROL Workspace]** > **[!UICONTROL Relatórios]** > **[!UICONTROL Envolvimento]** > **[!UICONTROL Tempo Real]**.

O Tempo real responde às seguintes perguntas: Quais são as tendências do meu site e por quê? Ele permite que você, como profissional de marketing, responda rapidamente e gerencie ativamente o desempenho do seu conteúdo e das suas campanhas de marketing. Os dados em tempo real relatados são menos de dois minutos latentes e são atualizados automaticamente a cada minuto.

![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report-realtime.png)

O painel inclui métricas de alta frequência do Adobe Analytics e análises do site para relatar visualmente o tráfego e as visualizações de notícias dinâmicas e sites de varejo na página. O Tempo real entende as tendências em seus dados de minuto a minuto, em segundos de coleta. Ele coleta e transmite dados em uma interface de atualização automática, usando a correlação e o rastreamento de conteúdo em tempo real e alguma conversão.

Dois dos cenários de uso mais comuns incluem editores que desejam promover/rebaixar histórias à medida que as atividades do usuário mudam, e profissionais de marketing que desejam acompanhar o lançamento de uma nova linha de produtos.

Como Administrador, você pode

* Crie até três relatórios em tempo real por conjunto de relatórios, usando dimensões, classificações e métricas existentes. Use as dimensões secundárias para correlacionar-se com (ou dividir) a principal.
* Adicione três dimensões (ou classificações) por relatório (uma principal e duas secundárias), além de uma métrica em todo o site.
* Use qualquer evento personalizado, evento de carrinho de compras ou instância.
* Visualize até 2 horas de dados históricos em tempo real e modifique essa configuração:

   * Últimos 15 minutos: granularidade de 1 minuto
   * Últimos 30 minutos: granularidade de 1 minuto
   * Última hora: granularidade de 2 minutos
   * Últimas 2 horas: granularidade de 4 minutos

* Compare, por exemplo, os valores da semana passada com os valores do ano passado (bem como com o total de hoje).

Lembre-se de que eVars (métricas de conversão) não são compatíveis, pois não há conceito de persistência. Embora seja possível selecionar métricas de conversão, elas só funcionarão se estiverem definidas na mesma página que as dimensões. Para obter mais informações, consulte a mensagem de aviso capturada em [Configurando Relatórios em Tempo Real](/help/admin/tools/manage-rs/edit-settings/realtime/t-realtime-admin.md).

A configuração e a visualização de relatórios em tempo real são restritas a administradores ou qualquer usuário nos grupos de permissão &quot;Acesso a todos os relatórios&quot; e &quot;Relatórios avançados&quot;. No entanto, o Tempo real respeita as permissões. Se, por exemplo, você não tiver direitos para ver a receita, não será possível visualizar um relatório em tempo real que inclua dados da receita.

## Latência dos dados como resultado da configuração A4T {#latency}

Depois que a integração A4T for habilitada no Adobe Target, haverá de 5 a 10 minutos adicionais de latência no Adobe Analytics. O aumento dessa latência permite que os dados do Analytics e do Target sejam armazenados na mesma ocorrência, permitindo dividir os testes por página e seção do site.

Esse aumento se reflete em todos os serviços e ferramentas da Adobe Analytics, incluindo os relatórios em tempo real e em transmissão ao vivo, e se aplica aos seguintes cenários:

* Para transmissão ao vivo, relatórios em tempo real e solicitações de API e dados atuais para variáveis de tráfego, somente as ocorrências com uma ID de dados complementar são atrasadas.
* Para dados atuais sobre métricas de conversão, dados finalizados e feeds de dados, todas as ocorrências são atrasadas em mais 5 a 7 minutos.

Esteja ciente de que o aumento da latência começa após a implementação do Identity Service, mesmo que essa integração não tenha sido integralmente implementada.
