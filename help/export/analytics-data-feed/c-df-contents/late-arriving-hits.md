---
title: Ocorrências de chegada tardia
description: Saiba como os feeds de dados tratam as ocorrências que chegam tarde.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 4d0007d1a23a81f0d5ba60541b4f7b9ac7b00ace
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 21%

---

# Ocorrências com atraso de chegada {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Permitir ocorrências de chegada tardia"
>abstract="Selecione essa opção para incluir dados que chegaram depois que o trabalho de feed de dados terminou de processar dados na frequência de relatório definida (geralmente diária ou a cada hora). Com essa opção ativada, sempre que um feed de dados processa dados, ele verifica todas as ocorrências atrasadas que chegaram e as reúne com o próximo arquivo de feed de dados enviado."

<!-- markdownlint-enable MD034 -->

## Entenda as ocorrências de chegada tardia

Os dados históricos podem chegar depois que uma tarefa de feed de dados terminar o processamento de uma determinada hora ou dia, por exemplo, por meio de ocorrências com carimbos de data e hora ou fontes de dados.

Quando um feed de dados normalmente processa dados, ele só procura os dados em sua janela de relatório (normalmente a hora ou o dia mais recente). Se os dados chegarem depois que um feed terminar de processar essa janela de relatório, esses dados nunca serão incluídos em nenhum feed de dados.

Com as ocorrências de chegada tardia ativadas, o método de processamento muda para incluir esses dados. Toda vez que um feed de dados processa dados, ele verifica todas as ocorrências atrasadas que chegaram e as reúne no próximo arquivo de feed de dados enviado.

## Habilitar ocorrências de chegada tardia

Antes de ativar a opção para permitir ocorrências de chegada tardia para um feed de dados, considere o seguinte:

* Os dados de dias diferentes aparecem frequentemente nos feeds de dados quando as ocorrências de chegada tardia são ativadas. Certifique-se de que a plataforma usada para ingerir feeds de dados possa acomodar dados de dias diferentes dentro do mesmo arquivo.
* Se um arquivo de feed de dados for reprocessado, as ocorrências de chegada tardia incluídas no arquivo original serão incluídas no arquivo reprocessado quando o reprocessamento ocorrer nos primeiros 5 dias. Após 5 dias, as ocorrências de chegada tardia não são incluídas no arquivo reprocessado.

Você pode habilitar ocorrências de chegada tardia ao criar ou editar um feed de dados habilitando a opção **[!UICONTROL Permitir ocorrências de chegada tardia]**, conforme descrito em [Criar um feed de dados](/help/export/analytics-data-feed/create-feed.md).
