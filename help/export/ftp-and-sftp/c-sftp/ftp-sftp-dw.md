---
description: A Adobe oferece suporte para a exportação de solicitações de Data Warehouse a servidores SFTP.
keywords: ftp;sftp
title: Enviar solicitações de Data Warehouse para servidores SFTP
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: d8bfad5d388f906c7c7301a9126813f5c2a5dbaa
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 52%

---

# Enviar solicitações de Data Warehouse para servidores SFTP

O Adobe oferece suporte à exportação de solicitações do Data Warehouse para servidores SFTP, conforme descrito em [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) no artigo [Configurar um destino de relatório para uma solicitação do Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

Certifique-se de que as tarefas a seguir sejam concluídas:

* Somente a porta 22 é usada ao solicitar um relatório de Data Warehouse.
* O arquivo Adobe `authorized_keys` está no diretório `.ssh`, localizado dentro do diretório raiz do usuário com o qual você fez o logon.
* O destino não seja `ftp.omniture.com`. O protocolo SFTP entre os servidores internos da Adobe não é compatível.
* O destino seja compatível com a autenticação de um fator (PKI, infraestrutura de chave pública). Se a autenticação de dois fatores for executada, o envio do relatório falhará. Verifique se seu servidor não está configurado para realizar a tentativa de autenticação de dois fatores. O Adobe Analytics exige que apenas a chave seja usada para fazer o logon.
* A Adobe oferece suporte para a criptografia SSHv2, mas não para SSHv1 (apenas chave RSA).

Para enviar uma solicitação de Data Warehouse via SFTP com sucesso:

1. Conclua as etapas descritas em [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) no artigo [Configurar um destino de relatório para uma solicitação de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), incluindo o download da chave pública.
1. Faça logon no site SFTP com as mesmas credenciais usadas para a solicitação de Data Warehouse.
1. No diretório raiz, navegue até a pasta de nome `.ssh` (caso essa pasta não exista, crie uma) e coloque o arquivo `authorized_keys` lá.

1. Conclua a solicitação do Data Warehouse caso ainda não o tenha feito, conforme descrito em [Configurar um destino de relatório para uma solicitação do Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).
