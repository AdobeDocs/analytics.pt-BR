---
description: Configuração e uso de contas FTP hospedadas pela Adobe.
keywords: ftp;sftp
title: Configurar contas FTP - visão geral
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 92%

---

# Configurar contas FTP - visão geral

Configuração e uso de contas FTP hospedadas pela Adobe.

A Adobe mantém clusters FTP altamente disponíveis e de alto desempenho que foram projetados para melhorar a confiabilidade da transferência de arquivo e garantir o alto desempenho.

Os clientes da Adobe recebem notificações de manutenção por meio do processo padrão, já que os eventos de manutenção são agendados. Para garantir que os sistemas FTP da Adobe funcionem conforme o esperado e continuem a oferecer uma transferência de dados confiável, segura e de alto desempenho, a Adobe exige que as seguintes diretrizes sejam cumpridas:

* A maioria das contas FTP da Adobe (classificações, fontes de dados e outros) são ativadas automaticamente quando o recurso em questão é configurado. O Atendimento ao cliente da Adobe pode configurar uma nova conta FTP de feed de dados e de envio geral de arquivos para você. Este processo é realizado para garantir a segurança e o espaço disponível para a conta FTP.
* Os usuários devem remover da conta FTP os dados entregues pela Adobe assim que eles forem transferidos com sucesso para seus sistemas.
* Informe à Adobe quando as contas FTP não forem mais necessárias para que elas possam ser desativadas.

O nome do host FTP da Adobe é `ftp://ftp.omniture.com` ou `ftp://ftp2.omniture.com`.

Esta informação, assim como o nome de usuário e a senha, deve ser fornecida dentro da [!UICONTROL Experience Cloud] (para classificações e fontes de dados) ou pelo representante da Adobe responsável pela configuração da conta, conforme sua solicitação. Caso não saiba qual endereço FTP usar, entre em contato com a equipe de conta do Adobe, que pode fornecer o endereço correto. Além disso, para contas de classificações e fontes de dados, não há um horário específico para o processamento dos arquivos FTP. A Adobe usa um script que pesquisa constantemente as contas FTP atrás de um novo processamento de arquivos. Os arquivos enviados para estas contas são processados o mais rápido possível.
