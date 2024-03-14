---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7cb7953e3321f2e8fa814ef6f1607cbe8d0f44de
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 27%

---

# Notas de versão atuais do Adobe Analytics (março de 2024)

**Última atualização**: quinta-feira, 13 de março de 2024

Essas notas de versão abrangem o período de lançamento de 12 de março de 2024 a abril de 2024. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **atualização do AppMeasurement** | [Versão do AppMeasurement v2.26.0](/help/implement/appmeasurement-updates.md) está disponível. | | terça-feira, 4 de março de 2024 |
| **Nova coluna disponível na página inicial de Projetos** | A variável **[!UICONTROL Usado pela última vez]** agora está disponível ao visualizar a guia Projetos na [Página de aterrissagem do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=pt-BR). <p>Essas informações podem ajudar você a determinar se um projeto é valioso para os usuários em sua organização, mostrando a data e a hora em que o projeto foi aberto pela última vez.</p> <p>Anteriormente, a variável **[!UICONTROL Usado pela última vez]** A coluna estava disponível somente no Gerenciador de métricas calculadas, no Gerenciador de segmentos e no Gerenciador de alertas.</p> |  | quinta-feira, 13 de março de 2024 |
| **Suporte do Analytics para sinalizadores de consentimento exigidos pelo Google para DMA** | Devido às novas regulamentações europeias de privacidade, o Google exige que os dados coletados na Europa que foram enviados a eles indiquem se dois tipos específicos de consentimento foram concedidos. **A partir de 6 de março**, a Google não aceitará mais dados de evento que não indiquem que o consentimento relevante foi concedido. A Adobe Analytics lançou suporte para capturar esses dados por meio de uma nova variável adConsent. É possível ver a nova variável listada no [Interface do usuário de relatórios de privacidade](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). Se você quiser ativar essa opção e já tiver a privacidade ativada para as variáveis de consentimento anteriores, será necessário ativar a privacidade novamente. |  | quinta-feira, 13 de março de 2024 |
| **Usar as mesmas contas de nuvem para Feeds de dados, Data Warehouse e conjuntos de classificação** | As contas e os locais em nuvem que você cria agora podem ser usados para exportar dados (com Feeds de dados e Data Warehouse) e importar dados (com conjuntos de classificação).<p> **Alterações ao configurar contas:** Os usuários podem Configurar contas de importação e exportação na nuvem e Configurar locais de importação e exportação na nuvem que podem ser usados para qualquer uma das seguintes finalidades:<ul><li>Importação de dados com conjuntos de classificações</li><li>Exportação de dados com feeds de dados</li><li>Exportar dados com o Data Warehouse.</li></ul><p>**Alterações ao gerenciar contas**: os usuários podem usar a página Locais (em Componentes > Locais) para exibir e gerenciar todas as contas e locais que criam, independentemente de onde foram criados. <p>Anteriormente, a página Locais era aplicada somente às contas criadas para importar dados com conjuntos de classificações.</p> | | Abril de 2024 |
| **Os administradores podem gerenciar todos os locais em sua organização** | Uma nova opção na página Locais permite que os administradores visualizem e gerenciem todos os locais na organização. <p>Anteriormente, os administradores podiam visualizar e gerenciar apenas os locais que criavam.</p> |  | Abril de 2024 |
| **O Activity Map usa menos chamadas de servidor para o SDK da Web** | Atualmente, os eventos de link de Activity Map são contados como seus próprios eventos e incorrem em custo extra. <p>Esse aprimoramento pega alguns eventos de link e os empacota na próxima ocorrência, de modo semelhante a como os eventos são tratados pelo AppMeasurement.</p> |  | quinta-feira, 3 de abril de 2024 |
| **Aumento nos limites padrão de tráfego baixo** | Entrada **meados de abril de 2024**, o Adobe começará a aumentar os limites de tráfego baixo do conjunto de relatórios padrão da seguinte maneira: ![limites de tráfego baixo](assets/thresholds.png) Isso afetará somente as variáveis que estão definidas abaixo dos novos limites. Essas alterações serão feitas de forma incremental, e esperamos que o trabalho seja concluído pela **fim de maio**. À medida que esses aumentos forem implementados, você poderá notar alterações nas variáveis de alta cardinalidade:<ul><li>Mais valores de dimensão podem estar disponíveis para relatórios.</li><li>Segmentos e métricas calculadas podem incluir mais dados.</li><li>Os conjuntos de relatórios virtuais baseados em segmentos podem incluir mais dados.</li><li>As exportações de classificação podem incluir mais dados.</li></ul> | | Meados de abril de 2024 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção dos seguintes problemas de classificações: AN-335632; AN-337559; AN-340164; AN-340370; AN-341089; AN-341211; AN-341284; AN-341469; AN-341481; AN-341 1760; AN-341778; AN-342144; AN-342258; AN-342338, AN-342400
* Correção dos seguintes problemas do Construtor de regras de classificações: AN-340921; AN-341269; AN-341292; AN-341467; AN-341666; AN-342145; AN-342329
* Correção do seguinte problema de Alertas inteligentes: AN-340736
* Correção do seguinte problema de segmentação: AN-336242
* Correção dos seguintes problemas de Data Warehouse: AN-335354; AN-339446; AN-339774; AN-340221; AN-340599; AN-341277; AN-342009; AN-342088; AN-342592
* Correção dos seguintes problemas de Feeds de dados: AN-335508; AN-340887; AN-341050; AN-341208; AN-341403; AN-341479; AN-341524; AN-341661; AN-342004; AN-342000 AN-342256; AN-342301; AN-342410; AN-342502; AN-342525
* Correção do seguinte problema de Report Builder: AN-340540
* Correção dos seguintes problemas do Analysis Workspace: AN-295889; AN-330981; AN-338818; AN-339730; AN-341114; AN-341520;

### Outras correções do Analytics

AN-312198; AN-338009; AN-339549; AN-333970; AN-334790; AN-336461; AN-336572; AN-339549; AN-341119; AN-341246; AN-341268; AN-341272; AN-341475; AN-341547; AN-341558; AN-341680; AN-342017;

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Adições de membros de objetos da API Adobe** | 17 de janeiro de 2024 | O Adobe pode adicionar membros opcionais de solicitação e resposta (pares de nome/valor) a objetos de API existentes a qualquer momento e sem aviso prévio ou alterações no controle de versão. A Adobe recomenda que você consulte a documentação da API de qualquer ferramenta de terceiros que você integre às nossas APIs para que essas adições sejam ignoradas no processamento, se não forem entendidas. Se implementadas corretamente, essas adições são alterações ininterruptas na implementação. A Adobe não removerá parâmetros nem adicionará parâmetros obrigatórios sem primeiro fornecer uma notificação padrão por meio de notas de versão. |
| **`getPageLoadTime`plug-in obsoleto** | 10 de janeiro de 2024 | Não há mais suporte para este plugin. Seu código utiliza o método performance.timing, que (de acordo com o MDN) foi [descontinuado](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Foi iniciado o trabalho em um plug-in atualizado. |

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
