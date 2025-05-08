---
description: O importador permite que você faça upload em massa de dados de classificação para relatórios de análise em um arquivo. A importação exige um formato de arquivo específico para fazer upload de dados de maneira bem-sucedida.
title: Arquivos de dados de classificação
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
source-git-commit: 04c626b1159be3e61569e462bf9d12957bd2a333
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 90%

---

# Arquivos de dados de classificação (herdados)

O importador permite que você faça upload em massa de dados de classificação para relatórios de análise em um arquivo. A importação exige um formato de arquivo específico para fazer upload de dados de maneira bem-sucedida.

Para ajudá-lo a criar arquivos de dados válidos, é possível baixar um arquivo de modelo que oferece uma estrutura de arquivo no qual você pode colar os dados de classificações. Para obter mais informações, consulte [Baixar modelo de classificações](/help/components/classifications/importer/c-download-saint-data.md).

Consulte [Estrutura geral do arquivo](/help/components/classifications/importer/c-saint-data-files.md) para obter mais informações sobre limites de caracteres nas classificações.

## Estrutura geral do arquivo

A ilustração a seguir é um exemplo de arquivo de dados:

![](assets/completed-saint-file.png)

Um arquivo de dados deve atender às seguintes regras de estrutura:

* As classificações não podem ter 0 (zero) como valor.
* A Adobe recomenda limitar a quantidade de colunas de importações e exportações para 30.
* Os arquivos enviados devem usar UTF-8 sem a codificação de caracteres BOM.
* É possível incorporar caracteres especiais (como tabulações, novas linhas e aspas) em uma célula, desde que o formato de arquivo v2.1 seja especificado e a célula tenha o [escape](/help/components/classifications/importer/importer-faq.md) adequado. Caracteres especiais incluem:

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  A vírgula não é um caractere especial.

