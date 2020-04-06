---
description: 'null'
title: Visão geral do Advertising Analytics
uuid: 00e461ff-3e17-4071-818b-93fd1e4b36f1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visão geral do Advertising Analytics

O Advertising Analytics permite visualizar todos os dados de pesquisa paga do Google e do Bing lado a lado, dentro do Adobe Analytics. Antes, quaisquer dados do Google AdWords/DFA ou do Microsoft Bing Ads teriam que ser visualizados no Adobe Advertising Cloud (AMO) ou no Google/Bing. Agora você tem os dados a seguir no Adobe Analytics: Impressões, Cliques, Custos, Pontuação de qualidade e Posição média diretamente de todos os mecanismos de pesquisa, assim como Instâncias de ID do AMO (Instâncias de clique).

>[!NOTE] O Yahoo Gemini foi absorvido pelo Microsoft Bing em 31 de março de 2019. Como consequência, a opção de conta de publicidade do Yahoo Gemini não está mais disponível.

Reunindo os dados desses mecanismos de pesquisa no Adobe Analytics, você pode analisar os mesmos dados usando a potência da área de trabalho da Análise. A new [Paid Search Performance](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) template in Workspace facilitates this analysis.

![](assets/aa_aw.png)

Essa integração tem como objetivo as seguintes audiências:

* O **analista** que precisa coletar relatórios de desempenho para o comerciante de pesquisa paga.
* O profissional de pesquisa **paga** que busca respostas para essas perguntas: Quanto tráfego estou enviando para nosso site e os clientes estão conversando? Quais são minhas campanhas de anúncios econômicas?

## Pré-requisitos {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics is available for Adobe Analytics [Select](https://www.adobe.com/br/analytics/compare-adobe-analytics-packages.html), [Prime](https://www.adobe.com/br/analytics/compare-adobe-analytics-packages.html), and [Ultimate](https://www.adobe.com/br/data-analytics-cloud/analytics/ultimate.html) SKUs only.

* Essa funcionalidade está disponível para clientes que não fazem parte da Advertising Cloud e que não fazem parte da AMO.
* Você deve ser um administrador do Adobe Analytics para ter acesso ao Advertising Analytics. Subsequentemente, você pode [conceder permissões](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) de acesso a não administradores.
* Qualquer conjunto de relatórios do Analytics no qual deseja exibir os dados de pesquisa do Google/Bing deve ser [mapeado para sua organização Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/mcloud/report-suite-mapping.html).
* For any report suite where you want to view Google/Bing search data, you must [enable those report suite/s for Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).

* Você precisa de credenciais de logon para um usuário com permissões de edição para a(s) conta(s) de pesquisa que deseja integrar ao Adobe Analytics, como uma ID de conta e senha do Google.
* No caso do Bing Ads, você também precisa da ID do cliente do Bing.
* If you use Internet Explorer 11 (or earlier), you will not be able to successfully [set up an advertising account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) for any of the three search engines. Em vez disso, use outros navegadores da Web.

## Permissões do Advertising Analytics {#section_FCC58EB635954A32990D4E67B52B4369}

O Analytics tem duas permissões que são concedidas automaticamente aos administradores do Analytics. Os administradores podem então optar por conceder essas permissões a não administradores.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Permissão </th> 
   <th colname="col2" class="entry"> Definição </th> 
   <th colname="col3" class="entry"> Conceder permissão no Adobe Analytics </th> 
   <th colname="col4" class="entry"> Conceder permissão se você estiver conectado à Adobe Experience Cloud </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gerenciamento do Advertising Analytics </p> </td> 
   <td colname="col2"> <p>Permite que os usuários configurem/editem/visualizações contas de pesquisa de publicidade. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol">Gerenciamento de usuário</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Editar acesso a todos os relatórios</span> &gt; <span class="uicontrol">Personalizar ferramentas do Analytics</span> &gt; <span class="uicontrol">Gerenciamento do Advertising Analytics</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Faça logon em adminconsole.adobe.com</span> &gt; <span class="uicontrol">Produtos</span> &gt; <span class="uicontrol">Perfil do produto</span> &gt; <span class="uicontrol">guia Permissões</span> &gt; <span class="uicontrol">Ferramentas do Analytics</span> &gt; <span class="uicontrol">Gerenciamento do Advertising Analytics</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuração do Advertising Analytics </p> </td> 
   <td colname="col2"> <p>Permite que os usuários configurem conjuntos de relatórios a serem provisionados para o Advertising Analytics. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol">Gerenciamento de usuário</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Editar acesso a todos os relatórios</span> &gt; <span class="uicontrol">Personalizar ferramentas do conjunto de relatórios</span> &gt; <span class="uicontrol">Configuração do Advertising Analytics</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Faça logon em adminconsole.adobe.com</span> &gt; <span class="uicontrol">Produtos</span> &gt; <span class="uicontrol">Perfil do produto</span> &gt; <span class="uicontrol">guia Permissões</span> &gt; <span class="uicontrol">Ferramentas do conjunto de relatórios</span> &gt; <span class="uicontrol">Configuração do Advertising Analytics</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Dimensões e métricas do Advertising Analytics {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

O Advertising Analytics adiciona as seguintes dimensões e métricas à área de trabalho da Análise, aos Relatórios e análises, ao Construtor de relatórios e à API de Relatórios do Analytics.

**Dimensões**

