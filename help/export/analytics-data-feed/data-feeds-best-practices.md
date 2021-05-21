---
description: 'A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados. Você deve '
keywords: Feed de dados;práticas recomendadas;pico de tráfego;por hora;ftp
title: Práticas recomendadas e informações gerais
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '219'
ht-degree: 100%

---

# Práticas recomendadas

A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados.

* Certificar-se de comunicar quaisquer picos de tráfego previstos antecipadamente. A latência afeta diretamente o tempo de processamento dos feeds de dados. Consulte [Agendar um pico de tráfego](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) no Guia do usuário do Administrador.
* Os feeds de dados não contêm um contrato de nível de serviço, a menos que explicitamente declarado em seu contrato com a Adobe. Normalmente, os feeds são entregues dentro de várias horas após a janela do relatório ser aprovada. No entanto, ocasionalmente pode levar até 12 horas ou mais.
* Verificar se há espaço suficiente no site do FTP. Remova arquivos do destino regularmente para que não fique sem espaço em disco.
* Os feeds por hora que usam vários processos de entrega de arquivos são os mais rápidos. Considere o uso de vários feeds de arquivo por hora se uma entrega em tempo hábil for uma prioridade alta da organização.
* Se estiver usando sFTP, não leia nem exclua arquivos com um sufixo `.part`. O sufixo `.part` indica que o arquivo foi parcialmente transferido. Depois que o arquivo é transferido, o sufixo `.part` desaparece.
* Se você automatizar o processo de ingestão de feed, considere a possibilidade de um arquivo ser transferido mais de uma vez. Arquivos duplicados podem ser reenviados pelo usuário ou raramente pela Adobe.
