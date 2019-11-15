---
description: O importador permite que você faça upload em massa de dados de classificação para relatórios de análise em um arquivo. A importação exige um formato de arquivo específico para fazer upload de dados de maneira bem-sucedida.
solution: Analytics
subtopic: Classifications
title: Arquivos de dados de classificação
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Arquivos de dados de classificação

O importador permite que você faça upload em massa de dados de classificação para relatórios de análise em um arquivo. A importação exige um formato de arquivo específico para fazer upload de dados de maneira bem-sucedida.

Para ajudá-lo a criar arquivos de dados válidos, é possível baixar um arquivo de modelo que oferece uma estrutura de arquivo no qual você pode colar os dados de classificações. Para obter mais informações, consulte [Download do modelo](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md)de classificações.

See [General File Structure](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) for more information about character limits in classifications.

See [Numeric 2 Classifications](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) for information about uploading data using numeric 2 classifications.

## Estrutura geral do arquivo

A ilustração a seguir é um exemplo de arquivo de dados:

![](assets/completed-saint-file.png)

Um arquivo de dados deve atender às seguintes regras de estrutura:

* As classificações não podem ter 0 (zero) como valor.
* A Adobe recomenda que você limite a quantidade de colunas de importações e exportações para 30.
* Os arquivos enviados devem usar UTF-8 sem a codificação de caracteres BOM.
* Caracteres especiais, como tecla tab, quebras de linha e aspas podem ser incorporados a uma célula, contanto que o formato de arquivo da versão 2.1 seja especificada e a célula seja devidamente [evitada](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md). Caracteres especiais incluem:

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   A vírgula não é um caractere especial.

