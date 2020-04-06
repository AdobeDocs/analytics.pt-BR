---
description: A variável de conversão do Custom Insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu objetivo principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados. Uma eVar pode ser baseada em visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.
keywords: eVar
title: Variáveis de conversão (eVar)
topic: Admin tools
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Variáveis de conversão (eVars)

A variável de conversão do Custom Insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu objetivo principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados. Uma eVar pode ser baseada em visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.

Quando uma eVar é definida como um valor para um visitante, a Adobe lembra automaticamente esse valor até que expire. Todos os eventos bem-sucedidos que um visitante encontra enquanto o valor de eVar está ativo são contados em relação ao valor de eVar.

As eVars são mais bem usadas para medir causa e efeito, como:

* Quais campanhas internas influenciaram a receita
* Quais anúncios em banner resultaram em um registro
* O número de vezes que uma pesquisa interna foi usada antes de fazer um pedido

Se a medição de tráfego ou definição de caminho for desejada, é recomendado usar variáveis de tráfego.

>[!NOTE] Somente um valor único pode ser armazenado em uma eVar em uma solicitação de imagem. Se vários valores forem desejados no valor de uma eVar, recomendamos a implementação de [Listar variáveis (list vars)](https://marketing.adobe.com/resources/help/pt_BR/sc/implement/listN.html).

## Variáveis de conversão - descrições {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descrições de campos usados ao [editar variáveis de conversão](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md).

<table id="table_E48D50926E6B492183300CA58A886927"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Elemento </p> </th> 
   <th colname="col2" class="entry"> <p>Descrição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Nome </span> </p> </td> 
   <td colname="col2"> <p>O nome amigável da variável de conversão. Esse nome é como a eVar é chamada em geral no relatórios e será o nome do relatório no menu esquerdo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Tipo</span> </p> <p>(somente eVar) </p> </td> 
   <td colname="col2"> <p>O tipo de valor da variável: </p> <p> <b>Cadeia de caracteres de texto</b>:</span> captura os valores de texto usados do site. Esse é o tipo mais comum de eVar e a configuração padrão. Funciona de forma semelhante a outras variáveis, em que o valor dentro dela é uma string de texto estática. Se você estiver rastreando coisas como campanhas internas ou palavras-chave de pesquisa interna, essa é a configuração recomendada. </p> <p> <b>Contador</b>:</span> conta o número de vezes que uma ação ocorre antes do evento bem-sucedido. Por exemplo, se você usa uma eVar para rastrear pesquisas internas no site, configure esse valor como <span class="uicontrol">sequência de caracteres de texto</span> para rastrear o uso de termos de pesquisa. Configure esse valor como <span class="uicontrol">contador</span> para contar o número de pesquisas efetuadas, independentemente dos temos de pesquisa usados. Por exemplo, você pode usar uma eVar de contador para rastrear o número de vezes que alguém usou sua pesquisa interna antes de realizar uma compra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Alocação </span> </p> </td> 
   <td colname="col2"> <p>Determina como o Analytics atribuirá crédito por um evento bem-sucedido se uma variável receber vários valores antes do evento. Os valores suportados incluem: </p> <p> <b>Mais recente</b>: o último valor de eVar sempre recebe crédito por eventos bem-sucedidos até que esse eVar expire. </p> <p> <b>Valor original</b>: a primeira eVar sempre recebe crédito por eventos bem-sucedidos até que essa eVar expire. </p> <p> <b> Linear</b>: aloca eventos bem-sucedidos igualmente entre todos os valores de eVar. Como a alocação Linear distribui com precisão os valores somente em uma visita, use essa alocação com Visita como expiração de eVar. </p> <p>Observação: a alternância da alocação de ou para Linear impede que os dados históricos sejam exibidos. A combinação de tipos de alocação na interface do relatórios pode levar a dados incorretos nos relatórios. Por exemplo, a alocação Linear pode dividir a receita entre vários valores diferentes de eVar. Depois de voltar para a alocação mais recente, 100% dessa receita seria associada ao valor único mais recente. Essa associação pode levar os usuários a conclusões incorretas. </p> <p>Para evitar a probabilidade de confusão no relatórios, o Analytics torna os dados históricos indisponíveis para a interface. Ele pode ser exibido se você decidir alterar a eVar de volta para a configuração de alocação inicial, embora não deva alterar as configurações de alocação de eVar apenas para acessar os dados históricos. A Adobe recomenda usar uma nova eVar quando novas configurações de alocação forem desejadas para dados já gravados, em vez de alterar as configurações de alocação em uma eVar que já tenha uma quantidade significativa de dados históricos acumulados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Expirar após</span> </p> </td> 
   <td colname="col2"> <p>Especifica um período de tempo, ou evento, após o qual o valor da eVar expira (não recebe mais crédito por eventos bem-sucedidos). Se um evento bem-sucedido ocorrer após a expiração da eVar, o valor Nenhum receberá o crédito pelo evento (nenhuma eVar estava ativa). </p> <p>Se você selecionar um evento como um valor de expiração, a variável expirará somente se o evento ocorrer. Se o evento não ocorrer, a variável nunca expirará. </p> <p>As opções de expiração disponíveis podem ser classificadas em quatro categorias principais: </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>Em uma visualização de página ou nível de visita.</b> Os eventos de conversão além da visualização de página ou da visita não estão associados à eVar. </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>Com base em um período, como dia, semana, mês ou ano.</b> eventos de conversão além do período de tempo especificado não estão associados à eVar. O período de expiração start quando a variável é definida. As eVars expiram com base no tempo definido, com a segunda (minuto, hora, dia, mês etc): 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTO=60 segundos </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">HORA=3600 segundos (60 minutos) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">DIA=86400 segundos (24 horas) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">SEMANA=604800 segundos (7 dias) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MÊS=2678400 segundos (31 dias) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">TRIMESTRE=8035200 segundos (93 dias - 3 meses de 31 dias) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">ANO=31536000 segundos (365 dias) </li> 
      </ul> <p> </p> <p>Se uma visita start às 7:00 da manhã de segunda-feira e uma eVar estiver definida dentro dessa visita às 7:15 da manhã, a expiração será a seguinte: </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">Expiração do dia: eVar expira às 7h15 de terça-feira. </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">Expiração da semana: eVar expira na segunda-feira seguinte às 7h15. </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">Expiração mensal: eVar expira 31 dias após a segunda-feira às 7h15. </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>eventos de conversão específicos.</b> Quaisquer outros eventos de conversão que forem acionados após o evento específico designado associam-se à eVar. </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>Nunca.</b> Contanto que o cookie Se o cookie <span class="varname">visitorID</span> estiver intacto, a passagem do tempo será indiferente entre o eVar e o evento. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Status</span> </p> <p>(somente eVar) </p> </td> 
   <td colname="col2"> <p>Define o status da eVar: </p> <p><b>Desativado</b>:</span> desativa a eVar. Remove a eVar da lista de variáveis de conversão. </p> <p> <b>Sem sub-relações</b>:</span> impede que você decomponha a eVar com uma sub-relação. </p> <p> <b>Sub-relações básicas</b>:</span> permite decompor uma eVar em qualquer relatório com sub-relações totais (por exemplo, Produtos ou Campanhas). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Redefinir</span> </p> </td> 
   <td colname="col2"> <p>Redefine qualquer valor existente na eVar. </p> <p>Use essa configuração ao redefinir o objetivo de uma eVar para que você combine um valor antigo em um novo relatório. A redefinição não apaga dados históricos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Merchandising</span> </p> <p>(somente eVar) </p> </td> 
   <td colname="col2"> <p>As variáveis de comercialização podem seguir uma de duas sintaxes: </p> <p> <b>Sintaxe de produtos</b>:</span> associa o valor de eVar a um produto. Observação: se a Sintaxe de produtos estiver selecionada, a seção Evento de vinculação de merchandising é desativada e não pode ser selecionada para edição. Os Eventos de vinculação não se aplicam a essa sintaxe. </p> </p> <p> <b>Sintaxe de variável de conversão</b>:</span> associa a eVar a um produto somente se um evento compulsório ocorrer. Nesse caso, você seleciona os eventos que atuam como Eventos de ligação. </p> <p>Alterar essa configuração sem atualizar seu código JavaScript de acordo resultará na perda de dados. Ver <a href="https://marketing.adobe.com/resources/help/pt_BR/sc/implement/var_merchandising.html">Variáveis de merchandising</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Evento compulsório de merchandising</span> </p> <p>(somente eVar) </p> </td> 
   <td colname="col2"> <p>Se Merchandising estiver definido como <span class="uicontrol">Sintaxe de variável de conversão</span>, os eventos selecionados vincularão o valor de eVar atual a um produto. </p> <p>Para usar um evento compulsório, defina <span class="uicontrol">Alocação como Mais recente</span>. Se <span class="uicontrol">Alocação for Valor original</span>, a primeira ligação de produto de eVar permanecerá até que eVar expire. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Expiração**

As `eVars` expiram depois de um período definido por você. Depois que a eVar expira, ela não recebe mais crédito por eventos bem-sucedidos. As eVars também podem ser configuradas para expirar em eventos bem-sucedidos. Por exemplo, se você tiver uma promoção interna que expira no final de uma visita, a promoção interna recebe crédito apenas para compras ou registros que ocorrem durante a visita em que foram ativados.

Há duas maneiras de expirar uma eVar:

* Você pode definir a eVar para expirar após um período ou evento especificado.
* É possível forçar a expiração de uma eVar redefinindo-a, o que é útil ao redefinir o objetivo de uma variável.

Por exemplo, se você alterar a expiração de uma eVar de 30 para 90 dias, os valores de eVar coletados continuarão a persistir pela duração do novo conjunto de expiração (nesse caso, 90 dias). O sistema simplesmente verifica a configuração de expiração atual e o último carimbo de data e hora definido do valor da eVar coletado para determinar a expiração. Somente a **[!UICONTROL Reset]** opção expira os valores e o faz imediatamente.

Outro exemplo: Se uma eVar for usada em maio para refletir promoções internas e expirar após 21 dias, e em junho for usada para capturar palavras-chave de pesquisa interna, em seguida, em 1º de junho, você deverá forçar a expiração ou redefinir a variável. Com isso, você ajudará a manter os valores da promoção interna fora dos relatórios de junho.

**Uso de maiúsculas e minúsculas**

As eVars não fazem distinção de letras maiúsculas e minúsculas, mas são exibidas com essa diferenciação na primeira ocorrência. Por exemplo, se a primeira instância da eVar1 estiver definida como &quot;Conectado&quot;, mas todas as instâncias subsequentes forem transmitidas como &quot;conectado&quot;, os relatórios sempre mostrarão &quot;Conectado&quot; como o valor da eVar.

**Contadores**

Embora as eVars sejam usadas com mais frequência para reter valores da string, elas também podem ser configuradas para atuar como contadores. As eVars são úteis como contadores quando você está tentando contar o número de ações que um usuário toma antes de um evento. Por exemplo, você pode usar uma eVar para capturar o número de pesquisas internas antes da compra. Sempre que um visitante pesquisar, a eVar deve conter um valor de &#39;+1&#39;. Se um visitante pesquisar quatro vezes antes de uma compra, você verá uma instância para cada contagem total: 1,00, 2,00, 3,00 e 4,00. No entanto, somente a 4,00 receberá crédito pelo evento da compra (Pedidos e métricas de receita). Somente números positivos são permitidos como valores de um contador eVar.