---
description: Essa tabela de referência define os campos, opções e atributos de acesso que você pode selecionar na página de Regras de processamento de canal de marketing.
seo-description: Essa tabela de referência define os campos, opções e atributos de acesso que você pode selecionar na página de Regras de processamento de canal de marketing.
seo-title: Regras de processamento do Canal de marketing - Definições
solution: Analytics
subtopic: Canais de marketing
title: Regras de processamento do Canal de marketing - Definições
topic: Reports and Analytics
uuid: 4 e 71 ff 5 b -912 a -4 dc 0-9 c 22-4 be 74 c 5 e 3 cc 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Regras de processamento do Canal de marketing - Definições

Essa tabela de referência define os campos, opções e atributos de acesso que você pode selecionar na página de Regras de processamento de canal de marketing.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Termo </p> </th> 
   <th colname="col2" class="entry"> <p>Definição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Todos </p> </td> 
   <td colname="col2"> <p>Ativa o canal apenas quando todas as regras da regra enumerada são verdadeiras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qualquer </p> </td> 
   <td colname="col2"> <p>Ativa este canal quando qualquer regra no conjunto de regras é verdadeira. Essa opção está disponível apenas se existir mais de uma regra na regra enumerada. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID do AMO </p> </td> 
   <td colname="col2"> <p>O código de rastreamento principal usado pelas integrações da Advertising Cloud e do Analytics. Quando uma dessas integrações estiver ativada, o prefixo do código de rastreamento pode ser usado para identificar canais específicos da Publicidade Cloud. Use "AMO ID" começa com "AL" para Pesquisa, "AC" para Exibição ou "AO" para o Social. Quando a ID do AMO é usada nos canais de marketing, as métricas de cliques/custo/impressão podem ser atribuídas ao canal correto (quando não configurado, essas métricas vão para Direto ou Nenhum). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID ED ED </p> </td> 
   <td colname="col2"> <p>O código de rastreamento secundário usado pela Advertising Cloud. A finalidade principal deste código de rastreamento é servir como a chave para enviar dados de volta à Ad Cloud. No entanto, também pode ser usado para identificar clickthroughs vs. display viewthroughs caso deseje visualizá-los como dois canais de marketing separados. Isso pode ser feito definindo a lógica do canal de marketing para "AMO EF ID" termina com ": d "for Display clickthroughs or" AMO EF ID "termina com": i "for Display viewthroughs. Se você não quiser dividir a Exibição em dois canais, use a dimensão ID do AMO em vez disso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variáveis de conversão </p> </td> 
   <td colname="col2"> <p>Consiste de eVars ativadas para esse conjunto de ferramentas de relatório, e se aplica apenas quando essas variáveis são definidas por meio do código Adobe na página. </p> <p>Consulte o <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf" scope="external" format="html">Guia de implementação </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Existe </p> </td> 
   <td colname="col2"> <p>Diversas seleções estão disponíveis, incluindo: </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol">Não existe</span>: especifica que o atributo da ocorrência não existe no pedido. Por exemplo, em um domínio de referência, se o usuário digitar um URL ou clicar em um marcador, o atributo de domínio de referência não existe. </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol"> Está vazio</span>: especifica que existe um atributo de ocorrência, geralmente um eVar ou parâmetro de sequência de consulta, mas não há valor associado ao atributo de ocorrência. </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol"> Não contém </span>: Permite especificar, por exemplo, que um domínio de referência não contém um valor específico (em vez de usar a seleção <span class="term"> Contém </span>. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificar o canal como </p> </td> 
   <td colname="col2"> <p>Associa a regra a um canal de marketing adicionado à página <span class="wintitle">Gerenciador de canal de marketing</span>. </p> <p>See <a href="../../components/c-marketing-channels/c-channels.md#task_98C9D3F5DBBC4B198E0A9ED4D3891E03" type="task" format="dita" scope="local"> Add marketing channels </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Corresponde a Regras de Detecção de Pesquisa Paga </p> </td> 
   <td colname="col2"> <p>Uma pesquisa paga detectada pela Adobe. Pesquisas pagas são quando as empresas pagam uma taxa para que o mecanismo de pesquisa relacione seus sites. As pesquisas pagas em geral aparecem no alto ou à direita dos resultados da pesquisa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Corresponde a Regras de Detecção de Pesquisa Natural </p> </td> 
   <td colname="col2"> <p>Uma pesquisa não paga detectada pelo relatório da Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referenciador corresponde a filtros internos de URL </p> </td> 
   <td colname="col2"> <p> Uma visita cujo URL da página corresponde a um filtro de URL interno, conforme definido para o conjunto de relatórios nas Ferramentas de administração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referenciador não corresponde a filtros internos de URL </p> </td> 
   <td colname="col2"> <p>O URL de referência não corresponde a um filtro de URL interno, conforme definido para o conjunto de relatórios nas Ferramentas de administração. Você pode utilizar essas configurações com <span class="term"> URL da página </span> e <span class="term"> Existe </span> para configurar uma regra catch-all, para que nenhuma visita chegue à seção <a href="../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7" type="section" format="dita" scope="local"> Nenhum canal identificado </a> do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ignorar ocorrências correspondentes a filtros de URL internos </p> </td> 
   <td colname="col2"> <p>(Para referenciadores) Acompanha apenas ocorrências provenientes de sites com referenciador externo. Em geral, mantenha essa configuração ativada, a menos que deseje incluir tráfego interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>É a primeira página da visita </p> </td> 
   <td colname="col2"> <p>A primeira página da visita detectada por um relatório Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Página </p> </td> 
   <td colname="col2"> <p>O nome de uma página da Web no seu site que foi marcada usando o Web beacon. Este valor é equivalente a  <span class="varname"> s.pageName </span>. Examples include <span class="varname"> Home Page </span> and <span class="varname"> About Us </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio de página </p> </td> 
   <td colname="col2"> <p>O domínio da página onde o visitante chega, como <span class="filepath">products.example.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio e caminho da página </p> </td> 
   <td colname="col2"> <p>O domínio e caminho como, por exemplo <span class="filepath">products.example.co.uk/mens/pants/overview.html </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio raiz da página (TLD+1) </p> </td> 
   <td colname="col2"> <p>O domínio raiz da página onde o visitante chega como, por exemplo, <span class="filepath">example.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL da página </p> </td> 
   <td colname="col2"> <p>O URL da página da Web de seu site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio de referência </p> </td> 
   <td colname="col2"> <p>O domínio de onde seus visitantes vieram antes visitarem seu site, por exemplo, referenciadores vindos de <span class="filepath">abcsite.com</span> x <span class="filepath">xyzsite.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parâmetro da sequência de caracteres de consulta </p> </td> 
   <td colname="col2"> <p>If a page URL on your site looks like <span class="filepath"> https://example.com/?page=12345&amp;cat=1 </span>, then page and cat are both query string parameters. (See <span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span>.) </p> <p>É possível especificar apenas um parâmetro da sequência de consulta por conjunto de regras. Para adicionar mais parâmetros da sequência de consulta, use <span class="uicontrol">ANY</span> como operador e acrescente novos parâmetros da sequência de caracteres de consulta à regra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referenciador </p> </td> 
   <td colname="col2"> <p>O local da página da Web (URL completo) onde seus visitantes estavam antes de chegarem ao seu site. O referenciador existe fora do seu domínio definido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio e caminho de referência </p> </td> 
   <td colname="col2"> <p>A concatenação de domínio de referência e caminho de URL. São exemplos: </p> <p> <span class="filepath"> www.example.com/products/id/12345 </span> </p> <p> <span class="filepath"> ad.example.com/foo </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parâmetro de referência </p> </td> 
   <td colname="col2"> <p>Um parâmetro da sequência de consulta no URL do referenciador. Por exemplo, se seus visitantes vêm de <span class="filepath">example.com/?page=12345&amp;cat=1</span>, page e cat são os parâmetros de referência. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio raiz de referência </p> </td> 
   <td colname="col2"> <p>O domínio raiz do referenciador. O referenciador existe fora do seu domínio definido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mecanismo de pesquisa </p> </td> 
   <td colname="col2"> <p>Um mecanismo de pesquisa como Google ou Yahoo! que trouxe visitantes ao seu site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Palavras-chave de pesquisa </p> </td> 
   <td colname="col2"> <p>Uma palavra usada para realizar uma pesquisa usando um mecanismo de pesquisa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mecanismo de pesquisa + Palavras-chave </p> </td> 
   <td colname="col2"> <p>Uma concatenação de palavra-chave de pesquisa e mecanismo de pesquisa para identificar de forma exclusiva o mecanismo de pesquisa. Por exemplo, se você pesquisar a palavra computador, o mecanismo de pesquisa e a palavra-chave serão identificados assim: </p> 
    <code>Código de rastreamento de pesquisa = " &lt; search_ type &gt;: &lt; mecanismo de pesquisa &gt;: &lt; palavra-chave de pesquisa &gt; "onde search_ type =" n "ou" p ", search_ engine =" Google "e search_ keyword =" computador " </code>
  <p><b>Observação:</b> n = natural; p = pago </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Defina o valor do canal como </p> </td> 
   <td colname="col2"> <p>Além de saber qual canal de marketing traz um visitante ao seu site, talvez você também queira saber que anúncio de banner, palavra-chave de pesquisa ou campanha por email dentro do canal está obtendo crédito pela atividade de um visitante do site. Esse ID é um valor de canal armazenado juntamente com o canal. Muitas vezes esse valor é um ID de campanha integrado à página inicial ou ao URL referenciador, em outros casos, é a combinação do mecanismo de pesquisa com a palavra-chave de pesquisa ou o URL referenciador que identifica melhor o visitante de determinado canal. </p> </td> 
  </tr> 
 </tbody> 
</table>



