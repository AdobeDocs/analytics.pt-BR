---
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042
translation-type: tm+mt

---
# Atraso de chegada de ocorrências

Os dados históricos podem chegar depois que um serviço de feed de dados termina o processamento para uma hora ou dia específico, como por meio de ocorrências com carimbo de data e hora ou fontes de dados. Atrasar ocorrências é uma personalização de backend fornecida pela Adobe para ajudar a incluir esses dados em feeds de dados.

## Como o atraso na chegada das ocorrências funciona

Quando um feed de dados normalmente processa dados, ele só observa os dados na janela de relatórios (normalmente, a hora ou o dia mais recente). Se os dados chegarem depois que um feed terminar de processar a janela, esses dados nunca serão incluídos em nenhum feed de dados.

Com o atraso de ocorrências ativadas, o método de processamento muda para incluir esses dados. Toda vez que um feed de dados processa dados, ele observa quaisquer ocorrências atrasadas que chegaram e batem no próximo arquivo de feed de dados enviado para o site FTP.

## Ativação de ocorrências atrasadas

A chegada tardia de ocorrências pode ser ativada manualmente pela Adobe em feeds de dados individuais. Antes de fazer isso, considere o seguinte:

* Os dados por dias diferentes são exibidos com frequência nos feeds de dados quando os hits chegam ao fim. Certifique-se de que a plataforma usada para assimilar feeds de dados pode acomodar os dados de dias diferentes dentro do mesmo arquivo.
* A chegada tardia de ocorrências aumenta o tempo de processamento. Normalmente, esse atraso é menor que hora, mas pode ser várias horas ou mais se o conjunto de relatórios receber um grande número de ocorrências atrasadas. A Adobe recomenda ativar essa configuração se a chegada oportuna para feeds de dados for fundamental para o fluxo de trabalho de sua organização.
* Se um arquivo de feed de dados for reprocessado, o atraso de chegada das ocorrências incluídas no arquivo original não será incluído no arquivo reprocessado.

Se você quiser ativar a chegada tardia de ocorrências para um feed de dados recorrente existente, entre em contato com o Atendimento ao cliente e inclua o seguinte:

* Uma nota que você gostaria de ativar atrasando a chegada de ocorrências para um feed de dados específico
* ID do conjunto de relatórios
* Nome do feed de dados
