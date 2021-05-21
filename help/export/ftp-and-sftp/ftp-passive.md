---
description: O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.
keywords: ftp;sftp
title: Usar o modo FTP passivo
uuid: e56e937e-ec42-45ec-ae8e-8a8ea1b76f3f
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '101'
ht-degree: 100%

---

# Usar o modo FTP passivo

O FTP ativo vs. FTP passivo controla a maneira como as conexões da porta são estabelecidas, mas essa escolha gera algumas consequências no firewall.

A Adobe usa o FTP passivo, uma maneira mais segura de transferir dados na qual o fluxo dos dados é configurado e iniciado pelo cliente File Transfer Program (FTP) no lugar do programa de servidor FTP. Se estiver com dificuldades para se conectar ao FTP da Adobe, verifique se você está usando o modo passivo.
