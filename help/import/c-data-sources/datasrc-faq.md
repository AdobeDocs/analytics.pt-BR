---
description: Este tópico oferece as respostas às perguntas mais frequentes.
subtopic: Data sources
title: Perguntas frequentes da Fonte de Dados
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 2a5d38fe-5c5b-4275-bc44-e9cb02ec2f5d
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '1496'
ht-degree: 100%

---

# Perguntas frequentes da Fonte de Dados

Este tópico oferece as respostas às perguntas mais frequentes.

## Como vincular dados offline a eventos online? {#offline}

Para que fontes de dados de ID de transação vinculem dados offline a eventos online, deve-se habilitar a Gravação de ID de transação. Consulte [Gravação da ID de transação](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C) para obter mais informações.

## Quanto custa para usar o recurso da Fonte de Dados? {#cost}

As fontes de dados não resultam em tarifas adicionais além da chamada de servidor padrão. Os encargos de chamada de servidor se aplicam somente aos tipos de fontes de dados de processamento completo, nas quais as ocorrências individuais são enviadas em linhas de dados. As fontes de dados de nível de tráfego e agregado não resultam em custos adicionais.

## Como faço para incluir comentários nos arquivos das Fontes de Dados? {#comments}

Todas as linhas que iniciam com um sinal de número (#) em um arquivo das Fontes de Dados são tratadas como comentário.

## Preciso incluir uma coluna de data nos dados de minha planilha? {#date}

Sim. Como muitos relatórios de marketing são marcados pela coluna de datas, as Fontes de dados exigem uma coluna de datas.

## Posso armazenar dados nas variáveis que já estou utilizando? {#variables}

A Adobe recomenda que você selecione variáveis novas, sem uso, para importar os dados por meio das Fontes de dados. Se não estiver seguro com relação à configuração de seu arquivo de dados, ou quiser conhecer melhor os riscos da reutilização de variáveis, entre em contato com o Atendimento ao cliente.

## Posso excluir dados que foram importados com a Fonte de Dados? {#imported}

Não. Os dados carregados nos relatórios por meio das Fontes de dados não poderão ser removidos após a importação, nem mesmo por técnicos da Adobe. Eles são inseridos nos dados existentes de maneira permanente, e se tornam indistinguíveis dos dados inseridos pelos meios tradicionais de coleta de dados (ou seja, JavaScript, ActionSource, API de Inserção de Dados etc.). Por isso, o Adobe recomenda que o upload de dados das Fontes de Dados seja feito primeiro em um relatório de teste, e só depois em um conjunto de produção.

## Quantos dados posso importar de uma vez? {#amount}

O processamento é interrompido se o tamanho exceder 50 MB, e não reinicia até que o total seja inferior a 50 MB. Para limitar os atrasos na geração de relatórios, não carregue mais de 90 dias de dados por dia.

## Quando importo dados por meio das Fontes de dados, os dados existentes são substituídos? {#overwrite}

Os dados da Fonte de dados nunca substituirão os dados existentes no relatório. Em vez disso, eles são somados aos dados existentes.

## Quando carrego meus dados por meio das Fontes de dados, por que não recebo também as métricas? {#metrics}

Quando carrega os dados das Fontes de dados, você está carregando as métricas que estarão disponíveis na interface do relatório.

Por exemplo, se estiver carregando a Receita da central de atendimento para os produtos que vende no site, você poderá ter essa Receita da central de atendimento no mesmo relatório da Receita online. No entanto, você não conseguirá usá-la junto com Visitas, porque você não carregou o total de visitas com ela. A Adobe só consegue gerar relatórios sobre as métricas e os elementos carregados por meio das Fontes de dados (além das métricas comuns do relatório de marketing).

## O que acontece se eu passar valores negativos por meio das Fontes de dados? {#negative}

O valor é diminuído de forma correspondente.

## Qual a diferença entre a Fonte de Dados de Tráfego e de Conversão (Genérico)? {#traffic}

A Fonte de Dados de Tráfego carrega muito mais rapidamente, ao passo que simplesmente atualiza os valores resumidos nas tabelas adequadas. A Fonte de Dados Genérica com conversão de dados (eventos etc.) cria uma ocorrência para cada valor na coluna a ser processada.

Exemplo de arquivo:

<table id="table_D5408E0BDB984229B4C60A66BB53CEBB"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Date </code> </p> </td> 
   <td colname="col2"> <p> <code> Event15 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 01/01/2013 </code> </p> </td> 
   <td colname="col2"> <p> <code> 553 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

O exemplo acima cria 553 ocorrências para serem processadas no sistema cache.

## A Fonte de Dados faz sub-relações, correlações e definições de caminhos na conta? {#breakdown}

Como o processo da Fonte de Dados (&quot;para FD Genérica, não Tráfego&quot;) cria ocorrências individuais que são processadas por cache, o processo de sub-relação é utilizado, porém não o processo de correlação. A definição de caminhos tem o potencial para ser processada, mas cada ocorrência seria sua própria visita, de modo que nenhuma definição de caminho é criada. Os dados da definição de caminhos são gerados para importações de log da Web.

## Existe diferenciação entre letras maiúsculas e minúsculas nas extensões dos arquivos durante o upload de um arquivo de classificação ou das Fonte de dados? {#case}

Se as extensões do arquivo de upload das Fontes de dados ou de um arquivo classificação estiverem em letra maiúscula, os arquivos não serão processados. As extensões do arquivo de upload da Fonte de dados devem estar em letra minúscula. Por exemplo, [!DNL file.TXT] e [!DNL file.FIN] não serão processados. Da mesma maneira, [!DNL .TAB] e [!DNL .FIN] não serão processados. No entanto, [!DNL .txt] e [!DNL .fin] são processados.

## Posso acrescentar mais eventos no modelo gerado ou estou limitado a três? {#template}

É possível adicionar quantos eventos você desejar. Contudo, o assistente permite apenas três eventos. Após criar o arquivo modelo, você pode adicionar mais eventos, conforme necessário.

## O que acontece com um arquivo de Fonte de dados quando um ou mais registros têm um número diferente de colunas do registro do cabeçalho? {#header}

Se você tiver um arquivo de Fonte de dados em que um ou mais registros têm um número diferente de colunas do registro do cabeçalho, ocorrerá o seguinte:

* Um email é enviado ao criador da fonte de dados, notificando-o do erro.
* O arquivo não é processado devido à incompatibilidade das colunas.

## As informações das Fontes de dados são submetidas a rollup? {#rollup}

As informações das Fontes de dados podem ser submetidas a rollup; no entanto, o Atendimento ao cliente da Adobe precisa reprocessar o rollup a partir de uma data do histórico para incluir os dados. Por exemplo, se hoje é 31 de outubro de 2015 e você carregou dados de 1 a 15 de agosto de 2015 usando as fontes de dados, o rollup deverá ser configurado para reprocessar a partir de 1 de agosto de 2015 para que os dados recém-importados sejam incluídos.

Observe, também, que os dados nunca podem ser carregados diretamente em um conjunto de relatórios de rollup por meio de Fontes de dados. Se você precisa que esses dados sejam incluídos em um rollup, eles devem ser importados em um conjunto de relatórios padrão, também chamado *`child suite`* para o rollup. Para obter mais infirmações, em contato com o Atendimento ao cliente da Adobe.

## Por que o Relatório de exibições de página não mostra dados das Fontes de dados para um único dia, mas mostra os dados corretos para uma semana? {#week}

As Fontes de Dados não informam dados de hora em hora. Quando você tenta gerar um relatório para um dia específico, os dados apenas podem ser analisados por hora, portanto nada é exibido no relatório. É possível visualizar os dados somente quando estes forem detalhados em um nível de unidade diário ou maior, o que pode ser obtido por meio da geração de um relatório semanal ou mensal.

## Como são calculados os Visitantes únicos em um upload de Fonte de dados no log do servidor da Web? {#unique}

A quantidade de Visitantes únicos em um registro do servidor da Web é calculada como as diferentes combinações de *`IP Address`* e *`User Agent`* no registro da Web. Cada combinação exclusiva desses dois itens é calculada como um visitante único. Se a coluna [!UICONTROL Agente de usuário] estiver em branco (ou não estiver incluída no log da Web) não teremos como fazer a contagem de Visitantes únicos, e todos os dados carregados serão contados como apenas um Visitante único (mesmo se houver vários endereços IP).

## Nas Fontes de dados, como sei qual login pertence a qual conjunto de relatórios? {#login}

Nas Fontes de dados, a ID do conjunto de relatórios é a primeira parte do login acrescida de um número aleatório que identifica a fonte de dados específica que foi configurada. Por exemplo, `RSID-drmossdev5 Login-drmossdev5_0001343430`.

## Como a versão 15 e a segmentação afetam as fontes de dados? {#segmentation}

Na versão 15, as Fontes de Dados se comportam de forma diferente com base no tipo de fonte:

* Processamento completo, registro da Web e fontes de dados de ID da transação aparecem normalmente. Quando os segmentos são aplicados, os dados são filtrados de acordo com as regras de segmento.
* As fontes de dados padrão ou de conversão (campanhas com anúncios, CRM, satisfação do cliente, desempenho do site, dados resumidos genéricos, compras online, clientes potenciais e cotações, além de dados de canais offline) aparecem na versão 15. No entanto, como essas fontes de dados não estão vinculadas a visitas ou visitantes, elas são filtradas quando os segmentos são aplicados.

## As métricas importadas por meio de uma ID de transação estão disponíveis nos feeds de dados de sequência de cliques e no data warehouse? {#clickstream}

O feed de dados contém as métricas de ID de transação que foram recebidas. Contudo, se você carregar os dados de ID de transação para uma data no passado, a única maneira de obter esses dados é baixar o feed de dados novamente para esse dia.

## As eVars que persistem atualmente no Perfil do visitante são alocadas nas métricas carregadas por meio de fontes de dados? {#visitor}

Não para o processamento completo, sim para a ID de transação. Como as fontes de dados de processamento completo são processadas usando perfis de visitante diferentes, mesmo que as IDs do visitante correspondam, elas não serão associadas a uma perspectiva de alocação de eVar. Como as fontes de dados de ID de transação são associadas ao perfil do visitante principal, as eVars persistentes são alocadas aos eventos carregados usando a ID de transação.

## As eVars carregadas com fontes de dados persistem no comportamento online posterior? {#evars}

Não. As eVars carregadas pelas fontes de dados da ID de Transação serão lidas somente nas informações de perfil armazenadas, não atualizarão o perfil.
Não. As eVars são as únicas variáveis salvas no instantâneo do perfil do visitante.

## Como os eventos numéricos e de moeda funcionam com as fontes de dados? {#numeric}

O processamento completo é compatível apenas com formatos de lista de eventos herdados, excluindo o valor de evento numérico/de moeda/contador (mais de 1) diretamente na lista de eventos, ou seja `"eventNN,eventKK"` não `"eventNN=#.##"`. Isso significa que ele só oferecerá suporte a um evento de contador se for passado na coluna de eventos no arquivo de fonte de dados e incrementado em 1.

Se forem necessários eventos numéricos, de moeda ou de contador (mais de 1), use a lista de produtos:

```js
s.products="Footwear;Running Shoes;1;99.99;event1=4.50";
s.products="Footwear;Running Shoes;1;99.99;event1=4.50|event4=1.99";
```
