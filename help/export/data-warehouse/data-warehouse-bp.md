---
description: Saiba mais sobre as diretrizes que ajudam a reduzir o tempo necessário para recuperar dados do Data Warehouse.
keywords: práticas recomendadas;falha;tempo limite;solução de problemas;best practices;failure;timeout;troubleshooting
title: Práticas recomendadas do Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 79%

---

# Práticas recomendadas do Data Warehouse

O Data Warehouse fornece uma interface flexível para executar relatórios personalizados. Use as diretrizes a seguir para ajudar a reduzir o tempo necessário para recuperar dados:

| Orientação | Descrição |
|--- |--- |
| Entender a quantidade de dados que está solicitando | Um relatório plurianual em um grande conjunto de relatórios pode conter dezenas de bilhões de linhas de dados. Pode levar dias, ou mesmo semanas, para processar e avaliar esses dados. Avalie como o relatório está sendo usado para determinar se alguns dados plurianuais estão disponíveis, ou se você pode dividir o relatório em várias solicitações. |
| Corresponder o período do relatório à granularidade | Relatar a granularidade requer tempo de processamento adicional. Se você estiver relatando a granularidade mensal de um ano inteiro, seus relatórios serão processados com muito mais rapidez se você enviar uma solicitação de relatório para cada mês. |
| Relatório em intervalos de datas concluídos | Os relatórios do Data Warehouse são gerados quando o intervalo de datas solicitado está concluído. Por exemplo, se você solicitar um relatório para a semana atual na quarta-feira, o relatório não será gerado até o domingo da semana seguinte. |
| Gerar relatórios de definição de caminho no Data Warehouse | As métricas de definição de caminho (entradas, saídas, devoluções etc.) não estão disponíveis no data warehouse. |
| Conjuntos de relatórios virtuais | O recurso de relatório do Data Warehouse para conjuntos de relatórios virtuais oferece suporte ao fuso horário alternativo configurado no conjunto de relatórios virtuais. |

