---
description: O SFTP é um protocolo seguro para transferência de dados que garante que ninguém possa ver seus dados a não ser você. Os serviços de engenharia da Adobe podem configurar uma conta SFTP para manter seus dados protegidos.
keywords: ftp;sftp
title: Protocolo de transferência segura de arquivo - visão geral
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Protocolo de transferência segura de arquivo - visão geral

O SFTP é um protocolo seguro para transferência de dados que garante que ninguém possa ver seus dados a não ser você. Os serviços de engenharia da Adobe podem configurar uma conta SFTP para manter seus dados protegidos.

## Envio da Adobe {#section_A47831BB1DCA490BB57F0940617AA506}

Isto significa que os servidores da Adobe “forçam” o envio do arquivo para os servidores. Essencialmente, nós enviamos os arquivos para o end point.

[O Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) e o Feed [de dados do](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) Analytics podem enviar dados por SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Construtor de relatórios

## Envio próprio {#section_FA29FAEF02FE40B8B32452146A036F48}

Isto significa que o arquivo é enviado para um dos servidores da Adobe usando um FTP normal. Se quiser que o arquivo seja colocado no servidor, você precisará retirá-lo do servidor da Adobe usando o SFTP do servidor para o servidor FTP da Adobe. É possível fazer isso usando um destes três métodos:

* [Conexão com a Adobe via SFTP sem uma senha.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Conecte-se a uma conta FTP da Adobe com SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* É possível enviar qualquer relatório para o FTP da Adobe, como por exemplo, feeds de dados/R&amp;A/Ad Hoc, e depois realizar o envio. A Adobe não pode fornecer esses relatórios ao servidor SFTP que você configurou.

