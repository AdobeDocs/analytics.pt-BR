---
description: O importador permite que você faça upload em massa de dados de classificação para relatórios de análise em um arquivo. A importação exige um formato de arquivo específico para fazer upload de dados de maneira bem-sucedida.
subtopic: Classifications
title: Arquivos de dados de classificação
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Arquivos de dados de classificação

O importador permite que você faça upload em massa de dados de classificação para relatórios de análise em um arquivo. A importação exige um formato de arquivo específico para fazer upload de dados de maneira bem-sucedida.

Para ajudá-lo a criar arquivos de dados válidos, é possível baixar um arquivo de modelo que oferece uma estrutura de arquivo no qual você pode colar os dados de classificações. Para obter mais informações, consulte [Baixar modelo de classificações](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md).

Consulte [Estrutura geral do arquivo](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) para obter mais informações sobre limites de caracteres nas classificações.

Consulte [Classificações numéricas 2](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) para obter mais informações sobre como fazer upload de dados usando as classificações numéricas 2.

## Estrutura geral do arquivo

A ilustração a seguir é um exemplo de arquivo de dados:

![](assets/completed-saint-file.png)

Um arquivo de dados deve atender às seguintes regras de estrutura:

* As classificações não podem ter 0 (zero) como valor.
* A Adobe recomenda que você limite a quantidade de colunas de importações e exportações para 30.
* Os arquivos enviados devem usar UTF-8 sem a codificação de caracteres BOM.
* Caracteres especiais, como tecla tab, quebras de linha e aspas podem ser incorporados a uma célula, contanto que o formato de arquivo da versão 2.1 seja especificada e a célula seja devidamente  [evitada](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md). Caracteres especiais incluem:

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   A vírgula não é um caractere especial.

