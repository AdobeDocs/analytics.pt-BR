---
title: Atualização de serviços SFTP - Perguntas frequentes
description: Perguntas frequentes sobre a atualização dos serviços SFTP planejada para maio de 2022.
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
source-git-commit: 43869c683ca30c94157c6822b53f02a917f6e3ff
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 91%

---

# Atualização de serviços SFTP - Perguntas frequentes

No verão de 2022, a Adobe Analytics atualizará seu protocolo de transferência segura de arquivo [SFTP] a fim de proporcionar uma maior segurança para as transferências de ficheiros. Com essa alteração, não haverá mais suporte para algumas configurações de cliente SFTP. Isso afeta apenas os dados enviados para a Adobe Analytics ou recuperados dela usando o SFTP. O protocolo FTP não será afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estão de acordo com as alterações detalhadas abaixo.

## Como posso determinar quais algoritmos, tipos de conexão e protocolos são usados atualmente pela minha organização?

O software FTP/SFTP usado deve indicar quais configurações específicas estão sendo usadas nas conexões configuradas para a troca de dados com o Adobe Analytics. Este software também deve incluir a documentação sobre as diferentes opções disponíveis para conexões. As opções que estarão disponíveis após essa atualização são amplamente compatíveis e aceitas no setor.

As opções de conexão que serão removidas são geralmente consideradas obsoletas e não são usadas em softwares atuais. Se você atualizou seu software FTP/SFTP nos últimos três anos, provavelmente já tem uma conexão compatível.

## Quais recursos do Adobe Analytics usam o SFTP para assimilação de dados?

Os recursos a seguir fornecem uma opção para fazer upload de dados para o Adobe Analytics usando o SFTP.

* [Classificações](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html?lang=pt-BR)

* [Feeds de dados](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html?lang=pt-BR)

* [Fontes de dados](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html?lang=pt-BR)

* [Relatórios entregues do Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html?lang=pt-BR)

* Além disso, algumas implementações personalizadas criadas por meio dos [Serviços de engenharia](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html?lang=pt-BR) podem usar o SFTP para trocar dados com a Adobe.

## Quais alterações específicas serão incluídas nesta atualização?

Veja abaixo uma lista detalhada de quais conexões e algoritmos serão removidos e quais serão
compatíveis:

* Algoritmos mac do protocolo SFTP:

   * Não serão mais compatíveis: hmac-md5, hmac-md5-96, hmac-ripemd160, hmacripemd160@openssh.com, hmac-sha1, hmac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com

   * Serão compatíveis apenas: hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com

* Algoritmo de cifras do protocolo SFTP:

   * Não serão mais compatíveis: 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * Serão compatíveis apenas: aes128-ctr, aes192-ctr, aes256-ctr

* Conexões compatíveis com o protocolo SFTP:

   * Não ofereceremos mais suporte ao uso de comandos scp e rsync ou conexões através do protocolo SFTP

   * Oferecemos suporte somente a conexões puras de protocolo SFTP

* Clientes/protocolos FTP/SFTP compatíveis:

   * FTP: vsftpd versão 3.0.2-25 ou superior

   * SFTP: openssh versão 7.4p1-21 ou superior
