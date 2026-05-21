---
title: Hora do dia
description: A hora numérica do dia, independentemente do dia.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
TQID: https://experienceleague.adobe.com/cktusukSxy7fHIIUi-7MSmx8Gl9FlUObfmJGS3VC3Jw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 82%

---

# Hora do dia

A [dimensão](overview.md) de &quot;Hora do dia&quot; informa a hora numérica de qualquer dia como um item de dimensão. Por exemplo, se você tiver um relatório que abrange de 1º de janeiro a 7 de janeiro, a primeira hora de cada dia será agrupada no mesmo item de dimensão. Esse relatório é importante se você quiser que um relatório seja dividido por hora relativa do dia, mas não quiser horas estáticas como itens de dimensão. Ela é especialmente valiosa como uma dimensão em relatórios programados, já que essa dimensão é acumulada com o intervalo de datas selecionado.

Essa dimensão se baseia no fuso horário do conjunto de relatórios, e não no fuso horário local do visitante. Por exemplo, se o seu conjunto de relatórios estiver no Horário da Montanha e um visitante da Califórnia visitar seu site às 10:00 AM, no horário do Pacífico, a ocorrência é agrupada abaixo do item de dimensão `11:00 AM`. Se você quiser uma dimensão que registre o tempo do visitante local, a Adobe recomenda usar o plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem `12:00 AM` - `11:00 PM`, representando a hora do dia em que a ocorrência aconteceu (arredondada para baixo). Por exemplo, se uma ocorrência foi gerada às 15h00, ela se agrupa no item de dimensão `3:00 PM`.:58

## Horário de verão

O horário de verão é uma prática em que os relógios são adiantados uma hora na primavera e atrasados uma hora no outono. Se o fuso horário de um conjunto de relatórios usar horário de verão, a Adobe ajusta os dados de acordo com essa hora.

* **Quando o horário de verão começar**: em março, os relatórios geralmente mostram um intervalo de uma hora nos dados em que o horário de verão começa. A hora não existia, portanto, não faz parte da coleção de dados. Observe que uma pequena quantidade de dados ainda pode chegar a essa hora. Os servidores de coleção de dados da Adobe levam vários segundos (até um minuto) para considerar os ajustes de horário de verão.
* **Quando o horário de verão terminar**: em novembro, os relatórios geralmente mostram uma hora dupla em que o horário de verão termina. A hora aconteceu duas vezes, então ambas as horas são agregadas nos relatórios.
