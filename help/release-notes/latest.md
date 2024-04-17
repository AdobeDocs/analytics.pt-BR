---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d2b2ebdbc6a3c0f20b8684ba5c1b4b89cefb8e5a
workflow-type: tm+mt
source-wordcount: '1240'
ht-degree: 51%

---

# Notas de versão atuais do Adobe Analytics (abril de 2024)

**Última atualização**: quinta-feira, 17 de abril de 2024

Essas notas de versão abrangem o período de lançamento de 17 de abril de 2024 a maio. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mídia de transmissão: enviar dados do Roku para o Edge Network do Adobe Experience Platform** | Agora quando [instalação do Media Analytics com Experience Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), você pode usar o SDK do Adobe Experience Platform Roku para enviar dados de mídia de transmissão para o Adobe Experience Platform. |  | 12 de abril de 2024 |
| **Fluxo de trabalho aprimorado para migração do SDK da Web** | A coleta de dados do Adobe Experience Platform agora mapeia automaticamente muitos campos do objeto de dados diretamente para o Adobe Analytics. Esse fluxo de trabalho aprimorado oferece os seguintes benefícios:<ul><li>Ele permite que sua organização migre para o SDK da Web sem se preocupar em criar ou aderir a um [!UICONTROL Esquema XDM]. Consulte [Mapeamento de variável de objeto de dados](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) para obter mais informações. (Mais links de documentação a seguir)</li><li>Depois de migrar para o SDK da Web, sua organização está em melhor posição para migrar do Adobe Analytics para o Customer Journey Analytics. Isso ocorre porque o SDK da Web permite uma migração mais simples para o Customer Journey Analytics.</li></ul> (Mais informações sobre esta e outras opções de migração serão disponibilizadas em breve.) |  | Abril de 2024 |
| **Aprimoramento de permissões somente para projeto [!UICONTROL Workspace] componentes** | Anteriormente, se um usuário (Usuário A) compartilhasse um projeto com outro usuário (Usuário B) e desse ao Usuário B acesso de edição ao projeto, o Usuário B poderia editar o projeto. No entanto, o usuário B não poderia editar [!UICONTROL Segmentos rápidos] incorporado no projeto. Essa limitação foi removida - o usuário B pode editar [!UICONTROL Segmentos rápidos] e outros componentes somente de projeto incorporados ao projeto compartilhado. |  | 17 de abril de 2024 |
| **Usar as mesmas contas de nuvem para [!UICONTROL Feeds de dados], [!UICONTROL Data Warehouse], e [!UICONTROL Conjuntos de classificações]** | As contas e os locais na nuvem que você criar agora poderão ser usados para exportar dados (com [!UICONTROL Feeds de dados] e [!UICONTROL Data Warehouse]) e importação de dados (com [!UICONTROL Conjuntos de classificações]).<p> **Alterações ao configurar contas:** Os usuários podem [Configurar contas de importação e exportação na nuvem](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) e [Configurar locais de importação e exportação na nuvem](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations) que podem ser utilizados para qualquer um dos seguintes fins:<ul><li>Importar dados com [!UICONTROL Conjuntos de classificações]</li><li>Exportar dados com [!UICONTROL Feeds de dados]</li><li>Exportar dados com [!UICONTROL Data Warehouse].</li></ul><p>**Alterações ao gerenciar contas**: os usuários podem usar o [Localizações](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) página (em [!UICONTROL Componentes] > Locações) para exibir e gerenciar todas as contas e locais que eles criam, independentemente de onde foram criados. <p>Anteriormente, a variável [!UICONTROL Localizações] página aplicada somente a contas que foram criadas para importação de dados com [!UICONTROL Conjuntos de classificações].</p> | | 17 de abril de 2024 |
| **Admins podem gerenciar todos os locais e contas da organização** | Uma nova opção na guia “Locais” (na página Componentes > Locais) permite que admins visualizem e gerenciem todos os locais da organização.<p>Uma nova opção no [Localização](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) A guia Contas (na página Componentes > Locais ) permite que os administradores visualizem e gerenciem todas as contas na organização.</p> <p>Anteriormente, admins podiam apenas visualizar e gerenciar os locais e contas que haviam criado.</p> |  | 17 de abril de 2024 |
| **Aumento nos limites padrão de tráfego baixo** | Em **meados de abril de 2024**, a Adobe começará a aumentar os limites padrão de tráfego baixo para conjuntos de relatórios da seguinte maneira: ![limites de tráfego baixo](assets/thresholds.png) isso afetará somente as variáveis que estão definidas abaixo dos novos limites. Essas alterações serão feitas de forma incremental e esperamos que o trabalho seja concluído até o **fim de maio**. À medida que esses aumentos forem implementados, você poderá notar alterações nas variáveis de alta cardinalidade:<ul><li>Mais valores de dimensão podem estar disponíveis para relatórios.</li><li>Segmentos e métricas calculadas podem incluir mais dados.</li><li>Os conjuntos de relatórios virtuais baseados em segmentos podem incluir mais dados.</li><li>As exportações de classificação podem incluir mais dados.</li></ul> | Meados de abril de 2024 | sábado, 31 de maio de 2024 |
| **O Activity Map usa menos chamadas de servidor para o SDK da web** | Atualmente, os eventos de link do Activity Map são contados como eventos separados e acarretam cobranças adicionais. <p>Esse aprimoramento seleciona alguns eventos de link e os reúne na próxima ocorrência, de modo semelhante a como os eventos são tratados pelo AppMeasurement.</p> |  | sábado, 31 de maio de 2024 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção dos seguintes problemas de classificações: AN-343439; AN-343503; AN-343504; AN-343986; AN-344262; AN-344564; AN-345204; AN-345234
* Correção dos seguintes problemas do Construtor de regras de classificação: AN-341488; AN-342501; AN-345751
* Correção do seguinte problema de Alertas inteligentes: AN-343466;
* Correção do seguinte problema de segmentação: AN-342313
* Correção do seguinte problema de Data Warehouse: AN-344292
* Correção dos seguintes problemas de Feeds de dados: AN-339545; AN-340092; AN-342124; AN-342862; AN-343737; AN-344035; AN-344329; AN-344703; AN-344721; AN-344 AN-345180; AN-345196; AN-345225; AN-345236; AN-345326; AN-345631; AN-345659
* Correção do seguinte problema de Fontes de dados: AN-343541
* Correção dos seguintes problemas do Analysis Workspace: AN-336303; AN-336472; AN-338422; AN-338556; AN-339718; AN-340147; AN-340301; AN-340421; AN-340951; AN-341 AN-342905; AN-342909; AN-343448; AN-343570; AN-344050; AN-344182; AN-344763; AN-344768;
* Correção dos seguintes problemas de administrador do Analytics: AN-342519; AN-342523; AN-343623; AN-343882; AN-344237; AN-344829; AN-345235;
* Correção dos seguintes problemas do A4T: AN-341619; AN-344402
* Correção do seguinte problema do aplicativo móvel: AN-342010

