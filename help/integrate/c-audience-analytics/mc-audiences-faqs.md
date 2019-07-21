---
description: Respostas a perguntas que você pode se fazer ao implantar o Audience Analytics.
seo-description: Respostas a perguntas que você pode se fazer ao implantar o Audience Analytics.
seo-title: Perguntas frequentes
solution: Marketing Cloud
title: Perguntas frequentes
uuid: 9 dfc 8 f 19-f 9 b 2-4 c 2 e-bff 9-3 d 91 cfe 01 bca
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Perguntas frequentes

Respostas a perguntas que você pode se fazer ao implantar o Audience Analytics.

## Perguntas frequentes jurídicas {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>P: Como faço para saber se tenho Informações pessoais identificáveis (PII) nos meus dados do Analytics? Caso afirmativo, como devo proceder?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">Se você tiver emails/endereços/etc em uma prop ou eVar, considere fazer o hash dos dados durante a coleta. </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">Se seu país considera endereços IP como PII, <a href="https://marketing.adobe.com/resources/help/en_US/reference/exclude_IP.html" format="html" scope="external">ative a ofuscação de IP </a>. </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">Entre em contato com o Administrador do Analytics para descobrir o que está sendo coletado. </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">Entre em contato com o departamento jurídico para descobrir o que é considerado como PII. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: Como faço para saber se meus conjuntos de relatórios fazem personalização local, ou direcionamento fora/no site?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">Isso não se aplica ao envio de dados do Adobe Analytics para o Adobe Audience Manager. </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">Pergunte-se: você compartilhará um segmento compartilhado pelo Analytics com uma dimensão de MCA para a Experience Cloud? </li> 
     <li id="li_C52D969681B94F4AAA18FDEB21EC5B49">Você está exportando (por meio de feeds de dados) para um sistema de Business Intelligence (BI) usado para esse propósito? </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Perguntas frequentes específicas sobre o AAM {#section_6BDF746BA6464359A6A89A64EB025D12}

<table id="table_15B44592161240BDA79F3B020EA9CC9D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: Como faço para criar um destino do Analytics no Audience Manager?</b> </p> </td> 
   <td colname="col2"> See <a href="https://marketing.adobe.com/resources/help/en_US/aam/create-analytics-destination.html" format="html" scope="external"> Configure an Analytics Destination in AAM </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Depois de criar e salvar um destino do Analytics, quanto leva até que os dados apareçam em meus conjuntos de relatórios selecionados?</b> </p> </td> 
   <td colname="col2"> <p>Pode demorar algumas horas para preencher seus conjuntos de relatórios com novos dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Criei um novo destino do Analytics, mas ele não é exibido na seção de Mapeamentos de destino de meus segmentos disponíveis. Onde e como posso encontrá-lo?</b> </p> </td> 
   <td colname="col2"> <p>Um destino do Analytics desaparece da seção de Mapeamentos de destino de um segmento ao selecionar a opção <span class="uicontrol">Mapear automaticamente todos os segmentos atuais e futuros</span> em <span class="uicontrol">Mapeamentos de segmentos </span>. </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>Para evitar que isso aconteça, selecione <span class="uicontrol">Mapear segmentos manualmente</span> em vez da opção automática. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>P: Isso fornecerá todas as informações do AAM, no Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Não, você terá acesso somente a dados relacionados a pessoas que visitam seu site durante ou depois da habilitação do Audience Manager Audiences e durante/depois da qualificação de segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>P: isso fornece um público-alvo totalmente direcionável por segmento?</b> </p> </td> 
   <td colname="col2"> <p>Não necessariamente. Isso indica a quantidade de visitantes no segmento que acessaram o site durante ou após a qualificação de segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>P: como isso difere do destino de cookies herdados no Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Os segmentos são qualificados e retornados em tempo real, na mesma ocorrência. </p> <p>Nomes amigáveis são exibidos automaticamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: E se alguns de meus conjuntos de relatórios apresentarem dados pessoais, e outros não?</b> </p> </td> 
   <td colname="col2"> <p>Dica: crie dois destinos; adicione os conjuntos de relatórios com dados pessoais a um destino e os conjuntos de relatórios sem dados pessoais ao outro destino. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Perguntas frequentes específicas sobre o Analytics {#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: Essa integração será exibida como uma dimensão ou um segmento no Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Como dimensões: IDs de públicos-alvo e Nomes de públicos-alvo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Onde posso usar essas dimensões no Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Quase em todos os lugares; elas são tratadas como qualquer outra dimensão coletada no Analytics. Há duas exceções: no momento, os dados não serão disponibilizados no Data Workbench ou na Transmissão em tempo real. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Por que não vejo dados sendo inseridos no Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Pode ser que você tenha controles de privacidade do AAM em conflito entre a fonte de dados e o destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Por que alguns de meus segmentos estão ausentes no Analytics, apesar de eu ter selecionado para enviar todos os segmentos?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">Seus controles de exportação de dados do AAM no destino e nas fontes de dados dos segmentos podem estar em conflito, o que evita que certos segmentos sejam enviados. </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">Se você estiver usando características de dados de terceiros em seus segmentos, tais segmentos não poderão ser compartilhados a destinos (um conjunto de conjuntos de relatórios) que contêm dados pessoais. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Por que vejo "Limite de público-alvo atingido" no meu relatório do Analytics? (Note: this will also be represented as Audience ID = -1 and "::max_audiences_exceeded::" in Data Warehouse)</b> </p> </td> 
   <td colname="col2"> <p>Por padrão, a integração do Audience Analytics para AAM envia para o Analytics todos os segmentos para os quais um usuário é classificado, em uma base “por ocorrência”. Se um visitante pertencer a mais de 150 segmentos do AAM em uma única ocorrência, os <b>150 segmentos qualificados mais recentemente</b> serão enviados ao Analytics, e a lista restante ficará truncada. </p> <p>Um sinalizador adicional é enviado ao Analytics, para avisar que a lista de segmentos está truncada, e é exibido como “Limite de público-alvo atingido” na dimensão Nome de público-alvo e “-1” na dimensão ID de público-alvo. </p> <p>Mesmo sendo improvável que um visitante seja qualificado para mais de 150 segmentos em uma única ocorrência, há uma pequena chance de isso ocorrer. Se você encontrar o erro “Limite de público-alvo atingido” em seu relatório, há duas opções: </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>Opção 1</b>: deixe a integração trabalhar em seu estado padrão, enviando os 150 segmentos qualificados mais recentemente para um certo visitante. </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>Opção 2:</b> no AAM, escolha os 150 segmentos que a sua empresa considera mais importantes para a integração. Em seguida, o AAM verificará os visitantes em relação a esses 150 segmentos. A desvantagem dessa abordagem é que você receberá somente esses 150 segmentos por todos os visitantes. Por outro lado, a abordagem da Opção 1 pode fornecer segmentos ilimitados devido à natureza “por ocorrência” da integração. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Chamadas adicionais de servidor serão cobradas ao Analytics para essa integração?</b> </p> </td> 
   <td colname="col2"> <p>Não. Públicos-alvo do AAM são incorporados no lado do servidor da ocorrência do Analytics. Isso não causa chamadas de servidor adicionais para o Analytics (primário ou secundário). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Perguntas frequentes sobre o encaminhamento pelo lado do servidor (SSF) {#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: Se eu tiver o SSF herdado implementado, preciso acessar o Admin do Analytics e ativar o SSF para conjuntos de relatórios?</b> </p> </td> 
   <td colname="col2"> <p>Sim. Na configuração de destino do AAM, você verá somente conjuntos de relatórios com SSF ativado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Por que não consigo ativar certos conjuntos de relatórios para SSF no Analytics Admin?</b> </p> </td> 
   <td colname="col2"> <p>Somente conjuntos mapeados para a sua Organização da Experience Cloud podem ser ativados. </p> </td> 
  </tr> 
 </tbody> 
</table>

For more FAQs on this topic, see [Server-Side Forwarding FAQ](/help/admin/admin/c-server-side-forwarding/ssf-faq.md).

## Perguntas frequentes gerais {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>P: Por que as contagens de visitantes de segmentos diferem entre o Audience Manager e o Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../integrate/c-audience-analytics/visitor-count-reconciliation.md#concept_03DD2B594C2B4D23907D5272DDFADFA0" format="dita" scope="local"> Diferenças na contagem de visitantes </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Qual é a diferença entre “públicos-alvo” no AAM e “segmentos” no Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../integrate/c-audience-analytics/aam-analytics-segments.md#concept_AB72F76AFAF14F82A5BB17809925813B" format="dita" scope="local"> Entenda os segmentos no Analytics e no Audience Manager </a>. </p> <p>Públicos-alvo do AAM são enviados e compartilhados como componentes de “dimensão” para serem usados no Analytics. Eles não são exibidos como segmentos no Construtor de segmentos, por exemplo, mas como dimensões que podem ser usadas para construir segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Qual é a diferença entre Atributos de clientes e os dados de cliente integrados do AAM?</b> </p> </td> 
   <td colname="col2"> <p>Atributos de clientes não são baseados em tempo; eles são aplicados retroativamente e progressivamente. Dados integrados do AAM são baseados em tempo e somente progressivos. Além disso, Atributos de clientes é uma tabela de pesquisa para IDs de visitante da Experience Cloud, enquanto a integração do AAM é uma combinação de dados em cada ocorrência referente a um visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: E abordagens herdadas a este problema, por exemplo, o beta anterior ou o plug-in de consulta cookie-destinations?</b> </p> </td> 
   <td colname="col2"> <p>Recomendamos que você implemente a nova integração e remova as anteriores. </p> </td> 
  </tr> 
 </tbody> 
</table>

