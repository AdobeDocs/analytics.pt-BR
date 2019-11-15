---
description: 'A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados. Você deve '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
solution: Analytics
title: Práticas recomendadas e informações gerais
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Práticas recomendadas e informações gerais

A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados. Você deve:

* Esperar que os feeds de dados sejam entregues dentro de 12 horas após o final de um determinado período de tempo em 95% das vezes.

   Por exemplo, se você tiver um feed que é atualizado por hora, a solicitação do feed de dados para o horário entre 3:00 e 4:00 deve ser entregue às 16:00 em 95% das vezes. Os feeds de dados de conjuntos de relatórios com grande volume de tráfego podem demorar mais para serem processados e entregues, especialmente se forem configurados como feeds diários em vez de feeds por hora.
* Certificar-se de [comunicar quaisquer picos de tráfego previstos](https://marketing.adobe.com/resources/help/en_US/reference/t_traffic_schedule_spike.html) antecipadamente. Qualquer latência de entrada afeta diretamente a rapidez do início do processo do feed de dados.
* Verificar se há espaço suficiente no site do FTP. Limpe-o regularmente para que você não fique sem espaço em disco.
* Ao alterar as credenciais do FTP, certifique-se de que elas estejam atualizadas no sistema de feed de dados da Adobe.
* Usar a disponibilização por hora, se possível. Os arquivos ficam menores e mais rápidos de produzir/transmitir.
* Considere o uso da entrega de "vários arquivos" (normalmente feita com feeds diários grandes). A disponibilização de múltiplos arquivos quebra o arquivo único em menores e os envia simultaneamente. Novamente, os arquivos menores agilizam a criação, a compactação/descompactação e a transmissão dos dados.
* Se você estiver usando sFTP como método de entrega, não leia e não exclua arquivos com o sufixo ".part". O sufixo ".part" indica que o arquivo foi parcialmente transferido, mas não foi concluído. Depois que o arquivo for transferido, ele será renomeado sem o sufixo ".part".
* Construa seu processo ETL esperando que, ocasionalmente, um arquivo possa ser transferido mais de uma vez. Caso contrário, você pode acabar com dados duplicados.
