---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7468463e2fe1de16221b4528919b6abd6c8aedcb
workflow-type: ht
source-wordcount: '1445'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Analytics (abril de 2024)

**Última atualização**: 17 de abril de 2024

Estas notas de versão abrangem o período de lançamento de 17 de abril a maio de 2024. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Transmissão de mídia: enviar dados do Roku à Adobe Experience Platform Edge Network** | Ao [instalar o Media Analytics com a Experience Platform Edge](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), agora é possível usar o SDK Roku da Adobe Experience Platform para enviar dados de mídia de streaming para a Adobe Experience Platform. |  | 12 de abril de 2024 |
| **Fluxo de trabalho aprimorado para migração de SDK da web** | Agora, os fluxos de dados mapeiam automaticamente os campos de objetos de dados do SDK da web diretamente para o Adobe Analytics. O [mapeamento de objetos de dados](/help/implement/aep-edge/data-var-mapping.md) é semelhante ao [mapeamento de objetos XDM](/help/implement/aep-edge/xdm-var-mapping.md), mas não requer um esquema XDM. Esse fluxo de trabalho aprimorado fornece os seguintes benefícios:<ul><li>Ele adia o requisito de usar um esquema até que você esteja pronto para enviar dados à Adobe Experience Platform. Se um esquema fosse necessário neste estágio de uma migração de implementação, você precisaria usar um esquema com base em campos do Adobe Analytics. Os serviços da Adobe Experience Platform, como o Customer Journey Analytics, não têm um conceito de props ou eVars. Um esquema focado no Analytics pode gerar problemas se a sua organização quiser usar seu próprio esquema no futuro.</li><li>Depois de fazer alterações de implementação no SDK da web, a sua organização estará em uma posição melhor para migrar do Adobe Analytics para o Customer Journey Analytics. Se você enviar dados ao Adobe Analytics por meio do SDK da web, não será necessário fazer alterações adicionais na implementação para enviar dados à Adobe Experience Platform. Em vez disso, é possível usar o preparo de dados para mapear campos de objetos de dados para o seu esquema XDM.</li></ul>Consulte [Migrar da extensão de tag do Adobe Analytics para a extensão de tag do SDK da web](/help/implement/aep-edge/web-sdk/analytics-extension-to-web-sdk.md) e [Migrar do AppMeasurement para o SDK da web](../implement/aep-edge/web-sdk/appmeasurement-to-web-sdk.md) para mais informações. |  | Abril de 2024 |
| **Aprimoramento de permissões para componentes exclusivos de projetos do [!UICONTROL Workspace]** | Antes, se o usuário A compartilhasse um projeto com o usuário B e concedesse acesso de edição ao projeto, o usuário B seria capaz de editá-lo. No entanto, o usuário B não poderia editar [!UICONTROL segmentos rápidos] incorporados no projeto. Essa limitação foi removida: o usuário B agora pode editar [!UICONTROL segmentos rápidos] e outros componentes exclusivos incorporados no projeto compartilhado. |  | 17 de abril de 2024 |
| **Usar as mesmas contas de nuvem para [!UICONTROL feeds de dados], [!UICONTROL data warehouse] e [!UICONTROL conjuntos de classificações]** | As contas e os locais em nuvem que você criar agora poderão ser usados para exportar (com [!UICONTROL feeds de dados] e [!UICONTROL data warehouse]) e importar dados (com [!UICONTROL conjuntos de classificações]).<p> **Alterações na configuração de contas:** os usuários podem [Configurar contas de importação e exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts) e [Configurar locais de importação e exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-locations) que podem ser usados para qualquer uma das seguintes finalidades:<ul><li>Importação de dados com [!UICONTROL conjuntos de classificações]</li><li>Exportação de dados com [!UICONTROL feeds de dados]</li><li>Exportação de dados com [!UICONTROL data warehouse].</li></ul><p>**Alterações no gerenciamento de contas e locais a partir da página [!UICONTROL Locais]**: usuários podem usar a página [Locais](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/locations-manager) (em [!UICONTROL Componentes] > Locais) para exibir e gerenciar todas as contas e locais que criarem, independentemente de onde tiverem sido criados. <p>Antes, a página [!UICONTROL Locais] aplicava-se somente às contas criadas para importar dados com [!UICONTROL conjuntos de classificações].</p>**Alterações ao gerenciar locais do [!UICONTROL data warehouse] ou de [!UICONTROL conjuntos de classificações]**<p>Ao gerenciar locais em uma determinada área do aplicativo ([!UICONTROL data warehouse] ou [!UICONTROL conjuntos de classificações]), somente os locais criados nessa área específica do aplicativo estão disponíveis. Por exemplo, ao visualizar a área do aplicativo do [!UICONTROL data warehouse], somente locais do [!UICONTROL data warehouse] estão disponíveis. Todas as contas ainda estarão disponíveis em cada área do aplicativo, independentemente da área do aplicativo na qual foram criadas. Antes, todas as contas e locais estavam disponíveis em cada área do aplicativo, independentemente da área do aplicativo na qual haviam sido criados. Isso ainda ocorre ao visualizar a área do aplicativo dos [!UICONTROL feeds de dados]. | | 17 de abril de 2024 |
| **Admins podem gerenciar todos os locais e contas da organização** | Uma nova opção na guia “Locais” (na página Componentes > Locais) permite que admins visualizem e gerenciem todos os locais da organização.<p>Uma nova opção na guia [Contas de locais](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/locations-manager) (na página Componentes > Locais) permite que administradores visualizem e gerenciem todas as contas da organização.</p> <p>Anteriormente, administradores podiam apenas visualizar e gerenciar os locais e contas que haviam criado.</p> |  | 17 de abril de 2024 |
| **Aumento nos limites padrão de tráfego baixo** | Em **meados de abril de 2024**, a Adobe começará a aumentar os limites padrão de tráfego baixo para conjuntos de relatórios da seguinte maneira: ![limites de tráfego baixo](assets/thresholds.png) isso afetará somente as variáveis que estão definidas abaixo dos novos limites. Essas alterações serão feitas de forma incremental e esperamos que o trabalho seja concluído até o **fim de maio**. À medida que esses aumentos forem implementados, você poderá notar alterações nas variáveis de alta cardinalidade:<ul><li>Mais valores de dimensão podem estar disponíveis para relatórios.</li><li>Segmentos e métricas calculadas podem incluir mais dados.</li><li>Os conjuntos de relatórios virtuais baseados em segmentos podem incluir mais dados.</li><li>As exportações de classificação podem incluir mais dados.</li></ul> | Meados de abril de 2024 | 31 de maio de 2024 |
| **O Activity Map usa menos chamadas de servidor para o SDK da web** | Atualmente, os eventos de link do Activity Map são contados como eventos separados e acarretam cobranças adicionais. <p>Esse aprimoramento seleciona alguns eventos de link e os reúne na próxima ocorrência, de modo semelhante a como os eventos são tratados pelo AppMeasurement.</p> |  | 31 de maio de 2024 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção dos seguintes problemas de classificação: AN-343439; AN-343503; AN-343504; AN-343986; AN-344262; AN-344564; AN-345204; AN-345234
* Correção dos seguintes problemas do construtor de regras de classificação: AN-341488; AN-342501; AN-345751
* Correção do seguinte problema dos alertas inteligentes: AN-343466;
* Correção do seguinte problema de segmentação: AN-342313
* Correção do seguinte problema do data warehouse: AN-344292
* Correção dos seguintes problemas dos feeds de dados: AN-339545; AN-340092; AN-342124; AN-342862; AN-343737; AN-344035; AN-344329; AN-344703; AN-344721; AN-344940; AN-345180; AN-345196; AN-345225; AN-345236; AN-345326; AN-345631; AN-345659
* Correção do seguinte problema das fontes de dados: AN-343541
* Correção dos seguintes problemas do Analysis Workspace: AN-336303; AN-336472; AN-338422; AN-338556; AN-339718; AN-340147; AN-340301; AN-340421; AN-340951; AN-341172; AN-342905; AN-342909; AN-343448; AN-343570; AN-344050; AN-344182; AN-344763; AN-344768;
* Correção dos seguintes problemas do administrador do Analytics: AN-342519; AN-342523; AN-343623; AN-343882; AN-344237; AN-344829; AN-345235;
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
