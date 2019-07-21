---
description: O data warehouse fornece uma interface flexível para executar relatórios personalizados. Seguir essas orientações pode ajudar a diminuir o tempo gasto para recuperar dados.
keywords: práticas recomendadas; falha; tempo limite; solução de problemas
seo-description: O data warehouse fornece uma interface flexível para executar relatórios personalizados. Seguir essas orientações pode ajudar a diminuir o tempo gasto para recuperar dados.
seo-title: Práticas recomendadas do Data Warehouse
solution: Analytics
title: Práticas recomendadas do Data Warehouse
topic: Data Warehouse
uuid: d 71 c 9138-22 d 9-4 f 92-885 e -593 f 83 f 2 bb 59
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Práticas recomendadas do Data Warehouse

O Data Warehouse fornece uma interface flexível para executar relatórios personalizados. Seguir essas orientações pode ajudar a diminuir o tempo gasto para recuperar dados.



| Orientação | Descrição |
|--- |--- |
| Executar Exibições de página, Visitas, Visitantes e outros relatórios padrão em Relatórios e análises | Antes de criar um relatório do Data Warehouse, veja se as informações que você está procurando já estão disponíveis nos relatórios. Em caso positivo, o relatório será produzido com muito mais rapidez devido ao pré-processamento realizado pelo Relatórios e análises para métricas comuns. |
| Entender a quantidade de dados que está solicitando | Um relatório plurianual em um grande conjunto de relatórios pode conter dezenas de bilhões de linhas de dados. Pode levar dias, ou mesmo semanas, para processar e avaliar esses dados. Avalie como o relatório está sendo usado para determinar se alguns dados plurianuais estão disponíveis, ou se você pode dividir o relatório em várias solicitações. |
| Corresponder o período do relatório à granularidade | Relatar a granularidade requer tempo de processamento adicional. Se você estiver relatando a granularidade mensal de um ano inteiro, seus relatórios serão processados com muito mais rapidez se você enviar uma solicitação de relatório para cada mês. |
| Relatório em intervalos de datas concluídos | Os relatórios do Data warehouse são gerados quando o intervalo de datas solicitado é concluído. Por exemplo, se você solicitar um relatório para a semana atual na quarta-feira, o relatório não será gerado até o domingo da semana seguinte. |
| Gerar relatórios de definição de caminho no Data Warehouse | Métricas de definição de caminho (entradas, saídas, retornos etc.) não estão disponíveis no data warehouse. |
| Conjuntos de relatórios virtuais | O recurso de relatório do Data Warehouse para conjuntos de relatórios virtuais oferece suporte ao fuso horário alternativo configurado no conjunto de relatórios virtuais. |