### Outras correções do Analytics

AN-336099; AN-337474; AN-337993; AN-339718; AN-339901; AN-340014; AN-341356; AN-343021; AN-343102; AN-343353; AN-343416; AN-340014; AN-344037; AN-344525; AN-345737

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Prazo de 13 meses para a expiração do`cust_visids`** salvo | 20 de março de 2024 | Uma versão futura do mecanismo de processamento de ocorrências do Analytics, programada para abril ou maio, começará a impor um prazo de 13 meses para a expiração do `cust_visids` salvo. Se o conjunto de relatórios estiver com a opção “Habilitar identificação de visitantes” ativada, esta configuração será usada para encontrar o `cust_visid` para um `visid_high/visid_low value` que não contenha `cust_visid` na ocorrência. Atualmente, não há um prazo de expiração para o mapeamento de um `cust_visid` para um `visid_high/visid_low`. Com esta versão, o mapeamento expirará se 13 meses se passarem desde que `visid_high/visid_low` teve um `cust_visid` em uma ocorrência. |
| **Adições de membros de objetos da API da Adobe** | 17 de janeiro de 2024 | A Adobe pode adicionar membros opcionais de solicitação e de resposta (pares nome/valor) a objetos de API já existentes a qualquer momento e sem aviso prévio ou alterações no controle de versão. A Adobe recomenda consultar a documentação da API de qualquer ferramenta de terceiros que você decida integrar às nossas APIs, para que essas adições sejam ignoradas no processamento se não forem compreendidas. Se implementadas corretamente, essas adições são alterações que não interrompem a implementação. A Adobe não removerá parâmetros nem adicionará parâmetros obrigatórios sem primeiro fornecer uma notificação padrão por meio das notas de versão. |

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
