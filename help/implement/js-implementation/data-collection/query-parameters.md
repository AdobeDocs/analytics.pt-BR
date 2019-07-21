---
description: As tabelas a seguir listam os parâmetros de consulta que contêm o valor para cada variável de análise enviada para a coleção de dados.
keywords: Implementação do Analytics
seo-description: As tabelas a seguir listam os parâmetros de consulta que contêm o valor para cada variável de análise enviada para a coleção de dados.
seo-title: Parâmetros de consulta da coleção de dados
solution: Analytics
title: Parâmetros de consulta da coleção de dados
topic: Desenvolvedor e implementação
uuid: 4 d 5 af 486-df 27-42 fe-bb 9 c -28938 dddf 2 b 2
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Parâmetros de consulta da coleção de dados

As tabelas a seguir listam os parâmetros de consulta que contêm o valor para cada variável de análise enviada para a coleção de dados.

Essas informações podem ser usadas ao depurar usando [Analisadores de pacote](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258), ao construir manualmente solicitações de imagem ou ao usar [Variáveis dinâmicas](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262).

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> Parâmetro </th> 
   <th class="entry"> Variável do Analytics </th> 
   <th class="entry"> Relatório preenchido </th> 
   <th class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> Nenhuma </td> 
   <td colname="col3"> Nenhum </td> 
   <td colname="col4"> Dica de localização do Audience Manager (usada na integração do perfil compartilhado da Experience Cloud) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> Nenhuma </td> 
   <td colname="col3"> Nenhum </td> 
   <td colname="col4"> Blob do Audience Manager (usado na integração do perfil compartilhado da Experience Cloud) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> Nenhuma </td> 
   <td colname="col3"> Nenhuma </td> 
   <td colname="col4"> ID do visitante do Analytics </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> Nenhuma </td> 
   <td> Nenhuma </td> 
   <td> Indica o início de uma solicitação de imagem. </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> Nenhuma </td> 
   <td> Nenhuma </td> 
   <td> Indica o fim de uma solicitação de imagem e significa que a solicitação não foi truncada. </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Tecnologia | Altura do navegador </td> 
   <td> Altura da janela do navegador (em pixels) </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Tecnologia | Largura do navegador </td> 
   <td> Largura da janela do navegador (em pixels) </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Tecnologia | Profundidade de cores do monitor </td> 
   <td> Qualidade de cor (em bits) </td> 
  </tr> 
  <tr> 
   <td> <code> c. <span class="varname"> [key] </code></span> </td> 
   <td> <p>s.contextData </p> </td> 
   <td> <p>Nenhum </p> </td> 
   <td> <p>Os pares de valores-chave são especificados em um dos formatos a seguir: </p> <p> <code> &lt;my.a&gt;red&lt;/my.a&gt; </code> </p> <p>or: </p> <p> <code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code> </p> <p>Cada um desses exemplos resulta em um valor de dados de contexto de <code>my.a = red </code>. É possível especificar vários pares de valor-chave. </p> <p>In the query string, this context data variable would appear as <code> c.&amp;my.a=red </code> </p> </td> 
  </tr> 
  <tr> 
   <td> c1-c75 </td> 
   <td> s.prop1-s.prop75 </td> 
   <td> Todos os relatórios de tráfego personalizados </td> 
   <td> Variáveis de tráfego usadas em relatórios de tráfego personalizados </td> 
  </tr> 
  <tr> 
   <td> cc </td> 
   <td> s.currencyCode </td> 
   <td> Nenhuma </td> 
   <td> A moeda utilizada no site </td> 
  </tr> 
  <tr> 
   <td> cdp </td> 
   <td> s.cookieDomainPeriods </td> 
   <td> Nenhuma </td> 
   <td> Indica o número de períodos em um domínio para rastreamento de cookie; configurado manualmente. </td> 
  </tr> 
  <tr> 
   <td> ce </td> 
   <td> s.charSet </td> 
   <td> Nenhuma </td> 
   <td> A codificação de caracteres da solicitação de imagem </td> 
  </tr> 
  <tr> 
   <td> cl </td> 
   <td> s.cookieLifetime (duração de s_vi cookie em segundos) </td> 
   <td> Nenhum </td> 
   <td> A duração do cookie do visitante. </td> 
  </tr> 
  <tr> 
   <td> ch </td> 
   <td> s.channel </td> 
   <td> Conteúdo do site | Seções do site </td> 
   <td> A variável de Seções do site usada no relatório de tráfego </td> 
  </tr> 
  <tr> 
   <td> cp </td> 
   <td> Tipo de ocorrência </td> 
   <td> Tipo de ocorrência </td> 
   <td> Indica se o comportamento é resultado de um primeiro plano de interação direto ou de informações que o dispositivo está enviando sem um plano de fundo de interação direto. </td> 
  </tr> 
  <tr> 
   <td> ct </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Tecnologia | Tipos de conexão </td> 
   <td> Tipo de conexão (Modem, LAN etc; pode preencher apenas em navegadores IE) </td> 
  </tr> 
  <tr> 
   <td> <code> D </code> </td> 
   <td> dynamicVariablePrefix </td> 
   <td> Nenhum </td> 
   <td> <p>Consulte <a href="../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262" format="dita" scope="local"> Variáveis dinâmicas </a>. </p> </td> 
  </tr> 
  <tr> 
   <td> eventos ou ev </td> 
   <td> s.events </td> 
   <td> Tráfego do site | Compras, Carrinho de compras, Eventos personalizados </td> 
   <td> Os eventos comerciais e personalizados que ocorreram na página; usado em relatórios de conversão </td> 
  </tr> 
  <tr> 
   <td> g </td> 
   <td> Nenhuma </td> 
   <td> Nenhuma </td> 
   <td> O URL atual da página, até 255 bytes. </td> 
  </tr> 
  <tr> 
   <td> -g </td> 
   <td> Nenhuma </td> 
   <td> Nenhuma </td> 
   <td> URLs de páginas superiores a 255 bytes são divididos. Os primeiros 255 bytes aparecem no parâmetro g e os bytes restantes aparecem posteriormente em uma sequência de consulta no parâmetro de consulta -g=. </td> 
  </tr> 
  <tr> 
   <td> h1-h5 </td> 
   <td> s.hier1-s.hier5 </td> 
   <td> Conteúdo do site | Relatórios de hierarquia </td> 
   <td> Variáveis de hierarquia; usado em relatórios de tráfego </td> 
  </tr> 
  <tr> 
   <td> hp </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Página inicial do visitante </td> 
   <td> Indica se a página atual é a página inicial do navegador (S ou N; pode preencher apenas em navegadores IE)  </td> 
  </tr> 
  <tr> 
   <td> j </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Tecnologia | Versão JavaScript </td> 
   <td> Mostra a versão do JavaScript atualmente instalada (normalmente 1.x) </td> 
  </tr> 
  <tr> 
   <td> k </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Tecnologia | Cookies </td> 
   <td> Cookies são suportados no navegador? (S, N ou U) </td> 
  </tr> 
  <tr> 
   <td> l1-l3 </td> 
   <td> s.list1-s.list3 </td> 
   <td> Conversão personalizada </td> 
   <td> Uma lista delimitada de valores passados para uma variável e, em seguida, reportados como itens de linha individuais para relatório. </td> 
  </tr> 
  <tr> 
   <td> mid </td> 
   <td> Nenhuma </td> 
   <td> Nenhum </td> 
   <td> ID de visitante da Experience Cloud </td> 
  </tr> 
  <tr> 
   <td> ndh </td> 
   <td> Nenhuma </td> 
   <td> Nenhuma </td> 
   <td> Indica se a solicitação de imagem se originou de um arquivo JS (1 ou 0) </td> 
  </tr> 
  <tr> 
   <td> ns </td> 
   <td> s.visitorNameSpace </td> 
   <td> Nenhuma </td> 
   <td> Especifica em qual domínio os cookies estão configurados </td> 
  </tr> 
  <tr> 
   <td> oid </td> 
   <td> s.objectID </td> 
   <td> Conteúdo do site | Links | ClickMap </td> 
   <td> Identificador de objeto para última página; usado no ClickMap </td> 
  </tr> 
  <tr> 
   <td> ot </td> 
   <td> Nenhuma </td> 
   <td> Conteúdo do site | Links | ClickMap </td> 
   <td> Nome da tag do objeto para última página; usado no ClickMap </td> 
  </tr> 
  <tr> 
   <td> p </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Tecnologia | Plug-ins do Netscape </td> 
   <td> Nomes de plug-ins de navegadores separados por ponto e vírgula </td> 
  </tr> 
  <tr> 
   <td> pageName (ou gn) </td> 
   <td> s.pageName </td> 
   <td> Conteúdo do site | Páginas </td> 
   <td> O nome designado da página no relatório </td> 
  </tr> 
  <tr> 
   <td> pageType (ou gt) </td> 
   <td> s.pageType </td> 
   <td> Conteúdo do site | Páginas não encontradas </td> 
   <td> Indica se é uma página 404 ("erro" ou em branco) </td> 
  </tr> 
  <tr> 
   <td> pccr </td> 
   <td> Nenhuma </td> 
   <td> Nenhuma </td> 
   <td> Ocorre apenas com novos visitantes; evita redirecionamentos infinitos (sempre verdadeiro) </td> 
  </tr> 
  <tr> 
   <td> pe </td> 
   <td> s.linkType </td> 
   <td> Conteúdo do site | Links | Links de saída, Downloads de arquivo, Links personalizados </td> 
   <td> Determina o tipo de acesso a link personalizado acionado </td> 
  </tr> 
  <tr> 
   <td> pev1 </td> 
   <td> Nenhuma </td> 
   <td> Conteúdo do site | Links | Links de saída, Downloads de arquivo, Links personalizados </td> 
   <td> O URL em que o acesso a link personalizado ocorreu </td> 
  </tr> 
  <tr> 
   <td> pev2 </td> 
   <td> Nenhuma </td> 
   <td> Conteúdo do site | Links | Links de saída, Downloads de arquivo, Links personalizados </td> 
   <td> Nome amigável do link personalizado </td> 
  </tr> 
  <tr> 
   <td> pev3 </td> 
   <td> Nenhuma </td> 
   <td> Todos os relatórios de vídeo </td> 
   <td> Usado para rastrear marcos no relatório de vídeo de legado; obsoleto com v15 </td> 
  </tr> 
  <tr> 
   <td> pf </td> 
   <td> Nenhum </td> 
   <td> Nenhum </td> 
   <td> Somente para uso da Adobe. Não alterar. </td> 
  </tr> 
  <tr> 
   <td> pid </td> 
   <td> Nenhuma </td> 
   <td> Conteúdo do site | Links | ClickMap </td> 
   <td> Identificador de página para última página; usado no ClickMap </td> 
  </tr> 
  <tr> 
   <td> pidt </td> 
   <td> Nenhuma </td> 
   <td> Conteúdo do site | Links | ClickMap </td> 
   <td> Tipo de identificador de página para última página; usado no ClickMap </td> 
  </tr> 
  <tr> 
   <td> products (ou pl) </td> 
   <td> s.products </td> 
   <td> Produtos | Produtos </td> 
   <td> Variável products usada em relatórios de conversão </td> 
  </tr> 
  <tr> 
   <td> purchaseID (ou pi) </td> 
   <td> s.purchaseID </td> 
   <td> Nenhuma </td> 
   <td> Usado para eliminar a duplicação de compras, evitando a inflação da receita </td> 
  </tr> 
  <tr> 
   <td> r </td> 
   <td> s.referrer </td> 
   <td> Todos os relatórios de origens de tráfego </td> 
   <td> URL de referência </td> 
  </tr> 
  <tr> 
   <td> s </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Tecnologia | Resoluções do monitor </td> 
   <td> Resolução da tela (largura × altura) </td> 
  </tr> 
  <tr> 
   <td> server (ou sv) </td> 
   <td> s.server </td> 
   <td> Conteúdo do site | Servidores </td> 
   <td> O servidor da página; usado no relatório de tráfego </td> 
  </tr> 
  <tr> 
   <td> state </td> 
   <td> s.state </td> 
   <td> Perfil do visitante | Estado do visitante </td> 
   <td> Especifica o estado conforme definido pela variável. </td> 
  </tr> 
  <tr> 
   <td> t </td> 
   <td> (automático, enviado com todas as ocorrências que não possuem um carimbo de data/hora) </td> 
   <td> Nenhum </td> 
   <td> <p>O parâmetro <code>t</code> está no seguinte formato: </p> 
    <code>dd/mm/aaaa; nbsp; hh: mm: ss &amp; amp; nbsp; D &amp; amp; nbsp; OFFSET </code>
  <p>Onde D é um número no intervalo <code>0-6</code>, que especifica o dia da semana e <code>AJUSTAR</code> representa: </p> 
    <code>offset &amp; amp; nbsp; de &amp; amp; nbsp; GMT &amp; amp; nbsp; in &amp; amp; nbsp; horas e amp; nbsp; * &amp; amp; nbsp; 60 &amp; amp; nbsp; * &amp; amp; nbsp; -&amp; amp; nbsp; 1 </code>
  <p> Por exemplo: </p> 
    <code>23/09/2016 &amp; amp; nbsp; 14:00:00 &amp; amp; nbsp; 1 &amp; amp; nbsp; 420 </code>
  </td> 
  </tr> 
  <tr> 
   <td> <code> ts </code> </td> 
   <td> <p>timestamp </p> </td> 
   <td> Nenhum </td> 
   <td> <p>O carimbo de data/hora calculado e enviado com a ocorrência. Normalmente é usado para rastreamento offline. </p> </td> 
  </tr> 
  <tr> 
   <td> v </td> 
   <td> Nenhuma </td> 
   <td> Perfil do visitante | Tecnologia | Java </td> 
   <td> Habilitado para Java (S ou N) </td> 
  </tr> 
  <tr> 
   <td> v0 </td> 
   <td> s.campaign </td> 
   <td> Campanhas | Códigos de rastreamento </td> 
   <td> Variável da campanha usada em relatórios de conversão </td> 
  </tr> 
  <tr> 
   <td> v1-v75 </td> 
   <td> s.eVar1-s.eVar75 </td> 
   <td> Todos os relatórios de conversão personalizados </td> 
   <td> Variáveis de conversão usadas em relatórios de conversão personalizados </td> 
  </tr> 
  <tr> 
   <td> vid </td> 
   <td> <p>s.visitorID </p> </td> 
   <td> Nenhuma </td> 
   <td> A ID exclusiva do visitante conforme definido na variável Variável da ID do visitante. </td> 
  </tr> 
  <tr> 
   <td> vmk </td> 
   <td> s.vmk </td> 
   <td> Nenhuma </td> 
   <td> Chave de migração do visitante; usada para migrar de cookies de terceiros para cookies primários. Obsoleto. </td> 
  </tr> 
  <tr> 
   <td> vvp </td> 
   <td> s.variableProvider </td> 
   <td> Nenhuma </td> 
   <td> Usado em integrações Genesis </td> 
  </tr> 
  <tr> 
   <td> xact </td> 
   <td> s.transactionID </td> 
   <td> Nenhuma </td> 
   <td> O ID de transação usado para vincular dados online com dados offline </td> 
  </tr> 
  <tr> 
   <td> zip </td> 
   <td> s.zip </td> 
   <td> Perfil do Visitante | Código postal/CEP </td> 
   <td> Determina o CEP definido pela variável </td> 
  </tr> 
  <tr> 
   <td> /5/ (para protocolo móvel) ou /1/ (para protocolo não móvel) no URL de solicitação de imagem. </td> 
   <td> Nenhuma </td> 
   <td> Nenhuma </td> 
   <td> <p> Controla a ordem em que os cookies e outros métodos são usados para identificar visitantes.  </p> </td> 
  </tr> 
 </tbody> 
</table>