* Os nomes de classificação não podem conter um sinal de interpolação (^), pois esse caractere é usado para indicar uma subclassificação.
* Tenha cuidado ao usar hífen. Por exemplo, se você usar um hífen (-) em um termo Social, o Social reconhece o hífen como um operador [!DNL Not] (o sinal de menos). Por exemplo, se você especificar *`fragrance-free`* como um termo usando a importação, o Social reconhece o termo como sem *`minus`* perfume e coleta as publicações que mencionam *`fragrance`*, mas não *`free`*.
* Os limites de caracteres são aplicados para classificar dados de relatório. Por exemplo, se você fizer upload de um arquivo de texto de classificações para produtos (*`s.products`*) com nomes de produtos com mais de 100 caracteres (bytes), os produtos não serão exibidos no relatório. Os códigos de rastreamento e todas as variáveis de conversão personalizadas (eVars) permitem 255 bytes. Essa política também se estende aos valores de coluna de classificação e subclassificação, que estão sujeitos ao mesmo limite de 255 bytes.
* Arquivos de dados delimitados por tabulação (crie o arquivo de modelo usando qualquer aplicativo de planilha ou editor de texto).
* Arquivo de extensão `.tab` ou `.txt`.
* Um sinal de número (#) identifica a linha como um comentário do usuário. A Adobe ignora qualquer linha que começa com #.
* Um sinal de dois quilos seguido por SC (`## SC`) identifica a linha como um comentário de cabeçalho de pré-processamento usado pelos relatórios. Não exclua estas linhas.
* Exportações de classificação podem ter chaves duplicadas devido às quebras de linha na chave. No caso de uma exportação FTP ou de navegador, isso pode ser resolvido ao habilitar aspas para a conta FTP. Isso incluirá aspas em todas as chaves com quebras de linha.
* A célula C1 na primeira linha do arquivo de importação contém um identificador de versão que determina como a classificação lida com o uso de orçamentos no resto do arquivo.

   * v2.0 ignora os orçamentos e considera que todos são parte das chaves e dos valores especificados. Por exemplo, considere este valor: &quot;Este é &quot;&quot;algum valor&quot;&quot;&quot;. v2.0 interpretaria isso literalmente como: &quot;Este é &quot;&quot;algum valor&quot;&quot;&quot;.
   * v2.1 faz com que as classificações considerem os orçamentos como parte da formatação de arquivo utilizada nos arquivos Excel. Portanto, v2.1 formataria o exemplo acima como: Este é &quot;algum valor&quot;.
   * Os problemas podem surgir quando v2.1 é especificado no arquivo, mas o que é necessário é v2.0; ou seja, quando aspas são utilizadas de forma ilegal na formatação do Excel. Por exemplo, se você tem um valor: &quot;VP NO REPS&quot; S/l Dress w/ Overlay. Com v2.1, esta formatação está incorreta (o valor deve ser cercado por aspas, e as aspas que fazem parte do valor real devem estar entre aspas) e as classificações não funcionarão além deste ponto.
   * Certifique-se de fazer um dos seguintes: altere o formato do arquivo para v2.0, modificando o cabeçalho (célula C1) dos arquivos enviados, OU implemente apropriadamente as aspas do Excel nos arquivos.

* A primeira linha (não comentário) do arquivo de dados contém os cabeçalhos de coluna usados para identificar os dados de classificação nessa coluna. O importador exige um formato de arquivo específico para fazer upload de dados de maneira bem-sucedida. Para obter mais informações, consulte [Formato de cabeçalho de coluna](/help/components/classifications/importer/c-saint-data-files.md).
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
   <td colname="col2"> <p>Exige que a Adobe gere automaticamente uma id única para este elemento. </p> <p>No contexto de campanha, este valor de controle instrui a Adobe a atribuir um identificador para cada elemento criativo. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Chave</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Determina que a coluna de dados representa o intervalo de dias associado ao item. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo vazio </p> </td> 
   <td colname="col2"> <p>Representa um valor NULO para o campo atual. Use este controle se uma coluna de dados específica não se aplicar ao registro atual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER Modifiers </p> </td> 
   <td colname="col2"> <p>Determina que a coluna de dados representa um campo <span class="wintitle">PER Modifier</span>. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Cabeçalhos PER Modifier</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formato do cabeçalho de coluna

>[!NOTE]
>
>A Adobe recomenda limitar a quantidade de colunas de importações e exportações para 30.

Os arquivos de classificação suporte os seguintes cabeçalhos de coluna:

### Chave

Cada valor deve ser exclusivo em todo o sistema. O valor deste campo corresponde a um valor atribuído à variável do [!DNL Analytics] no beacon do [!DNL JavaScript] do site. Os dados desta coluna devem incluir ~autogen~ ou qualquer outro código de acompanhamento exclusivo.

### Cabeçalho da coluna de classificação

>[!NOTE]
>
>Os valores no cabeçalho da coluna [!UICONTROL Classificações] devem corresponder exatamente à convenção de nomeação da classificação ou a importação não ocorrerá. Por exemplo, se o(a) admin alterar [!UICONTROL Campanhas] para [!UICONTROL Nomes de campanhas internas] no [!UICONTROL Gerenciador de configuração de campanhas], o cabeçalho da coluna do arquivo deverá mudar para corresponder essa alteração. “Chave” é um valor de classificação reservado (cabeçalho). Não é permitido utilizar novas classificações chamadas “Chave”.

Além disso, o arquivo de dados oferece suporte às seguintes convenções de cabeçalho adicionais para identificar subclassificações e outras colunas de dados especializadas:

### Cabeçalho de subclassificação

Por exemplo, `Campaigns^Owner` é um cabeçalho de coluna para a coluna que contém `Campaign Owner` valores. Da mesma forma, `Creative Elements^Size` é um cabeçalho de coluna para a coluna que contém a subclassificação `Size` da classificação `Creative Elements`.

## Resolução de problemas envolvendo classificações

* [Problemas comuns com o Upload](https://helpx.adobe.com/br/analytics/kb/common-saint-upload-issues.html): artigo de base de conhecimento que descreve problemas resultantes de formatos de arquivos incorretos e conteúdos de arquivos.
