---
description: Configuração e uso de contas FTP hospedadas pela Adobe.
keywords: ftp;sftp
title: Configurar contas FTP - visão geral
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
TQID: https://experienceleague.adobe.com/38oslnk-IS87YU9qpOJyEoqytnrMuK5lp3VtYnTyQOg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 6%

---

# Configurar contas FTP ou SFTP - visão geral

Configurar e usar contas FTP ou SFTP hospedadas pela Adobe.

A Adobe mantém clusters FTP ou SFTP altamente disponíveis e de alto desempenho projetados especificamente para melhorar a confiabilidade da transferência de arquivos e, ao mesmo tempo, garantir alto desempenho.

Os clientes da Adobe recebem notificações de manutenção por meio de seu processo padrão, já que os eventos de manutenção são programados. Para garantir que os sistemas FTP ou SFTP da Adobe funcionem conforme projetado e continuem a fornecer transferências de dados seguras, confiáveis e de alto desempenho, a Adobe solicita a adesão às seguintes diretrizes:

* A maioria das contas FTP ou SFTP da Adobe (classificações, fontes de dados e outras) é ativada automaticamente quando o recurso especificado é configurado. Para contas de feed de dados e de entrega de arquivos gerais, o Atendimento ao cliente da Adobe pode configurar uma nova conta FTP ou SFTP para você. Esse processo está em vigor para garantir a segurança e o espaço disponíveis para a conta FTP ou SFTP.
* Os usuários devem remover os dados entregues pela Adobe à conta FTP ou SFTP depois que os dados forem transferidos com êxito para seus sistemas.
* Notifique a Adobe quando contas FTP ou SFTP não forem mais necessárias, para que elas possam ser desativadas.

O nome do host FTP da Adobe é `ftp://ftp.omniture.com` ou `ftp://ftp2.omniture.com`.

Esta informação, assim como o nome de usuário e a senha, deve ser fornecida dentro do CX Enterprise (para classificações e fontes de dados) ou pelo representante da Adobe responsável pela configuração da conta, conforme sua solicitação. Se você não souber o endereço FTP ou SFTP a ser usado, entre em contato com a equipe de conta da Adobe, que poderá fornecer o endereço correto. Além disso, para contas de classificações e fontes de dados, a Adobe não tem uma hora específica do dia em que os arquivos FTP ou SFTP são processados. Em vez disso, o Adobe usa um script que pesquisa constantemente contas FTP ou SFTP para o processo de novos arquivos. Os arquivos carregados nessas contas são processados o mais rápido possível.
