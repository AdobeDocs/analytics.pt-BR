---
title: Perguntas frequentes sobre o Activity Map
description: Perguntas frequentes sobre o Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 15%

---

# Perguntas frequentes sobre o Activity Map

Perguntas frequentes sobre o Activity Map.

+++Como conceder permissões ao Activity Map?

As permissões para usar o Activity Map e suas dimensões associadas são tratadas no [Adobe Admin Console](/help/admin/admin-console/home.md).

Os [itens de permissão](/help/admin/admin-console/permissions/product-profile.md) necessários para o Activity Map incluem:

* **[!UICONTROL Ferramentas do Analytics]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL Ferramentas do Analytics]** > **[!UICONTROL Publicação de segmentos]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Alcance de rolagem do Activity Map]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Link Activity Map Por Região]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Região Activity Map]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Link Activity Map]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Página Activity Map]**

Consulte [Permissões de perfil de produto para Ferramentas do Analytics](/help/admin/admin-console/permissions/analytics-tools.md) para obter mais informações.

+++

+++Todos os clientes do Analytics têm acesso ao Activity Map?

Organizações com um contrato do Adobe Analytics Standard, Premium e Ultimate têm acesso ao Activity Map. Esses tipos de contrato representam a maioria dos clientes da Adobe Analytics.

+++

+++Como o Activity Map oferece suporte a Aplicativos de página única (SPA)?

A cada poucos segundos, o Activity Map verifica a página da Web em busca de alterações. O Activity Map encontra novo conteúdo na página sem exigir um recarregamento, mas esse novo conteúdo é sempre atribuído ao primeiro valor de dimensão da página.

* O Activity Map verifica se a visibilidade dos links que ele conhece foi alterada. Se uma alteração na visibilidade for encontrada, a coluna Presente da tabela de Links na página para esse link será atualizada com [!UICONTROL Exibido] ou [!UICONTROL Oculto].

* Quando a interação do usuário cria novo conteúdo, todos os novos elementos que o AppMeasurement determina como um link são adicionados à tabela [!UICONTROL Links na página]. O Activity Map envia uma nova solicitação de dados que inclui esses novos links. Os novos links aparecem na tabela [!UICONTROL Links na Página] quando a solicitação de dados é retornada.

+++

+++O Activity Map fornece dados sobre links que são visualizados, mas não clicados?

Não, o Adobe não rastreia automaticamente os links que só foram exibidos.

+++

+++Quais navegadores e versões são compatíveis com o Activity Map?

O Activity Map é compatível com a versão mais recente da maioria dos navegadores modernos.

+++

+++O Activity Map aumenta as chamadas do servidor?

O Activity Map não envia chamadas de servidor sozinho. Em vez disso, as variáveis de dados de contexto de Activity Map são incluídas com chamadas de exibição de página do Analytics na página subsequente. No entanto, algumas versões anteriores do Activity Map no SDK da Web enviam uma chamada separada para dados Activity Map. Se você estiver na versão mais recente do Web SDK, os dados de Activity Map serão mesclados com o evento a seguir.

+++

+++Por que alguns números de classificação estão ausentes na sobreposição?

Alguns links, como aqueles contidos em menus, estão ocultos na página. Como resultado, as sobreposições do link correspondente não são exibidas. A classificação é calculada para todos os links na página, incluindo links ocultos.

+++

+++Como a classificação de links é determinada no Relatório de todos os links?

* **No modo gradiente e bolha**: a coluna de métrica determina a classificação. Para os links com o mesmo valor métrico, a classificação ainda é baseada na ordem alfabética da ID do link.
* **No modo ganhador e perdedor**: a coluna de porcentagem obtida determina a classificação. Para os links com o mesmo ganho, a classificação ainda é baseada na ordem alfabética da ID do link.

+++

+++Como o Activity Map funciona com páginas que usam vários conjuntos de relatórios?

Por padrão, o Activity Map usa o conjunto de relatórios associado à primeira tag na página. É possível selecionar um conjunto de relatórios diferente por meio da guia **[!UICONTROL Configurações de Activity Map]** > **[!UICONTROL Outros]**.

+++

+++Por quanto tempo o Activity Map verifica o Adobe Analytics na página?

O Activity Map verifica a presença do Adobe Analytics por até 20 segundos após um evento de conclusão de página.

+++

+++Como o Activity Map lida com o conteúdo dinâmico?

O Activity Map verifica se ocorreram alterações no estado da página da Web a cada dois segundos, como:

* Conteúdo HTML que se tornou visível
* Conteúdo HTML que está oculto
* Novo conteúdo HTML que foi inserido

Se o conteúdo estiver oculto ou exibido, a extensão alterará automaticamente o estado dos links afetados (e, portanto, as sobreposições), de oculto para exibido ou vice-versa. Se novo conteúdo for inserido, o aplicativo recuperará os links associados, extrairá os dados de análise e adicionará sobreposições para esses links.

+++

+++Em qual métrica se baseia o Relatório de fluxo de página?

