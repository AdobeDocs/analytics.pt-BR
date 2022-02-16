---
description: O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.
keywords: ftp;sftp
title: Usar o modo FTP passivo
feature: FTP Export
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 100%

---

# Usar o modo FTP passivo

O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.

A Adobe usa o FTP passivo, uma maneira mais segura de transferir dados na qual o fluxo dos dados é configurado e iniciado pelo cliente File Transfer Program (FTP) no lugar do programa de servidor FTP. Se estiver com dificuldades para se conectar ao FTP da Adobe, verifique se você está usando o modo passivo.
