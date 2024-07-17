---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cb0eab15dac6d679e9f912010045e6be2e47df4a
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 46%

---

# Notas de versão atuais do Adobe Analytics (julho de 2024)

**Última atualização**: quinta-feira, 17 de julho de 2024

Essas notas de versão abrangem o período de lançamento de 17 de julho de 2024 a agosto de 2024. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Melhorias no SDK da Web para rastreamento de link** | Várias melhorias notáveis estão disponíveis na versão mais recente do SDK da Web em relação ao rastreamento de link, que beneficia diretamente o Activity Map. Esses novos recursos estão disponíveis na biblioteca JavaScript do SDK da Web e na extensão de tag do SDK da Web.<ul><li>Agrupamento de eventos: quando um visitante clica em um link interno, é possível optar por agrupar dados do evento na próxima página, em vez de acionar uma chamada de evento separada para o rastreamento de link. Essa melhoria reduz o número de eventos que o SDK da Web usa em relação ao limite contratual.</li><li>Propriedades de clique de filtro: um novo retorno de chamada que substitui `OnBeforeLinkClickSend`. Você pode usar essa chamada de retorno para filtrar ou ofuscar dados relacionados ao link antes de enviá-lo para o Adobe.</li></ul><p>Consulte [clickCollection](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollection) no guia do usuário do SDK da Web para obter mais informações.</p> | O Open Beta foi iniciado em 10 de julho de 2024 | A ser definido |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção de um problema que impedia os usuários de fazer logon na interface do usuário do Analytics (AN-352953)
* Correção de um problema que impedia os usuários de fazer logon no aplicativo móvel do Analytics (AN-352463)
* Correção de um problema que impedia o download do projeto como um PDF (AN-352680)
* Correção de um problema em que as classificações não eram importadas. (AN-352178)

### Outras correções do Analytics

AN-352905; AN-352902; AN-352693; AN-352659; AN-352619;
AN-352577; AN-352575; AN-352572; AN-352571; AN-352549; AN-352501; AN-352499; AN-352478; AN-352466; AN-352437; AN-352378; AN-352355; AN-352341; AN-352318; AN-352297; AN-352272; AN-352267; AN-352263; AN-352088; AN-352019; AN-352018; AN-351978; AN-351908; AN-351809; AN-351750; AN-351689; AN-351624; AN-351564; AN-351524; AN-351507; AN-351416; AN-351414; AN-351405; AN-351299; AN-351283; AN-351231; AN-350710; AN-349912; AN-349786; AN-348300; AN-348061; AN-347865; AN-347676; AN-347478; AN-343611; AN-343114; AN-334124

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Prazo de 13 meses para a expiração do`cust_visids`** salvo | 22 de maio de 2024 | Uma versão futura do mecanismo de processamento do Analytics Hit, **programada para julho de 2024**, começará a impor um prazo de 13 meses para a expiração de `cust_visids` salvo. Se o conjunto de relatórios estiver com a opção “Habilitar identificação de visitantes” ativada, esta configuração será usada para encontrar o `cust_visid` para um `visid_high/visid_low value` que não contenha `cust_visid` na ocorrência. Atualmente, não há um prazo de expiração para o mapeamento de um `cust_visid` para um `visid_high/visid_low`. Com esta versão, o mapeamento expirará se 13 meses ou mais se passarem desde que o `visid_high/visid_low` teve um `cust_visid` em uma ocorrência. |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Fim da vida útil da API do Adobe Analytics (versão 1.4)** | quinta-feira, 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API herdados do Analytics a seguir estão programados para atingir seu fim de vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação Adobe Analytics WSSE</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API do Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth na [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre EOL da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.26.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/appmeasurement-updates).


## Recursos relacionados

* [Notas de versão anteriores para 2024](/help/release-notes/2024.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do complemento Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
