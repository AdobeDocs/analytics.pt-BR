---
description: Saiba mais sobre as diretrizes e recomendações para o consentimento dos usuários ao armazenamento ou à leitura de cookies não essenciais em dispositivos ou navegadores.
title: Quais são as diretrizes da CNIL para consentimento e cookies do usuário?
translation-type: ht
source-git-commit: c5ebc92622e012699d64c27701b24a88429e9f4f
workflow-type: ht
source-wordcount: '504'
ht-degree: 100%

---


# Isenção de consentimento da CNIL

Em 1º de outubro de 2020, a Autoridade Francesa de Proteção de Dados (a &quot;CNIL&quot;) publicou uma versão revisada de suas diretrizes de cookies (as &quot;Diretrizes&quot;) e de suas recomendações finais sobre como obter o consentimento dos usuários ai armazenamento ou à leitura de cookies não essenciais e tecnologias similares em dispositivos ou navegadores de usuários (as &quot;Recomendações&quot;).

As Diretrizes preveem uma isenção limitada do requisito de consentimento (&quot;Isenção de consentimento&quot;). A Isenção de consentimento aplica-se a cookies de análise cuja finalidade é limitar-se a medir o público-alvo do site ou aplicativo somente em nome do editor da Web. As Diretrizes estabelecem que, para que a Isenção do consentimento seja aplicável, as seguintes condições devem ser implementadas:

* 25 meses de retenção máxima.  Você pode examinar suas configurações atuais de retenção de dados em Analytics > Admin > Governança de dados.  [Retenção de dados](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=pt-BR)
* Limite de cookies de 13 meses.  Você pode substituir a expiração do cookie do Analytics usando a variável `cookieLifetime`.  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=pt-BR)
* Escopo limitado. O escopo do cookie deve ser limitado a um único site ou aplicativo. [Cookies do navegador](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=pt-BR&quot;\l&quot;third-party-cookie-implementations)
* Anonimização. Torne anônimo o último octeto do endereço IP. [Configurações gerais da conta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=pt-BR)
* Oculte a ID de visitante dos relatórios.  Por padrão, as IDs de visitante não estão visíveis no Adobe Workspace e no Adobe Reports and Analytics.  As IDs de visitante estão disponíveis nos Feeds de dados e no Data Warehouse.  O acesso aos Feeds de dados e ao Data Warehouse pode ser limitado pelas [Permissões de acesso no Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR&quot;\l&quot;task_040673FE3E3E429B9531FBCB8B6A4391)
* Parâmetros de geolocalização. A geolocalização não pode ser mais precisa do que o nível de código postal. [Opção de CEP](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=pt-BR&quot;\l&quot;zip-in-adobe-experience-platform-launch) e [Configurações gerais da conta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=pt-BR&quot;\l&quot;admin-tools)
* Defina as opções de aceitação.  O Serviço de aceitação permite configurar os protocolos para o visitante a fim de determinar se você pode adicionar um cookie no dispositivo ou no navegador do usuário quando ele visitar o site. [Serviço de aceitação](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=pt-BR)
* Impedir compartilhamento de dados.  Para impedir o compartilhamento de dados com o Adobe Audience Manager, use a variável de contexto `opt.dmp` para [Relatórios de privacidade](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=pt-BR&quot;\l&quot;variables) para evitar que as ocorrências sejam compartilhadas.
* Capacidade de acesso e exclusão. Utilize o Privacy Service para acessar e excluir solicitações. [Analytics e Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=pt-BR)

## Considerações adicionais para a coleta de dados

As seguintes considerações adicionais são aplicáveis:

* Nenhuma medição fora do site ou aplicativo sem consentimento prévio, por exemplo, nenhuma campanha fora do site, campanhas de email ou iFrames.
* A coleta de informações pessoais em variáveis não é permitida sem consentimento.
* Os dados só devem ser utilizados para produzir estatísticas anônimas, sem combinação com outros dados.
* Os dados não são usados para ações de referência cruzada.
* Os dados de geolocalização do GPS não são coletados.

Para obter mais informações, consulte o site [Isenção de cookies da CNIL](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