* As classificações não podem conter um caractere (^) já que ele é usado para indicar uma subclassificação.
* Tenha cuidado ao usar hífen. Por exemplo, se você usar um hífen (-) em um termo Social, o Social reconhece o hífen como um operador [!DNL Not] (o sinal de menos). Por exemplo, se você especificar *`fragrance-free`* como um termo usando a importação, o Social reconhece o termo como sem *`minus`* perfume e coleta as publicações que mencionam *`fragrance`*, mas não *`free`*.
* Os limites de caracteres são aplicados para classificar dados de relatório. Por exemplo, se você fizer upload de um arquivo de texto de classificações para produtos (*`s.products`*) com nomes de produtos com mais de 100 caracteres (bytes), os produtos não serão exibidos no relatório. Os códigos de rastreamento e todas as variáveis de conversão personalizadas (eVars) permitem 255 bytes.
* Arquivos de dados delimitados por tabulação (crie o arquivo de modelo usando qualquer aplicativo de planilha ou editor de texto).
* Arquivo de extensão [!DNL .tab] ou [!DNL .txt].
* Um sinal de número (#) identifica a linha como um comentário do usuário. A Adobe ignora qualquer linha que começa com #.
* Um sinal de número duplo seguido de SC (##SC) identifica a linha como um comentário do cabeçalho de pré-processamento utilizado pelo relatório. Não exclua estas linhas.
* Exportações de classificação podem ter chaves duplicadas devido às quebras de linha na chave. No caso de uma exportação FTP ou de navegador, isso pode ser resolvido ao habilitar aspas para a conta FTP. Isso incluirá aspas em todas as chaves com quebras de linha.
* A célula C1 na primeira linha do arquivo de importação contém um identificador de versão que determina como a classificação lida com o uso de orçamentos no resto do arquivo.

   * v2.0 ignora os orçamentos e considera que todos são parte das chaves e dos valores especificados. Por exemplo, considere este valor: &quot;Este é &quot;&quot;algum valor&quot;&quot;&quot;. v2.0 interpretaria isso literalmente como: &quot;Este é &quot;&quot;algum valor&quot;&quot;&quot;.
   * v2.1 faz com que as classificações considerem os orçamentos como parte da formatação de arquivo utilizada nos arquivos Excel. Portanto, v2.1 formataria o exemplo acima como: Este é &quot;algum valor&quot;.
   * Os problemas podem surgir quando v2.1 é especificado no arquivo, mas o que é necessário é v2.0; ou seja, quando aspas são utilizadas de forma ilegal na formatação do Excel. Por exemplo, se você tem um valor: &quot;VP NO REPS&quot; S/l Dress w/ Overlay. Com v2.1, esta formatação está incorreta (o valor deve ser cercado por aspas, e as aspas que fazem parte do valor real devem estar entre aspas) e as classificações não funcionarão além deste ponto.
   * Certifique-se de fazer o seguinte: altere o formato do arquivo para v2.0, modificando o cabeçalho (célula C1) dos arquivos enviados, OU implemente apropriadamente as aspas do Excel nos arquivos.

* A primeira linha (não comentário) do arquivo de dados contém os cabeçalhos de coluna usados para identificar os dados de classificação nessa coluna. O importador exige um formato de arquivo específico para fazer upload de dados de maneira bem-sucedida. Para obter mais informações, consulte [Formato de cabeçalho de coluna](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).
* As linhas de dados encontram-se logo após a linha de cabeçalho em um arquivo de dados. Cada linha de dados deve conter um campo de dados para cada cabeçalho de coluna.
* O arquivo de dados oferece suporte para os seguintes códigos de controle, os quais a Adobe usa para fornecer estrutura para o arquivo e importar os dados de classificações corretamente:

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CÓDIGO DE CONTROLE </th> 
   <th colname="col2" class="entry"> DESCRIÇÃO </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;New Line&gt; </p> </td> 
   <td colname="col2"> <p>Um caractere de nova linha é o único delimitador compatível entre linhas/registros de datas no arquivo de dados. Normalmente, você só precisa inserir esses caracteres especificamente ao escrever um programa para gerar automaticamente arquivos de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>Exige que a Adobe gere automaticamente uma id exclusiva para este elemento. </p> <p>No contexto de campanha, este valor de controle instrui a Adobe a atribuir um identificador para cada elemento criativo. Consulte <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > Chave </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Determina que a coluna de dados representa o intervalo de dias associado ao item. Consulte <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > Data </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo vazio </p> </td> 
   <td colname="col2"> <p>Representa um valor NULO para o campo atual. Use este controle se uma coluna de dados específica não se aplicar ao registro atual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER Modifiers </p> </td> 
   <td colname="col2"> <p>Determina que a coluna de dados representa um campo <span class="wintitle">PER Modifier</span>. Consulte <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  >Cabeçalhos PER Modifier</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Problemas de upload do comuns](https://helpx.adobe.com/br/analytics/kb/common-saint-upload-issues.html)


## Formato do cabeçalho de coluna

>[!NOTE] A Adobe recomenda que você limite a quantidade de colunas de importações e exportações para 30.

Os arquivos de classificação suporte os seguintes cabeçalhos de coluna:

### Chave

Cada valor deve ser exclusivo em todo o sistema. O valor deste campo corresponde a um valor atribuído à variável do [!DNL Analytics] no beacon do [!DNL JavaScript] do site. Os dados desta coluna devem incluir ~autogen~ ou qualquer outro código de acompanhamento exclusivo.

### Cabeçalho da coluna de classificação

Por exemplo, relatórios e análises incluem automaticamente duas classificações para [!UICONTROL Campaign] variáveis: [!UICONTROL Campaigns] e [!UICONTROL Creative Elements]. To add data to the [!UICONTROL Campaigns] classification, the column heading in the classification data file would be [!UICONTROL Campaigns].

>[!NOTE] Os valores no cabeçalho da [!UICONTROL Classifications] coluna devem corresponder exatamente à convenção de nomenclatura da classificação, ou a importação falhará. Por exemplo, se o administrador mudar [!UICONTROL Campaigns] para [!UICONTROL Internal Campaign Names] na coluna [!UICONTROL Campaign Set-up Manager], o cabeçalho da coluna do arquivo deve ser alterado para corresponder.

Além disso, o arquivo de dados oferece suporte às seguintes convenções adicionais de cabeçalho para identificar subclassificações e outras colunas de dados especializadas:

### Cabeçalho de subclassificação

Por exemplo, [!UICONTROL Campaigns^Owner] é um cabeçalho de coluna para a coluna que contém [!UICONTROL Campaign Owner] valores. Da mesma forma, [!UICONTROL Creative Elements^Size] é um cabeçalho de coluna para a coluna que contém a [!UICONTROL Size] subclassificação da [!UICONTROL Creative Elements] classificação.

### Cabeçalhos de métrica de classificação

Por exemplo, [!UICONTROL Campaigns^~Cost] se refere à [!UICONTROL Cost] métrica na [!UICONTROL Campaigns] classificação.

### Cabeçalho PER modifier

Os cabeçalhos *`Per Modifier`* são indicados adicionando *`~per`* ao cabeçalho de métrica de classificação. Por exemplo, se o cabeçalho *`Metric`* for *`Campaigns^~Cost`*, o cabeçalho modificador PER será *`Campaigns^~Cost~per`*. A Adobe oferece suporte às seguintes palavras-chave *`PER Modifier`*:

Esses caracteres têm um significado especial em um arquivo de dados. Sempre que possível, evite o uso dessas palavras em nomes e dados de atributos.

**FIXO:** valor fixo. Não executa qualquer escala.

**DIA:** Multiplica o valor pelo número de dias no relatório.

**ORDEM:** Multiplica o valor pelo número de ordens para o item da linha no relatório.

**CHECKOUT:** Multiplica o valor pelo número de checkouts para o item da linha no relatório.

**UNIDADE:** Multiplica o valor pelo número de unidades para o item da linha no relatório.

**RECEITA:** Multiplica o valor pela receita para o item da linha no relatório.

**SCADD:** Multiplica o valor pelo número de vezes que o [!UICONTROL Shopping Cart Add] evento foi chamado por item de linha no relatório.

**SCREMOVER:** Multiplica o valor pelo número de vezes que o [!UICONTROL Shopping Cart Remove] evento foi chamado por item de linha no relatório.

**INSTÂNCIA:** Multiplica o valor pelo número de instâncias para o item da linha no relatório.

**CLIQUE:** Multiplica o valor pelo número de cliques para o item da linha no relatório.

**EVENTO:** Multiplica o valor pelo número de vezes que um evento personalizado especificado ocorreu por item da linha no relatório.

**Exemplo:** Se a Campanha A custar US$ 10.000, a [!UICONTROL Campaigns^~Cost] coluna conterá um valor de 10.000 e a coluna [!UICONTROL Campaigns^~~Costper] conterá [!UICONTROL FIXED]. Ao exibir o custo para a Campanha A nos relatórios, você notará $10.000 como o valor fixo para a Campanha A para o intervalo de datas do relatório.

**Exemplo:** Se a Campanha B custar aproximadamente US$ 2 por clique, a [!UICONTROL Campaigns^~Cost] coluna conterá 2 e a coluna **[!UICONTROL Campaigns^~~Costper]** conterá [!UICONTROL CLICK]. Ao exibir o custo para a Campanha B nos relatórios, a Adobe calcula (2 * [número de cliques]) como o valor dinâmico para o intervalo de datas do relatório. Isso dá a você um cálculo do custo total com base no número de cliques realizados na Campanha B.

### Data

As datas das campanhas são normalmente intervalos (datas inicial e final) associados a campanhas individuais. As datas devem aparecer no formato AAAA/MM/DD. Por exemplo, 2013/06/15-2013/06/30.

Para obter mais informações, consulte [Classificações de conversão](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html).

>[!NOTE] Na Versão de manutenção do [!DNL Analytics] de 10 de maio de 2018, a Adobe começou a limitar a funcionalidade de classificações numéricas e habilitadas por data. Esses tipos de classificações foram removidos das interfaces Admin e Importador de classificações. Nenhuma classificação numérica ou habilitada por data pode ser adicionada. As classificações existentes ainda podem ser gerenciadas (atualizadas, excluídas) por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Classifications] pode ser usado para atribuir intervalos de datas às suas campanhas ou outras conversões [!UICONTROL classifications], o que permite uma medição de campanha mais precisa. Após especificar um intervalo de datas, qualquer valor correspondente que ocorrer fora do intervalo de datas não será classificado. Isso é útil para uma medição de campanha que deseja utilizar as datas exatas em que uma campanha estava Disponível, e não todos os hits que correspondem a campanha propriamente dita. Para classificar com sucesso um valor com intervalo de datas, as seguintes condições devem ser atendidas:

* The [!UICONTROL classification] must be based on a conversion variable.
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* O intervalo de datas envolvido deve conter uma data de início e uma data de término (opcional).

Para classificar campanhas baseadas em intervalo de datas:

1. Faça logon em [!DNL Analytics] Admin > Classificações.
1. Click the **[!UICONTROL Browser Export]** tab, ensure the settings to your date-enabled classification are correct, then click Export File.
1. Abra esse arquivo no Microsoft Excel ou outro editor de planilhas.
1. Uma das colunas terminará com

   ^~período~
que é a coluna em que o intervalo de datas deve ser inserido.
1. Nessa coluna, insira o intervalo de datas de cada valor no seguinte formato:

   `YYYY/MM/DD - YYYY/MM/DD`. Não deixe de:

   * Colocar espaços em ambos os lados do travessão.
   * Usar um hífen (-) para separar os intervalos, e não um traço ou um travessão.
   * Colocar um zero antes de meses com um só dígito.
   * Colocar um data de início para o intervalo de datas; a data de término é opcional.

1. Salve o arquivo e faça upload no [!DNL Analytics] acessando Admin| Classificações | Importar arquivo.

>[!NOTE] Um valor de chave específico não pode ter mais de um intervalo de datas.

## Resolução de problemas envolvendo classificações

* [Problemas comuns com o Upload](https://helpx.adobe.com/br/analytics/kb/common-saint-upload-issues.html): artigo de base de conhecimento que descreve problemas resultantes de formatos de arquivos incorretos e conteúdos de arquivos.