Todos os dados mostrados se baseiam nas exibições de página.

+++

+++Posso exportar dados do Activity Map por meio de feeds de dados?

Sim. As [colunas do feed de dados](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) que o Activity Map usa são:

* Link Activity Map: `clickmaplink`
* Página de Activity Map: `clickmappage`
* Região do Activity Map: `clickmapregion`
* Link Activity Map por região: `clickmaplinkbyregion`

+++

+++Os segmentos funcionam no modo Online?

Não, os segmentos não funcionam no modo Online.

+++

+++O Activity Map é compatível com os conjuntos de relatórios virtuais?

Sim. No entanto, devido às limitações do conjunto de relatórios virtual, o modo Activity Map Live não é compatível com os conjuntos de relatórios virtuais.

+++

+++Como posso desabilitar o Activity Map?

O método para desativar o Activity Map depende do seu tipo de implementação:

* **Extensão do Web SDK**: nas configurações de extensão, desmarque as caixas **[!UICONTROL Coletar cliques internos em links]**, **[!UICONTROL Coletar cliques em links externos]** e **[!UICONTROL Coletar cliques em links de download]**.
* **Biblioteca JavaScript do Web SDK**: Defina [`clickCollectionEnabled`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) como `false`.
* **Extensão do Analytics**: nas configurações de extensão, desmarque a caixa denominada **[!UICONTROL Usar Activity Map]**.
* **AppMeasurement**: remova ou comente o módulo Activity Map em `AppMeasurement.js` ou substitua a chamada de função de módulo por um corpo vazio:

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++Quais são os requisitos do sistema para usar a sobreposição de Activity Map?

Você pode usar a versão mais recente do Chrome, Edge ou Firefox com a extensão Activity Map.

+++

+++O que devo considerar ao usar o Activity Map para informações de identificação pessoal?

Considere os seguintes cenários em que dados de identificação pessoal podem ser coletados usando o Activity Map:

* **Links de email**: se for possível clicar em um endereço de email para abrir o cliente de email do usuário, o Activity Map poderá coletar o endereço de email que foi clicado.
* **Links da ID de usuário**: depois que um visitante faz logon, o Activity Map pode registrar todos os links que contenham a ID de usuário do visitante.
* **Links de informações confidenciais**: para instituições financeiras, informações confidenciais, como número de conta, poderão ser rastreadas se forem um link e os visitantes clicarem neles.
* **Links contendo informações pessoais**: em sites da área de saúde, os links podem conter informações pessoais. Se um visitante clicar nesses links, o Activity Map coletará o texto do link.

+++

+++Que dados o Activity Map rastreia por padrão?

O Activity Map rastreia os seguintes elementos:

* Uma marca `<a>` ou `<area>` com uma propriedade `href`. Os links de marca de âncora (`#`) não são rastreados por padrão.
* Um atributo `onclick` que define uma variável `s_objectID`
* Uma marca `<input>` ou um botão `submit` com um valor ou texto filho
* Uma marca `<input>` com tipo `image` e uma propriedade `src`
* Uma marca `<button>` sem o atributo `type="button"`. Se você deseja rastrear `<button>` tags, considere usar atributos como `role="button"` ou `submit="button"`.

+++

+++Quais são alguns exemplos de links que o Activity Map rastreia automaticamente?

Veja a seguir alguns exemplos em que o Activity Map tem todas as informações necessárias para rastrear um link.

```html
<a href="home.html">Home</a>

<input type="submit" value="Submit"/>

<input type="image" src="submit-button.png"/>

<p onclick="var s_objectID='Market rates';">
  <span class="title">Current Market Rates</span>
  <span class="subtitle">1.45 USD</span>
</p>

<div onclick="s.tl(true,'o','Chat button')">
  <span class="title">Chat with an agent now</span>
  <span class="subtitle">Current wait: 0 minutes</span>
</div>
```

+++

+++Quais são alguns exemplos de links que o Activity Map NÃO rastreia automaticamente?

* A marca de âncora não tem um `href` válido
* Nenhum método [`s_objectID`](/help/implement/vars/page-vars/s-objectid.md) ou [`tl()`](/help/implement/vars/functions/tl-method.md) presente
* A propriedade `src` está ausente em um elemento de entrada de formulário

Veja a seguir alguns exemplos em que o Activity Map não rastreia cliques:

```html
<!-- Anchor tag does not have a valid href -->
<a name="innerAnchor">Section header</a>

<!-- Neither s_objectID or tl() method present -->
<p onclick="showPanel('stock price')">
  <span class="title">Current company stock price</span>
  <span class="subtitle">987.65 USD</span>
</p>

<!-- Neither s_objectID or tl() method present -->
<input type="radio" onclick="changeState(this)" name="group1" value="A"/>
<input type="radio" onclick="changeState(this)" name="group1" value="B"/>
<input type="radio" onclick="changeState(this)" name="group1" value="C"/>

<!-- src property missing on a form input element -->
<input type="image"/>
```

+++
