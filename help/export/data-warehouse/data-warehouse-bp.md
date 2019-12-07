---
description: O data warehouse fornece uma interface flexível para executar relatórios personalizados. Seguir essas orientações pode ajudar a diminuir o tempo gasto para recuperar dados.
keywords: best practices;failure;timeout;troubleshooting
title: Práticas recomendadas do Data Warehouse
topic: Data warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Práticas recomendadas do Data Warehouse

O Data Warehouse fornece uma interface flexível para executar relatórios personalizados. Seguir essas orientações pode ajudar a diminuir o tempo gasto para recuperar dados.



| Orientação | Descrição |
|--- |--- |
| Executar exibições de página, visitas, visitantes e outros relatórios padrão no Relatórios e análises | Antes de criar um relatório do Data Warehouse, veja se as informações que você está procurando já estão disponíveis nos relatórios. Em caso afirmativo, o relatório será disponibilizado muito mais rapidamente devido ao pré-processamento realizado pelo Relatórios e análises para métricas comuns. |
| Entender a quantidade de dados que está solicitando | Um relatório plurianual em um grande conjunto de relatórios pode conter dezenas de bilhões de linhas de dados. Pode levar dias, ou mesmo semanas, para processar e avaliar esses dados. Avalie como o relatório está sendo usado para determinar se alguns dados plurianuais estão disponíveis, ou se você pode dividir o relatório em várias solicitações. |
| Corresponder o período do relatório à granularidade | Relatar a granularidade requer tempo de processamento adicional. Se você estiver relatando a granularidade mensal de um ano inteiro, seus relatórios serão processados com muito mais rapidez se você enviar uma solicitação de relatório para cada mês. |
| Relatório em intervalos de datas concluídos | Os relatórios do Data Warehouse são gerados quando o intervalo de datas solicitado é concluído. Por exemplo, se você solicitar um relatório para a semana atual na quarta-feira, o relatório não será gerado até o domingo da semana seguinte. |
| Gerar relatórios de definição de caminho no Data Warehouse | Métricas de definição de caminho (entradas, saídas, retornos etc.) não estão disponíveis no data warehouse. |
| Conjuntos de relatórios virtuais | O recurso de relatório do Data Warehouse para conjuntos de relatórios virtuais oferece suporte ao fuso horário alternativo configurado no conjunto de relatórios virtuais. |
