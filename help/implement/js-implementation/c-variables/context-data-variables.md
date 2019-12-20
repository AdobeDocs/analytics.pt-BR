---
description: 'As variáveis de dados de contexto permitem que você defina variáveis em cada página, que podem ser lidas pelas regras de processamento. '
keywords: Analytics Implementation;contextdata;s.contextdata
subtopic: Variables
title: Variáveis de dados de contexto
topic: Developer and implementation
uuid: 4b215803-99d4-46f2-b3c1-e78558987764
translation-type: tm+mt
source-git-commit: 5d69587886c87bc62ad744c51d56bb6cd9e53167

---


# Variáveis de dados de contexto

As variáveis de dados de contexto permitem que você defina variáveis em cada página, que podem ser lidas pelas regras de processamento. 

Você pode enviar dados nas variáveis de dados de contexto que estão mapeados por meio de Regras de processamento, em vez de atribuir valores explícitos para os props e eVars no seu código. As Regras de processamento fornecem uma interface gráfica eficaz para fazer mudanças nos dados que são recebidos. Com base nos valores enviados nos dados de contexto, você poderá definir eventos, copiar valores para o eVars e props, bem como executar instruções condicionais.

> [!NOTE]As variáveis de dados de contexto não fazem distinção entre maiúsculas e minúsculas. Por exemplo, as 2 variáveis a seguir são idênticas:
>```
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>```
>e
>```
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```

O uso do contexto de dados ajuda a evitar as atualizações de código para suportar configurações de conjunto de relatórios diferentes.

Por exemplo, você pode definir a seguinte variável Variável *`s.contextData`*:

```
s.contextData['myco.rsid'] = 'value'
```

Usando Regras de processamento, você pode adicionar uma condição que verifique se existe uma variável de `myco.rsid`Dados de contexto. Quando a variável for encontrada, você poderá adicionar uma ação para copiá-la em uma prop ou eVar.

As variáveis de Dados de contexto também podem ser diretamente definidas na interface de regras de processamento para armazenar um valor temporariamente, ou para coletar valores com base em uma variável de dados de contexto que você sabe que será usada no conjunto de relatórios. Por exemplo, se você precisar trocar dois valores, poderá criar uma variável de dados de contexto para armazenar um valor durante a troca.

Como as regras de processamento se aplicam somente quando os dados são coletados, é importante definir as regras de processamento antes de você começar a enviar dados de contexto. Os valores dos dados de contexto que não são lidos pelas regras de processamento quando uma ocorrência é processada são descartados.

## Regras {#section_2229739F6B1A4C1CAD7140BDF4687523}

<table id="table_4433A32A952340699B189CAEAF158B06"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Regra </p> </th> 
   <th colname="col2" class="entry"> <p>Descrição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nomes e caracteres suportados </p> </td> 
   <td colname="col2"> <p>os nomes de variável de dados só podem conter caracteres alfanuméricos, sublinhados e pontos. Os caracteres adicionais serão eliminados. As variáveis de Dados de contexto não têm uma designação numérica. Em vez disso, elas são nomeadas. </p> <p>For example, the context data variable <code> login_page-home </code> automatically becomes <code> login_pagehome </code>. Todos os dados enviados para a variável <code> login_page-home </code> são alocados em <code> login_pagehome </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Namespace </p> </td> 
   <td colname="col2"> <p>Uma prática recomendada é prefixar suas variáveis com o nome de sua empresa, nome do site ou um valor semelhante para garantir que o nome seja único em todo o conjunto de relatórios. </p> <p>As variáveis de dados de contexto podem ser nomeadas de maneira semelhante a outras variáveis do JavaScript. Be aware that the namespace <code> a.* </code> is reserved for use by Adobe products in context variable names. Por exemplo, a biblioteca AppMeasurement para iOS usa <code> a.InstallEvent </code> para medir as instalações do aplicativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limites de URL para Internet Explorer </p> </td> 
   <td colname="col2"> <p>Talvez você encontre uma limitação de URL mais antiga para o Internet Explorer 6 e 7, na qual os URLs são truncados em 2000 bytes. Você pode usar o depurador <span class="keyword">DigitalPulse</span> para determinar o tamanho de uma string de URL. </p> <p>Com as últimas atualizações do AppMeasurement (setembro de 2014), o HTTP POST passou a ser usado com o Internet Explorer 8+, eliminando os problemas de truncamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versão do AppMeasurement com suporte </p> </td> 
   <td colname="col2"> <p>As variáveis de Dados de contexto requerem ao menos um código H23 ou posterior. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como enviar dados de contexto em uma chamada de rastreamento de link {#section_35EBE5D1CF29427598BD4B2165CE64FC}

Inclua `ContextData` + o nome da variável que você deseja incluir em `s.linkTrackVars`:

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 
```

## Exemplos {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

Possíveis maneiras de substituir a implementação da variável *`s.pageName`*, supondo que as regras de processamento estejam configuradas corretamente para cada:

```
s.contextData['page'] = "Home Page" 
s.contextData['pagename'] = document.title // Takes the web page's title and passes it into the pageName context data variable 
s.contextData['pagevar'] = s.pageName // This example would be considered redundant, as both the pageName and contextData variable are available in Processing rules
```

Outros exemplos para implementar as variáveis de dados de contexto:

```
s.contextData['owner'] = "Jesse" 
s.contextData['campaign'] = "Campaign A" 
s.contextData['author'] = "Sheridan Andrius"
```

Para obter um exemplo, consulte [Copiar uma variável de dados de contexto para uma eVar](https://marketing.adobe.com/resources/help/en_US/reference/processing_rules_copy_context_data.html) na Referência do Analytics.
