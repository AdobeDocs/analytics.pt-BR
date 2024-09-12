---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7dd42948073b56a33c1d00f9b4292d1cc3416470
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 66%

---

# Notas de versão atuais do Adobe Analytics (setembro de 2024)


**Última atualização**: quinta-feira, 11 de setembro de 2024

Essas notas de versão abrangem o período de lançamento de 11 de setembro de 2024 até o início de outubro. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
|--- | --- | --- | --- |
| **Informações adicionais na coluna “Usado em” no gerenciador de métricas calculadas e no gerenciador de segmentos** | A coluna &quot;Usado em&quot; no gerenciador de métricas calculadas e no gerenciador de segmentos contém as novas áreas de relatório a seguir:<ul><li>**Report Builder**: mostra o número de métricas calculadas ou segmentos que estão sendo usados no Report Builder.</li><li>**Componentes ad hoc**: mostra o número de métricas calculadas ad hoc ou de segmentos ad hoc que estão sendo usados em projetos. Essas métricas calculadas e segmentos ad hoc (também conhecidos como “métricas calculadas rápidas” e “segmentos rápidos”) podem ser usados somente no projeto em que foram criados, portanto, eles são relatados separadamente a partir da área de relatório “Projeto”, na coluna “Usado em”.</li></ul>Para obter mais informações, consulte [Gerenciador de métricas calculadas](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager) e [Gerenciador de segmentos](https://experienceleague.adobe.com/en/docs/analytics/components/segmentation/segmentation-workflow/seg-manage). |  | 11 de setembro de 2024 |
| **extensão do Activity Map v3** | A extensão Activity Map v3 está disponível. Se você tiver a extensão v2 instalada, desinstale-a antes de instalar a extensão v3. Navegue até **[!UICONTROL Ferramentas]** > **[!UICONTROL Activity Map]** para obter a versão mais recente da extensão. |  | 3 de setembro de 2024 |


## Correções no Adobe Analytics

A4T: AN-355736
Activity Map: AN-353779
Analysis Workspace: AN-348485; AN-349693; AN-357247
Aplicativo móvel do Analytics: AN-352645
Classificações: AN-355636; AN-355651; AN-355753; AN-356005; AN-356439; AN-356540; AN-356577; AN-356622
Análise entre dispositivos: AN-355138
Feeds de dados: AN-356258; AN-357133
Data Warehouse: AN-339292; AN-353807
Locais de exportação: AN-356912
API de privacidade: AN-352420
Report Builder: AN-352555; AN-354316
Projetos programados: AN-355971
Segmentação: AN-352095;
Relatórios do Target: AN-355748

Outras correções: AN-349698; AN-349880; AN-354860; AN-355355; AN-356289;

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Prazo de 13 meses para a expiração do`cust_visids`** salvo | 20 de agosto de 2024 | A versão de **20 de agosto de 2024** do mecanismo de processamento de ocorrências do Analytics impõe uma expiração de 13 meses do `cust_visids` salvo. Se o conjunto de relatórios estiver com a opção “Habilitar identificação de visitantes” ativada, esta configuração será usada para encontrar o `cust_visid` para um `visid_high/visid_low value` que não contenha `cust_visid` na ocorrência. Previamente, não havia um prazo de expiração para o mapeamento de um `cust_visid` para um `visid_high/visid_low`. Com esta versão, o mapeamento expirará se 13 meses ou mais se passarem desde que o `visid_high/visid_low` teve um `cust_visid` em uma ocorrência. |
| **Campos XDM de detalhes de implementação adicionais mapeados automaticamente** | 11 de setembro de 2024 | Ao usar o Edge Network Adobe Experience Platform para enviar dados para o Adobe Analytics, os campos XDM `xdm.implementationdetails.name` e `xdm.implementationdetails.environment` agora sempre mapeiam para as variáveis de dados de contexto `c.a.x.implementationdetails.name` e `c.a.x.implementationdetails.environment`. Anteriormente, alguns cenários impediam o preenchimento desses valores. Ajuste todas as regras de processamento relevantes para acomodar a disponibilidade desses valores. |

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
