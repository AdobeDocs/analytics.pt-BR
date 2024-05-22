---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9821150194e6bc89a5a2dec15a7957aaa177948e
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 41%

---

# Notas de versão atuais do Adobe Analytics (maio de 2024)

**Última atualização**: quarta-feira, 21 de maio de 2024

Essas notas de versão abrangem o período de lançamento de 15 de maio de 2024 a junho. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nova documentação para atualização do Adobe Analytics para o Customer Journey Analytics** | Para organizações que estão atualizando do Adobe Analytics para o Customer Journey Analytics, há várias opções de atualização e várias considerações a serem levadas em conta com base na implementação atual do Adobe Analytics em uma organização e nas metas de longo prazo. Novos recursos de documentação agora estão disponíveis para ajudá-lo a entender melhor:<ul><li>Os vários caminhos de atualização existentes</li><li>Quais caminhos de atualização estão disponíveis com base na implementação Adobe Analytics atual de uma organização</li><li>As vantagens e desvantagens de cada caminho de atualização</li><li>Orientação passo a passo para cada caminho de upgrade</li><li>Considerações para manuseio de dados históricos</li></ul>[Introdução à atualização para o Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Disponível agora |
| **Definir `contextData` campos via XDM** | Os clientes que enviam dados para a Adobe Analytics por meio do Edge Network de experiência podem [definir valores de dados de contexto](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/contextdata) diretamente no XDM ou nas partes &quot;dados&quot; da carga. |  | Disponível agora |
| **API do Relatório em tempo real 2.0 do Analytics** | A nova API 2.0 de relatórios em tempo real no Adobe Analytics melhora a integração do cliente e fornece resultados rápidos de relatórios. Esses resultados podem ser usados de forma programática para trabalhar com relatórios básicos, de tendências e de detalhamento. [Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | | sexta-feira, 30 de maio de 2024 |
| **Mídia de transmissão: envie dados da Web para o Adobe Experience Platform Edge Network com o SDK da Web** | Agora você pode usar o SDK da Web da Adobe Experience Platform para enviar dados da Web de mídia de transmissão para o Edge Network da Adobe Experience Platform. Esse aprimoramento permite criar campanhas mais personalizadas e fornecer conteúdo mais personalizado, resultando em mais dados de rastreamento a serem relatados.<p>Essa alteração fornece um método de coleta unificada para implementações da Web em todas as soluções de plataforma, como Customer Journey Analytics, CDP em tempo real Adobe, Adobe Journey Optimizer e encaminhamento de eventos. Anteriormente, a única maneira de enviar dados da Web de mídia de transmissão para o Edge Network era usando a API do Media Edge. <p>(Link de documentação atualizado a seguir)</p> | | 31 de maio de 2024 |
| **Aumento nos limites padrão de tráfego baixo** | Em **meados de abril de 2024**, a Adobe começará a aumentar os limites padrão de tráfego baixo para conjuntos de relatórios da seguinte maneira: ![limites de tráfego baixo](assets/thresholds.png) isso afetará somente as variáveis que estão definidas abaixo dos novos limites. Essas alterações serão feitas de forma incremental e esperamos que o trabalho seja concluído até o **fim de maio**. À medida que esses aumentos forem implementados, você poderá notar alterações nas variáveis de alta cardinalidade:<ul><li>Mais valores de dimensão podem estar disponíveis para relatórios.</li><li>Segmentos e métricas calculadas podem incluir mais dados.</li><li>Os conjuntos de relatórios virtuais baseados em segmentos podem incluir mais dados.</li><li>As exportações de classificação podem incluir mais dados.</li></ul> | Meados de abril de 2024 | 31 de maio de 2024 |
| **Configurações do administrador para controlar as contas e os locais usados para exportação e importação** | Uma nova guia &quot;Configurações do administrador&quot; no Gerenciador de locais fornece aos administradores controle sobre se os usuários podem criar e editar contas e locais. Essas configurações se aplicam quando os usuários configuram contas de importação e exportação em nuvem e configuram locais de importação e exportação em nuvem. <p>Os administradores também podem limitar os tipos de contas (Google Cloud Platform, Azure RBAC, Amazon S3 e assim por diante) que os usuários podem criar e usar.</p><p>Anteriormente, qualquer usuário podia criar, editar e usar contas e locais para qualquer tipo de conta.</p><p>(Link de documentação atualizado a seguir)</p> | Junho de 2024 | Junho de 2024 |
| **Compartilhar contas e locais usados para exportação e importação** | Agora os usuários podem disponibilizar as contas e os locais que criam para todos os usuários em sua organização. Somente os proprietários de contas e locais e os administradores do sistema podem editar e excluir contas e locais.<p>Anteriormente, contas e locais podiam ser usados somente pelo usuário que os criava.</p><p>Essas configurações estão disponíveis quando os usuários configuram contas de importação e exportação na nuvem e configuram locais de importação e exportação na nuvem. </p> <p>(Link de documentação atualizado a seguir)</p> | Junho de 2024 | Junho de 2024 |
| **Activity Map para usar menos chamadas de servidor para o SDK da Web** | Atualmente, os eventos de link do Activity Map são contados como eventos próprios e resultam em cobranças adicionais. Esse aprimoramento seleciona alguns eventos de link e os reúne na próxima ocorrência, de modo semelhante a como os eventos são tratados pelo AppMeasurement. <p>(Link de documentação atualizado a seguir)</p> | Beta começa em 31 de maio de 2024 | A ser definido |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção dos seguintes problemas de Classificações: AN-343186; AN-344711; AN-344856; AN-345094; AN-345179; AN-346265; AN-345288; AN-346339; AN-346560; AN-3434 7572; AN-347681; AN-347768; AN-348024
* Correção dos seguintes problemas de Data Warehouse: AN-346789; AN-347031; AN-347568;
* Correção dos seguintes problemas de Feeds de dados: AN-343616; AN-345831; AN-345988; AN-346124; AN-346232; AN-346972; AN-347680; AN-347755; AN-347954
* Correção do seguinte problema de Fontes de dados: AN-347890;
* Correção dos seguintes problemas do Analysis Workspace: AN-321503; AN-343103; AN-343471; AN-345171; AN-345223; AN-345912; AN-346026; AN-346330; AN-346839; AN-347 679
* Correção do seguinte problema do A4T: AN-345118;

### Outras correções do Analytics

AN-327749; AN-332949; AN-342881; AN-343171; AN-343708; AN-344034; AN-345559; AN-346023; AN-346230; AN-34630; AN-346469; AN-346606; AN-346750; AN-346973; AN-347026; AN-347110; AN-347439;

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Atualizações da região ISO** | sábado, 10 de maio de 2024 | A Adobe realizará as atualizações de 2024 da região ISO em sábado, 7 de junho de 2024. Você poderá ver pequenas atualizações de informações geográficas (região) após esta versão. |
| **Prazo de 13 meses para a expiração do`cust_visids`** salvo | 20 de março de 2024 | Uma versão futura do mecanismo de processamento de ocorrências do Analytics, programada para abril ou maio, começará a impor um prazo de 13 meses para a expiração do `cust_visids` salvo. Se o conjunto de relatórios estiver com a opção “Habilitar identificação de visitantes” ativada, esta configuração será usada para encontrar o `cust_visid` para um `visid_high/visid_low value` que não contenha `cust_visid` na ocorrência. Atualmente, não há um prazo de expiração para o mapeamento de um `cust_visid` para um `visid_high/visid_low`. Com esta versão, se 13 meses ou mais tiverem passado desde `visid_high/visid_low` teve um `cust_visid` em uma ocorrência, o mapeamento expira. |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.26.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2023](/help/release-notes/2023.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
