---
description: 'A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados. Você deve '
keywords: Feed de dados; práticas recomendadas; pico de tráfego; por hora; ftp
seo-description: 'A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados. Você deve '
seo-title: Práticas recomendadas e informações gerais
solution: Analytics
title: Práticas recomendadas e informações gerais
uuid: f 2 d 6 c 13 a -5 d 4 e -4 fc 2-8 baa -28 c 69 f 0 cf 5 f 6
translation-type: tm+mt
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566

---


# Práticas recomendadas e informações gerais

A seguir você encontra algumas das práticas recomendadas para processamento e entrega de feed de dados. Você deve:

* Esperar que os feeds de dados sejam entregues dentro de 12 horas após o final de um determinado período de tempo em 95% das vezes.

   Por exemplo, se você tiver um feed que é atualizado por hora, a solicitação do feed de dados para o horário entre 3:00 e 4:00 deve ser entregue às 16:00 em 95% das vezes. Os feeds de dados de conjuntos de relatórios com grande volume de tráfego podem demorar mais para serem processados e entregues, especialmente se forem configurados como feeds diários em vez de feeds por hora.
* Certificar-se de [comunicar quaisquer picos de tráfego previstos](https://marketing.adobe.com/resources/help/en_US/reference/t_traffic_schedule_spike.html) antecipadamente. Qualquer latência de entrada afeta diretamente a rapidez do início do processo do feed de dados.
* Verificar se há espaço suficiente no site do FTP. Limpe-o regularmente para não ficar sem espaço em disco.
* Ao alterar as credenciais do FTP, certifique-se de que elas estejam atualizadas no sistema de feed de dados da Adobe.
* Usar a disponibilização por hora, se possível. Os arquivos ficam menores e mais rápidos de produzir/transmitir.
* Considerar a disponibilização de “multiarquivos” (normalmente, feito com feeds diários de alto volume). A disponibilização de múltiplos arquivos quebra o arquivo único em menores e os envia simultaneamente. Novamente, os arquivos menores agilizam a criação, a compactação/descompactação e a transmissão dos dados.
* Se estiver usando sFTP como método de entrega, não leia e não exclua arquivos com o sufixo “.part”. O sufixo “.part” indica que o arquivo está parcialmente transferido e incompleto. Uma vez que o arquivo tenha sido transferido, o mesmo será renomeado sem o sufixo “.part”.
* Construa seu processo ETL esperando que, ocasionalmente, um arquivo possa ser transferido mais de uma vez. Caso contrário, você pode acabar com dados duplicados.
