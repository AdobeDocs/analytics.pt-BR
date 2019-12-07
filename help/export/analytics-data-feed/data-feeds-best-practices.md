---
description: 'A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados. Você deve '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: Práticas recomendadas e informações gerais
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Práticas recomendadas

A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados.

* Certificar-se de comunicar quaisquer picos de tráfego previstos antecipadamente. A latência afeta diretamente o tempo de processamento dos feeds de dados. Consulte [Agendar um pico](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) de tráfego no Guia do usuário do Administrador.
* Os feeds de dados não contêm um contrato de nível de serviço, a menos que explicitamente declarado em seu contrato com a Adobe. Normalmente, os feeds são entregues dentro de várias horas após a janela do relatório ser aprovada, no entanto, ocasionalmente pode levar até 12 horas ou mais.
* Verificar se há espaço suficiente no site do FTP. Remova arquivos do destino regularmente para que você não fique sem espaço em disco.
* Os feeds por hora usando vários processos de entrega de arquivos são os mais rápidos. Considere o uso de vários feeds de arquivo por hora se uma entrega em tempo hábil for uma prioridade alta para sua organização.
* Se estiver usando sFTP, não leia nem exclua arquivos com um `.part` sufixo. O `.part` sufixo indica que o arquivo foi parcialmente transferido. Depois que o arquivo é transferido, o `.part` sufixo desaparece.
* Se você automatizar seu processo de ingestão de feed, considere a possibilidade de um arquivo ser transferido mais de uma vez. Arquivos duplicados podem ser reenviados pelo usuário ou raramente pela Adobe.
