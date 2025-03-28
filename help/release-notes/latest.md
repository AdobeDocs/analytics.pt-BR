---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e0f6b7b5b2933add7f67873a945b78e4200116eb
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 98%

---

# Notas de versão atuais do Adobe Analytics (versão de março de 2025)

**Última atualização**: 12 de março de 2025

Essas notas de versão abrangem o período de lançamento de 5 de março a maio de 2025. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Atualização do campo de dados de contexto do Analytics`a.locale`** | Esta atualização altera a forma como o campo de dados de contexto `a.locale` do Analytics é definido ao coletar dados via Experience Edge. Quando os dados são enviados para o Adobe Analytics usando a Experience Edge, os campos do Analytics são preenchidos com base em um mapeamento de campos XDM. O mapeamento para `c.a.locale` faz referência a um campo XDM não padrão, `xdm.environment.language`. Este campo será atualizado para fazer referência ao campo correto, `xdm.environment._dc.language`.<p>O mapeamento continuará fazendo referência a `xdm.environment.language` para oferecer compatibilidade com versões anteriores. Para fins de continuidade, se ambos os campos forem definidos, `xdm.environment.language` terá prioridade. Você pode exibir a lista completa de mapeamentos do XDM para campos padrão do Analytics [aqui](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | 5 de março de 2025 |
| **Guia de atualização do Customer Journey Analytics** | Permite gerar um guia passo a passo para atualizar do Adobe Analytics para o Customer Journey Analytics. Este guia é personalizado para sua organização e leva em consideração seu ambiente atual do Adobe Analytics, seus usos pretendidos para o Customer Journey Analytics e quaisquer ajustes que sua organização deseje fazer para economizar tempo.<p>Para começar a gerar seu guia personalizado, faça logon no [!DNL Customer Journey Analytics] e selecione **[!UICONTROL Atualizar para o Customer Journey Analytics]** na guia **[!UICONTROL Workspace]**.<p>[Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 11 de março de 2025 |
| **Dimensões exclusivas do Data Warehouse** | A partir de maio de 2025, a Adobe começará a definir dimensões (variáveis personalizadas, como eVars e props) que possuem uma cardinalidade extremamente alta como “Exclusiva do Data Warehouse”. Variáveis de alta cardinalidade têm muitos valores distintos; exemplos incluem carimbos de data e hora ou UUIDs. Essas dimensões não estarão mais disponíveis para relatórios no Analysis Workspace.<p>Os candidatos a essa alteração são dimensões que excedem os limites de tráfego baixo muito cedo no mês. Os relatórios do Analysis Workspace que são baseados nesses tipos de dimensão não são úteis, porque os dados relatáveis representam apenas uma pequena parte dos valores iniciais coletados.<p>Como o Data Warehouse não impõe limites de tráfego baixo, você ainda pode criar relatórios ou segmentos úteis com base nesses tipos de dimensões. | | Maio de 2025 |


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
