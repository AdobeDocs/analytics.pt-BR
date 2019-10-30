---
description: O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.
keywords: ftp;sftp
seo-description: O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.
seo-title: Usar o modo FTP passivo
solution: Analytics
title: Usar o modo FTP passivo
uuid: e56e937e-ec42-45ec-ae8e-8a8ea1b76f3f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Usar o modo FTP passivo

O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.

A Adobe usa o FTP passivo, uma maneira mais segura de transferir dados na qual o fluxo dos dados é configurado e iniciado pelo cliente File Transfer Program (FTP) no lugar do programa de servidor FTP. Se estiver com dificuldades para se conectar ao FTP da Adobe, verifique se você está usando o modo passivo.