* As classificações não podem conter um caractere (^) já que ele é usado para indicar uma subclassificação.
* Tenha cuidado ao usar hífen. For example, if you use a hyphen (-) in a Social term, Social recognizes the hyphen as a [!DNL Not] operator (the minus sign). For example, if you specify *`fragrance-free`* as a term using the import, Social recognizes the term as fragrance *`minus`* free and collects posts that mention *`fragrance`*, but not *`free`*.
* Os limites de caracteres são aplicados para classificar dados de relatório. Por exemplo, se você carregar um arquivo de texto de classificações para produtos ( *`s.products`*) com nomes de produtos com mais de 100 caracteres (bytes), os produtos não serão exibidos no relatório. Os códigos de rastreamento e todas as variáveis de conversão personalizadas (eVars) permitem 255 bytes.
* Arquivos de dados delimitados por tabulação (crie o arquivo de modelo usando qualquer aplicativo de planilha ou editor de texto).
* Either a [!DNL .tab] or [!DNL .txt] file extension.
* Um sinal de número (#) identifica a linha como um comentário do usuário. A Adobe ignora qualquer linha que começa com #.
* Um sinal de número duplo seguido de SC (##SC) identifica a linha como um comentário do cabeçalho de pré-processamento utilizado pelo relatório. Não exclua estas linhas.
* Exportações de classificação podem ter chaves duplicadas devido às quebras de linha na chave. No caso de uma exportação FTP ou de navegador, isso pode ser resolvido ao habilitar aspas para a conta FTP. Isso incluirá aspas em todas as chaves com quebras de linha.
* A célula C1 na primeira linha do arquivo de importação contém um identificador de versão que determina como a classificação lida com o uso de orçamentos no resto do arquivo.

   * v2.0 ignora os orçamentos e considera que todos são parte das chaves e dos valores especificados. Por exemplo, considere este valor: "Este é ""algum valor""". v2.0 interpretaria isso literalmente como: "Este é ""algum valor""".
   * v2.1 faz com que as classificações considerem os orçamentos como parte da formatação de arquivo utilizada nos arquivos Excel. Portanto, v2.1 formataria o exemplo acima como: Este é "algum valor".
   * Os problemas podem surgir quando v2.1 é especificado no arquivo, mas o que é necessário é v2.0; ou seja, quando aspas são utilizadas de forma ilegal na formatação do Excel. Por exemplo, se você tem um valor: "VP NO REPS" S/l Dress w/ Overlay. Com v2.1, esta formatação está incorreta (o valor deve ser cercado por aspas, e as aspas que fazem parte do valor real devem estar entre aspas) e as classificações não funcionarão além deste ponto.
   * Certifique-se de fazer o seguinte: altere o formato do arquivo para v2.0, modificando o cabeçalho (célula C1) dos arquivos enviados, OU implemente apropriadamente as aspas do Excel nos arquivos.

* A primeira linha (não comentário) do arquivo de dados contém os cabeçalhos de coluna usados para identificar os dados de classificação nessa coluna. O importador exige um formato de arquivo específico para fazer upload de dados de maneira bem-sucedida. Para obter mais informações, consulte Formato [de cabeçalho de](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)coluna.
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
   <td colname="col2"> <p>Determina que a coluna de dados representa um campo <span class="wintitle">PER Modifier</span>. See <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > PER Modifier Headings </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Problemas comuns de upload](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)


## Formato de cabeçalho de coluna

> [!NOTE] A Adobe recomenda que você limite a quantidade de colunas de importações e exportações para 30.

Os arquivos de classificação suporte os seguintes cabeçalhos de coluna:

### Chave

Cada valor deve ser exclusivo em todo o sistema. The value in this field corresponds to a value assigned to the [!DNL Analytics] variable in your Web site's [!DNL JavaScript] beacon. Data in this column might include ~autogen~ or any other unique tracking code.

### Cabeçalho da coluna de classificação

Por exemplo, os Reports &amp; Analytics incluem automaticamente duas classificações para as variáveis de [!UICONTROL Campanha]: [!UICONTROL Campanhas] e [!UICONTROL Elementos Criativos]. Para adicionar dados à classificação [!UICONTROL Campanhas], o cabeçalho da coluna no arquivo de dados de classificação será [!UICONTROL Campanhas].

> [!NOTE] Os valores no cabeçalho da coluna [!UICONTROL Classificações] devem corresponder exatamente à convenção de nomenclatura da classificação, ou a importação falhará. Por exemplo, se o administrador mudar [!UICONTROL Campanhas] para [!UICONTROL Nomes de Campanha Interna] no [!UICONTROL Gerenciador de Configuração da Campanha], o cabeçalho da coluna do arquivo deve ser alterado para o mesmo nome.

Além disso, o arquivo de dados oferece suporte às seguintes convenções adicionais de cabeçalho para identificar subclassificações e outras colunas de dados especializadas:

### Cabeçalho de subclassificação

Por exemplo, [!UICONTROL Campanhas^Proprietário] é um cabeçalho de coluna para a coluna que contém valores de [!UICONTROL Proprietário da campanha]. Da mesma forma, [!UICONTROL Elementos Criativos^Tamanho] é um cabeçalho de coluna para a coluna que contém a subclassificação [!UICONTROL Tamanho] da classificação [!UICONTROL Elementos Criativos]

### Cabeçalhos de métricas de classificação

Por exemplo, [!UICONTROL Campanhas^~Custo] refere-se à métrica [!UICONTROL Custo] na classificação [!UICONTROL Campanhas].

### Cabeçalho PER modifier

*`Per Modifier`* são denotados adicionando *`~per`* ao cabeçalho da métrica de classificação. Por exemplo, se o *`Metric`* cabeçalho for *`Campaigns^~Cost`*, o cabeçalho PER modifier será *`Campaigns^~Cost~per`*. A Adobe oferece suporte às seguintes *`PER Modifier`* palavras-chave:

Esses caracteres têm um significado especial em um arquivo de dados. Sempre que possível, evite o uso dessas palavras em nomes e dados de atributos.

**FIXO:** valor fixo. Não executa qualquer escala.

**DIA:** Multiplica o valor pelo número de dias no relatório.

**ORDEM:** Multiplica o valor pelo número de ordens para o item da linha no relatório.

**CHECKOUT:** Multiplica o valor pelo número de checkouts para o item da linha no relatório.

**UNIDADE:** Multiplica o valor pelo número de unidades para o item da linha no relatório.

**RECEITA:** Multiplica o valor pela receita para o item da linha no relatório.

**SCADD:** Multiplica o valor pelo número de vezes que o evento [!UICONTROL Adição ao carrinho de compras] foi chamado por item da linha no relatório.

**SCREMOVE:** Multiplica o valor pelo número de vezes que o evento [!UICONTROL Remoção do carrinho de compras] foi chamado por item da linha no relatório.

**INSTÂNCIA:** Multiplica o valor pelo número de instâncias para o item da linha no relatório.

**CLIQUE:** Multiplica o valor pelo número de cliques para o item da linha no relatório.

**EVENTO:** Multiplica o valor pelo número de vezes que um evento personalizado especificado ocorreu por item da linha no relatório.

**** Exemplo: Se a Campanha A custar $10.000, a coluna [!UICONTROL Campanhas^~Custo] contém um valor de 10.000 e a coluna [!UICONTROL Campanhas^~~Costper] contém [!UICONTROL FIXO]. Ao exibir o custo para a Campanha A nos relatórios, você notará $10.000 como o valor fixo para a Campanha A para o intervalo de datas do relatório.

**** Exemplo: Se a Campanha B custar aproximadamente $2 por clique, a coluna [!UICONTROL Campanhas^~Custo] conterá 2 e a coluna **[!UICONTROL Campanhas^~~Costper]** conterá [!UICONTROL CLICK]. When displaying the Cost for Campaign B in the reports, Adobe calculates (2 * [number of clicks]) on the fly for the date range of the report. Isso dá a você um cálculo do custo total com base no número de cliques realizados na Campanha B.

### Data

As datas das campanhas são normalmente intervalos (datas inicial e final) associados a campanhas individuais. As datas devem aparecer no formato AAAA/MM/DD. Por exemplo, 2013/06/15-2013/06/30.

Para obter mais informações, consulte [Classificações de conversão](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications).

> [!NOTE] Na versão de 10 de maio de 2018, [!DNL Analytics] Manutenção, a Adobe começou a limitar a funcionalidade de classificações numéricas e com data ativada. Esses tipos de classificações foram removidos das interfaces Admin e Importador de classificações. Nenhuma classificação numérica ou habilitada por data pode ser adicionada. As classificações existentes ainda podem ser gerenciadas (atualizadas, excluídas) por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Classificações] podem ser usadas para atribuir intervalos de datas a suas campanhas ou outras [!UICONTROL classificações]de conversão, o que permite avaliações de campanha mais precisas. Após especificar um intervalo de datas, qualquer valor correspondente que ocorrer fora do intervalo de datas não será classificado. Isso é útil para uma medição de campanha que deseja utilizar as datas exatas em que uma campanha estava Disponível, e não todos os hits que correspondem a campanha propriamente dita. Para classificar com sucesso um valor com intervalo de datas, as seguintes condições devem ser atendidas:

