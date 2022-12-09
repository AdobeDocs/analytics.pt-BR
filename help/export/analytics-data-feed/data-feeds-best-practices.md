---
description: A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados.
keywords: Feed de dados;práticas recomendadas;pico de tráfego;por hora;ftp
title: Práticas recomendadas e informações gerais
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 6f7f46b0fee46e572a65f639ea511478c0118f4e
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 100%

---

# Práticas recomendadas

A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados.

* Certificar-se de comunicar quaisquer picos de tráfego previstos antecipadamente. A latência afeta diretamente o tempo de processamento dos feeds de dados. Consulte [Agendar um pico de tráfego](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md) no Guia do usuário do Administrador.

* Os feeds de dados não contêm um contrato de nível de serviço, a menos que explicitamente declarado em seu contrato com a Adobe. Normalmente, os feeds são entregues dentro de várias horas após a janela do relatório ser aprovada. No entanto, ocasionalmente pode levar até 12 horas ou mais.

* Verificar se há espaço suficiente no site do FTP. Remova arquivos do destino regularmente para que não fique sem espaço em disco.

* Os feeds por hora que usam vários processos de entrega de arquivos são os mais rápidos. Considere o uso de vários feeds de arquivo por hora se uma entrega em tempo hábil for uma prioridade alta da organização.

* Se estiver usando sFTP, não leia nem exclua arquivos com um sufixo `.part`. O sufixo `.part` indica que o arquivo foi parcialmente transferido. Depois que o arquivo é transferido, o sufixo `.part` desaparece.

* Se você automatizar o processo de ingestão de feed, considere que as ocorrências e os arquivos poderão ser transferidos mais de uma vez. O processo de ingestão de feed precisa lidar com ocorrências e arquivos duplicados sem causar erros nem duplicar dados. Recomendamos usar a combinação das colunas `hitid_high` e `hitid_low` para identificar uma ocorrência de maneira exclusiva.

   Em casos raros, você pode ver valores `hitid_high` e `hitid_low` duplicados. Se isso acontecer, confirme se o arquivo não foi enviado e processado anteriormente. Se apenas algumas linhas em um arquivo estiverem duplicadas, considere adicionar `visit_num` e `visit_page_num` para ajudar a determinar a exclusividade.
