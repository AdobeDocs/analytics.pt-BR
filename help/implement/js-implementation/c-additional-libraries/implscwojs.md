---
description: Como implementar o Analytics usando uma tag de imagem HTML (solicitação de imagem codificada).
keywords: Analytics Implementation;html image tag;hardcoded image request
title: Implementar o Analytics usando tags de imagem HTML
topic: Developer and implementation
uuid: 0c098a57-7c71-4362-812c-36e37848a5ae
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementar o Analytics usando tags de imagem HTML

Como implementar o Analytics usando uma tag de imagem HTML (solicitação de imagem codificada).

O navegador solicita então a imagem. Os dados são movidos com a solicitação de imagem por meio das variáveis, na string de consulta da solicitação de imagem. O JavaScript combina variáveis do nível do navegador com variáveis do nível da página para uma solução abrangente de coleta de dados. Em alguns casos, uma tag de imagem totalmente criada no servidor é apropriada. Os elementos padrão de uma implementação baseada em JavaScript são listados como a seguir:

<table id="table_20BBE4387F234CF199E6C99741AF265C"> 
 <tbody> 
  <tr> 
   <td> Código HTML </td> 
   <td> Esta parte consiste em código JavaScript colocado nas páginas HTML (ou modelos) que definem o valor das variáveis JavaScript. </td> 
  </tr> 
  <tr> 
   <td> Biblioteca de JavaScript </td> 
   <td> <p>O arquivo contém código comum que: </p> 
    <ul id="ul_ED50D66F2B2B476E8D9063099995998D"> 
     <li id="li_E88F6F28EC8946469ADCEAFF2F0A4EBA">Consulta o navegador sobre várias propriedades, como versão do JavaScript, versão do SO, tamanho e resolução do monitor que está sendo usado e outras variáveis </li> 
     <li id="li_5CEBE37709D943B7921447FA7054A565">Codifica e concatena todas as variáveis em uma solicitação de imagem (&lt;img&gt;) que transporta essas variáveis para os servidores de coleta de dados. Em seguida, ele referencia um arquivo da biblioteca de JavaScript que é carregado e executado. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> &lt;noscript&gt; tag </td> 
   <td> Uma versão simplificada da solicitação de imagem é inserida em uma tag &lt;noscript&gt; que é executada se o usuário tiver desativado o JavaScript ou não tiver recursos de JavaScript. Essa parte da implementação é opcional e geralmente se aplica a aproximadamente 2% da população da internet. </td> 
  </tr> 
 </tbody> 
</table>

O JavaScript pode detectar configurações do navegador que não estão disponíveis para um servidor, como altura/largura da janela do navegador, e plug-ins do Netscape. Se você usar um método do lado do servidor para criar uma tag de imagem, essas variáveis não poderão ser capturadas. O JavaScript define um número aleatório na solicitação de imagem para superar o armazenamento em cache do navegador e do servidor proxy. Isso permite que todas as exibições de página sejam acompanhadas precisamente. Em determinadas situações, o código do lado do servidor tem vantagens sobre o código JavaScript, incluindo as seguintes:

* O JavaScript é muito preciso (98-100%). Algumas vezes, a precisão máxima é desejada, mesmo em situações em que um usuário clica rapidamente em outra página antes da execução do JavaScript. A criação tag de imagem no lado do servidor aumenta o nível de precisão em vários pontos percentuais.
* Para eventos de conversão de rastreamento, como compras, nos quais a precisão é muito importante.
* Essa estratégia também pode ser usada para preencher totalmente a solicitação de imagem na tag <noscript> para rastrear usuários sem JavaScript ou com JavaScript desativado.

> [!NOTE] O uso de tags de imagem geradas no servidor requer mais tempo para implementação e é mais difícil de depurar, implantar e manter. A Adobe incentiva fortemente que os clientes usem a coleta de dados baseada em JavaScript em todas as páginas em que isso for possível. Diversos relatórios e recursos, incluindo mapa de cliques de visitantes, links para download, links de saída e variáveis baseadas em navegadores (largura/altura do navegador etc) não podem ser coletados ou suportados com o uso desse método de implementação.

