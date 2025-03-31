---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 53175bbf54dd452502e1502b272ebb86c8b133ef
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 64%

---

# Notas de versão atuais do Adobe Analytics (versão de março de 2025)

**Última atualização**: terça-feira, 31 de março de 2025

Essas notas de versão abrangem o período de lançamento de 5 de março a maio de 2025. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Atualização do campo de dados de contexto do Analytics`a.locale`** | Esta atualização altera a forma como o campo de dados de contexto `a.locale` do Analytics é definido ao coletar dados via Experience Edge. Quando os dados são enviados para o Adobe Analytics usando a Experience Edge, os campos do Analytics são preenchidos com base em um mapeamento de campos XDM. O mapeamento para `c.a.locale` faz referência a um campo XDM não padrão, `xdm.environment.language`. Este campo será atualizado para fazer referência ao campo correto, `xdm.environment._dc.language`.<p>O mapeamento continuará fazendo referência a `xdm.environment.language` para oferecer compatibilidade com versões anteriores. Para fins de continuidade, se ambos os campos forem definidos, `xdm.environment.language` terá prioridade. Você pode exibir a lista completa de mapeamentos do XDM para campos padrão do Analytics [aqui](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | 5 de março de 2025 |
| **Guia de atualização do Customer Journey Analytics** | Permite gerar um guia passo a passo para atualizar do Adobe Analytics para o Customer Journey Analytics. Este guia é personalizado para sua organização e leva em consideração seu ambiente atual do Adobe Analytics, seus usos pretendidos para o Customer Journey Analytics e quaisquer ajustes que sua organização deseje fazer para economizar tempo.<p>Para começar a gerar seu guia personalizado, faça logon no [!DNL Customer Journey Analytics] e selecione **[!UICONTROL Atualizar para o Customer Journey Analytics]** na guia **[!UICONTROL Workspace]**.<p>[Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 11 de março de 2025 |
| **Dimensões exclusivas do Data Warehouse** | A partir de maio de 2025, a Adobe começará a definir determinadas dimensões (variáveis personalizadas, como eVars e props) como &quot;somente Data Warehouse&quot;. Isso se aplica às dimensões que apresentam as seguintes características:<ul><li> Durante um período de vários meses, a variável atinge o limite de tráfego baixo nos primeiros dias do mês.</li><li>> 90% dos valores transmitidos são vistos apenas uma vez durante o mês.</li></ul>Exemplos incluem dimensões contendo carimbos de data e hora, UUIDs ou outros dados que têm cardinalidade extremamente alta e em que novos valores exclusivos são transmitidos para quase todas as ocorrências (ou visitas ou visitantes) ao longo do mês. Essas dimensões geralmente excedem os limites de tráfego baixo muito rapidamente e apenas uma parte muito pequena dos valores é reportável no Analysis Workspace. Isso torna os relatórios que utilizam essas dimensões confusos, pois não mostram informações úteis ou precisas. Essas dimensões não seguem a finalidade ou se beneficiam da funcionalidade de tráfego baixo, que tem como objetivo fornecer uma maneira de criar relatórios sobre valores que se tornam &quot;populares&quot; depois que a dimensão excede os limites de tráfego baixo durante o mês. [Saiba mais](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic.)<p>Dimensões marcadas como &quot;Somente Data Warehouse&quot; não estarão disponíveis para relatórios no Analysis Workspace. No entanto, eles ainda estarão disponíveis para relatórios por meio do Data Warehouse, pois limites de tráfego baixo não se aplicam aqui.<p>Isso não significa que todas as dimensões que atingiram os limites de tráfego baixo são candidatas a serem marcadas como &quot;somente Data Warehouse&quot;. A maioria das dimensões que atingem os limites de tráfego baixo realmente atende à intenção de funcionalidade de tráfego baixo:<ul><li>A maioria dos valores transmitidos não é exclusiva.</li><li>Os valores comuns continuam a entrar depois que os limites de tráfego baixo são atingidos durante o mês.</li><li>Novos valores &quot;populares&quot; ainda podem ocorrer.</li></ul>Somente as dimensões em que quase todos os valores transmitidos são novos e exclusivos serão marcadas como &quot;Somente Data Warehouse&quot;. Aumentar os limites de tráfego baixo não é uma solução, dada a exclusividade dos dados coletados nessas situações. | | Maio de 2025 |


## Correções no Adobe Analytics

**Activity Map**: AN-361038
**Ferramentas administrativas**: AN-362178; AN-369483
**API do Analytics 1.4**: AN-369615
**Analysis Workspace**: AN-353491; AN-363403; AN-367230; AN-367313; AN-368582; AN-369821; AN-370227;
**Classificações**: AN-369848; AN-370196; AN-370226; AN-370437
**Feeds de dados**: AN-366162; AN-368906; AN-369066; AN-369087; AN-369225; AN-369798
**Governança de dados**: AN-365157
**Fontes de dados**: AN-367550
**Platform**: AN-363931
**Report Builder**: AN-367460; AN-368975

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| N/D |  |  |

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 17 de janeiro de 2025 | Os clientes da API do Adobe Analytics e da transmissão ao vivo que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até **30 de junho de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fim da vida útil da API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |


## AppMeasurement

Para obter as atualizações mais recentes sobre os lançamentos do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de versão anteriores para 2025](/help/release-notes/2025.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recente para [produtos da Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
