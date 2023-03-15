---
description: O data warehouse fornece uma interface flexível para executar relatórios personalizados. Seguir essas orientações pode ajudar a diminuir o tempo gasto para recuperar dados.
keywords: práticas recomendadas;falha;tempo limite;solução de problemas;best practices;failure;timeout;troubleshooting
title: Práticas recomendadas do Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 98%

---

# Práticas recomendadas do Data Warehouse

O Data Warehouse fornece uma interface flexível para executar relatórios personalizados. Seguir essas orientações pode ajudar a diminuir o tempo gasto para recuperar dados.



| Orientação | Descrição |
|--- |--- |
| Executar Exibições de página, Visitas, Visitantes e outros relatórios padrão em Reports &amp; Analytics | Antes de criar um relatório do Data Warehouse, veja se as informações que você está procurando já estão disponíveis em relatórios. Em caso afirmativo, o relatório será produzido com muito mais rapidez devido ao pré-processamento realizado pelos Reports &amp; Analytics para métricas comuns. |
| Entender a quantidade de dados que está solicitando | Um relatório plurianual em um grande conjunto de relatórios pode conter dezenas de bilhões de linhas de dados. Pode levar dias, ou mesmo semanas, para processar e avaliar esses dados. Avalie como o relatório está sendo usado para determinar se alguns dados plurianuais estão disponíveis, ou se você pode dividir o relatório em várias solicitações. |
| Corresponder o período do relatório à granularidade | Relatar a granularidade requer tempo de processamento adicional. Se você estiver relatando a granularidade mensal de um ano inteiro, seus relatórios serão processados com muito mais rapidez se você enviar uma solicitação de relatório para cada mês. |
| Relatório em intervalos de datas concluídos | Os relatórios do Data Warehouse são gerados quando o intervalo de datas solicitado está concluído. Por exemplo, se você solicitar um relatório para a semana atual na quarta-feira, o relatório não será gerado até o domingo da semana seguinte. |
| Gerar relatórios de definição de caminho no Data Warehouse | Métricas de definição de caminho (entradas, saídas, retornos etc.) não estão disponíveis no data warehouse. |
| Conjuntos de relatórios virtuais | O recurso de relatório do Data Warehouse para conjuntos de relatórios virtuais oferece suporte ao fuso horário alternativo configurado no conjunto de relatórios virtuais. |
