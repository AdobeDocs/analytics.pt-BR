---
description: Instruções para configurar a transferência segura com os servidores FTP da Adobe.
keywords: ftp;sftp
title: Conexão com uma conta FTP da Adobe com SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 100%

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

Para informações mais detalhadas, consulte [Como conectar à Adobe por SFTP sem senha_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
