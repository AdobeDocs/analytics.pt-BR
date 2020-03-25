---
description: A Fonte de Dados oferece suporte às seguintes variáveis no processamento de dados como chamada do servidor padrão (Genérico > Processamento completo).
subtopic: Data sources
title: Processamento completo
topic: Developer and implementation
uuid: 590ae89c-6e17-453b-b701-ce1adbea6fa4
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Processamento completo

A Fonte de Dados oferece suporte às seguintes variáveis no processamento de dados como chamada do servidor padrão (Genérico > Processamento completo).

As fontes de dados de processamento completa são processadas como se fossem recebidas pelos servidores da Adobe no tempo especificado (cada ocorrência contém um carimbo de data e hora).

* [Perfil do visitante](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_6065627D0C144506965F562C80AE67F8)
* [Referência da coluna](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_92BAE76639E3404E97276B1BE0581078)

## Perfil do visitante {#section_6065627D0C144506965F562C80AE67F8}

Como os dados das fontes de dados de processamento completo são processados por meio de perfis do visitante diferentes, mesmo que a ID do visitante nos dados carregados corresponda aos dados coletados com o JavaScript ou outra biblioteca de AppMeasurement, os perfis de visitantes não serão conectados em uma perspectiva de alocação de eVar.

Por exemplo, um usuário com uma ID de visitante `"user@example.com"` visita seu site durante uma campanha de marketing chamada &quot;Liquidação de primavera&quot;, que é armazenada na variável da campanha. Posteriormente, se você carregar uma transação usando a mesma ID de visitante, a campanha &quot;Liquidação de primavera&quot; não receberá crédito pela receita ou pelos eventos de sucesso carregados por meio de fontes de dados de processamento completo.

## Referência da coluna {#section_92BAE76639E3404E97276B1BE0581078}

