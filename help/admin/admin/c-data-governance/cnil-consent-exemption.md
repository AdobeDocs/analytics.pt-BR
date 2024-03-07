---
description: Saiba mais sobre as diretrizes e recomendações para o consentimento dos usuários ao armazenamento ou à leitura de cookies não essenciais em dispositivos ou navegadores.
title: Quais são as diretrizes da CNIL para consentimento e cookies do usuário?
feature: Data Governance
role: Admin
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 96%

---

# Isenção de consentimento da CNIL

Em 1º de outubro de 2020, a Autoridade Francesa de Proteção de Dados (a “CNIL”) publicou uma versão revisada de suas diretrizes de cookies (as “Diretrizes”) e de suas recomendações finais sobre a obtenção do consentimento dos usuários para armazenar ou ler cookies não essenciais e tecnologias semelhantes nos dispositivos ou navegadores dos usuários (as “Recomendações”).

As Diretrizes fornecem uma isenção limitada do requisito de consentimento (“Isenção de consentimento”). A Isenção de consentimento aplica-se a cookies de análise cuja finalidade é limitar-se a medir o público-alvo do site ou aplicativo somente em nome do editor da Web. As Diretrizes estabelecem que, para que a Isenção do consentimento seja aplicável, as seguintes condições devem ser implementadas:

* 25 meses de retenção máxima.  Você pode revisar suas configurações atuais de retenção de dados em [!UICONTROL Analytics] > [!UICONTROL Administrador] > [!UICONTROL Governança de dados].  [Retenção de dados](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=pt-BR)
* Desative cookies de terceiros na ECID. [disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=pt-BR#id-service-api), [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=pt-BR#id-service-api) e [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=pt-BR#id-service-api)
* Limite de cookies de 13 meses.  Você pode substituir a expiração do cookie do Analytics usando a variável `cookieLifetime`.  Os cookies da Experience Cloud, incluindo o Analytics e a ECID, estendem a data de expiração do cookie com cada visita.  Para definir uma expiração de cookie estática e não cumulativa, é possível: (1) gravar o código personalizado para definir uma data na qual excluir o cookie ou (2) usar sua CMP para controlar a data da redefinição do cookie.   [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=pt-BR) e [Cookies da Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=pt-BR#ec-cookies)
* Escopo limitado. O escopo do cookie deve ser limitado a um único site ou aplicativo. [Cookies do navegador](https://experienceleague.adobe.com/docs/analytics/technotes/cookies/cookies.html#third-party-cookie-limitations)
* Anonimização. Torne anônimo o último octeto do endereço IP. [Configurações gerais da conta](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
* Oculte a ID de visitante dos relatórios.  Por padrão, as IDs de visitante não estão visíveis no Adobe Workspace e no Adobe Reports and Analytics.  As IDs de visitante estão disponíveis nos Feeds de dados e no Data Warehouse.  O acesso aos Feeds de dados e ao Data Warehouse pode ser limitado por [Permissões de acesso no Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=pt-BR) e [Referência da coluna Feed de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR#columns%2C-descriptions%2C-and-data-types)
* Parâmetros de geolocalização. A geolocalização não pode ser mais precisa do que o nível de código postal. [Opção de CEP](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html) e [Configurações gerais da conta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=pt-BR)
* Defina as opções de aceitação.  O serviço de aceitação permite definir protocolos de visitante para determinar se você pode definir um cookie no dispositivo ou navegador do usuário que visita seu site. [Serviço de aceitação](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=pt-BR)
* Impedir compartilhamento de dados.  Para impedir o compartilhamento de dados com o Adobe Audience Manager, use a variável de contexto `opt.dmp` para [Relatórios de privacidade](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) para evitar que as ocorrências sejam compartilhadas.
* Capacidade de acesso e exclusão. Utilize o Privacy Service para acessar e excluir solicitações. [Analytics e Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=pt-BR)

## Considerações adicionais para a coleta de dados

As seguintes considerações adicionais são aplicáveis:

* O Adobe Analytics opera centros de processamento de dados nos Estados Unidos, Reino Unido e Singapura para fornecer flexibilidade a todos os clientes para que possam coletar, processar e armazenar seus dados regionalmente. Ao realizar a configuração inicial do Adobe Analytics, os clientes selecionam o local do centro de processamento de dados desejado. Os dados dos clientes são armazenados na região selecionada para o produto principal do Analytics.
* Considere coletar o status de aceitação em uma variável do Analytics para separar os dados de aceitação dos dados de rejeição para segmentação, conjuntos de relatórios virtuais ou rotear para pontos finais separados.
* Nenhuma medição fora do site ou aplicativo sem consentimento prévio, por exemplo, nenhuma campanha fora do site, campanhas de email ou iFrames.
* A coleta de informações pessoais em variáveis não é permitida sem consentimento. [Controlar atividades da Experience Cloud com base no consentimento do usuário](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html#implementing-opt-in-on-the-page)
* Os dados só devem ser utilizados para produzir estatísticas anônimas, sem combinação com outros dados.
* Os dados não são usados para ações de referência cruzada.
* Os dados de geolocalização do GPS não são coletados.
* Quando o usuário final der o consentimento, as configurações acima poderão ser modificadas e as restrições relaxadas.

>[!IMPORTANT]
>
>Este documento não se destina a ser um aconselhamento jurídico ou regulamentar e não constitui garantia ou compromisso contratual por parte da Adobe. Recomendamos que os clientes procurem aconselhamento jurídico independente sobre as obrigações legais e regulamentares dos clientes em questões relacionadas a este assunto.


Para obter mais informações, consulte o site [Isenção de cookies da CNIL](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).

