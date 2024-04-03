---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: aac32bdda365ce4534f1d4c04e816eb6f03b991c
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 96%

---

# Notas de versão atuais do Adobe Analytics (março de 2024)

**Última atualização**: quinta-feira, 3 de abril de 2024

Essas notas de versão abrangem o período de lançamento de 12 de março de 2024 a abril de 2024. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Alteração no protocolo de exclusão para projetos do Workspace** | Anteriormente, os projetos excluídos nunca eram removidos do sistema. Agora, começaremos a limpar os projetos excluídos após 180 dias. Durante os 180 dias após a exclusão, os usuários ainda podem acessar um projeto excluído por meio da interface da Web se tiverem um URL para o projeto. | | 14 de março de 2024 |
| **Atualização do AppMeasurement** | A [versão v2.26.0 do AppMeasurement](/help/implement/appmeasurement-updates.md) está disponível. | | 4 de março de 2024 |
| **Nova coluna disponível na página de destino Projetos** | A coluna **[!UICONTROL Usado pela última vez]** agora está disponível ao visualizar a guia Projetos na [página de destino do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=pt-BR). <p>Essas informações podem ajudar você a determinar se um projeto é útil para os usuários em sua organização, mostrando a data e a hora em que ele foi aberto pela última vez.</p> <p>Anteriormente, a coluna **[!UICONTROL Usado pela última vez]** estava disponível apenas no gerenciador de métricas calculadas, no gerenciador de segmentos e no gerenciador de alertas.</p> |  | 13 de março de 2024 |
| **Suporte do Analytics para sinalizadores de consentimento exigidos pelo Google para a DMA** | Devido às novas regulamentações europeias de privacidade, o Google exige que os dados coletados na Europa e enviados a ele indiquem se dois tipos específicos de consentimento foram concedidos. **A partir de 6 de março**, o Google não aceitará mais dados de evento que não indiquem que o consentimento relevante foi concedido. O Adobe Analytics agora permite capturar esses dados por meio de uma nova variável adConsent. É possível ver a nova variável listada na [interface dos relatórios de privacidade](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). Se deseja ativar essa opção e já tiver habilitado a privacidade para as variáveis de consentimento anteriores, é necessário habilitar a privacidade novamente.<p>A [dimensão de consentimento da plataforma de publicidade](/help/components/dimensions/ad-consent.md) mostra se foi adquirido consentimento com respeito ao envio de dados a provedores de publicidade externos, como o Google. |  | 13 de março de 2024 |
| **Uso do Report Builder incluído na coluna “Usado em” no gerenciador de métricas calculadas e no gerenciador de segmentos** | Ao visualizar a coluna **Usado em** no gerenciador de métricas calculadas ou no gerenciador de segmentos, agora há dados de uso disponíveis para o Report Builder.<p>Anteriormente, os dados de uso disponíveis no gerenciador de segmentos eram relacionados apenas a alertas, projetos, projetos agendados e métricas calculadas, enquanto que os dados de uso do gerenciador de métricas calculadas eram relacionados apenas a alertas, projetos e projetos agendados.</p> |  | Julho |
| **Usar as mesmas contas de nuvem para feeds de dados, data warehouse e conjuntos de classificação** | As contas e os locais de nuvem que você criar agora poderão ser usados para exportar (com feeds de dados e o data warehouse) e importar dados (com conjuntos de classificação).<p> **Alterações na configuração de contas:** usuários podem configurar contas de importação e exportação na nuvem, bem como configurar locais de importação e exportação na nuvem que podem ser usados para qualquer uma das seguintes finalidades:<ul><li>Importação de dados com conjuntos de classificações</li><li>Exportação de dados com feeds de dados</li><li>Exportação de dados com o data warehouse.</li></ul><p>**Alterações no gerenciamento de contas**: usuários podem usar a página de locais (em Componentes > Locais) para exibir e gerenciar todas as contas e locais que criarem, independentemente de onde tiverem sido criados. <p>Anteriormente, a página de locais aplicava-se somente às contas criadas para importar dados com conjuntos de classificações.</p> | | Abril de 2024 |
| **Admins podem gerenciar todos os locais e contas da organização** | Uma nova opção na guia “Locais” (na página Componentes > Locais) permite que admins visualizem e gerenciem todos os locais da organização.<p>Uma nova opção na guia “Contas de locais” (na página Componentes > Locais) permite que admins visualizem e gerenciem todas as contas da organização.</p> <p>Anteriormente, admins podiam apenas visualizar e gerenciar os locais e contas que haviam criado.</p> |  | Abril de 2024 |
| **O Activity Map usa menos chamadas de servidor para o SDK da web** | Atualmente, os eventos de link do Activity Map são contados como eventos separados e acarretam cobranças adicionais.  <p>Esse aprimoramento seleciona alguns eventos de link e os reúne na próxima ocorrência, de modo semelhante a como os eventos são tratados pelo AppMeasurement.</p> |  | quinta-feira, 1 de maio de 2024 |
| **Aumento nos limites padrão de tráfego baixo** | Em **meados de abril de 2024**, a Adobe começará a aumentar os limites padrão de tráfego baixo para conjuntos de relatórios da seguinte maneira: ![limites de tráfego baixo](assets/thresholds.png) isso afetará somente as variáveis que estão definidas abaixo dos novos limites. Essas alterações serão feitas de forma incremental e esperamos que o trabalho seja concluído até o **fim de maio**. À medida que esses aumentos forem implementados, você poderá notar alterações nas variáveis de alta cardinalidade:<ul><li>Mais valores de dimensão podem estar disponíveis para relatórios.</li><li>Segmentos e métricas calculadas podem incluir mais dados.</li><li>Os conjuntos de relatórios virtuais baseados em segmentos podem incluir mais dados.</li><li>As exportações de classificação podem incluir mais dados.</li></ul> | | Meados de abril de 2024 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção dos seguintes problemas de classificação: AN-335632; AN-337559; AN-340164; AN-340370; AN-341089; AN-341211; AN-341284; AN-341469; AN-341481; AN-341760; AN-341778; AN-342144; AN-342258; AN-342338, AN-342400
* Correção dos seguintes problemas do construtor de regras de classificação: AN-340921; AN-341269; AN-341292; AN-341467; AN-341666; AN-342145; AN-342329
* Correção do seguinte problema dos alertas inteligentes: AN-340736
* Correção do seguinte problema de segmentação: AN-336242
* Correção dos seguintes problemas de data warehouse: AN-335354; AN-339446; AN-339774; AN-340221; AN-340599; AN-341277; AN-342009; AN-342088; AN-342592
* Correção dos seguintes problemas de feeds de dados: AN-335508; AN-340887; AN-341050; AN-341208; AN-341403; AN-341479; AN-341524; AN-341661; AN-342000; AN-342125; AN-342256; AN-342301; AN-342410; AN-342502; AN-342525
* Correção do seguinte problema do Report Builder: AN-340540
* Correção dos seguintes problemas do Analysis Workspace: AN-295889; AN-330981; AN-338818; AN-339730; AN-341114; AN-341520;