* The [!UICONTROL classification] must be based on a conversion variable.
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* O intervalo de datas envolvido deve conter uma data de início e uma data de término (opcional).

Para classificar campanhas baseadas em intervalo de datas:

1. Faça logon em [!DNL Analytics] Admin &gt; Classificações.
1. Clique na guia **[!UICONTROL Exportação de navegador], certifique-se de que as configurações da sua classificação date-enabled estão corretas e, em seguida, clique em Exportar arquivo.**
1. Abra esse arquivo no Microsoft Excel ou outro editor de planilhas.
1. Uma das colunas terminará com

   ^~período~que é a coluna na qual inserir o intervalo de datas.
1. Nessa coluna, insira o intervalo de datas de cada valor no seguinte formato:

   `YYYY/MM/DD - YYYY/MM/DD`. Não deixe de:

   * Colocar espaços em ambos os lados do travessão.
   * Usar um hífen (-) para separar os intervalos, e não um traço ou um travessão.
   * Colocar um zero antes de meses com um só dígito.
   * Colocar um data de início para o intervalo de datas; a data de término é opcional.

1. Salve o arquivo e faça upload dele [!DNL Analytics] indo para Admin| Classificações| Importar arquivo.

> [!NOTE] Um valor de chave específico não pode ter mais de um intervalo de datas.

## Solução de problemas de classificações

* [Problemas comuns com o Upload](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html): artigo de base de conhecimento que descreve problemas resultantes de formatos de arquivos incorretos e conteúdos de arquivos.

