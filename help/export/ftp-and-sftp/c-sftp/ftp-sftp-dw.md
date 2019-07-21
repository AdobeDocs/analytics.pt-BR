---
description: A Adobe oferece suporte à exportação de solicitações do Data Warehouse para servidores SFTP.
keywords: ftp; sftp
seo-description: A Adobe oferece suporte à exportação de solicitações do Data Warehouse para servidores SFTP.
seo-title: Enviar solicitações do Data Warehouse para servidores SFTP
solution: Analytics
title: Enviar solicitações do Data Warehouse para servidores SFTP
uuid: 393634 a 1-0643-4 d 63-bb 6 e-fb 80 f 1 ba 76 c 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Enviar solicitações do Data Warehouse para servidores SFTP

A Adobe oferece suporte à exportação de solicitações do Data Warehouse para servidores SFTP.

Certifique-se de que as tarefas a seguir sejam concluídas:

A Adobe oferece suporte à exportação de solicitações do Data Warehouse para servidores SFTP, desde que estes sejam atendidos:

* [!DNL sftp://] é especificado no campo host (por exemplo [!DNL sftp://ftp.example.com],) e a porta apenas 22 é usada ao solicitar um relatório do Data Warehouse.

   You can also use the [!DNL sftp+norename://] option, as described below.

* [!DNL authorized_keys] O arquivo da Adobe está no [!DNL .ssh] diretório dentro do diretório raiz do usuário com o qual você fez logon

* O destino não seja [!DNL ftp.omniture.com]. O protocolo sFTP entre os servidores internos da Adobe não é compatível.
* O destino seja compatível com a autenticação de um fator (PKI, infraestrutura de chave pública). Se a autenticação de dois fatores for executada, o envio do relatório falhará. Verifique se seu servidor não está configurado para realizar a tentativa de autenticação de dois fatores. O Adobe Analytics exige que apenas a chave seja usada para fazer o logon.
* A Adobe oferece suporte para a criptografia SSHv2, mas não para SSHv1 (apenas chave RSA).

To successfully send a [!DNL Data Warehouse] request via SFTP:

1. Obtenha o arquivo [!DNL authorized_keys] fazendo com que os usuários da sua organização entrem em contato com o Atendimento ao Cliente.
1. Depois que o arquivo for obtido, faça o logon no site FTP com as mesmas credenciais usadas para a solicitação de [!DNL Data Warehouse].
1. In the root directory, navigate to the folder named [!DNL .ssh] (if one does not exist, create one) and place the [!DNL authorized_keys] file there.

1. Go to the [!DNL Data Warehouse] request manager. Configure a solicitação conforme desejado e, em seguida, clique em **[!UICONTROL Opções avançadas de envio]**.

1. In the pop-up window, click **[!UICONTROL FTP]**, then specify the ftp site (including the [!DNL sftp://] protocol, such as [!DNL sftp://ftp.omniture.com]) via port 22.

   Including the [!DNL sftp://] protocol is only permitted when using SFTP. Regular FTP requests should omit the protocol prefix (such as, [!DNL ftp.omniture.com] instead of [!DNL ftp://ftp.omniture.com]).

1. No campo Pasta, insira o nome da pasta na qual você deseja colocar o arquivo. É necessário inserir o nome de uma pasta.
1. Insira o mesmo nome de usuário e senha usados na Etapa 2.
1. Clique em **[!UICONTROL Enviar]**.

O comando sftp PUT coloca um arquivo temporário com uma extensão .part em um diretório específico. Quando o upload for concluído, a extensão do arquivo será renomeada para a extensão final e estará pronta para ser utilizada.

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. Essa abordagem é adequada quando o servidor SFTP lida com a renomeação de arquivos durante o upload automático, e não há chance do arquivo ser processado antes que o upload seja concluído.
