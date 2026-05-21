---
description: Instruções para configurar a transferência segura com os servidores FTP da Adobe.
keywords: ftp;sftp
title: Conexão com uma conta FTP da Adobe com SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
TQID: https://experienceleague.adobe.com/uXtJtDP58tSIzb9AvoAknAYoMt7SknJSgxRKNgIAXM8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 38%

---

# Conexão com uma conta FTP com SFTP

Para configurar a transferência segura com FTP:

1. (Condicional) Se desejar configurar a transferência segura com os servidores FTP da Adobe:

   1. Solicite uma conta FTP hospedada pela Adobe (cota de 50 MB).

   1. Criar chaves públicas/privadas.

      * No ambiente Linux, execute:

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        Se sua política não permitir que você use o ed25519, execute:

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

        **Observação:** isso normalmente se aplica a clientes que operam sob o FIPS 186-4, já que o ed25519 é suportado pela primeira vez no FIPS 186-5 mais recente.

      * Em um ambiente Windows, use puttyGen.

1. (Condicional) Se quiser configurar a transferência segura com seu próprio local FTP, você deve ter um host SFTP, nome de usuário e site de destino que contenham uma chave pública RSA ou ed25519 válida. Você pode baixar a chave pública apropriada ao criar o feed.

1. Crie um arquivo com o nome [!DNL `authorized_keys`] (sem extensão).

1. Copie o conteúdo da chave pública para [!DNL `authorized_keys`].

1. Faça upload de [!DNL `authorized_keys`] para uma conta FTP:

   * Conecte-se a uma conta FTP da Adobe.
   * Crie um diretório [!DNL .ssh] (caso ele ainda não exista).
   * Faça upload do arquivo [!DNL `authorized_keys`] para o diretório [!DNL .ssh].

1. Faça logon em uma conta FTP com o SFTP para testar a conexão.

Para obter informações mais detalhadas, consulte [Conectar-se à Adobe via SFTP sem uma senha](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).

