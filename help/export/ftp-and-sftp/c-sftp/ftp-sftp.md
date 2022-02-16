---
description: O SFTP é um protocolo seguro para transferência de dados, e garante que ninguém veja seus dados a não ser você. Os serviços de engenharia da Adobe podem configurar uma conta SFTP para manter seus dados protegidos.
keywords: ftp;sftp
title: Protocolo de transferência segura de arquivo - visão geral
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 100%

---

# Protocolo de transferência segura de arquivo - visão geral

O SFTP é um protocolo seguro para transferência de dados, e garante que ninguém veja seus dados a não ser você. Os serviços de engenharia da Adobe podem configurar uma conta SFTP para manter seus dados protegidos.

## Entrega por push {#section_A47831BB1DCA490BB57F0940617AA506}

Isto significa que os servidores da Adobe “forçam” o envio do arquivo para os servidores. Essencialmente, nós enviamos os arquivos para o end point.

O [Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) e o [Feed de dados do Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=pt-BR) podem enviar dados por SFTP.

As ferramentas do Analytics a seguir **não podem** enviar dados via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## Envio próprio {#section_FA29FAEF02FE40B8B32452146A036F48}

Isto significa que o arquivo é enviado para um dos servidores da Adobe usando um FTP normal. Se quiser armazenar o arquivo no seu servidor, faça o envio do arquivo para o servidor da Adobe por meio do SFTP do seu servidor para o servidor FTP da Adobe. É possível fazer isso usando um destes três métodos:

* [Conexão com a Adobe via SFTP sem uma senha.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Conexão com uma conta FTP da Adobe com SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* É possível enviar qualquer relatório para o FTP da Adobe, como por exemplo, feeds de dados/R&amp;A/Ad Hoc, e depois realizar o envio. A Adobe não poderá enviar esses relatórios para o servidor SFTP caso você já tenha ajustado as configurações.
