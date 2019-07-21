---
description: Existem diversos tipos de variáveis disponíveis na Experience Cloud. Os dois tipos mais populares, Props e eVars, permitem que sua organização informe sobre dimensões personalizadas para site que os relatórios padrão prontos não oferecem.
keywords: Implementação do Analytics; prop; evar; props x evars; convenção de nomenclatura; variáveis de tráfego; persistence; evento bem-sucedido; caminho
seo-description: Existem diversos tipos de variáveis disponíveis na Experience Cloud. Os dois tipos mais populares, Props e eVars, permitem que sua organização informe sobre dimensões personalizadas para site que os relatórios padrão prontos não oferecem.
seo-title: Comparação de Props e eVars
solution: Analytics
title: Comparação de Props e eVars
topic: Desenvolvedor e implementação
uuid: 0 f 02760 f-ff 69-481 c-a 817-799 f 02 dafe 8 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Comparação de Props e eVars

Existem diversos tipos de variáveis disponíveis na Experience Cloud. Os dois tipos mais populares, Props e eVars, permitem que sua organização informe sobre dimensões personalizadas para site que os relatórios padrão prontos não oferecem.

Ao determinar quais variáveis são atribuídas a que local, é importante compreender as diferenças entre a funcionalidade de Prop e de eVar. Compreender essas diferenças permite que sua organização decida que tipo de variável é melhor para ser usada. 

**Props x eVars**

As seguintes são as principais diferenças entre props e eVars:

* **Convenção de nomes**: As props são consideradas variáveis de tráfego, o que significa que são usadas para relatar a popularidade de várias dimensões de site. As eVars são consideradas variáveis de conversão. Elas são usadas para determinar quais dimensões de site contribuem mais com os eventos de sucesso.
* **Persistência**: As props não persistem além da solicitação de imagem na qual foi disparada. Elas não podem ser associadas a outras variáveis que não estejam na mesma solicitação de imagem. As eVars, contudo, são persistentes. Uma variável back-end é usada para preservar o valor disparado originalmente para que possa associar-se a eventos de sucesso no futuro.
* **Eventos de sucesso**: Eventos de sucesso, também conhecidos como eventos de conversão, são métricas que medem o número de vezes que um visitante alcança um objetivo. Esse evento pode ser qualquer coisa, desde a compra de algo do site à inscrição de um boletim informativo. As eVars são projetadas para relatar eventos de conversão, para mostrar quais valores tem mais sucesso em influenciar visitantes a atingir seus objetivos. Variáveis de tráfego não têm essa mesma funcionalidade. No entanto, é possível visualizar métricas de participação se você configurar seu conjunto de relatórios corretamente.
* **Definição de caminho**: As props podem usar a definição de caminho, que permite que sua organização veja um caminho específico que um visitante tomou no contexto a variável sendo exibida. Um representante da Adobe pode habilitar a definição de caminho, se for solicitado. As eVars não pode usar a definição de caminho.
* **Métricas potencialmente disponíveis**: As métricas disponíveis entre props e eVars variam muito com base nas configurações da variável e a plataforma/versão dos dados. A lista a seguir ilustra o que pode ser ativado, não o que está ativado por padrão. Se desejar uma métrica específica no relatório, mas não a vir, faça com que um dos usuários suportados de sua organização entre em contato com o atendimento ao cliente.

