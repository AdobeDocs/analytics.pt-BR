---
description: Saiba mais sobre as diretrizes que ajudam a reduzir o tempo necessário para recuperar dados do Data Warehouse.
keywords: práticas recomendadas;falha;tempo limite;solução de problemas;best practices;failure;timeout;troubleshooting
title: Práticas recomendadas do Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
TQID: https://experienceleague.adobe.com/fWshdRnbrh11kLLT3DiW0a-qMJ13o8v4EMH-t-ceWC8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 27%

---

# Práticas recomendadas do Data Warehouse

O Data Warehouse fornece uma interface flexível para executar relatórios personalizados. Use as diretrizes a seguir para ajudar a reduzir o tempo necessário para recuperar dados:

| Diretriz | Descrição |
|--- |--- |
| Entenda a quantidade de dados que você está solicitando | Um relatório plurianual sobre um grande conjunto de relatórios pode conter dezenas de bilhões de linhas de dados. Pode levar dias, ou mesmo semanas, para processar e avaliar esses dados. Avalie como o relatório está sendo usado para determinar se alguns dos dados plurianuais estão disponíveis ou se você pode dividir o relatório em várias solicitações. |
| Corresponder o período do relatório à granularidade | A granularidade do relatório requer mais tempo de processamento. Se você estiver relatando a granularidade mensal de um ano inteiro, seus relatórios serão processados muito mais rapidamente se você enviar uma solicitação de relatório para cada mês. |
| Relatório de intervalos de dados concluídos | Os relatórios do Data Warehouse são gerados quando o intervalo de datas solicitado está concluído. Por exemplo, se você solicitar um relatório para a semana atual na quarta-feira, o relatório não será gerado até o domingo da semana seguinte. |
| Gerar relatórios de definição de caminho no Data Warehouse | Métricas de definição de caminho (entradas, saídas, devoluções etc.) não estão disponíveis no data warehouse. |
| Conjuntos de relatórios virtuais | Os relatórios do Data Warehouse sobre conjuntos de relatórios virtuais são compatíveis com o fuso horário alternativo configurado no conjunto de relatórios virtual. |