>[!IMPORTANT]
>
>Esta integração cria um novo conjunto de dimensões por meio de classificações da variável da ID do AMO. Essas novas dimensões não afetam nem modificam seus canais de marketing ou dimensões variáveis de rastreamento de campanha existentes. A ID da AMO é conectada a um perfil quando um visitante chega ao site a partir de um anúncio de pesquisa pago. Dessa forma, as dimensões AMO podem ser usadas para analisar tanto as métricas AMO fornecidas por essa integração quanto quaisquer dados capturados a jusante pelo visitante (visitas, visitantes, visualizações de página, taxa de rejeição, pedidos, receita, eventos personalizados etc.). Eles também podem ser divididos por outras dimensões quando forem relatórios em outras métricas no site.
>
>As classificações dessas métricas são atualizadas diariamente. Dessa forma, se você fizer alterações nos metadados em um mecanismo de pesquisa, poderá não ver essas alterações refletirem até o dia seguinte em que as classificações forem atualizadas.

| Nome da Classificação (Dimensão) | Definição |
|--- |--- |
| Tipo de correspondência de palavra-chave (ID AMO) | O tipo de correspondência da palavra-chave. Normalmente, os valores serão amplos, frases, exatos ou nenhum valor se o tipo de anúncio não tiver um tipo de correspondência. |
| Plataforma de publicidade (ID AMO) | O nome do mecanismo de pesquisa. Os valores podem incluir o Google AdWords ou o Microsoft Bing Ads. |
| Conta (ID AMO) | O nome da conta do mecanismo de pesquisa que está sendo rastreada. |
| Campanha (ID AMO) | O nome da campanha na sua conta do mecanismo de pesquisa. |
| Grupo de publicidade (ID AMO) | O nome do grupo de publicidade nas campanhas do mecanismo de pesquisa. |
| Anúncio (ID AMO) | O Título do anúncio + a Descrição do anúncio usados em seu anúncio. |
| Palavra-chave (ID AMO) | O valor de Palavra-chave de sua conta de mecanismo de pesquisa |
| Tipo de correspondência (ID AMO) | O Tipo de correspondência da palavra-chave atribuído à sua palavra-chave. Normalmente, os valores serão amplos, uma frase, exatos ou nenhum valor se o tipo de Anúncio não tiver um tipo de correspondência. |
| Tipo de anúncio (ID AMO) | O tipo de anúncio sendo fornecido, que tipicamente é “Anúncio de texto”. |
| Título do anúncio (ID AMO) | O objeto de Título usado em seu Anúncio. |
| Descrição do anúncio (ID AMO) | O objeto de Descrição do anúncio usado em seu Anúncio. |
| URL de exibição de anúncio (ID AMO) | O objeto de URL de exibição do anúncio usado em seu Anúncio. |
| URL de destino do anúncio (ID AMO) | O URL da página de aterrissagem ou URL final atribuído a seu anúncio. |
| Rede (ID AMO) | A rede na qual o anúncio está sendo veiculado. No Advertising Analytics, esse valor sempre é “Pesquisa“. |
| Posicionamento (ID AMO) | O site de posicionamento gerenciado (para redes de conteúdo). Somente posicionamentos gerenciados usam esta dimensão. |
| Público alvo do produto (ID AMO) | O nome de direcionamento do produto usado em anúncios PLA (não o produto comprado). |
| Otimização (ID AMO) | Isso não é usado pelo Advertising Analytics. É usado somente pelos clientes da Advertising Cloud. |
| Dispositivo (ID AMO) | Não usado no momento. Placeholder para possível futura melhoria de produto feita ao tipo de dispositivo de destino indicado (por exemplo móvel, desktop) do anúncio (não o dispositivo do visitante). |

**Métricas**

>[!IMPORTANT]
>
>As métricas fornecidas pelo Advertising Analytics (listadas abaixo) são dados a nível de resumo dos mecanismos de pesquisa. Eles não estão conectados aos perfis de visitantes do Analytics. Eles estão conectados somente à variável da ID AMO e às dimensões de classificação associadas. Como tal, eles não devem ser reportados por nenhuma dimensão/segmento diferente daqueles baseados nas dimensões da ID AMO. Isso resultará na exibição de zeros no Analytics para os dados. É possível incluí-las em métricas calculadas com outras métricas, mas essa métrica calculada também deve ser dividida somente pelas dimensões da ID AMO.
>
>Essas métricas são dados obtidos diariamente para que não tenham dados do dia atual. Também não devem ser reportados com granularidade inferior à diária.
>
>Há uma métrica de Instâncias de ID AMO definida quando a ID AMO é definida em uma landing page (ou seja, um click-through). Essa métrica é capturada em tempo real com a ocorrência de landing page e está disponível para detalhamentos com outras dimensões também definidas na landing page.

| Nome da métrica | Definição |
|--- |--- |
| Impressões do AMO | O número de impressões de anúncios, conforme reportado pelo mecanismo de pesquisa. |
| Cliques do AMO | O número de cliques em anúncios, conforme relatado pelo mecanismo de pesquisa. |
| Custo do AMO | O custo pago para cada palavra-chave/publicidade, conforme relatado pelo mecanismo de pesquisa. |
| Pos. média | Uma métrica calculada que reflete a posição média das publicidades, conforme relatado pelo mecanismo de pesquisa. |
| Média Pontuação de qualidade do AMO | Uma métrica calculada que reflete a pontuação de qualidade média, conforme relatado pelo mecanismo de pesquisa. |
