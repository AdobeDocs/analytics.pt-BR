---
description: A Adobe oferece suporte à exportação de solicitações do Data Warehouse para servidores SFTP.
keywords: ftp;sftp
title: Enviar solicitações de Data Warehouse para servidores SFTP
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Enviar solicitações de Data Warehouse para servidores SFTP

A Adobe oferece suporte à exportação de solicitações do Data Warehouse para servidores SFTP.

Certifique-se de que as tarefas a seguir sejam concluídas:

A Adobe oferece suporte para a exportação de solicitações do Data Warehouse para servidores SFTP, desde que:

* [!DNL sftp://] é especificado no campo host (por exemplo, [!DNL sftp://ftp.example.com]) e SOMENTE a porta 22 é usada ao solicitar um relatório do Data Warehouse.

   Você também pode usar a [!DNL sftp+norename://] opção, conforme descrito abaixo.

* Adobe's [!DNL authorized_keys] file is in the [!DNL .ssh] directory within the root directory of the user you log in with

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

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. Essa abordagem é apropriada quando o servidor SFTP lida com a renomeação de arquivos durante o upload automaticamente e não há nenhuma chance de o arquivo ser processado antes da conclusão do upload.
