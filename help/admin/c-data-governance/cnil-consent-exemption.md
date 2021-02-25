---
description: Saiba mais sobre as diretrizes e recomendações para o consentimento dos usuários em armazenar ou ler cookies não essenciais em dispositivos ou navegadores.
title: Quais são as diretrizes da CNIL para consentimento e cookies do usuário?
translation-type: tm+mt
source-git-commit: c5ebc92622e012699d64c27701b24a88429e9f4f
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---


# Isenção de Consentimento CNIL

Em 1º de outubro de 2020, a Autoridade Francesa de Proteção de Dados (CNIL) publicou uma versão revisada de suas diretrizes de cookies (as &quot;Diretrizes&quot;) e suas recomendações finais sobre como obter o consentimento dos usuários em armazenar ou ler cookies não essenciais e tecnologias similares em dispositivos ou navegadores de usuários (o &quot;Recommendations&quot;).

As Orientações preveem uma isenção limitada do requisito de consentimento (&quot;Isenção de consentimento&quot;). A Isenção de consentimento aplica-se a cookies de análise cuja finalidade é limitar-se a medir a audiência do site ou aplicativo somente em nome do editor da Web. As Orientações estabelecem que, para que a isenção do consentimento seja aplicável, devem ser aplicadas as seguintes condições:

* 25 meses de retenção máxima.  Você pode revisar suas configurações atuais de retenção de dados em Analytics > Admin > Controle de dados.  [Retenção de dados](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* Limite de cookies de 13 meses.  Você pode substituir a expiração do cookie do Analytics usando a variável `cookieLifetime`.  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html)
* Âmbito limitado. O escopo do cookie deve ser limitado a um único site ou aplicativo. [Cookies do navegador](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en&quot;\l&quot;cookie-implementações de terceiros)
* Anonimização. Anônimo do último octeto do endereço IP. [Configurações gerais da conta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* Ocultar a ID do visitante do relatórios.  Por padrão, as IDs de visitante não estão visíveis na Adobe Workspace e no Adobe Reports and Analytics.  As IDs de visitante estão disponíveis nos Feeds de dados e na Data Warehouse.  O acesso aos feeds de dados e à Data Warehouse pode ser limitado por [Permissões de acesso em Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en&quot;\l&quot;tarefa_040673FE3E3E429B9531FBCB8B6A4391)
* Parâmetros de geolocalização. A localização geográfica não pode ser mais precisa do que o nível de código postal. [Configurações ](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en&quot;\l&quot;zip-in-adobe-experience-platform-launch) de conta  [geral e opção CEP](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en&quot;\l&quot;admin-tools)
* Defina as opções de aceitação.  O serviço de aceitação permite definir protocolos de visitante para determinar se você pode definir um cookie no dispositivo ou navegador do usuário ao visitar seu site. [Serviço de aceitação](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Impedir compartilhamento de dados.  Para impedir o compartilhamento de dados com o Adobe Audience Manager, use a variável de contexto `opt.dmp` para [Relatórios de privacidade](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en&quot;\l&quot;variables) para impedir que as ocorrências sejam compartilhadas.
* Capacidade de acesso e exclusão. Utilize a Privacy Service para acessar e excluir solicitações. [Analytics e Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## Considerações adicionais para a coleta de dados

As seguintes considerações adicionais são aplicáveis:

* Nenhuma medição fora do site ou aplicativo sem consentimento prévio, por exemplo, nenhuma campanha fora do site, campanhas de email ou iFrames.
* A coleta de informações pessoais em variáveis não é permitida sem consentimento.
* Os dados só devem ser utilizados para produzir estatísticas anônimas, sem combinação com outros dados.
* Os dados não são usados para ações de referência cruzada.
* Os dados de localização geográfica do GPS não são coletados.

Para obter mais informações, consulte o site [Isenção de cookies CNIL](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
