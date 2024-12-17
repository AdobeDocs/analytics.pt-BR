---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 99%

---

# Notas de versão atuais do Adobe Analytics (versão de 23 de outubro de 2024)

**Última atualização**: 9 de dezembro de 2024

Estas notas de versão abrangem o período de lançamento de 16 de outubro de 2024 até o fim de 2024. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Novo Report Builder para Adobe Analytics** | O novo aplicativo Report Builder traz uma atualização importante para o Adobe Analytics, incluindo melhor desempenho, interface do usuário simplificada e compatibilidade com a API 2.0 e com o Microsoft Excel no Mac, Windows e navegadores da web. Este aplicativo pode ser usado junto com o aplicativo legado, mas não no mesmo arquivo. Um recurso de atualização é fornecido para atualizar pastas de trabalho legadas para o novo aplicativo. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/report-builder/report-buider-overview) |  | 16 de outubro de 2024 |
| **Exportação de JSON para migrar a implementação de tags para tags de SDK da web** | Esta atualização da extensão de tags do Analytics está relacionada à migração para o SDK da web. Você pode usar essa atualização para a extensão do Adobe Analytics como parte do fluxo de trabalho a fim de recriar as configurações de extensão com a extensão SDK da web. Na extensão de tags do Adobe Analytics, é possível exibir as configurações de eVars, props e eventos como JSON, que podem ser exportadas para edição e incluídas na extensão SDK da web. |  | 31 de outubro de 2024 |
| **Novas informações sobre fatores de solicitação no desempenho do Analysis Workspace** | Uma nova seção “Fatores de solicitação” agora está disponível ao analisar o desempenho no Analysis Workspace. Para saber mais sobre como as solicitações são processadas e os vários fatores que influenciam os tempos de processamento, consulte “Fatores de solicitação” em [Otimizar o desempenho do Analysis Workspace](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance). |  | 1º de outubro de 2024 |
| **Período de retenção da ID da transação** | O período de retenção de 90 dias da ID da transação será estendido para 25 meses em janeiro de 2025. A variável `transactionID` identifica exclusivamente uma transação para que a ocorrência possa ser vinculada a dados enviados por meio de Fontes de dados. |  | 22 de janeiro de 2025 |

## Correções no Adobe Analytics

Analysis Workspace: AN-356287; AN-358435; AN-359456; AN-359826; AN-360215
Ferramentas do administrador: AN-342485; AN-347931; AN-348704; AN-357723; AN-358453; AN-358717; AN-359548; AN-360136
Classificações: AN-359025; AN-359283; AN-359368; AN-359710; AN-359752; AN-359759; AN-359799; AN-359887; AN-360543; AN-360566; AN-360612; AN-360741; AN-360942; AN-360952
Análises entre dispositivos: AN-359210
Atributos do cliente: AN-357897
Coleta de dados: AN-351131; AN-351309; AN-355678; AN-359856
Feeds de dados: AN-359699
API de reparo dos dados: AN-360256
Fontes de dados: AN-359290
Data warehouse: AN-359820
Alertas de excesso: AN-358132

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Clientes de fora do Campaign perderão o acesso aos acionadores** | 16 de outubro de 2023 | Em 30 de janeiro de 2025, os clientes do Adobe Analytics que não tiverem uma licença do Adobe Campaign perderão o acesso à opção de configurar e consumir acionadores. Os clientes precisam comprar o Campaign, planejar para para de usar os acionadores ou procurar outras ferramentas da Adobe que ofereçam recursos de acionador. |
| **Campos do XDM dos detalhes de implementação adicionais mapeados automaticamente** | 11 de setembro de 2024 | Ao usar a Edge Network da Adobe Experience Platform para enviar dados ao Adobe Analytics, os campos do XDM `xdm.implementationdetails.name` e `xdm.implementationdetails.environment` agora sempre mapeiam para as variáveis de dados de contexto `c.a.x.implementationdetails.name` e `c.a.x.implementationdetails.environment`. Anteriormente, alguns cenários impediam o preenchimento desses valores. Ajuste todas as regras de processamento relevantes para acomodar a disponibilidade desses valores. |

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Fim da vida útil da API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.26.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/appmeasurement-updates).


## Recursos relacionados

* [Notas de versão anteriores para 2024](/help/release-notes/2024.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de Mídia de Streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
