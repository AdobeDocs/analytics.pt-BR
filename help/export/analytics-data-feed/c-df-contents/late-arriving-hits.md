---
title: Ocorrências com atraso de chegada
description: Saiba como os feeds de dados tratam as ocorrências que chegam tarde.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 5816868d3899d2938330471d1e59757141b16c69
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 70%

---

# Ocorrências com atraso de chegada {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Permitir ocorrências de chegada tardia"
>abstract="Selecione essa opção para incluir dados que chegaram depois que o trabalho de feed de dados terminou de processar dados na frequência de relatório definida (diariamente, a cada hora ou a cada 15 minutos). Com essa opção ativada, sempre que um feed de dados processa dados, ele verifica todas as ocorrências atrasadas que chegaram e as reúne com o próximo arquivo de feed de dados enviado."

<!-- markdownlint-enable MD034 -->

Os dados históricos podem chegar depois que um processo de feed de dados terminar o processamento de uma determinada hora ou dia, por exemplo, por meio de ocorrências com carimbos de data e hora ou fontes de dados. As ocorrências posteriores são uma configuração de personalização de backend fornecida pela Adobe para ajudar a incluir esses dados nos feeds de dados.

## Como as ocorrências de chegada tardias funcionam

Quando um feed de dados normalmente processa dados, ele só procura os dados em sua janela de relatório (normalmente a hora ou o dia mais recente). Se os dados chegarem depois que um feed terminar de processar essa janela de relatório, esses dados nunca serão incluídos em nenhum feed de dados.

Com as ocorrências de chegada atrasadas habilitadas, o método de processamento muda para incluir esses dados. Toda vez que um feed de dados processa dados, ele verifica todas as ocorrências atrasadas que chegaram e as reúne no próximo arquivo de feed de dados enviado para o site FTP.

## Habilitar ocorrências de chegada atrasadas

As ocorrências de chegada tardia podem ser habilitadas manualmente pela Adobe em feeds de dados individuais. Antes de fazer isso, considere o seguinte:

* Os dados de dias diferentes aparecem frequentemente nos feeds de dados quando as ocorrências de chegada tardia são habilitadas. Certifique-se de que a plataforma usada para ingerir feeds de dados possa acomodar dados de dias diferentes dentro do mesmo arquivo.
* Se um arquivo de feed de dados for reprocessado, as ocorrências de chegada tardia incluídas no arquivo original serão incluídas no arquivo reprocessado quando o reprocessamento ocorrer nos primeiros 5 dias. Após 5 dias, as ocorrências de chegada atrasadas não são incluídas no arquivo reprocessado.

Se você quiser habilitar ocorrências de chegada tardia para um feed de dados recorrente existente, peça a um usuário suportado para entrar em contato com o Atendimento ao cliente e incluir o seguinte:

* Uma observação que você gostaria de habilitar ocorrências de chegada tardia para um feed de dados específico
* ID do conjunto de relatórios
* Nome do feed de dados
