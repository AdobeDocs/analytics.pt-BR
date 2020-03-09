---
description: 'No Assistente de solicitações: etapa 1, você pode aplicar um nível de granularidade à solicitação de dados. A granularidade especifica o nível de detalhes baseado em tempo que está incluída no relatório.'
title: Granularidade
topic: Report builder
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Granularidade

No Assistente de solicitações: etapa 1, você pode aplicar um nível de granularidade à solicitação de dados. A granularidade especifica o nível de detalhes baseado em tempo que está incluída no relatório.

Valores válidos são Hora, Dia, Semana, Mês, Trimestre, Ano e Agregado.

## Como o Report Builder processa a granularidade

Suponha que você escolha um intervalo de datas para um mês com granularidade [!UICONTROL Mês]. As solicitações mostram totais para a métrica com base em dados correspondentes a exatamente um mês. Se o intervalo de datas da sua solicitação abrange um trimestre, o relatório mostra três valores: um para cada unidade de mês, ou fração disso. Se hoje for 18 de março, escolher o último trimestre retorna um valor para 1º de janeiro - 31 de janeiro, outro valor para 1º de fevereiro - 28 de fevereiro e um valor final para 1º de março - 17 de março.
