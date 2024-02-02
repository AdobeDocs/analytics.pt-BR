---
description: Perguntas frequentes sobre o Advertising Analytics.
title: Perguntas frequentes sobre análises de publicidade
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 591b82e271cc7474e9b413015804d4fe37d9050c
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 50%

---

# Perguntas frequentes

## Acesso/Direitos {#access}

+++ Preciso ser um cliente do Adobe Advertising Cloud ou do Adobe Advertising Cloud (AMO) para acessar essa funcionalidade?

Não, essa funcionalidade está disponível para clientes que não são da Advertising Cloud e nem do AMO. </p> <p>Os clientes do AMO podem aproveitar da integração Analytics-AMO existente; eles não poderão usar o Advertising Analytics.

+++

+++ Quais SKUs do Adobe Analytics dão direito ao uso do Advertising Analytics?

O Advertising Analytics está disponível para o Adobe Analytics

* [Selecionar](https://www.adobe.com/br/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/br/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/br/data-analytics-cloud/analytics/ultimate.html)

+++

+++ Preciso pagar a mais para usar o Advertising Analytics?

Não, fora do provisionamento de SKU adequado, a Advertising Analytics não incorre em custo extra.

+++

+++ O Advertising Analytics conta com o meu uso de chamadas do servidor

Não, o Advertising Analytics usa um tipo de fonte de dados especial que não implica custos de chamada de servidor.

+++

+++ Se eu já usar o Advertising Cloud/AMO, ainda posso usar a funcionalidade do Advertising Analytics?

Qualquer conta de mecanismo de pesquisa compatível passará para o Advertising Analytics e será exibida como somente leitura. Todas as edições ou atualizações devem ser tratadas na Advertising Cloud/AMO.

+++

+++ Eu possuo o SKU correto, mas não consigo acessar o Advertising Analytics. Por quê?

O Advertising Analytics está disponível somente para administradores do Adobe Analytics; no entanto, os administradores podem conceder acesso a não administradores. Entre em contato com seu administrador para obter os direitos de acesso.

+++

## Usar o Advertising Analytics {#using}

+++ Quais contas de mecanismo de pesquisa são incluídas no Advertising Analytics?

As contas de mecanismo de pesquisa incluem o Google AdWords e o Microsoft Bing.

+++

+++ Onde acesso o Advertising Analytics?

Depois de fazer logon no Adobe Analytics, navegue até o [!UICONTROL Admin]. Em seguida, selecione [!UICONTROL Advertising Analytics] para adicionar as contas do mecanismo de pesquisa.

+++

+++ Como os dados são coletados e transmitidos para o Analytics?

O Advertising Analytics utiliza uma série de APIs personalizadas para transmitir dados de mecanismos de pesquisa por meio da Adobe Advertising Cloud para o Analytics.

+++

+++ Quais dados de pesquisa eu obtenho com essa integração?

Você obterá

* Impressões
* Cliques
* Custos
* Pontuação de qualidade
* Posição média diretamente dos mecanismos de pesquisa, bem como
* Instâncias de ID do AMO (instâncias de clique).

+++

+++ É possível detalhar meus dados do Advertising Analytics por outros dados do Analytics (métricas/dimensões)?

Não, os dados brutos de pesquisa entrarão como um conjunto de dados independente. Contudo, há uma versão de Instâncias dos dados de clique que pode ser detalhada por outros dados do Analytics.

+++ Qual é a definição dos vários indicadores de status para minhas contas (Pendente, Ativo, Pausado etc.)? Cada um desses indicadores de status identifica o estágio do ciclo de vida de cada conta de mecanismo de pesquisa.

* [!UICONTROL Pending]
* [!UICONTROL Pausado] significa que a conta já tinha sido configurada mas foi colocada em um estado de inatividade.
* [!UICONTROL Ativo] significa que a conta foi totalmente configurada e está transferindo os dados de pesquisa.

+++

+++ Estou tentando mapear minhas contas do Advertising Analytics para um conjunto de relatórios específico, mas não está disponível no modal do Conjunto de relatórios. Por quê?

Antes de atribuir um conjunto de relatórios a uma conta do Advertising Analytics, o conjunto de relatórios desejado precisa ser [provisionado para relatórios do Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
Isso é feito por meio de uma página de Admin separada, acessível em: Administração > Conjuntos de relatórios > [selecionar conjunto de relatórios] > Editar configurações > Configuração do Advertising Analytics.

+++

+++ É possível atribuir um conjunto de relatórios virtual a uma conta do Advertising Analytics?

Os conjuntos de relatórios virtuais não coletam dados, portanto, não é possível mapear diretamente uma conta do Advertising Analytics para um conjunto de relatórios virtual. No entanto, é possível mapear a conta do Advertising Analytics para o Conjunto de relatórios principal do Conjunto de relatórios virtuais no qual você deseja ver os dados. As métricas do mecanismo de pesquisa (clique/custo/impressões) podem não ser exibidas no conjunto de relatórios virtual a menos que você inclua uma condição &quot;ou&quot; na lógica do segmento com base na ID do AMO (ou sua classificação). Exemplo: adicionar “todas as ocorrências em que a ID do AMO existe” incluirá as métricas do mecanismo de pesquisa no segmento.

+++

+++ As métricas do Advertising Analytics podem ser relatadas no <b>Canais de marketing</b> relatório?

Não, elas não estão incluídas no relatório de Canais de marketing.

+++

+++ Quando os dados de pesquisa são transferidos para o Analytics?

Os dados de pesquisa são transferidos dos mecanismos de pesquisa por volta de 6:00 no fuso horário de seu Data Center do Analytics. Nesse momento os dados do AMO são coletados e inseridos no conjunto de relatórios. Em seguida, são convertidos para o fuso horário do conjunto de relatórios como parte da inserção de dados no Analytics.

+++

+++ O que pode ser <b>capturado antes do clique</b>? Trazemos impressões, custo, posição média etc, mesmo sem o clique? </p> </td>

A ID do AMO capturará as métricas do mecanismo de pesquisa: Impressões, Custo, Cliques, Posição média e Pontuação de qualidade média. Se não houver nenhum clique, mas houver impressões, os dados de impressão/posição/pontuação de qualidade serão enviados para o Analytics. Normalmente, se não houver cliques também não há custo.

+++

+++ Em que nível esses dados estão sendo capturados? <b>Visitante? Ocorrência?</b>

As métricas do mecanismo de pesquisa são capturadas no nível de ocorrência e conectadas à ID do AMO (e suas classificações). São dados de nível de resumo e não são conectados a visitas/visitantes. Sendo assim, as métricas do mecanismo de pesquisa só podem ser usadas em segmentos do escopo de nível de ocorrência e que são baseados na ID do AMO (ou em suas classificações).

A ID do AMO também é capturada na página de aterrissagem na ocorrência dessa página (que a conecta à visita/ao visitante) e persiste em downstream para obter crédito de outras métricas do Analytics (até que expire ou seja substituída por uma nova ID do AMO). É totalmente incorporada ao conjunto de dados, como qualquer outra eVar.

+++

+++ Capturamos apenas google.com ou <b>versões de países</b> (como google.co.uk, google.it, google.fr ou google.de) também?

A classificação da Plataforma de anúncio captura estes valores: &quot;Google Adwords&quot; e &quot;Bing Ads&quot;. Uma prática recomendada é incluir o código do país como parte do nome das campanhas. Assim é possível filtrar ou segmentar (por exemplo, se todas as campanhas começarem com countrycode_, criar um segmento onde Campanhas (AMO ID) comece com “UK_” fornecerá apenas dados do Reino Unido).

+++

+++ A métrica &quot;Custo AMO&quot; é o custo pago por cada palavra-chave/anúncio, conforme relatado pelo mecanismo de pesquisa. Esse é o Custo líquido ou o Custo bruto?

&quot;Custo AMO&quot; é apenas o custo pago aos mecanismos de pesquisa. Ele não inclui taxas de plataforma para agência ou otimização/gerenciamento de pesquisa.

+++

+++ Há planos para incluir outros canais de publicidade, como <b>Exibir</b> ou <b>Social</b>?

Não, atualmente não temos planos para esses outros canais no roteiro.

+++


## Rastreamento automático vs. manual {#section_7437C4698A6D482EB7ED94A948390119}

<table id="table_9738FF8459574ED2937A860A665BE739"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>P: Ao configurar a conta publicitária, aparece que o <b>Rastreamento automático</b> pode levar a consequências não intencionais. Que tipos de consequências pode ocorrer? </p> </td> 
   <td colname="col2"> <p>R: 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">O modo automático tentará anexar os parâmetros de URL ao final dos URLs de modelo/destino de rastreamento no formato adequado. <b>Contudo, é sua responsabilidade garantir que os parâmetros de URL adicionados persistam corretamente na página de aterrissagem final. </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">O modo automático pode inserir palavras-chave ao URL de aterrissagem, e seu servidor da Web pode não ser compatível com palavras-chave com caracteres especiais. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>P: Se eu configurar o Rastreamento manual ou o Automático inicialmente, <b>poderei alternar</b> para o outro modo posteriormente? Quais são as implicações? </p> </td> 
   <td colname="col2"> <p>R: Sim, é possível alterar, mas será necessário remover a lógica de rastreamento antiga antes da alteração. Isso pode resultar em inatividade do rastreamento no dia que a alteração for feita (especialmente se estiver mudando do manual para o automático). Dessa forma, é recomendado não alterar, exceto seja absolutamente necessário. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Alterar do Manual para o Automático</b>: remova as adições manuais feitas aos modelos de rastreamento, altere o botão na interface do usuário do Advertising Analytics de Manual para Automático e salve a configuração. Observe que pode levar até x horas para que o sistema preencha os códigos de rastreamento automático. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Alterar do Automático para o Manual</b>: atualize o botão de Manual para Automático na interface do usuário de instalação do Advertising Analytics e implante os códigos de rastreamento manual o mais rápido possível. Ao implantar os códigos de rastreamento manual, se você encontrar os códigos de rastreamento automático nos modelos de rastreamento do mecanismo de pesquisa, remova-os. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
