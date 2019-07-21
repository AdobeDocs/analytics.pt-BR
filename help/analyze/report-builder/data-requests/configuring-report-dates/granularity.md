---
description: Na Etapa 1 do Assistente de solicitações, é possível aplicar um nível de granularidade à solicitação de dados. A granularidade especifica o nível de detalhes baseado em tempo que está incluída no relatório.
seo-description: Na Etapa 1 do Assistente de solicitações, é possível aplicar um nível de granularidade à solicitação de dados. A granularidade especifica o nível de detalhes baseado em tempo que está incluída no relatório.
seo-title: Granularidade
solution: Analytics
title: Granularidade
topic: Construtor de relatórios
uuid: 948 b 3 ff 2-fcff -45 fc -9 e 8 c -8 a 025 ac 562 b 1
translation-type: tm+mt
source-git-commit: d75c58caf1220031fa36483a0ad50ea6f7be7c39

---


# Granularidade

No Assistente de solicitações: etapa 1, você pode aplicar um nível de granularidade à solicitação de dados. A granularidade especifica o nível de detalhes baseado em tempo que está incluída no relatório.

Valores válidos são Hora, Dia, Semana, Mês, Trimestre, Ano e Agregado.

## Como o Construtor de relatórios processa a granularidade

Suponha que você escolha um intervalo de datas para um mês com granularidade [!UICONTROL Mês]. As solicitações mostram totais para a métrica com base em dados correspondentes a exatamente um mês. Se o intervalo de datas da sua solicitação abrange um trimestre, o relatório mostra três valores: um para cada unidade de mês, ou fração disso. Se hoje for 18 de março, escolher o último trimestre retorna um valor para 1º de janeiro - 31 de janeiro, outro valor para 1º de fevereiro - 28 de fevereiro e um valor final para 1º de março - 17 de março.
