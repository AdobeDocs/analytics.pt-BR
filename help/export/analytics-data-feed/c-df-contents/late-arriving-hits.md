---
title: Ocorrências com atraso de chegada
description: Saiba como os feeds de dados tratam as ocorrências que chegam tarde.
translation-type: ht
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Ocorrências com atraso de chegada

Os dados históricos podem chegar depois que uma tarefa de feed de dados terminar o processamento de uma determinada hora ou dia, por exemplo, por meio de ocorrências com carimbos de data e hora ou fontes de dados. As ocorrências posteriores são uma configuração de personalização de backend fornecida pela Adobe para ajudar a incluir esses dados nos feeds de dados.

## Como as ocorrências de chegada tardias funcionam

Quando um feed de dados normalmente processa dados, ele só procura os dados em sua janela de relatório (normalmente a hora ou o dia mais recente). Se os dados chegarem depois que um feed terminar de processar essa janela de relatório, esses dados nunca serão incluídos em nenhum feed de dados.

Com as ocorrências de chegada atrasadas ativadas, o método de processamento muda para incluir esses dados. Toda vez que um feed de dados processa dados, ele verifica todas as ocorrências atrasadas que chegaram e as reúne no próximo arquivo de feed de dados enviado para o site FTP.

## Habilitar ocorrências de chegada atrasadas

As ocorrências de chegada tardia podem ser ativadas manualmente pela Adobe em feeds de dados individuais. Antes de fazer isso, considere o seguinte:

* Os dados de dias diferentes aparecem frequentemente nos feeds de dados quando as ocorrências de chegada tardia são ativadas. Certifique-se de que a plataforma usada para ingerir feeds de dados possa acomodar dados de dias diferentes dentro do mesmo arquivo.
* A chegada tardia de ocorrências aumenta o tempo de processamento. Normalmente, esse atraso é menor que a hora, mas pode ser de várias horas ou mais se o conjunto de relatórios receber um grande número de ocorrências em atraso. A Adobe recomenda não ativar essa configuração se a chegada oportuna para feeds de dados for imperativa para o fluxo de trabalho de sua organização.
* Se um arquivo de feed de dados for reprocessado, as ocorrências de chegada tardia incluídas no arquivo original não serão incluídas no arquivo reprocessado.

Se você quiser ativar ocorrências de chegada tardia para um feed de dados recorrente existente, peça a um usuário suportado para entrar em contato com o Atendimento ao cliente e incluir o seguinte:

* Uma observação que você gostaria de ativar ocorrências de chegada tardia para um feed de dados específico
* ID do conjunto de relatórios
* Nome do feed de dados
