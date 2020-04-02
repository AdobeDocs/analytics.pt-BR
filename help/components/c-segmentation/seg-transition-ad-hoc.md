---
description: Se você está acostumado a trabalhar com o Construtor de segmentos na Ad Hoc Analysis, estas Perguntas frequentes explicam o que acontece aos segmentos e pastas existentes, e quais ações são necessárias.
keywords: segmentation;segments
title: Guia de transição para a Ad Hoc Analysis
topic: Segments
uuid: d409d71a-f8d9-42a2-add2-37d426cd40d1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Guia de transição para a Ad Hoc Analysis

Se você está acostumado a trabalhar com o Construtor de segmentos na Ad Hoc Analysis, estas Perguntas frequentes explicam o que acontece aos segmentos e pastas existentes, e quais ações são necessárias.

## Recursos {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* Os segmentos são universais para todos os conjuntos de relatórios. Anteriormente, os segmentos eram específicos do conjunto de relatórios.
* A Ad Hoc Analysis inclui a atualização do Construtor de segmentos e uma atualização completa do Gerenciador de segmentos.
* Agora você pode marcar segmentos para organizar e pesquisar depois, em vez de usar pastas. Anteriormente, as pastas eram usadas na [!DNL Ad Hoc Analysis] para organizar os segmentos.

## O que aconteceu com meus segmentos existentes? {#section_76CF47142D1A4FB6A0718AD9073049FE}

Seus segmentos existentes continuarão a funcionar como anteriormente. Quaisquer relatórios com esses segmentos aplicados continuarão a funcionar corretamente.

A maioria dos segmentos de conjunto e pré-definidos mais antigos serão migrados como modelos de segmentos no construtor de segmentos. Os modelos de segmentos são usados para criar rapidamente segmentos personalizados com públicos comuns. Os modelos de segmento não podem ser aplicados diretamente a um relatório, mas podem ser salvos facilmente em um segmento personalizado.

Os modelos de segmento são marcados com um ícone especial no Construtor de segmentos.

## O que aconteceu com minhas pastas de segmento existentes?  {#section_FB04DCF775694E69B761DCA53F301C30}

Em vez de pastas da análise ad hoc, o Gerenciador de segmentos usa tags. Os nomes das pastas são convertidos automaticamente em tags e estas são aplicadas aos respectivos segmentos.

## O que aconteceu com os relatórios agendados com segmentos aplicados?  {#section_81D1B215533C46E99E17BAE7A3376FDF}

Os relatórios agendados continuar a funcionar apropriadamente com os segmentos definidos.

Ao excluir um segmento, os relatórios e painéis agendados com esse segmento aplicado continuam a funcionar normalmente, ou seja, o segmento ou painel continua a usar o segmento excluído.

## O que é um Contêiner de ocorrência? Ele é diferente de um Contêiner de exibições da página?  {#section_65BBE60A836C4001938830DDA15DC256}

O contêiner de Visualização de página foi renomeado para contêiner de Ocorrência para indicar que esse contêiner segmenta todos os tipos de dados e não apenas visualizações de página. Por exemplo, chamadas de rastreamento de link e chamadas trackAction de SDKs móveis são todas incluídas ou excluídas pelo contêiner de ocorrências.

Observe que não ocorreu uma alteração na forma como esse contêiner funciona; ele foi apenas renomeado.

## Quais direitos e privilégios são necessários para que eu possa usar, criar e gerenciar segmentos?  {#section_648DFA3A882146C485A84ED014EEC707}

Todos os usuários podem criar e editar segmentos pessoais. Esses segmentos podem ser compartilhados diretamente com qualquer outro usuário do Analytics. Usuários da Ad Hoc Analysis podem ver os segmentos criados e compartilhados diretamente com o usuário.

No console da Web de Segmentação unificada, os administradores podem editar qualquer segmento e compartilhá-los com grupos ou com as pessoas na organização.

## É possível visualizar todos os segmentos na minha empresa?  {#section_AC2D328C7410419E80C7C17971CD95B3}

Todos os segmentos da análise ad hoc que você possui e os segmentos compartilhados com você são exibidos.

## É possível gerenciar todos os segmentos do Analytics no Gerenciador de segmentos?  {#section_AF5EDD72C74A4739BD40C4AF125CE489}

A análise ad hoc só exibe segmentos criados por você ou que tenham sido compartilhados com você. Somente para a análise ad hoc é possível usar o Gerenciador de segmento (Organizar segmentos) para gerenciar os segmentos da análise ad hoc. Use o Gerenciador de segmentos na Segmentação unificada para gerenciar todos os segmentos do Analytics.

## O que devo fazer com segmentos duplicados que possuem o mesmo nome, mas podem ter definições diferentes? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Agora que os segmentos funcionam em vários conjuntos de relatórios, você pode acabar descobrindo que possui vários segmentos com o mesmo nome. Recomendamos que você

* Renomeie os segmentos com o mesmo nome, mas com diferentes definições, ou
* Exclua os segmentos que não são mais necessários.

## Como a Adobe recomenda que eu limpe os segmentos?  {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Marque todos os segmentos com uma tag legada.
* Analise todos os seus segmentos.
* Quando apropriado, adicione-os à biblioteca de segmentos.
* Aprovar segmentos canônicos.

## Por que não posso excluir esse segmento? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Se o segmento foi publicado na Experience Cloud, não é possível excluí-lo nem editá-lo. Entretanto, é possível copiá-lo e editar a versão copiada.

## Mais informações sobre o que acontece com os segmentos existentes  {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Categoria de segmentos </th> 
   <th colname="col2" class="entry"> O que ocorre com esses segmentos? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Segmentos favoritos na Ad Hoc Analysis </td> 
   <td colname="col2">Esses segmentos da Ad Hoc Analysis são exibidos como segmentos regulares no Adobe Analytics. <p>Eles não devem ser confundidos com o recurso Favoritos no Gerenciador de segmentos, que permite que você marque os segmentos como favoritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmentos pré-configurados na Ad Hoc Analysis: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Visitas únicas à página </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Visitas de dispositivos móveis </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Visitas da pesquisa natural </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Visitantes da pesquisa paga </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Visitantes com cookie de ID do visitante </li> 
    </ul> </td> 
   <td colname="col2"> <p>Esses segmentos serão transferidos como modelos de segmento no construtor de segmentos. </p> <p>Os relatórios com esses segmentos aplicados continuarão funcionando da forma correta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmentos da Experience Cloud (Suite): 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Não compradores </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Compradores </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Novas visitas </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Visitas de sites sociais </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Visitas de mais de 10 minutos* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Visitas com mais de cinco visitas anteriores* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Visitas do Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> A maioria desses segmentos (exceto os marcados com um asterisco *) serão transferidos como modelos de segmento no construtor de segmentos. Além disso, vários novos modelos de segmento foram adicionados. </p> <p>Os relatórios com esses segmentos aplicados continuarão funcionando da forma correta. </p> </td> 
  </tr> 
 </tbody> 
</table>

