---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: a85150e1299e0d5164c4eaa0fe9d5d6f67ef15b3
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 56%

---

# Notas de versão atuais do Adobe Analytics (junho de 2024)

**Última atualização**: quinta-feira, 12 de junho de 2024

Essas notas de versão abrangem o período de lançamento de 12 de junho de 2024 a julho. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Selecionar vários campos em um filtro suspenso** | Quando vários campos são adicionados a um filtro suspenso, os usuários podem selecionar mais de um campo por vez. O painel é filtrado para incluir qualquer um dos campos selecionados. <p>Anteriormente, os usuários podiam selecionar apenas um campo por vez em um filtro suspenso.</p><p>(Link de documentação em breve.)</p> |  | quinta-feira, 19 de junho de 2024 |
| **Sumário de projetos do Workspace** | Um novo sumário está disponível para projetos. O índice fornece links que permitem aos usuários ir rapidamente para painéis e visualizações no projeto. O índice pode ser ativado para projetos individuais ou para todos os projetos de um determinado usuário.<p>(Link de documentação em breve.) |  | quinta-feira, 19 de junho de 2024 |
| **Criar hiperlinks para itens de dimensão em uma tabela de forma livre** | É possível criar hiperlinks para um ou mais itens de dimensão para torná-los clicáveis em uma tabela de forma livre no Analysis Workspace. <p>Você pode criar hiperlinks para itens de dimensão com valores de URL ou criar URLs personalizados para itens de dimensão com valores que não sejam de URL.</p><p>Você pode criar URLs personalizados dinâmicos para vários itens de dimensão usando variáveis. As variáveis podem fazer referência ao valor de um item de dimensão ou à dimensão de detalhamento.</p><p>(Link de documentação em breve.)<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | quinta-feira, 19 de junho de 2024 |
| **Configurações do administrador para controlar as contas e os locais usados para exportação e importação** | Um novo [Guia &quot;Configurações do administrador&quot; no Gerenciador de locais](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) O fornece aos administradores controle sobre se os usuários podem criar e editar contas e locais. Essas configurações se aplicam quando os usuários [configurar contas de importação e exportação na nuvem](/help/components/locations/configure-import-accounts.md) e [configurar locais de importação e exportação na nuvem](/help/components/locations/configure-import-locations.md). <p>Administradores também podem limitar os tipos de conta (Google Cloud Platform, Azure RBAC, Amazon S3 e assim por diante) que os usuários podem criar e usar.</p><p>Anteriormente, qualquer usuário podia criar, editar e usar contas e locais para qualquer tipo de conta.</p> | 12 de junho de 2024 | 30 de junho de 2024 |
| **Compartilhar contas e locais usados para exportação e importação** | Agora os usuários podem disponibilizar as contas e os locais que criam para todos os usuários em sua organização. Somente os proprietários de contas e locais e os administradores do sistema podem editar e excluir contas e locais.<p>Anteriormente, contas e locais podiam ser usados somente pelo usuário que os criava.</p><p>Essas configurações estão disponíveis quando os usuários [configurar contas de importação e exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts) e [configurar locais de importação e exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-locations). </p> | 12 de junho de 2024 | 30 de junho de 2024 |
| **O Activity Map usa menos chamadas de servidor para o SDK da Web** | Atualmente, os eventos de link do Activity Map são contados como eventos próprios e resultam em cobranças adicionais. Esse aprimoramento seleciona alguns eventos de link e os reúne na próxima ocorrência, de modo semelhante a como os eventos são tratados pelo AppMeasurement. <p>(Link para a documentação será atualizado em breve)</p> | Beta aberto começa em 19 de junho de 2024 | A ser definido |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção dos seguintes problemas de Classificações: AN-347682; AN-348396; AN-348625; AN-348668; AN-348926; AN-348936; AN-349040; AN-349191; AN-349195; AN-349 9443; AN-349697; AN-349758; AN-349862; AN-350051; AN-350054; AN-350208; AN-350497; AN-350525; AN-351067
* Correção dos seguintes problemas de Data Warehouse: AN-346862; AN-349409; AN-349926; AN-350629; AN-350996
* Correção dos seguintes problemas de Feeds de dados: AN-346727; AN-348282; AN-348334; AN-348725; AN-348726; AN-348823; AN-349081; AN-349207; AN-349307; AN-3497 349729; AN-349742; AN-349742; AN-349878; AN-349943; AN-350527;
* Correção do seguinte problema das fontes de dados: AN-350038
* Correção dos seguintes problemas do Analysis Workspace: AN-342953; AN-346346; AN-349590; AN-349717; AN-350057; AN-350697; AN-350904
* Correção dos seguintes problemas de Report Builder: AN-348903; AN-350691
* Correção dos seguintes problemas do A4T: AN-347690; AN-350853

### Outras correções do Analytics

AN-346470; AN-346850; AN-347227; AN-348145; AN-348564; AN-349001; AN-349008; AN-349211; AN-349719; AN-350523;

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Prazo de 13 meses para a expiração do`cust_visids`** salvo | 22 de maio de 2024 | Uma versão futura do mecanismo de processamento do Analytics Hit, **programada para julho de 2024**, começará a impor um prazo de 13 meses para a expiração de `cust_visids` salvo. Se o conjunto de relatórios estiver com a opção “Habilitar identificação de visitantes” ativada, esta configuração será usada para encontrar o `cust_visid` para um `visid_high/visid_low value` que não contenha `cust_visid` na ocorrência. Atualmente, não há um prazo de expiração para o mapeamento de um `cust_visid` para um `visid_high/visid_low`. Com esta versão, o mapeamento expirará se 13 meses ou mais se passarem desde que o `visid_high/visid_low` teve um `cust_visid` em uma ocorrência. |
| **Atualizações da região ISO** | 10 de maio de 2024 | A Adobe realizará as atualizações de 2024 da região ISO em 7 de junho de 2024. Você poderá ver pequenas atualizações de informações geográficas (região) após este lançamento. |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.26.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2024](/help/release-notes/2024.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
