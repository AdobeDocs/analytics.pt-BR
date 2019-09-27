---
description: A classification is a way of categorizing Analytics variable data, then displaying the data in different ways when you generate reports.
seo-description: Uma classificação é uma forma de classificar os dados variáveis do Analytics e, em seguida, exibir os dados de maneiras diferentes ao gerar relatórios.
seo-title: Sobre as classificações
solution: Analytics
subtopic: Classificações
title: Sobre as classificações
topic: Ferramentas administrativas
uuid: abc1a1be-8e37-4b7e-81fd-3e99ac27fc6a
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Sobre as classificações

Uma classificação é uma forma de classificar os dados variáveis do Analytics e, em seguida, exibir os dados de maneiras diferentes ao gerar relatórios.

Visão geral em vídeo de [Classificações do Analytics](https://video.tv.adobe.com/v/16853/?captions=por_br).

**[!UICONTROL Admin]** &gt; Conjuntos **[!UICONTROL de]** relatórios &gt; **[!UICONTROL Editar configurações]** &gt; *`<Traffic or Conversion>`*

Ao classificar, você estabelece uma relação entre a variável e os metadados relacionados a ela. Na maioria das vezes, as classificações são usadas em campanhas. Os dados coletados por meio das informações de variáveis (eVars, props e eventos) podem ser centralizados aplicando os metadados aos valores coletados nas variáveis.

![Step Info](assets/sub_class_create.png)

Depois de classificado, qualquer relatório que você puder gerar usando a variável-chave também poderá ser gerado com os atributos associados. Por exemplo, é possível classificar [!UICONTROL IDs de produto] com outros atributos de produto, como nome do produto, cor, tamanho, descrição e SKU. O aumento dos dados de relatórios e análises com outros atributos oferece oportunidades de relatórios mais profundos e complexos.

>[!IMPORTANT]
>
>A capacidade de importar classificações Numérico 2 e Ativadas por data foi removida da base de código. Essa alteração será aplicada na Versão de manutenção de junho de 2019. Se você tiver colunas Numéricas ou Ativadas por data no arquivo de importação, essas células serão ignoradas silenciosamente e todos os outros dados nesse arquivo serão importados normalmente. As classificações existentes ainda podem ser exportadas por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

>[!NOTE]
>
>Na versão de 10 de maio de 2018 da Analytics Maintenance, a Adobe começou a limitar a funcionalidade de classificações numéricas e ativadas por data. Esses tipos de classificações foram removidos das interfaces Admin e Importador de classificações. Nenhuma classificação numérica ou habilitada por data pode ser adicionada. As classificações existentes ainda podem ser gerenciadas (atualizadas, excluídas) por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

Depois de criar as classificações, você pode aproveitar os novos atributos de dados no Adobe Analytics.

**Exemplo de códigos de rastreamento**

Digamos que, em vez de visualizar campanhas só pelo código de rastreamento, você queira ver os resultados da campanha pelo mecanismo de pesquisa, palavras-chave e canal de campanha. Em vez de dedicar variáveis de conversão a cada um deles, você poderá criar três classificações da variável de campanha para representar o mecanismo de pesquisa, palavras-chave e canal de campanha. Essa estratégia permite ver os eventos bem-sucedidos do site por todas as quatro variáveis, sem outra marcação.

Os relatórios e análises contêm classificações pré-definidas para a variável do código de rastreamento, que oferece relatórios baseados na classificação, chamados Elementos Criativos e Campanhas. É preciso configurar manualmente as classificações para todas as outras variáveis de conversão e de tráfego.

Consulte [Classificações de tráfego](/help/admin/admin/c-traffic-variables/traffic-classifications.md) e [Classificações de conversão](https://marketing.adobe.com/resources/help/en_US/reference/conversion_classifications.html).

A tabela a seguir descreve os diferentes tipos de classificação disponíveis e os tipos de variáveis que os suportam. Revise as informações em General File Structure before uploading data files.[](../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9EFF968DF5D244A887DE94075431C1BE)

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>TIPO </p> </th> 
   <th colname="col2" class="entry"> <p>DISPONIBILIDADE </p> </th> 
   <th colname="col3" class="entry"> <p>DESCRIÇÃO </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Texto</span> </p> </td> 
   <td colname="col2"> <p>Variáveis de conversão e de tráfego </p> </td> 
   <td colname="col3"> <p>As classificações de texto definem uma categoria que permite a você agrupar dados variáveis para a geração de relatórios. </p> <p>Por exemplo: se você vende camisetas, talvez queira categorizar as vendas (conversão) por cor, tamanho e estilo, para que possa gerar relatórios que o permitam ver as vendas de camisetas organizadas por essas categorias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Texto ativado por data</span> </p> <p>Observação:  Na versão de 10 de maio de 2018 da Analytics Maintenance, a Adobe começou a limitar a funcionalidade de classificações ativadas por data. Esses tipos de classificações foram removidos das interfaces Admin e Importador de classificações. Não é possível adicionar novas classificações ativadas por data. As classificações existentes ainda podem ser gerenciadas (atualizadas, excluídas) por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios. </p> </td> 
   <td colname="col2"> <p>Variáveis de conversão </p> </td> 
   <td colname="col3"> <p>Uma classificação de texto ativada por data permite que você atribua intervalos de datas a uma classificação de texto. Isso é comumente utilizado em classificações de campanha, de modo que você pode aproveitar a exibição do gráfico de Gantt no relatório <span class="wintitle">Campanhas</span>. </p> <p>É possível incluir as datas da campanha atual no arquivo de dados que preenche os dados de classificação. </p> <p>O Relatórios e análises coleta códigos de rastreamento de campanha mesmo se a data final da campanha já tiver passado, mas os dados da campanha coletados após a data final da campanha não estiverem associados à campanha. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Numérico</span> <p>Observação:  Na versão de 10 de maio de 2018 da Analytics Maintenance, a Adobe começou a limitar a funcionalidade de classificações numéricas. Esses tipos de classificações foram removidos das interfaces Admin e Importador de classificações. No new numeric classifications can be added. As classificações existentes ainda podem ser gerenciadas (atualizadas, excluídas) por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios. </p> </p> </td> 
   <td colname="col2"> <p>Variáveis de conversão </p> </td> 
   <td colname="col3"> <p>As classificações numéricas permitem que você aplique valores numéricos fixos para os relatórios de <span class="wintitle">Conversão</span>. Essas classificações aparecem como métricas nos relatórios. </p> <p>Ao estudar a possibilidade de adicionar uma classificação <span class="wintitle">numérica</span>, o valor numérico deve ser fixo e imutável ao longo do tempo. </p> </td> 
  </tr> 
 </tbody> 
</table>

