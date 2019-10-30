---
description: Informações sobre o modelo .txt da Fonte de dados.
seo-description: Informações sobre o modelo .txt da Fonte de dados.
seo-title: Referência do arquivo de importação
solution: Analytics
subtopic: Fontes de dados
title: Referência do arquivo de importação
topic: Desenvolvedor e implementação
uuid: cc58f8d8-cb6e-4908-846f-0a41c6da805d
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Referência do arquivo de importação

Informações sobre o modelo .txt da Fonte de dados.

Utilize o Assistente das Fontes de Dados para gerar um modelo de importação. O arquivo de importação das Fontes de Dados inclui os seguintes dados:

* Um sinal de número (#) identifica aquela linha como um comentário.
* É possível inserir comentários adicionais ao arquivo, conforme necessário.
* Um comentário que apresenta o título do arquivo modelo.
*  Um comentário que apresenta os nomes da métrica externa e das dimensões dos dados especificados no [!UICONTROL Assistente de ativação da fonte de dados].

Os títulos das colunas são utilizados para identificar os dados de cada coluna do arquivo da Fonte de Dados. Há três tipos de títulos de coluna:

**Data**: (Obrigatório) Uma marca de tempo para cada linha de dados no arquivo.

**Variáveis**: Os nomes das variáveis de relatório mapeadas para as dimensões de dados da fonte de dados.

**Eventos**: Os nomes dos eventos mapeados para as métricas da fonte de dados.

Use o modelo da Fonte de dados para criar um arquivo de Fontes de dados que contenha os dados que você deseja carregar. Ao criar o arquivo da Fonte de Dados, lembre-se que:

* Com efeito, cada linha do arquivo da Fonte de Dados contém um registro de dados, em que cada registro é composto de diversos campos delimitados por tabulação. Os títulos das colunas no modelo da Fonte de Dados define a ordem desses campos. Por exemplo:

   ```
     #Sample data file for mycorp_report_suite 
     #Imported data for ad impressions applied to Event 6
     Date     Tracking Code      Event 6 
     1/1/2009     NYT8453A      8754
     1/1/2009     WSJ4453B      9492
     1/1/2009     BHG44563      10553
     1/2/2009     NYT8453A      6452
     1/2/2009     WSJ4453B      7237
     1/2/2009     BHG44563      9031
   ```

* Se você carregar vários arquivos de dados, as Fontes de Dados os carregarão em ordem alfabética. Os arquivos que precisam ser processados cronologicamente, devem ser nomeados de modo que sua ordem alfabética corresponda a sua ordem cronológica. Por exemplo:

   ```
   log_2009-01-01_13:00.txt
   log_2009-01-01_13:15.txt
   log_2009-01-01_13:30.txt
   ```

* Para acelerar o processamento de seu arquivo de Fontes de dados, a Adobe recomenda reunir os dados do evento (métrica) em uma única linha, por data.

   Por exemplo, se seu arquivo de Fontes de dados mapeia dados de impressão de anúncio para o Evento 6, crie uma linha de dados única que inclua o total de impressões de anúncio por dia, em vez de criar uma entrada de linha de dados separada para cada impressão de anúncio que ocorreu em um determinado dia.
* Se você precisa carregar dados de datas anteriores à criação de seu conjunto de relatórios, entre em contato com um Gerente de contas para alterar a data mais antiga de geração de relatórios.

**Arquivo .FIN**

Quando terminar de preencher o arquivo da Fonte de dados, você poderá fazer o FTP do arquivo no Analytics. No entanto, outro arquivo é necessário para que seus dados sejam processados. You will need to upload an empty text file with the same name of your data file, but with a [!DNL .fin] extension.

For example, if you upload a (tab-delimited) data file called [!DNL myproductdata.txt], you would also need to upload an empty text file called [!DNL myproductdata.fin]. Without the [!DNL .fin] file, data would never be processed.