<table id="table_FB963F60857A4AD79562324FB6F4B6A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Métrica </p> </th> 
   <th colname="col2" class="entry"> <p>Props </p> <p>(Variáveis de tráfego) </p> </th> 
   <th colname="col3" class="entry"> <p>eVars </p> <p>(Variáveis de conversão) </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Profundidade média da página </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_165C1BF1574247CEA9190ADCABF79D69" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo médio gasto </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_9F0F396E11B442959EC3E5D4D508496D" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taxa de rejeição </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_A268EAF747EA45F8A6A93A1B66667A06" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_09D486144CEA4293A505DCA3F90B82EC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devoluções </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_471A02B78FD842BB97ED3FF4A5908B03" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D2F11B5687484D9EBF6D1DEB3F303A20" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas calculadas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_7FAB1CF2ACC44D9198C648D3FC9E52D9" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8BCC2EE92CC04778809D1BD48D2623D7" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eventos de conversão personalizada </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D75C764B83AE4491A7E68C459FED1300" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entradas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E9A1FCDFCB924D75ABFAEBD5570D4EE0" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5E57974B5A64F3FA3A145428420EB23" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Saídas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_BE343F94EAD74D54B6ABC80E8A76A9BD" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_3183B2BB62C24B048EDED3295F2BEC85" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Instâncias </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8733F5AC189E43DAA8D1847416EA68C8" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_B10AB2898F3D4EBA947FADB27B118143" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exibições de página </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8BD2B23FBDA64A648BED40A2993F7C1C" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_CBDFD74340FA4973847033C1F956F0AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas de participação </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E63F978830FB46809E62654F37C4C182" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_6AB756A4598F4452887D29AD4971985A" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas de compra </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8F8AB7CD02764245BA73CA1E6B69BAE1" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recargas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_FBE0C84E01004937B7B408198A33A9E7" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas do carrinho de compras </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_123993465D734EABB311730ED03263F6" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Acesso único </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_038C6991E3F341B18E7A355D17C88895" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo Total Gasto </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_090587D29F1649319033D5A15B34B138" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_841DF09FD32A44B1B1B876F4E0CE29AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitantes únicos </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_38556E6A43B04E2E8A01855452D30A83" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5D4BDE1AA9C4C58A6402418390EEC52" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitas </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_017BB279C5824028870360A5D4D27556" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

* **Análises**: As props usam correlações, que mostram exibições de página para outras variáveis de tráfego disparadas na mesma solicitação de imagem. As eVars usam subrelações, que fornecem um detalhamento em outras variáveis de conversão em rela'~ao a eventos de sucesso.

## Vantagens exclusivas de props e eVars {#section_B384031AB8674065BA5187B0A3A3DAB9}

Com o lançamento da versão 15, os recursos entre props e eVars são muito menos distintos. As eVars foram atualizadas recentemente para incluir recursos como visitas/visitantes únicos com carga de processamento mínima, bem como métricas de definição de caminho.

As props têm certas vantagens em relação às eVars, e podem ser evitadas:

* Os dados da prop são coletados e disponibilizados nos relatórios quase instantaneamente. As eVars podem levar mais de 30 minutos para serem exibidas nos dados do conjunto de relatórios.
* Todas as props podem ter relatórios do tipo fluxograma ativados, o que permite ver o percurso dos visitantes no seu site. These pathing flow reports are available for both Props and eVars in [!UICONTROL Ad Hoc Analysis].
* As props podem ser corresponder a vários níveis, enquanto as eVars podem ser sub-relacionadas apenas uma vez. Tal limitação pode ser eliminada por meio da segmentação, fornecendo dados idênticos como correlações.
* As métricas de participação permitem ver quais valores de prop já participaram de um evento bem-sucedido.

Por outro lado, as eVars apresentam algumas vantagens que superam a natureza limitada das props:

* As eVars podem usar eventos bem-sucedidos como métricas. O mesmo não acontece com as props.
* A expiração da eVar pode ser personalizada, incluindo a possibilidade de ter uma expiração de cada ocorrência (valores não persistentes). As props não persistem de forma alguma.

As métricas de definição de caminho, como Tempo total gasto, Entradas e Saídas originalmente não estavam disponíveis para as eVars. Contudo, as atualizações recentes deixaram essas métricas disponíveis, aumentando o valor das eVars.

## Qual deve ser usada {#section_022D016A4EEB45179A15BFF044A261A4}

**Props:** se a latência for a maior preocupação e você quiser medir somente o tráfego (e não eventos bem-sucedidos) com esta dimensão.

**eVars:** se detalhamentos de dados e relacionamentos forem as maiores preocupações.

>[!TIP]
>
>Se não quiser que uma evar persista, você pode alterar sua expiração para'ocorrência'para que ela não mantenha dados além da ocorrência.

