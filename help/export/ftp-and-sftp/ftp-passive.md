---
description: O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.
keywords: ftp;sftp
title: Usar o modo FTP passivo
uuid: e56e937e-ec42-45ec-ae8e-8a8ea1b76f3f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Usar o modo FTP passivo

O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.

A Adobe usa o FTP passivo, uma maneira mais segura de transferir dados na qual o fluxo dos dados é configurado e iniciado pelo cliente File Transfer Program (FTP) no lugar do programa de servidor FTP. Se estiver com dificuldades para se conectar ao FTP da Adobe, verifique se você está usando o modo passivo.
