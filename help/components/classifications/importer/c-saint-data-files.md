---
description: O importador permite o upload em massa de dados de classificação para relatórios do Analytics em um arquivo. A importação requer um formato de arquivo específico para uploads de dados bem-sucedidos.
title: Arquivos de dados de classificação
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
TQID: https://experienceleague.adobe.com/NKh-IIAZg2rqdpsJJrM765aXYvKGtpLjGWdwWhbiGTw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 1045
ht-degree: 37%

---

# Arquivos de dados de classificação (herdados)

{{classification-importer-deprecation}}

O importador permite o upload em massa de dados de classificação para relatórios do Analytics em um arquivo. A importação requer um formato de arquivo específico para uploads de dados bem-sucedidos.

Para ajudá-lo a criar arquivos de dados válidos, você pode baixar um arquivo de modelo que fornece uma estrutura de arquivo na qual é possível colar os dados de classificações. Para obter mais informações, consulte [Baixar modelo de classificações](/help/components/classifications/importer/c-download-saint-data.md).

Consulte [Estrutura geral do arquivo](/help/components/classifications/importer/c-saint-data-files.md) para obter mais informações sobre limites de caracteres nas classificações.

## Estrutura geral do arquivo

A ilustração a seguir é um exemplo de arquivo de dados:

![](assets/completed-saint-file.png)

Um arquivo de dados deve seguir as seguintes regras de estrutura:

* As classificações não podem ter um valor de 0 (zero).
* A Adobe recomenda limitar a quantidade de colunas de importações e exportações para 30.
* Os arquivos carregados devem usar UTF-8 sem codificação de caracteres BOM.
* É possível incorporar caracteres especiais (como tabulações, novas linhas e aspas) em uma célula, desde que o formato de arquivo v2.1 seja especificado e a célula tenha o [escape](/help/components/classifications/importer/importer-faq.md) adequado. Os caracteres especiais incluem:

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  A vírgula não é um caractere especial.

* Os nomes de classificação não podem conter um sinal de interpolação (^), pois esse caractere é usado para indicar uma subclassificação.
* Tenha cuidado ao usar um hífen. Por exemplo, se você usar um hífen (-) em um termo Social, o Social reconhece o hífen como um operador [!DNL Not] (o sinal de menos). Por exemplo, se você especificar *`fragrance-free`* como um termo usando a importação, o Social reconhece o termo como sem *`minus`* perfume e coleta as publicações que mencionam *`fragrance`*, mas não *`free`*.
* Os limites de caracteres são aplicados para classificar dados de relatório. Por exemplo, se você fizer upload de um arquivo de texto de classificações para produtos (*`s.products`*) com nomes de produtos com mais de 100 caracteres (bytes), os produtos não serão exibidos no relatório. Os códigos de rastreamento e todas as variáveis de conversão personalizadas (eVars) permitem 255 bytes. Essa política também se estende aos valores de coluna de classificação e subclassificação, que estão sujeitos ao mesmo limite de 255 bytes.
* Arquivos de dados delimitados por tabulação (crie o arquivo de modelo usando qualquer aplicativo de planilha ou editor de texto).
* Arquivo de extensão `.tab` ou `.txt`.
* Um sinal de libra (#) identifica a linha como um comentário do usuário. O Adobe ignora qualquer linha que comece com #.
* Um sinal de dois quilos seguido por SC (`## SC`) identifica a linha como um comentário de cabeçalho de pré-processamento usado pelos relatórios. Não exclua essas linhas.
* As exportações de classificação podem ter chaves duplicadas devido a caracteres de nova linha na chave. Em uma exportação de FTP ou navegador, isso pode ser resolvido ativando as cotações da conta FTP. Isso colocará aspas ao redor de cada chave com caracteres de nova linha.
* A célula C1 na primeira linha do arquivo de importação contém um identificador de versão que determina como as classificações lidam com o uso de aspas no restante do arquivo.

   * A v2.0 ignora aspas e presume que todas fazem parte das chaves e valores especificados. Por exemplo, considere este valor: &quot;Este é &quot;&quot;algum valor&quot;&quot;. A v2.0 interpretaria isso literalmente como: &quot;Este é &quot;&quot;algum valor&quot;&quot;.
   * A v2.1 informa às classificações que as aspas fazem parte da formatação de arquivo usada em arquivos do Excel. Portanto, a v2.1 formataria o exemplo acima como: Este é &quot;algum valor&quot;.
   * Podem surgir problemas quando a versão 2.1 é especificada no arquivo, mas o que realmente se deseja é a versão 2.0, ou seja, quando as aspas são usadas de maneiras que são ilegais na formatação do Excel. Por exemplo, se você tiver um valor: &quot;VP NO REPS&quot; S/l Dress w/ Overlay. Com a v2.1, essa é uma formatação incorreta (o valor deve ser entre aspas de abertura e fechamento e as aspas que fazem parte do valor real devem ser evitadas por aspas) e as classificações não funcionarão além desse ponto.
   * Certifique-se de fazer um dos seguintes: altere o formato do arquivo para v2.0, modificando o cabeçalho (célula C1) dos arquivos enviados, OU implemente apropriadamente as aspas do Excel nos arquivos.

* A primeira linha (sem comentário) do arquivo de dados contém os cabeçalhos de coluna usados para identificar os dados de classificação nessa coluna. O importador requer um formato específico para os títulos das colunas. Para obter mais informações, consulte [Formato de cabeçalho de coluna](/help/components/classifications/importer/c-saint-data-files.md).
* Imediatamente após a linha de cabeçalho em um arquivo de dados, encontram-se as linhas de dados. Cada linha de dados deve conter um campo de dados para cada cabeçalho de coluna.
* O arquivo de dados oferece suporte aos seguintes códigos de controle, que o Adobe usa para fornecer estrutura ao arquivo e importar corretamente os dados de classificação:

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CÓDIGO DE CONTROLE </th> 
   <th colname="col2" class="entry"> DESCRIÇÃO </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;Nova linha&gt; </p> </td> 
   <td colname="col2"> <p>Um novo caractere de linha é o único delimitador compatível entre as linhas/registros de dados no arquivo de dados. Normalmente, você só precisa inserir esses caracteres especificamente ao gravar um programa para gerar arquivos de dados automaticamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>Solicita que o Adobe gere automaticamente uma ID exclusiva para esse elemento. </p> <p>No contexto da campanha, esse valor de controle instrui o Adobe a atribuir um identificador a cada elemento criativo. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Chave</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~período~ </p> </td> 
   <td colname="col2"> <p>Determina que a coluna de dados representa o intervalo de datas associado ao item. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo vazio </p> </td> 
   <td colname="col2"> <p>Representa um valor NULL para o campo atual. Use esta opção se uma determinada coluna de dados não se aplicar ao registro atual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>POR Modificadores </p> </td> 
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
