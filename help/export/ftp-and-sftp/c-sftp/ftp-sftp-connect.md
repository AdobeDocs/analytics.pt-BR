---
description: Instruções para configurar a transferência segura com os servidores FTP da Adobe.
keywords: ftp; sftp
seo-description: Instruções para configurar a transferência segura com os servidores FTP da Adobe.
seo-title: Conecte-se a uma conta FTP da Adobe com SFTP
solution: Analytics
title: Conecte-se a uma conta FTP da Adobe com SFTP
uuid: 4 faf 27 b 8-7276-4 c 68-87 cb -35802 b 809 e 27
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Conecte-se a uma conta FTP da Adobe com SFTP

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

1. Teste a conexão fazendo logon na conta FTP usando o SFTP.

For more detailed information, see [How to Connect to Adobe via sFTP Without a Password_...](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846).
