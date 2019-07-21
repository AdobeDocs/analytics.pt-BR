---
description: O SFTP é um protocolo seguro para transferência de dados que garante que ninguém poderá ver seus dados, mas você. Os serviços de engenharia da Adobe podem configurar uma conta SFTP para manter seus dados protegidos.
keywords: ftp; sftp
seo-description: O SFTP é um protocolo seguro para transferência de dados que garante que ninguém poderá ver seus dados, mas você. Os serviços de engenharia da Adobe podem configurar uma conta SFTP para manter seus dados protegidos.
seo-title: Protocolo de transferência segura de arquivo - Visão geral
solution: Analytics
title: Protocolo de transferência segura de arquivo - Visão geral
uuid: 7 dd 1 a 867-e 828-4 c 7 b-bf 11-75 a 81 d 4 c 149 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Protocolo de transferência segura de arquivo - Visão geral

O SFTP é um protocolo seguro para transferência de dados que garante que ninguém poderá ver seus dados, mas você. Os serviços de engenharia da Adobe podem configurar uma conta SFTP para manter seus dados protegidos.

## Envio da Adobe {#section_A47831BB1DCA490BB57F0940617AA506}

Isto significa que os servidores da Adobe “forçam” o envio do arquivo para os servidores. Essencialmente, nós enviamos os arquivos para o end point.

[O Data Warehouse](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md#concept_904ADB7B4FE04DCCB90EFDB6D0DB1076) e [o Feed de dados do Analytics](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) podem enviar dados via SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Construtor de relatórios

## Envio próprio {#section_FA29FAEF02FE40B8B32452146A036F48}

Isto significa que o arquivo é enviado para um dos servidores da Adobe usando um FTP normal. Se desejar o arquivo em seu servidor, é necessário puxá-lo para o servidor da Adobe usando o SFTP do seu servidor para o servidor FTP da Adobe. É possível fazer isso usando um destes três métodos:

* [Conecte-se à Adobe via SFTP sem uma senha.](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846)
* [Conecte-se a uma conta FTP da Adobe com SFTP.](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md#concept_01176600188441C6AFB28F5E264D89F8)
* É possível enviar qualquer relatório para o FTP da Adobe, como por exemplo, feeds de dados/R&amp;A/Ad Hoc, e depois realizar o envio. A Adobe não pode enviar esses relatórios ao servidor SFTP que você configurou.

