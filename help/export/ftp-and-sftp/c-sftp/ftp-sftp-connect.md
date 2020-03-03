---
description: Instruções para configurar a transferência segura com os servidores FTP da Adobe.
keywords: ftp;sftp
title: Conexão com uma conta FTP da Adobe com SFTP
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conexão com uma conta FTP da Adobe com SFTP

Instruções para configurar a transferência segura com os servidores FTP da Adobe.

1. Solicite uma conta FTP hospedada pela Adobe (cota de 50 MB).
1. Crie chaves RSA públicas/privadas. No Linux, execute:

   ```
   ssh-keygen -t rsa
   ```

   Se você está em um ambiente Windows, use puttyGen para criar as chaves.

1. Crie um arquivo com o nome [!DNL authorized_keys] (sem extensão).
1. Copie o conteúdo da chave pública para [!DNL authorized_keys].
1. Faça upload de [!DNL authorized_keys] para uma conta FTP:

   * Conecte-se a uma conta FTP da Adobe.
   * Crie um diretório [!DNL .ssh] (caso ele ainda não exista).
   * Faça upload do arquivo [!DNL authorized_keys] para o diretório [!DNL .ssh].

1. Faça logon em uma conta FTP com o SFTP para testar a conexão.

Para informações mais detalhadas, consulte [Como conectar aà Adobe por SFTP sem senha_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
