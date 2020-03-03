---
description: A Adobe oferece suporte para a exportação de solicitações de Data Warehouse a servidores SFTP.
keywords: ftp;sftp
title: Enviar solicitações de Data Warehouse para servidores SFTP
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Enviar solicitações de Data Warehouse para servidores SFTP

A Adobe oferece suporte para a exportação de solicitações de Data Warehouse a servidores SFTP.

Certifique-se de que as tarefas a seguir sejam concluídas:

A Adobe oferece suporte para as solicitações de Data Warehouse para servidores SFTP, desde que:

* O protocolo [!DNL sftp://] seja especificado no campo de hospedagem (por exemplo, [!DNL sftp://ftp.example.com]) e APENAS a porta 22 seja usada durante a solicitação do relatório de Data Warehouse.

   Você também pode usar a opção [!DNL sftp+norename://], conforme descrito abaixo.

* O campo [!DNL authorized_keys] da Adobe esteja no diretório [!DNL .ssh], localizado dentro do diretório raiz do usuário com o qual você fez o logon

* O destino não seja [!DNL ftp.omniture.com]. O protocolo sFTP entre os servidores internos da Adobe não é compatível.
* O destino seja compatível com a autenticação de um fator (PKI, infraestrutura de chave pública). Se a autenticação de dois fatores for executada, o envio do relatório falhará. Verifique se seu servidor não está configurado para realizar a tentativa de autenticação de dois fatores. O Adobe Analytics exige que apenas a chave seja usada para fazer o logon.
* A Adobe oferece suporte para a criptografia SSHv2, mas não para SSHv1 (apenas chave RSA).

Para enviar uma solicitação de [!DNL Data Warehouse] via SFTP com sucesso:

1. Obtenha o arquivo [!DNL authorized_keys] fazendo com que os usuários da sua organização entrem em contato com o Atendimento ao Cliente.
1. Depois que o arquivo for obtido, faça o logon no site FTP com as mesmas credenciais usadas para a solicitação de [!DNL Data Warehouse].
1. No diretório raiz, navegue até a pasta de nome [!DNL .ssh] (caso essa pasta não exista, crie uma) e coloque o arquivo [!DNL authorized_keys] lá.

1. Vá até o gerenciador de solicitações do [!DNL Data Warehouse]. Configure a solicitação conforme desejado e, em seguida, clique em **[!UICONTROL Opções avançadas de envio]**.

1. Na janela pop-up, clique em **[!UICONTROL FTP]** e, em seguida, especifique o site ftp (incluindo o protocolo [!DNL sftp://], como [!DNL sftp://ftp.omniture.com]) pela porta 22.

   A inclusão do protocolo [!DNL sftp://] só é permitida durante o uso do sFTP. Solicitações de FTP comuns devem omitir o prefixo do protocolo (como por exemplo, [!DNL ftp.omniture.com] em vez de [!DNL ftp://ftp.omniture.com]).

1. No campo Pasta, insira o nome da pasta na qual você deseja colocar o arquivo. É necessário inserir o nome de uma pasta.
1. Insira o mesmo nome de usuário e senha usados na Etapa 2.
1. Clique em **[!UICONTROL Enviar]**.

O comando sftp PUT coloca um arquivo temporário com uma extensão .part em um diretório específico. Quando o upload for concluído, a extensão do arquivo será renomeada para a extensão final e estará pronta para ser utilizada.

Alternativamente, [!DNL sftp+norename://] pode ser especificado em vez de [!DNL sftp://] para carregar o arquivo diretamente com o nome final, sem um nome de arquivo temporário [!DNL .part] durante o carregamento. Essa abordagem é adequada quando o servidor SFTP lida com a renomeação de arquivos durante o upload automático, e não há chance do arquivo ser processado antes que o upload seja concluído.
