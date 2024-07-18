---
description: Instruções para configurar a transferência segura com os servidores FTP da Adobe.
keywords: ftp;sftp
title: Conexão com uma conta FTP da Adobe com SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 62132284ca70f3bdb1a8896e4548b8b63a5c03c8
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 58%

---

# Conexão com uma conta FTP com SFTP

Para configurar a transferência segura com FTP:

1. (Condicional) Se você deseja configurar a transferência segura com servidores FTP Adobe:

   1. Solicite uma conta FTP hospedada pela Adobe (cota de 50 MB).

   1. Criar chaves RSA públicas/privadas.

      * No ambiente Linux, execute:

        ```
        ssh-keygen -t rsa
        ```

      * Em um ambiente Windows, use puttyGen.

1. (Condicional) Se quiser configurar a transferência segura com seu próprio local FTP, você deve ter um host SFTP, nome de usuário e site de destino que contenham uma chave pública RSA ou DSA válida. Você pode baixar a chave pública apropriada ao criar o feed.

1. Crie um arquivo com o nome [!DNL authorized_keys] (sem extensão).

1. Copie o conteúdo da chave pública para [!DNL authorized_keys].

1. Faça upload de [!DNL authorized_keys] para uma conta FTP:

   * Conecte-se a uma conta FTP da Adobe.
   * Crie um diretório [!DNL .ssh] (caso ele ainda não exista).
   * Faça upload do arquivo [!DNL authorized_keys] para o diretório [!DNL .ssh].

1. Faça logon em uma conta FTP com o SFTP para testar a conexão.

Para informações mais detalhadas, consulte [Como conectar à Adobe por SFTP sem senha_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
