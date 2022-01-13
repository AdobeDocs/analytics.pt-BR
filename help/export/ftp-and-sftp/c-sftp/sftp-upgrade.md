---
title: Atualização de serviços SFTP - Perguntas frequentes
description: Perguntas frequentes sobre a atualização dos serviços SFTP planejada para maio de 2022.
source-git-commit: eb9bdcbd99d45afc913c5ade37e8fb5c62a3a456
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 2%

---


# Atualização de serviços SFTP - Perguntas frequentes

Ligado **2 de maio de 2022**, a Adobe Analytics atualizará seu Protocolo de transferência segura de arquivo [SFTP] a fim de proporcionar uma maior segurança para as transferências de ficheiros. Com essa alteração, algumas configurações de cliente SFTP não serão mais suportadas. Também adicionaremos algumas opções de conexão que estarão disponíveis por **1° de março de 2022**. Isso afetará somente os dados enviados ou recuperados da Adobe Analytics por meio do SFTP. O protocolo FTP não será afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estão de acordo com as alterações detalhadas abaixo.

## Como posso determinar quais algoritmos, tipos de conexão e protocolos são usados atualmente pela minha organização?

O software FTP/SFTP usado deve indicar quais configurações específicas estão sendo usadas nas conexões configuradas para troca de dados com a Adobe Analytics. Este software também deve incluir documentação sobre as diferentes opções disponíveis para conexões. As opções que serão suportadas após essa atualização são amplamente aceitas e aceitas no setor.

## Quais recursos do Adobe Analytics usam o SFTP para assimilação de dados?

Os recursos a seguir fornecem uma opção para fazer upload de dados para a Adobe Analytics usando SFTP.

* [Classificações](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html)

* [Feeds de dados](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [Fontes de dados](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Relatórios entregues do Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* Além disso, algumas implementações personalizadas criadas por meio do [Serviços de engenharia](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html) pode usar o SFTP para trocar dados com o Adobe.

## Que alterações específicas serão incluídas nesta atualização?

Abaixo está uma lista detalhada de quais conexões e algoritmos serão removidos e quais serão compatíveis:

* Algoritmos mac do protocolo SFTP:

   * Não apoiaremos mais: hmac-md5, hmac-md5-96, hmac-ripemd160, hmacripemd160@openssh.com, hmac-sha1, hmac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com

   * Só apoiaremos: hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com

* Algoritmo de cifras do protocolo SFTP:

   * Não apoiaremos mais: 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * Só apoiaremos: aes128-ctr, aes192-ctr, aes256-ctr

* Conexões compatíveis com o protocolo SFTP:

   * Não ofereceremos mais suporte ao uso de comandos scp e rsync ou conexões através do protocolo sftp

   * Oferecemos suporte somente a conexões puras de protocolo SFTP

* Clientes/protocolos FTP/SFTP compatíveis:

   * FTP: vsftpd versão 3.0.2-25 ou superior

   * SFTP: versão do openssh 7.4p1-21 ou superior