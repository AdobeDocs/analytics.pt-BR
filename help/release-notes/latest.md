---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ae03f0d9e5f22c8e8ff6550a33a6f9d18432f46f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 86%

---

# Notas de versão atuais do Adobe Analytics (outubro de 2024)

**Última atualização**: sexta-feira, 17 de outubro de 2024

Essas notas de versão abrangem o período de lançamento de 2 de outubro de 2024 a 22 de outubro de 2024. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| Novo Report Builder para Adobe Analytics | O novo aplicativo Report Builder traz recursos atualizados para o Adobe Analytics, como melhor desempenho, interface de usuário simplificada, suporte à API 2.0 e suporte ao Microsoft Excel no Mac, Windows e navegadores da Web. [Saiba mais](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/report-buider-overview) |  | quinta-feira, 16 de outubro de 2024 |

## Correções no Adobe Analytics

Analysis Workspace: AN-343611; AN-355870; AN-357100; AN-358364; AN-358756; AN-359269
Aplicativo móvel do Analytics: AN-354085
Classificações: AN-353074; AN-357533; AN-358308; AN-358350; AN-358732; AN-358925; AN-359249
Análise entre dispositivos: AN-357968
Feeds de dados: AN-358489; AN-358542
Data Warehouse: AN-352181; AN-356701; AN-356802; AN-356804; AN-359162

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Campos do XDM dos detalhes de implementação adicionais mapeados automaticamente** | 11 de setembro de 2024 | Ao usar a Edge Network da Adobe Experience Platform para enviar dados ao Adobe Analytics, os campos do XDM `xdm.implementationdetails.name` e `xdm.implementationdetails.environment` agora sempre mapeiam para as variáveis de dados de contexto `c.a.x.implementationdetails.name` e `c.a.x.implementationdetails.environment`. Anteriormente, alguns cenários impediam o preenchimento desses valores. Ajuste todas as regras de processamento relevantes para acomodar a disponibilidade desses valores. |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Fim da vida útil da API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API herdados do Analytics a seguir estão programados para atingir seu fim de vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.26.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/appmeasurement-updates).


## Recursos relacionados

* [Notas de versão anteriores para 2024](/help/release-notes/2024.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do complemento Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
