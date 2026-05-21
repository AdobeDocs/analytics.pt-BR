---
description: O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.
keywords: ftp;sftp
title: Usar o modo FTP passivo
feature: FTP Export
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
TQID: https://experienceleague.adobe.com/R0fWu2Ik2OQB7VtF9ZVEEX1iLJfTl9A1YvlBm2p3nyU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 100
ht-degree: 48%

---

# Usar o modo FTP passivo

O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.

O Adobe usa FTP passivo, que é uma forma mais segura de transferência de dados, em que o fluxo de dados é configurado e iniciado pelo cliente FTP (File Transfer Program, programa de transferência de arquivos), em vez do programa do servidor FTP. Se tiver dificuldade para se conectar ao FTP da Adobe, certifique-se de usar o modo passivo.
