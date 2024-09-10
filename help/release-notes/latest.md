---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 0f05faf76c26000f714e95ed2469ff13b7e3b72e
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 85%

---

# Notas de versão atuais do Adobe Analytics (agosto de 2024)

**Última atualização**: terça-feira, 9 de setembro de 2024

Estas notas de versão englobam o período de lançamento de 14 de agosto a setembro de 2024. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Informações adicionais na coluna &quot;Usado em&quot; no gerenciador de métrica calculada e no gerenciador de segmento** | A coluna &quot;Usado em&quot; no gerenciador de métricas calculadas e no gerenciador de segmentos contém as novas áreas de relatório a seguir:<ul><li>**Report Builder:** mostra o número de métricas calculadas ou segmentos que estão sendo usados no Report Builder.</li><li>**Componentes ad hoc:** Mostra o número de métricas calculadas ad hoc ou de segmentos ad hoc que estão sendo usados em projetos. Essas métricas e segmentos calculados ad hoc (também conhecidos como &quot;métricas calculadas rápidas&quot; e &quot;segmentos rápidos&quot;) podem ser usados somente no projeto em que foram criados, portanto, são relatados separadamente da área de relatório &quot;Projeto&quot; na coluna &quot;Usado em&quot;.</li></ul><p>(Links de documentação atualizados a seguir.)</p> | N/D | quinta-feira, 11 de setembro de 2024 |
| **Melhorias no SDK da Web para rastreamento de link** | Várias melhorias notáveis estão disponíveis na versão mais recente do SDK da Web em relação ao rastreamento de link, que beneficia diretamente o Activity Map. Esses novos recursos estão disponíveis na biblioteca JavaScript do SDK da Web e na extensão de tag do SDK da Web.<ul><li>Agrupamento de eventos: quando um visitante clica em um link interno, é possível optar por agrupar dados do evento na próxima página, em vez de acionar uma chamada de evento separada para o rastreamento de link. Essa melhoria reduz o número de eventos que o SDK da Web usa em relação ao limite contratual.</li><li>Filtrar propriedades de clique: um novo retorno de chamada que substitui `OnBeforeLinkClickSend`. Você pode usar essa chamada de retorno para filtrar ou ofuscar dados relacionados ao link antes de enviá-lo à Adobe.</li></ul><p>Consulte [clickCollection](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/commands/configure/clickcollection) no guia do usuário do SDK da Web para obter mais informações.</p> | O Open Beta começou em 10 de julho de 2024 | 18 de julho de 2024 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção de um problema no qual vários valores desconhecidos eram exibidos no Workspace (AN-353632)
* Correção de um problema no qual o email de notificação não era enviado após a adição de novos clientes ou novos perfis de produto do Analytics no Admin Console (AN-350930)

### Outras correções do Analytics

AN-354361; AN-354248; AN-354211; AN-354324; AN-351532; AN-349808; AN-347831; AN-353777; AN-354092; AN-354064; AN-354202; AN-354006; AN-354097; AN-352548; AN-353819; AN-353818; AN-353628; AN-353747; AN-353527; AN-353490; AN-352647; AN-352656; AN-351274; AN-352135; AN-351519; AN-344906; AN-353697; AN-354499; AN-354402; AN-354062; AN-353905; AN-353932; AN-354142; AN-354194; AN-354182; AN-353758; AN-353039; AN-353612; AN-350799; AN-354414; AN-354636; AN-354249; AN-353637; AN-350949; AN-349402; AN-355103; AN-354174; AN-353823; AN-354819; AN-354215; AN-354219; AN-354040; AN-354763; AN-354597; AN-354478; AN-354528; AN-354335

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Prazo de 13 meses para a expiração do`cust_visids`** salvo | 20 de agosto de 2024 | A versão de **20 de agosto de 2024** do mecanismo de processamento de ocorrências do Analytics impõe uma expiração de 13 meses do `cust_visids` salvo. Se o conjunto de relatórios estiver com a opção “Habilitar identificação de visitantes” ativada, esta configuração será usada para encontrar o `cust_visid` para um `visid_high/visid_low value` que não contenha `cust_visid` na ocorrência. Previamente, não havia um prazo de expiração para o mapeamento de um `cust_visid` para um `visid_high/visid_low`. Com esta versão, o mapeamento expirará se 13 meses ou mais se passarem desde que o `visid_high/visid_low` teve um `cust_visid` em uma ocorrência. |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Fim da vida útil da API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API herdados do Analytics a seguir chegarão ao seu fim de vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.26.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/appmeasurement-updates).


## Recursos relacionados

* [Notas de versão anteriores para 2024](/help/release-notes/2024.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do complemento Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
