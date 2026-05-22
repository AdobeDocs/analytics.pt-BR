---
title: Atualização de serviços SFTP - Perguntas frequentes
description: Perguntas frequentes sobre a atualização dos serviços SFTP planejada.
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
TQID: 'https://experienceleague.adobe.com/HKI-iOTx-gHbsmL8BJszgs5e5nlflk67s64eqs2dd-k'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 444
ht-degree: 95%

---

# Atualização de serviços SFTP - Perguntas frequentes

Em 20 de setembro de 2022, o Adobe Analytics atualizará os seus serviços de Protocolo de transferência segura de arquivo [SFTP], a fim de proporcionar mais segurança para as transferências de arquivos. Com essa alteração, não haverá mais suporte para algumas configurações de cliente SFTP. Isso afeta somente os dados enviados para ou recuperados do Adobe Analytics por meio do SFTP. O protocolo FTP não será afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estão de acordo com as alterações detalhadas abaixo.

## Como posso determinar quais algoritmos, tipos de conexão e protocolos são usados atualmente pela minha organização?

O software FTP/SFTP usado deve indicar quais configurações específicas estão sendo usadas nas conexões configuradas para a troca de dados com o Adobe Analytics. Este software também deve incluir a documentação sobre as diferentes opções disponíveis para conexões. As opções que estarão disponíveis após essa atualização são amplamente compatíveis e aceitas no setor.

As opções de conexão que serão removidas são geralmente consideradas obsoletas e não são usadas em softwares atuais. Se você atualizou seu software FTP/SFTP nos últimos três anos, provavelmente já tem uma conexão compatível.

## Quais recursos do Adobe Analytics usam o SFTP para ingestão de dados?

Os recursos a seguir fornecem uma opção para fazer upload de dados para o Adobe Analytics usando o SFTP.

* [Classificações](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)

* [Atributos do cliente](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=pt-BR)

* [Feeds de dados](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)

* [Fontes de dados](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)

* [Relatórios entregues do Data Warehouse](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)

* Além disso, algumas implementações personalizadas criadas por meio dos [Serviços de engenharia](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md) podem usar o SFTP para trocar dados com a Adobe.

## Quais alterações específicas serão incluídas nesta atualização?

Veja abaixo uma lista detalhada de quais conexões e algoritmos serão removidos e quais serão
compatível:

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
