---
description: Instruções para configurar a transferência segura com os servidores FTP da Adobe.
keywords: ftp;sftp
solution: Analytics
title: Conexão com uma conta FTP da Adobe com SFTP
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Conexão com uma conta FTP da Adobe com SFTP

Instruções para configurar a transferência segura com os servidores FTP da Adobe.

1. Solicite uma conta FTP hospedada pela Adobe (cota de 50 MB).
1. Crie chaves RSA públicas/privadas. No Linux, execute:

   ```
   ssh-keygen -t rsa
   ```

   Se você está em um ambiente Windows, use puttyGen para criar as chaves.

1. Create a file named [!DNL authorized_keys] (no extension).
1. Copy the contents of the Public key into [!DNL authorized_keys].
1. Upload [!DNL authorized_keys] to an FTP account:

   * Conecte-se a uma conta FTP da Adobe.
   * Create a [!DNL .ssh] directory (if it does not already exist).
   * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. Teste a conexão fazendo logon na conta FTP usando SFTP.

[Para obter informações mais detalhadas, consulte ](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)Como se conectar à Adobe via sFTP sem uma senha_....
