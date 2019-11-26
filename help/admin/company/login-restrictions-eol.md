---
title: Fim da vida útil para [!UICONTROL impor restrições de logon de IP]
description: Saiba mais sobre a duração do fim da vida útil e as implicações para [!UICONTROL Impor restrições de logon de IP]
translation-type: tm+mt
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# Fim da vida útil para [!UICONTROL impor restrições de logon de IP]

O recurso **[Impor restrições](/help/admin/company/security-manager.md)** de logon de IP no Adobe Analytics permite que você inclua endereços IP específicos (considerados seguros) para permitir logons bem-sucedidos e acesso ao ambiente do Adobe Analytics. Em muitos casos, esse recurso é usado para configurar um endereço IP corporativo como o único endereço IP seguro do qual os usuários podem fazer logon. Portanto, para usar o Adobe Analytics, isso requer que os usuários estejam em um escritório corporativo ou façam logon na rede via VPN.

Estamos planejando o fim da vida útil desse recurso em outubro de 2020.

## Por que estamos acabando com essa característica?

Esse recurso é dividido em algumas circunstâncias pela migração de logon da Experience Cloud e/ou pelo logon da Experience Cloud. Sabe-se que é quebrado para clientes que usam Atributos **[!UICONTROL do]** cliente ou Biblioteca **[!UICONTROL de]** público-alvo.

Além disso, se você tiver várias Soluções da Experience Cloud, poderá circunscrever esse requisito fazendo logon na Experience Cloud com uma das outras soluções, pois esse recurso não existe ou não é suportado fora do Analytics. Os usuários também podem contornar isso via falsificação de IP.

Por fim, a Adobe tem uma solução alternativa funcional e muito superior por meio do logon único e das Federated ID. Este recurso oferece maior controle e segurança sobre a experiência de logon dos usuários. Consulte abaixo para obter mais informações.

## Como a remoção deste recurso afeta você?

Para qualquer cliente que tenha **[!UICONTROL restrições]** de logon de IP definidas, esse recurso será removido em outubro de 2020. Nesse momento, quaisquer restrições de logon de IP ainda em vigor não serão mais aplicadas. Se você ainda precisar restringir o logon por endereço IP, deverá revisar e implementar a solução recomendada de Logon único e Federated IDs (mais informações e recursos abaixo).

Além disso, a configuração **[!UICONTROL Impor restrições]** de logon de IP será removida de **[!UICONTROLAdmin &gt; Configurações da empresa &gt; Gerenciador]** de segurança na interface do usuário do Analytics (como mostrado abaixo).

![](assets/sec-manager2.png)

## Quais são suas outras opções?

Como mencionado acima, esse recurso do Analytics será encerrado. Para dar a você tempo para implementar SSO e Federated IDs, adiamos a data EOL para outubro de 2020.

As IDs SSO e Federated são soluções superiores ao recurso Restrição de logon de IP que temos em vigor hoje e fornecerão mais controle, segurança e recursos. Para obter informações sobre como configurar SSO/Federated IDs, temos a seguinte documentação de ajuda disponível. Recomendamos que você os leia minuciosamente e trabalhe com seu departamento de TI para implementá-los:

* [Logon único e a Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Console admin. - Documentação de configuração de identidade](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [Admin Console - Tutorial de configuração de identidade (vídeo)](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Configurar tutorial da Federated ID (vídeo)](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Logon único - perguntas comuns](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Tipos de identidade suportados pela Adobe](https://helpx.adobe.com/enterprise/using/identity.html)

Se você quiser continuar a expressar seu suporte para Restrições de logon de IP e solicitar que ele seja fornecido pela Experience Cloud, poderá votar nesse recurso na página [do](https://forums.adobe.com/ideas/11648)Fórum.