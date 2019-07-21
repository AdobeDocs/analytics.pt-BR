---
description: Permite que você controle o acesso aos dados de relatório. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email.
seo-description: Permite que você controle o acesso aos dados de relatório. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email.
seo-title: Gerenciador de segurança
solution: Analytics
title: Gerenciador de segurança
topic: Ferramentas administrativas
uuid: b 3 fbdba 0-e 2 bf -4 d 67-92 e 3-ef 05711141 d 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Gerenciador de segurança

Permite que você controle o acesso aos dados de relatório. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Configurações da empresa]** &gt; **[!UICONTROL Segurança]**

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
   <td colname="col2"> <p>Limita o acesso a relatórios de determinados endereços IP ou intervalos de endereço IP. </p> <p>Você pode adicionar até 100 entradas na lista de Filtros de endereço IP, e cada entrada precisa ser um endereço específico ou um intervalo de endereços. </p> <p> <span class="wintitle"> Impor restrições de logon de IP</span> não é aplicado até que haja pelo menos uma entrada na lista de Filtro de endereço IP. </p> <p> <span class="uicontrol"> Endereço IP aceito</span>: Para especificar um intervalo de endereços IP, coloque o intervalo entre parênteses (por exemplo, <code>
 
 192.168.10.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> <p>Falhas no logon são registradas e visualizadas no <a href="../../admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232" format="dita" scope="local">Log de uso e acesso</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Impor restrições de domínio de email</span> </td> 
   <td colname="col2"> <p>Filtra os domínios e endereços de email em que o Analytics envia marcadores, relatórios para download e alertas. </p> <p>A lista de filtro de email oferece suporte a até 100 entradas e cada entrada pode ser um endereço de email ou todo um domínio de email. </p> <p>Se um relatório programado tiver um destino de email não aprovado, o Analytics envia uma notificação por email sobre o problema e um link para desprogramar o relatório. </p> <p> <span class="wintitle"> Impor restrições de domínio de email</span> não é empregado até que exista pelo menos uma entrada na lista de <span class="wintitle">Filtro de domínio de email aceito</span>. </p> <p> <span class="uicontrol"> Domínios e endereços de email aceitos</span>: Para especificar um intervalo de endereços IP, coloque o intervalo entre parênteses (por exemplo, <code>
 
 192.168.10.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Notificação de recuperação de senha</span> </td> 
   <td colname="col2"> <p>Notifica os administradores especificados sobre quando um usuário tenta redefinir a senha de uma conta de usuário. </p> <p> <span class="uicontrol"> Admins disponíveis</span>: exibe todos os administradores. Você pode clicar e ao mesmo tempo pressionar Ctrl ou Shift para selecionar vários administradores. </p> <p> <span class="uicontrol"> Membros de email</span>: exibe o grupo de email definido no momento.  </p> </td> 
  </tr> 
 </tbody> 
</table>