<table id="table_AAC04491D643467B9C80FDEF88130B13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável JavaScript </th> 
   <th colname="col2" class="entry"> Variável de coluna do processamento completo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>campaign </p> </td> 
   <td colname="col2"> <p>campaign </p> </td> 
   <td colname="col3"> <p>Código de rastreamento de campanha de conversão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>canal </p> </td> 
   <td colname="col2"> <p>canal </p> </td> 
   <td colname="col3"> <p>Sequência de caracteres de canal (por exemplo, seção de esportes). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>currencyCode </p> <p>Observação: essa variável também tem suporte das fontes de dados padrão como <code> currency code </code>. </p> </td> 
   <td colname="col3"> <p>Código de moeda da receita (por exemplo, US$). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>carimbo de data e hora </p> </td> 
   <td colname="col2"> <p>date </p> </td> 
   <td colname="col3"> <p>Use o formato de data ISO 8601, <code> YYYY-MM-DDThh:mm:ss±UTC_offset </code> (por exemplo, <code> 2013-09-01T12:00:00-07:00 </code>), ou o formato de hora Unix (o total de segundos decorridos desde 1° de janeiro de 1970). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>N</i> </p> </td> 
   <td colname="col2"> <p>eVar<i>N</i>, ou seja &lt;eVar2&gt;…&lt;/eVar2&gt; </p> </td> 
   <td colname="col3"> <p>Nome do eVar de conversão. É possível ter até 75 eVars ( <span class="varname"> eVar1 </span> - <span class="varname"> eVar75 </span>). </p> <p>Você pode especificar o nome do eVar (eVar12) ou um nome amigável (Campanha publicitária 3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>events </p> </td> 
   <td colname="col2"> <p>events </p> </td> 
   <td colname="col3"> <p>Sequência de eventos, formatada com a mesma sintaxe da variável <a href="https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/page-vars/events/event-serialization.html"  >s.events</a>. </p> <p>Por exemplo: </p> 
    <code>
      scAdd,event1,event7 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hier<i>N</i> </p> </td> 
   <td colname="col2"> <p>hier<i>N</i>, ou seja &lt;hier2&gt;…&lt;/hier2&gt; </p> </td> 
   <td colname="col3"> <p>Nome da hierarquia. É possível ter até 5 hierarquias ( <span class="varname"> hier1</span> - <span class="varname">hier5 </span>). </p> <p>Você pode especificar o nome de hierarquia padrão (<span class="varname">hier2</span>) ou um nome amigável (<span class="term">Yankees </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkName </p> </td> 
   <td colname="col2"> <p>linkName </p> </td> 
   <td colname="col3"> <p>Nome do link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkType </p> </td> 
   <td colname="col2"> <p>linkType </p> </td> 
   <td colname="col3"> <p>Tipo de link. Os valores para os quais existe suporte incluem: </p> 
    <ul id="ul_E441013055A9447AB6C3FB05B6099F7D"> 
     <li id="li_A33F66F30B60479284F72AE3AD4BF499"> <b>d</b>: Link de download </li> 
     <li id="li_182F695AA2D044DAB036BAFE38BC3915"> <b>e</b>: Link de saída </li> 
     <li id="li_4FD4D542D1774607860BEF41C1B090D1"> <b>o</b>: Link personalizado. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkURL </p> </td> 
   <td colname="col2"> <p>linkURL </p> </td> 
   <td colname="col3"> <p>HREF do link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageName </p> </td> 
   <td colname="col2"> <p>pageName </p> </td> 
   <td colname="col3"> <p>Nome da página </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageType </p> </td> 
   <td colname="col2"> <p>pageType </p> </td> 
   <td colname="col3"> <p>Tipo de página ("Página de Erro"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageURL </p> </td> 
   <td colname="col2"> <p>pageURL </p> </td> 
   <td colname="col3"> <p>URL da página (por exemplo, <code>https://www.mysite.com/index.html)</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>products </p> </td> 
   <td colname="col2"> <p>products </p> </td> 
   <td colname="col3"> <p>Lista de produtos (por exemplo, <code> "Sports;Ball;1;5.95") </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop1 - prop75 </p> </td> 
   <td colname="col2"> <p>prop<i>N</i>, ou seja &lt;prop2&gt;…&lt;/prop2&gt; </p> </td> 
   <td colname="col3"> <p>Sequência de caracteres de número de variável de propriedade (por exemplo, <span class="term"> Seção de Esportes </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchaseID </p> </td> 
   <td colname="col2"> <p>purchaseID </p> </td> 
   <td colname="col3"> <p>Número da ID de compra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>s_account </p> </td> 
   <td colname="col2"> <p>reportSuiteID </p> </td> 
   <td colname="col3"> <p>ID(s) do conjunto de relatórios para o qual deve ser atribuída a ocorrência. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>servidor </p> </td> 
   <td colname="col2"> <p>servidor </p> </td> 
   <td colname="col3"> <p>Sequência de caracteres do servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>state </p> </td> 
   <td colname="col2"> <p>state </p> </td> 
   <td colname="col3"> <p>Sequência de caracteres do estado de conversão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zip </p> </td> 
   <td colname="col2"> <p>zip </p> </td> 
   <td colname="col3"> <p>CEP de conversão. </p> </td> 
  </tr> 
 </tbody> 
</table>

A tabela a seguir contém variáveis de tráfego que são automaticamente preenchidas quando são utilizadas as bibliotecas do JavaScript. Essas propriedades não têm variáveis associadas, mas podem ser importadas usando fontes de dados.

<table id="table_FDBC5BD225644AA09078C0570BE709FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variável de coluna do processamento completo </p> </th> 
   <th colname="col2" class="entry"> <p>Descrição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>browserHeight </p> </td> 
   <td colname="col2"> <p>Altura do navegador em pixels (por exemplo, 768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>browserWidth </p> </td> 
   <td colname="col2"> <p>Largura do navegador em pixels (por exemplo, 1024). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conjunto de gráficos </p> </td> 
   <td colname="col2"> <p>O caractere suportado definido para seu site. Por exemplo, UTF-8, ISO-8859-1, e assim por diante. </p> <p>Para obter uma lista completa, consulte o informe <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/multibyte/index.html"  >Conjuntos de caracteres de múltiplos bytes</a> (internacionalização). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickAction </p> </td> 
   <td colname="col2"> <p>Identificador de objeto para o mapa de cliques do visitante (oid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickActionType </p> </td> 
   <td colname="col2"> <p>Tipo de identificador de objeto para o mapa de cliques do visitante (oidt) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContext </p> </td> 
   <td colname="col2"> <p>Identificador de página para o mapa de cliques do visitante (pid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContextType </p> </td> 
   <td colname="col2"> <p>Identificador de página para o mapa de cliques do visitante (pidt) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickSourceID </p> </td> 
   <td colname="col2"> <p>Índice da fonte para o mapa de cliques do visitante (oi) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickTag </p> </td> 
   <td colname="col2"> <p>Nome da tag do objeto para o mapa de cliques do visitante (ot) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>colorDepth </p> </td> 
   <td colname="col2"> <p>Profundidade de cores do monitor em bits (por exemplo, 24). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>connectionType </p> </td> 
   <td colname="col2"> <p>Tipo de conexão do visitante (<span class="term">lan </span> ou <span class="term">modem </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookiesEnabled </p> </td> 
   <td colname="col2"> <p>S ou N, se o visitante possui suporte para os cookies da sessão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>O código de moeda padrão usado em seu site. </p> <p>Por exemplo, US$ = dólar americano, € = Euro, JPY = Iene japonês etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>homePage </p> </td> 
   <td colname="col2"> <p>S ou N, é a página atual da página inicial do visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaEnabled </p> </td> 
   <td colname="col2"> <p>S ou N, o visitante tem o Java habilitado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaScriptVersion </p> </td> 
   <td colname="col2"> <p>Versão do JavaScript (por exemplo, 1.3) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>plugins </p> </td> 
   <td colname="col2"> <p>Lista de nomes de plug-in para navegador separados por ponto e vírgula. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>propN </p> </td> 
   <td colname="col2"> <p>Valores da propriedade para suas propriedades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>referenciador </p> </td> 
   <td colname="col2"> <p>URL para o referenciador da página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>resolution </p> </td> 
   <td colname="col2"> <p>Resolução do monitor (por exemplo, 1024x768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>scXmlVer </p> </td> 
   <td colname="col2"> <p>Número da versão da solicitação de XML de relatórios de marketing (por exemplo, 1.0). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>fuso horário </p> </td> 
   <td colname="col2"> <p>Fuso horário do visitante, deslocamento do GMT em horas (por exemplo, -8). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorID </p> </td> 
   <td colname="col2"> <p>Número da ID do visitante. </p> </td> 
  </tr> 
 </tbody> 
</table>