### Outras correções do Analytics

AN-312198; AN-338009; AN-339549; AN-333970; AN-334790; AN-336461; AN-336572; AN-339549; AN-341119; AN-341246; AN-341268; AN-341272; AN-341475; AN-341547; AN-341558; AN-341680; AN-342017;

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Prazo de 13 meses para a expiração do`cust_visids`** salvo | 20 de março de 2024 | Uma versão futura do mecanismo de processamento de ocorrências do Analytics, programada para abril ou maio, começará a impor um prazo de 13 meses para a expiração do `cust_visids` salvo. Se o conjunto de relatórios estiver com a opção “Habilitar identificação de visitantes” ativada, esta configuração será usada para encontrar o `cust_visid` para um `visid_high/visid_low value` que não contenha `cust_visid` na ocorrência. Atualmente, não há um prazo de expiração para o mapeamento de um `cust_visid` para um `visid_high/visid_low`. Com esta versão, o mapeamento expirará se 13 meses se passarem desde que `visid_high/visid_low` teve um `cust_visid` em uma ocorrência. |
| **Adições de membros de objetos da API da Adobe** | 17 de janeiro de 2024 | A Adobe pode adicionar membros opcionais de solicitação e de resposta (pares nome/valor) a objetos de API já existentes a qualquer momento e sem aviso prévio ou alterações no controle de versão. A Adobe recomenda consultar a documentação da API de qualquer ferramenta de terceiros que você decida integrar às nossas APIs, para que essas adições sejam ignoradas no processamento se não forem compreendidas. Se implementadas corretamente, essas adições são alterações que não interrompem a implementação. A Adobe não removerá parâmetros nem adicionará parâmetros obrigatórios sem primeiro fornecer uma notificação padrão por meio das notas de versão. |
| Plug-in **`getPageLoadTime`descontinuado** | 10 de janeiro de 2024 | Não há mais suporte para este plugin. Seu código utiliza o método performance.timing, que (de acordo com o MDN) foi [descontinuado](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Foi iniciado o trabalho em um plug-in atualizado. |

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
