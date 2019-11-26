---
description: Permite que você controle o acesso aos dados de relatório. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email.
solution: Analytics
title: Gerenciador de segurança
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 229ce50a24bd7b86e3859775bb4fbeba1c6a5668

---


# Gerenciador de segurança

Permite que você controle o acesso aos dados de relatório. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; Configurações **** da empresa &gt; **[!UICONTROL Segurança]**

<table id="table_F1AD9DE5094A4FC2B9DA8D01198F944B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Exigir senhas de alta segurança </span> </td> 
   <td colname="col2">Faz com que os usuários criem senhas mais seguras que sigam as seguintes regras: 
    <ul id="ul_100CC57EB4374DAA87B2074BA8B46F26"> 
     <li id="li_4D9102C361044FADBC14402A8398F2F3">Deve ter pelo menos oito caracteres de comprimento. </li> 
     <li id="li_AFE9568C14894E93BFDFDC84DCD2838D">Ter, pelo menos, um símbolo/caractere numérico entre o primeiro e o último caractere. </li> 
     <li id="li_ECA05BEF7BFD4430B09D4A953B41D2A6">Ter pelo menos um caractere alfa. </li> 
     <li id="li_6928045588E94E28851BB15991C8D51E">Não pode ser encontrada em um dicionário nem conter palavras de um dicionário (inglês). </li> 
     <li id="li_C3DD4608CA6F43E4B1E4FCFC6D116371">Não pode incluir 3 (três) caracteres consecutivos do nome de usuário do logon. </li> 
     <li id="li_687838CA01B94EE29EF4C09F485C5537">Deve ser diferente das 10 senhas anteriores. </li> 
    </ul> <p>Observação: Esse recurso é empregado em novas senhas subsequentes. Não verifica senhas existentes nem força os usuários a alterarem as senhas existentes. Por isso, considere ativar a expiração da senha para forçar os usuários a alterarem suas senhas e aderirem às regras de senhas de alta segurança. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Expiração da senha</span> </td> 
   <td colname="col2"> Faz com que os usuários mudem regularmente a senha de suas contas de usuário. É possível especificar o intervalo em que deseja que as senhas expirem e fazer as senhas expirarem imediatamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Impor restrições de logon de IP</span> </td> 
   <td colname="col2"> <p>(Essa funcionalidade não pode ser usada juntamente com o logon da Experience Cloud. Observe que essa funcionalidade não estará mais disponível a partir de outubro de 2020.) Limita o acesso a relatórios de determinados endereços IP ou intervalos de endereço IP. </p> <p>Você pode adicionar até 100 entradas na lista de Filtros de endereço IP, e cada entrada precisa ser um endereço específico ou um intervalo de endereços. </p> <p> <span class="wintitle"> Impor restrições de logon de IP</span> não é aplicado até que haja pelo menos uma entrada na lista de Filtro de endereço IP. </p> <p> <span class="uicontrol"> Endereço IP aceito</span>: Para especificar um intervalo de endereço IP, coloque o intervalo entre parênteses (por exemplo, 
     <code>
       192.168.10.[20-240]
     </code>). Também é possível usar curingas (*) para especificar qualquer número de 0 a 255 (por exemplo, 
     <code>
       192.168.[10-14].*
     </code>) </p> <p>Falhas no logon são registradas e visualizadas no <a href="/help/admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232">Log de uso e acesso</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Impor restrições de domínio de email</span> </td> 
   <td colname="col2"> <p>Filtra os domínios e endereços de email em que o Analytics envia marcadores, relatórios para download e alertas. </p> <p>A lista de filtro de email oferece suporte a até 100 entradas e cada entrada pode ser um endereço de email ou todo um domínio de email. </p> <p>Se um relatório programado tiver um destino de email não aprovado, o Analytics envia uma notificação por email sobre o problema e um link para desprogramar o relatório. </p> <p> <span class="wintitle"> Impor restrições de domínio de email</span> não é empregado até que exista pelo menos uma entrada na lista de <span class="wintitle">Filtro de domínio de email aceito</span>. </p> <p> <span class="uicontrol"> Domínios e endereços de email aceitos</span>: Para especificar um intervalo de endereço IP, coloque o intervalo entre parênteses (por exemplo, 
     <code>
       192.168.10.[20-240]
     </code>). Também é possível usar curingas (*) para especificar qualquer número de 0 a 255 (por exemplo, 
     <code>
       192.168.[10-14].*
     </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Notificação de recuperação de senha</span> </td> 
   <td colname="col2"> <p>Notifica os administradores especificados sobre quando um usuário tenta redefinir a senha de uma conta de usuário. </p> <p> <span class="uicontrol"> Admins disponíveis</span>: exibe todos os administradores. Você pode clicar e ao mesmo tempo pressionar Ctrl ou Shift para selecionar vários administradores. </p> <p> <span class="uicontrol">Membros de email</span>: exibe o grupo de email definido no momento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fim da vida útil para [!UICONTROL impor restrições de logon de IP]

O recurso **[!UICONTROL Impor restrições]** de logon de IP é um recurso do Brevemente herdado do Analytics que permite a lista de permissões de endereços IP específicos considerados seguros para permitir logons bem-sucedidos e acesso ao ambiente do Adobe Analytics. Em muitos casos, esse recurso é usado para configurar um endereço IP corporativo como o único endereço IP seguro do qual os usuários podem fazer logon. Portanto, para usar o Adobe Analytics, isso requer que os usuários estejam em um escritório corporativo ou façam logon na rede via VPN.

### Por que estamos considerando isso para o fim da vida?

Esse recurso é dividido em algumas circunstâncias pela migração de logon da Experience Cloud e/ou pelo logon da Experience Cloud. Sabe-se que é quebrado para clientes que usam Atributos **[!UICONTROL do]** cliente ou Biblioteca **[!UICONTROL de]** público-alvo.

Além disso, se você tiver várias Soluções da Experience Cloud, poderá circunscrever esse requisito fazendo logon na Experience Cloud com uma das outras soluções, pois esse recurso não existe ou não é suportado fora do Analytics. Os usuários também podem contornar isso via falsificação de IP.

Por fim, a Adobe tem uma solução alternativa funcional e muito superior por meio do logon único e das Federated ID. Este recurso oferece maior controle e segurança sobre a experiência de logon dos usuários.

### Como a remoção deste recurso afeta você?

Para qualquer cliente que tenha **[!UICONTROL restrições]** de logon de IP definidas, esse recurso será removido em outubro de 2020. Nesse momento, quaisquer restrições de logon de IP ainda em vigor não serão mais aplicadas. Se você ainda precisar restringir o logon por endereço IP, deverá revisar e implementar a solução recomendada de Logon único e Federated IDs (mais informações e recursos abaixo).

Além disso, o gerenciador **[!UICONTROL Impor restrições]** de logon de IP será removido do **[!UICONTROLAadministrador &gt; Configurações da empresa &gt; Gerenciador]** de segurança na interface do usuário do Analytics (como mostrado abaixo).

![](assets/sec-manager2.png)

### Quais são suas outras opções?

Como mencionado acima, esse recurso do Analytics será encerrado. Para dar a você tempo para implementar SSO e Federated IDs, adiamos a data EOL para outubro de 2020.

As IDs SSO e Federated são soluções superiores ao recurso Restrição de logon de IP que temos em vigor hoje e fornecerão mais controle, segurança e recursos.

Para obter informações sobre como configurar SSO/Federated IDs, temos a seguinte documentação de ajuda disponível. Recomendamos que você os leia minuciosamente e trabalhe com seu departamento de TI para implementá-los:

* [Logon único e a Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Console admin. - Documentação de configuração de identidade](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [Admin Console - Tutorial de configuração de identidade (vídeo)](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Configurar tutorial da Federated ID (vídeo)](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Logon único - perguntas comuns](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Tipos de identidade suportados pela Adobe](https://helpx.adobe.com/enterprise/using/identity.html)

Se você quiser continuar a expressar seu suporte para Restrições de logon de IP e solicitar que ele seja fornecido pela Experience Cloud, poderá votar nesse recurso na página [do](https://forums.adobe.com/ideas/11648)Fórum. Para mais perguntas ou informações sobre SSO/Federated ID e EXC, contacte Ryan Monger (monger@adobe.com).
