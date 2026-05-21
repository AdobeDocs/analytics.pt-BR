---
description: A Adobe oferece suporte para a exportação de solicitações de Data Warehouse a servidores SFTP.
keywords: ftp;sftp
title: Enviar solicitações de Data Warehouse para servidores SFTP
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
TQID: https://experienceleague.adobe.com/nBerOKEbILwAK5OyayVgdBPN8vq24kk-DXY6XMT50wg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 35%

---

# Enviar solicitações de Data Warehouse para servidores SFTP

A Adobe oferece suporte à exportação de solicitações do Data Warehouse para servidores SFTP, conforme descrito em [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) no artigo [Configurar um destino de relatório para uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

Certifique-se de que as tarefas a seguir sejam concluídas:

* Somente a porta 22 é usada ao solicitar um relatório do Data Warehouse.
* O arquivo `authorized_keys` da Adobe está no diretório `.ssh`, localizado dentro do diretório raiz do usuário com o qual você fez o logon.
* O destino não seja `ftp.omniture.com`. O protocolo SFTP entre os servidores internos da Adobe não é compatível.
* O destino oferece suporte à autenticação de um fator (PKI). Se houver um desafio de dois fatores, a entrega do relatório falhará. Verifique se seu servidor não está configurado para realizar a tentativa de autenticação de dois fatores. O Adobe Analytics exige que somente a chave e nada mais seja usado para fazer logon.
* O Adobe oferece suporte à criptografia SSHv2 e retorna ao SSHv1 (somente chave RSA).

Para enviar uma solicitação de Data Warehouse via SFTP com sucesso:

1. Conclua as etapas descritas em [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) no artigo [Configurar um destino de relatório para uma solicitação do Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), incluindo o download da chave pública.
1. Faça logon no site SFTP com as mesmas credenciais usadas para a solicitação Data Warehouse.
1. No diretório raiz, navegue até a pasta de nome `.ssh` (caso essa pasta não exista, crie uma) e coloque o arquivo `authorized_keys` lá.

1. Conclua a solicitação do Data Warehouse caso ainda não o tenha feito, conforme descrito em [Configurar um destino de relatório para uma solicitação do Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).
