---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: adbd342948ce3c38107a86613d77a9bf90a7df97
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 90%

---

# Notas de versão atuais do Adobe Analytics (lançamento em junho de 2025)

**Última atualização**: quarta-feira, 24 de junho de 2025

Essas notas de versão abrangem o período de lançamento de 18 de junho a 15 de julho de 2025. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Suporte para destinos em nuvem seguros no novo Report Builder** | O complemento Javascript Report Builder agora é compatível com a exportação de relatórios para os seguintes destinos de armazenamento na nuvem:<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>Anteriormente, somente destinos FTP e de email estavam disponíveis. O FTP não é mais compatível devido a preocupações de segurança.</p><p>Para obter mais informações, consulte [Agendar pastas de trabalho exportando para destinos na nuvem](/help/analyze/report-builder/report-builder-export.md).</p><p>Além dessas alterações, ao criar um local no Adobe Analytics, o campo Usar com agora fornece a opção de usar o local com o Report Builder, conforme descrito em [Configurar locais de importação e exportação da nuvem](/help/components/locations/configure-import-locations.md).</p> |  | 19 de junho de 2025 (originalmente 18 de junho) |
| **Nova experiência de visualização** | O painel usado para visualizar segmentos, métricas calculadas, entre outras coisas, agora usa uma visualização de barra horizontal, em vez de uma visualização de rosca. |  | 18 de junho de 2025 |
| **Caixa de diálogo do modelo de atribuição modificada** | Agora você pode definir o container e o período separadamente na caixa de diálogo do modelo de atribuição. |  | 18 de junho de 2025 |
| **Navegação atualizada na interface de Atributos do cliente** | A interface de Atributos do cliente agora pode ser acessada diretamente do seletor de aplicativos na Adobe Experience Cloud. |  | A ser determinado |
| **Mídia de transmissão: suporte a dados de programação** | Agora você pode fazer upload dos dados programados de conteúdo antigo de mídias de transmissão ao vivo para rastrear com mais facilidade e precisão o número de visualizadores. Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:<ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. Você pode até coletar dados de número de visualizadores para tópicos ou segmentos de programa específicos. Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.<p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo, e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais. Saiba mais |  | 15 de agosto de 2025 (originalmente 25 de junho de 2025) |

## Correções no Adobe Analytics

**A4T**: AN-379045
**Advertising Analytics**: AN-377338
**Alertas**: AN-377229
**Analysis Workspace**: AN-378891; AN-379589; AN-379604; AN-381270; AN-382264; AN-382414;
**API 1.4**: AN-380188
**API 2.0**: AN-373078; AN-379006; AN-381248
**Classificações**: AN-379209; AN-379315; AN-379567; AN-379573; AN-379749; AN-379764; AN-379818; AN-380433; AN-381670; AN-381751; AN-381994; AN-382055; AN-382682; AN-383059; AN-383409
**Análise de contribuição**: AN-369822
**Feeds de dados**: AN-365552; AN-367158; AN-378288; AN-379754; AN-380433; AN-380855; AN-380959; AN-381115; AN-381657; AN-381931
**Data Warehouse**: AN-379244
**Plataforma**: AN-375847
**Regras de processamento**: AN-375157
**Report Builder**: AN-371395; AN-372174; AN-373815; AN-383194
**Chamadas do servidor**: AN-380930
**Logs de uso e acesso**: AN-372130; AN-382123
**Conjuntos de relatórios virtuais**: AN-382010


## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Report Builder legado** | 18 de junho de 2025 | O complemento do Report Builder legado será removido em junho de 2026. Todos os usuários devem começar a atualizar suas pastas de trabalho legadas para o [novo Report Builder](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/report-builder/rb-overview). O novo Report Builder está disponível para clientes do Adobe Analytics e do Customer Journey Analytics. Ele tem [quase todos os recursos da versão anterior](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks#unsupported), além de muitos novos recursos e melhorias convenientes para a interface. Para facilitar o processo de atualização, o novo Report Builder inclui um recurso fácil de conversão de pastas de trabalho. O novo Report Builder está disponível somente como complemento por meio da Microsoft Store. Muitas organizações exigem um processo de aprovação interna para que o complemento possa ser disponibilizado aos usuários. Reserve tempo para esse processo e comece a trabalhar com sua organização agora para garantir que tenha tempo suficiente para atualizar suas pastas de trabalho antes do fim da vida útil. |
| **Acesso via domínios herdados ou via SSO herdado** | 10 de abril de 2025 | A Adobe planeja atualizar como os usuários acessam o Adobe Analytics para melhorar a segurança e simplificar a sua experiência de logon. Como parte dessa iniciativa, o acesso por meio de domínios herdados ou de um SSO herdado, incluindo `my.omniture.com`, será descontinuado permanentemente em **2 de janeiro de 2026**. Após essa data, as credenciais de logon herdadas e o SSO herdado não funcionarão mais. Todos os usuários precisarão fazer logon via `experience.adobe.com`, usando suas IDs da Adobe Experience Cloud. Se precisar de assistência com o sua ID da Experience Cloud, entre em contato com o administrador do Adobe Analytics da sua organização ou com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/contact.html). |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 17 de janeiro de 2025 | Os clientes da API do Adobe Analytics e da transmissão ao vivo que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até **30 de junho de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |



## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement, consulte as [notas de versão do AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de versão anteriores para 2025](/help/release-notes/2025.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recente para [produtos da Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
