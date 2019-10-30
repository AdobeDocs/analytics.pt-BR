---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Implementação do Analytics
seo-description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
seo-title: Variáveis de página
solution: Analytics
subtopic: Variáveis
title: Variáveis de página
topic: Desenvolvedor e implementação
uuid: 2578eddd-74db-4a8a-96f2-d0289ec1826b
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Variáveis de página

As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

A variável exibe a altura da janela do navegador.

<!-- 
browserheight.xml
-->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

**Parâmetros**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Parâmetro de consulta </th> 
   <th class="entry"> Valor </th> 
   <th class="entry"> Exemplo </th> 
   <th class="entry"> Relatórios afetados </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>Um inteiro positivo </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Tráfego &gt; Tecnologia &gt; Altura do navegador  </p> </td> 
  </tr> 
 </tbody> 
</table>

## browserWidth {#concept_BA0C4C2D655D41A4AEF059E21E4A55A2}

A variável exibe a largura da janela do navegador.

<!-- 

browserwidth.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

**Parâmetros**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Parâmetro de consulta</b> </p> </td> 
   <td> <p> <b>Valor</b> </p> </td> 
   <td> <p> <b>Exemplo</b> </p> </td> 
   <td> <p> <b>Relatórios afetados</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>Um inteiro positivo </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Tráfego &gt; Tecnologia &gt; Largura do navegador  </p> </td> 
  </tr> 
 </tbody> 
</table>

## campaign {#concept_C7BF7B8A69D048A6AB482052A98A91F8}

A variável identifica campanhas de marketing usadas para trazer visitantes para o site. Normalmente, o valor de é retirado de um parâmetro da string de consulta.

<!-- 

campaign.xml

 -->

**Parâmetros**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 Bytes </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>Conversão &gt; Campanhas &gt; Código de rastreamento </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

Todos os elementos de uma campanha de marketing devem ter um código de rastreamento exclusivo. Por exemplo, uma palavra-chave do mecanismo de pesquisa pago pode ter um código de rastreamento 112233. Quando alguém clicar na palavra-chave com código de rastreamento 112233 e for roteado para o site correspondente, a variável *`campaign`* registrará o código de rastreamento.

Existem duas formas principais de preencher a variável *`campaign`*:

* O plug-in [!UICONTROL getQueryParam], usado no arquivo JavaScript, recupera um parâmetro da string de consulta do URL. Para obter mais informações sobre o plug-in [!UICONTROL getQueryParam], consulte [Plug-ins de implementação](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Atribua um valor à variável *`campaign`* no HTML da página da Web.

Com qualquer método de preenchimento da variável *`campaign`*, o tráfego do botão Voltar pode aumentar o número real de click-throughs de um elemento de campanha.

Por exemplo, um visitante entra em seu site clicando em uma palavra-chave de pesquisa paga. Quando o visitante chega à página inicial, o URL contém um parâmetro da string de consulta identificando o código de rastreamento da palavra-chave. O visitante então clica em um link para outra página, mas imediatamente clica no botão Voltar para retornar à página inicial. Quando o visitante chega à página inicial uma segunda vez, o URL com o parâmetro da string de consulta identifica novamente o código de rastreamento. E um segundo click-through é registrado, aumentando o número de click-throughs de forma falsa.

Para evitar esse aumento de click-throughs, a Adobe recomenda usar o plug-in [!UICONTROL getValOnce] para forçar que cada click-through da campanha seja contado somente uma vez por sessão. Para obter mais informações sobre o plug-in [!UICONTROL getValOnce], consulte [Plug-ins de implementação](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**Sintaxe e valores possíveis** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

A variável *`campaign`* tem as mesmas limitações que todas as outras variáveis.  A Adobe recomenda limitar o valor ao padrão de caracteres ASCII.

**Uso de maiúsculas e minúsculas** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

As eVars não fazem distinção de letras maiúsculas e minúsculas, mas são exibidas com essa diferenciação na primeira ocorrência. Por exemplo, se a primeira instância da eVar1 for definida como "Conectado" mas todas as instâncias subsequentes forem transmitidas como "conectado", os relatórios sempre mostrarão "Conectado" como valor da eVar.

**Exemplos** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**Configurações** {#section_4083F281968443169EAF8C0E8529D7BC}

Cada valor campaign permanece ativo para um usuário e recebe crédito pelas atividades e eventos bem-sucedidos desse usuário, até expirar. É possível alterar a expiração da variável campaign na Admin Console.

**Armadilhas, dúvidas e dicas** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* Para impedir o aumento de click-throughs, use o plug-in [!UICONTROL getValOnce] para que o click-through de uma campanha seja contado somente uma vez por sessão. Para obter mais informações sobre o plug-in [!UICONTROL getValOnce], consulte [Plug-ins de implementação](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Para obter mais informações sobre o rastreamento das campanhas de marketing e compras de palavras-chaves, consulte [Campanhas](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Use o [!DNL DigitalPulse Debugger] para ver o valor real de campaigns (v0 no depurador). Se v0 não for exibido no depurador, nenhum dado de campanha será registrado para essa página.

## marketing {#concept_C7770B8C15724A99B10F8F468AF82D0D}

A variável usada com mais frequência para identificar uma seção do site.

<!-- 

channel.xml

 -->

Por exemplo, um vendedor pode ter seções como Eletrônicos, Brinquedos ou Vestuário. Um site de mídia pode ter seções como Notícias, Esportes ou Negócios.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | CH | Conteúdo do site &gt; Seções do site | "" |

A Adobe recomenda preencher a variável de canal em todas as páginas. Você também pode ativar uma correlação entre as variáveis *`channel`* e [!UICONTROL page name].

Quando as seções têm um ou mais níveis de subseções, é possível exibir essas seções na variável *`channel`* ou usar variáveis separadas para identificar esses níveis.

**Sintaxe e valores possíveis** {#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

A variável *`channel`* não tem limitações extras em seus valores.

**Exemplos** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Armadilhas, dúvidas e dicas** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

Se o site contiver vários níveis, é possível usar *`hierarchy`* ou outra variável para designar esses níveis. O valor *`channel`* não persiste, mas os eventos bem-sucedidos acionados na mesma página são atribuídos ao valor *`channel`*.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

A variável é usada para mostrar o número de bits usados para exibir cor em cada pixel da tela.

<!-- 

colordepth.xml

 -->

Por exemplo, 32 representa 32 bits de cor na tela. Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em `props/eVars`, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo | Relatórios afetados |
|---|---|---|---|
| c | 8,16 e 32 | 32 | Tráfego &gt; Tecnologia &gt; Monitorar intensidade de cor |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

A variável, no Internet Explorer, indica se o navegador está configurado em uma conexão LAN ou moderna.

<!-- 

conntype.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em `props/eVars`, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo | Relatórios afetados |
|---|---|---|---|
| ct | lan ou moderna | lan | Tráfego &gt; Tecnologia &gt; Tipo de conexão |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

A variável indica se um cookie de sessão primária pode ser definido por JavaScript.

<!-- 

cookiesenabled.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em `props/eVars`, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo |
|---|---|---|
| k | Y ou N | S |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

(Desaprovado) A variável permite selecionar o centro de dados para o qual seus dados são enviados.

<!-- 

dc.xml

 -->

> [!NOTE] A variável dc está obsoleta. Você deve definir *`trackingServer`* para todas as implementações com o valor gerado pelo [!UICONTROL Gerenciador de Códigos] no s_code.js.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | 112 |

O centro de dados é identificado na variável *`dc`* para corresponder a [!UICONTROL ActionSource].

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

As variáveis [!UICONTROL eVar] são usadas para criar relatórios personalizados.

<!-- 

eVarN.xml

 -->

Quando uma eVar é definida com um valor para um visitante, o valor é lembrado até ser expirado. Todos os eventos bem-sucedidos que um visitante encontra enquanto o valor eVar está ativo são contabilizados para o valor eVar.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 255 Bytes | V1-v75 ( [ou v100 ou v250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) | Conversão personalizada | "" |

**Expiração** {#section_6DB5882B960D4660AE248B91B76883C4}

As [!UICONTROL eVars] expiram depois de um período definido por você. Depois que a eVar expira, ela não recebe mais crédito por eventos bem-sucedidos. As eVars também podem ser configuradas para expirar em eventos bem-sucedidos. Por exemplo, se você tiver uma promoção interna que expira no fim de uma visita, a promoção interna recebe crédito apenas pelas compras ou registros ocorridos durante a visita em que foi ativada.

Existem duas formas de determinar a expiração de uma eVar:

* É possível definir a eVar para expirar depois de um período ou evento especificado.
* É possível forçar a expiração de uma eVar, o que é útil quando se estabelece um novo objetivo para uma variável.

Se uma eVar for usada em maio para refletir promoções internas e expirar depois de 21 dias, e em junho ela for usada para capturar as palavras-chaves da pesquisa interna, no dia 1º de junho você deverá forçar a expiração da variável ou redefini-la. Com isso, você ajudará a manter os valores da promoção interna fora dos relatórios de junho.

**Uso de maiúsculas e minúsculas** {#section_6E9145B7FCC2438E95BB35AAE3857412}

As eVars não fazem distinção de letras maiúsculas e minúsculas, mas são exibidas com essa diferenciação na primeira ocorrência. Por exemplo, se a primeira instância da eVar1 for definida como "Conectado" mas todas as instâncias subsequentes forem transmitidas como "conectado", os relatórios sempre mostrarão "Conectado" como valor da eVar.

**Contadores** {#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

Embora as eVars sejam usadas com mais frequência para reter valores da string, elas também podem ser configuradas para atuar como contadores. As eVars são úteis como contadores quando você está tentando contar o número de ações adotadas por um usuário antes de um evento. Por exemplo, você pode usar uma eVar para capturar o número de pesquisas internas antes da compra. Sempre que um visitante pesquisar, a eVar deverá conter um valor de "+1". Se um visitante pesquisar quatro vezes antes de uma compra, você verá uma instância para cada contagem total: 1,00, 2,00, 3,00 e 4,00. No entanto, somente a 4,00 receberá crédito pelo evento da compra (Pedidos e métricas de receita).  Somente números positivos são permitidos como valores de um contador eVar.

**Sub-relações** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

Um requisito comum de um relatório [!UICONTROL eVar personalizado] é a capacidade de desmembrar um relatório [!UICONTROL eVar personalizado ]em outro. Por exemplo, se uma eVar contiver gênero e outra contiver salário, você poderá fazer a seguinte pergunta: entre as visitantes do sexo feminino de meu site, quanta receita foi gerada por mulheres que ganham mais de US$ 50,000 por ano. Todas as eVar que forem totalmente sub-relacionadas permitem esse tipo de desmembramento nos relatórios. Por exemplo, se a eVar gênero tiver sub-relações totais ativadas, todos os outros relatórios eVar personalizados poderão ser desmembrados por gênero e o gênero poderá ser desmembrado por todos os outros. Para ver a relação entre dois relatórios, somente um deles precisa ter as sub-relações totais ativadas. Por padrão, os relatórios [!UICONTROL Campanhas], [!UICONTROL Produtos ]e [!UICONTROL Categoria] são totalmente sub-relacionados (todas as eVar podem ser desmembradas por campanhas ou produtos).

**Sintaxe e valores possíveis** {#section_BD46438B14F3488FB9AC42994C317B06}

Embora seja possível renomear a eVars, ela deve ser sempre mencionada no arquivo JavaScript pela eVarX, onde X é um número entre 1 e 75 ([ou 100 ou 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

```js
s.eVarX="value"
```

Quando não forem usadas como um contador, as eVars terão as mesmas limitações que todas as demais variáveis. Se a eVar for um "contador", espera-se que ela receba valores numéricos, como "1" ou "2,5". Se mais que duas casas decimais forem fornecidas, o contador da eVar é arredondado por duas casas decimais. Um contador eVar não pode conter números negativos.

**Exemplos** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Configurações** {#section_BD1FE63001C84D3DB69F3DEE243960B6}

As eVars podem ser configuradas em [!UICONTROL Analytics &gt; Admin &gt; Conjuntos de relatórios &gt; Editar configurações &gt; Conversão &gt; Variáveis de conversão]. Todas as eVars podem ser configuradas com [!UICONTROL Nome], [!UICONTROL Tipo], [!UICONTROL Alocação],[!UICONTROL  Expirar após] ou [!UICONTROL Redefinir]. Cada configuração é tratada separadamente.

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Configuração </th> 
   <th class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nome </td> 
   <td> Permite alterar o nome do relatório eVar no <span class="keyword">Analytics </span>. <p>A eVar ainda deve ser mencionada como s.eVarX no código JavaScript, independentemente do nome fornecido ao relatório no <span class="keyword">Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Tipo </td> 
   <td> Permite mostrar se a eVar é uma string de texto ou um contador. </td> 
  </tr> 
  <tr> 
   <td> Alocação </td> 
   <td> Usada para configurar qual valor da eVar recebe crédito pelos eventos bem-sucedidos. <p>Se Alocação for definida como "Mais recente (último)", B receberá o crédito. </p> <p>Se Alocação for definida como "Valor original (primeiro)", A receberá o crédito. </p> <p>Se Alocação for definida como "Linear", A e B recebem o crédito por metade do valor de compra. </p> </td> 
  </tr> 
  <tr> 
   <td> Expirar após </td> 
   <td> Permite determinar se uma eVar expira em um evento específico, como compra, ou depois de um período predefinido. </td> 
  </tr> 
  <tr> 
   <td> Redefinir </td> 
   <td> Se você marcar a caixa de seleção <span class="wintitle">Redefinir</span> para uma eVar e clicar em <span class="wintitle">Salvar</span> na parte inferior da página, todos os valores dessa eVar serão expirados imediatamente. Depois disso, somente novos valores da eVar receberão crédito por eventos bem-sucedidos. </td> 
  </tr> 
 </tbody> 
</table>

**Armadilhas, dúvidas e dicas** {#section_DA6912C802E445F986C6DE4234C6C737}

* Diferente das variáveis [!UICONTROL prop], as variáveis eVar não têm permissão para serem listas de valores delimitados. Se você preencher uma eVar com uma lista de valores, por exemplo, "um,dois,três", a string exata será exibida nos relatórios.
* Os contadores eVar não podem conter números negativos.

## Eventos {#concept_FFD115543D54401B98FE683BD7D5B3FE}

A variável é usada para registrar eventos bem-sucedidos do carrinho de compras, bem como eventos bem-sucedidos personalizados.

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Sem limite </td> 
   <td> events </td> 
   <td> <p>Eventos do carrinho de compras </p> <p>Eventos Personalizados </p> </td> 
   <td> N/A </td> 
  </tr> 
 </tbody> 
</table>

Um [!UICONTROL evento] deve ser considerado um marco em um site. Eventos bem-sucedidos são preenchidos mais frequentemente na página de confirmação final de um processo, como processo de registro ou assinatura de boletins informativos. Os eventos personalizados são definidos com o preenchimento da variável events com valores literais definidos na seção Valores possíveis abaixo.

Por padrão, os eventos bem-sucedidos são configurados como eventos *contadores*. Eventos contadores contam o número de vezes que um evento bem-sucedido foi definido (x + 1). Os eventos também podem ser configurados como *numéricos*. Os eventos numéricos permitem especificar o número de incremento (como pode ser necessário na contagem de valores dinâmicos ou arbitrários, como o número de resultados retornados por uma pesquisa interna).

Um tipo de evento final, *moeda*, permite definir o valor a ser adicionado (semelhante a eventos numéricos), mas é exibido como moeda em relatórios e está sujeito a conversões de moeda com base no valor s. *`currencyCode`* e na configuração padrão de moeda do seu conjunto de relatórios. Para obter informações adicionais sobre o uso de eventos numéricos e de moedas, consulte [Produtos](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**Configuração da variável** {#section_9195286C34C54B02B2598E2B856492C3}

A variável [!UICONTROL s.events] é ativada por padrão para todas as implementações. Os sete eventos de conversão pré-configurados são ativados automaticamente para todos os novos conjuntos de relatórios. Qualquer usuário com nível administrativo pode ativar novos eventos personalizados (event1- [event100 ou event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) usando o Admin Console.

**Valores possíveis** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

A seguir está uma lista de valores possíveis para a variável events:

| Evento | Descrição | Relatórios preenchidos |
|---|---|---|
| prodView | Exibições do produto | Produtos |
| scOpen | Abrir/inicializar um novo carrinho de compras | Carrinhos |
| scAdd | Adicionar itens ao carrinho | Adições ao carrinho |
| scRemove | Remover itens do carrinho | Remoções do carrinho |
| scView | Exibir carrinho de compras | Exibições do carrinho |
| scCheckout | Iniciando o processo de checkout | Finalizações |
| purchase | Conclusão de uma compra (pedido) | Pedidos |
| event1 - event1000 (event100 para um produto pontual) | Eventos personalizados | Eventos Personalizados |

**Sintaxe e exemplos** {#section_45A159DF00114066B8551DDEB15E084C}

Os eventos contadores são definidos com a inserção dos eventos desejados na variável [!UICONTROL s.events], em uma lista separada por vírgulas (se vários eventos forem transmitidos).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

Se houver um código H23 ou posterior, os eventos contadores poderão ter inteiros maiores que um atribuídos a eles.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

A implementação de eventos contadores com valores inteiros atribuídos trata os eventos como se eles tivessem sido acionados várias vezes dentro da solicitação de imagem. Os eventos contadores não permitem decimais. É recomendável usar eventos numéricos, caso essa funcionalidade seja necessária.
É necessário incluir os eventos numéricos e de moeda na variável [!UICONTROL s.events], embora eles geralmente recebam seu valor numérico (p. ex. 24,99) na variável [!UICONTROL s.products]. Isso permite especificar valores numéricos e de moeda às entradas individuais de produtos.

**Serialização de eventos** {#section_A89488EF4471405AAFC4D6DD05E77621}

Por padrão, um evento é contado sempre que é definido no seu site.

Consulte [Serialização de eventos](../../../implement/js-implementation/event-serialization.md#concept_092B638D7FEE423D91F8A57EA8E09705) para obter mais informações.

**Sintaxe** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**Exemplos** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```

## hierN {#concept_C4475D1584D544ACB4C0A573EB60FA08}

A [!UICONTROL variável de hierarquia] determina a localização de uma página da hierarquia do site.

<!-- 

hierN.xml

 -->

Essa variável é útil para sites com mais de três níveis na estrutura do site. Por exemplo, um site jornalístico pode ter quatro níveis na seção de Esporte: Esportes, Esportes locais, Beisebol e Red Sox. Se alguém visitar a página Beisebol, as páginas Esportes, Esportes locais e Beisebol refletirão essa visita.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 255 Bytes | H1-H5 | Hierarquia | "" |

Há cinco variáveis de [!UICONTROL hierarquia] disponíveis, que devem ser ativadas pelo Atendimento ao cliente da Adobe. Quando a hierarquia é ativada, você deve escolher um delimitador para a variável e o número máximo de níveis para a hierarquia. Por exemplo, se o delimitador for uma vírgula, a hierarquia de esportes pode ser exibida como o seguinte.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Verifique se nenhum dos nomes da sua seção inclui o delimitador. Por exemplo, se uma de suas seções for chamada "Técnico Griffin, Jim", você deverá escolher um delimitador diferente de vírgula. Cada seção da hierarquia é limitada a 255 bytes, com limite total de variável de 255 bytes. Depois que um delimitador é escolhido (no momento da criação da hierarquia), ele não é alterado facilmente.

Contate o Atendimento ao cliente da Adobe para obter instruções sobre a alteração do delimitador de uma hierarquia existente. Os delimitadores também pode consistir em vários caracteres, como || ou /|\, que têm uma probabilidade menor de aparecer na seção de hierarquia.

**Sintaxe e valores possíveis** {#section_0739948A68A2420DAB1CBEA3115A5A66}

Não coloque espaço entre cada delimitador. No exemplo de sintaxe a seguir, N é um número entre um e cinco.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Não use o delimitador, exceto para delimitar os níveis da hierarquia. O delimitador pode ser qualquer caractere ou caracteres de sua escolha.

**Exemplos** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Configurações** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* O delimitador não pode ser alterado depois que a hierarquia é configurada. Se for necessário alterar o delimitador da sua hierarquia, entre em contato com o Atendimento ao cliente da Adobe.
* Não é possível alterar o número de níveis depois que a hierarquia é configurada.

> [!NOTE] As alterações nas hierarquias pode resultar em encargos de serviço.

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

A variável no Internet Explorer indica se a página atual foi definida como página inicial do usuário.

<!-- 

homepage.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo | Relatórios afetados |
|---|---|---|---|
| hp | Y ou N | S | Tráfego &gt; Tecnologia &gt; Página inicial |

## javaEnabled {#concept_F24A3536F1F0453DA214B16BAA5A6F67}

A variável indica se Java estava ativado no navegador.

<!-- 

javaEnabled.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de doPlugins.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo | Relatórios afetados |
|---|---|---|---|
| v | Y ou N | S | Tráfego &gt; Tecnologia &gt; Java |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

A variável indica a versão do JavaScript suportada pelo navegador.

<!-- 

javascriptVersion.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo | Relatórios afetados |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Tráfego &gt; Tecnologia &gt; Versão do JavaScript |

A Versão H.10 e superior do arquivo JavaScript detecta precisamente o arquivo até a versão 1.7 (a versão mais recente quando a H.10 foi lançada). Versões anteriores do arquivo JavaScript só detectavam até a versão 1.3

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

A variável é uma variável opcional usada no [!UICONTROL Rastreamento de link] que determina o nome de um link personalizado, de download ou de saída.

<!-- 

linkName.xml

 -->

A variável *`linkName`* normalmente não é necessária porque o terceiro parâmetro na função *`tl()`* a substitui.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 bytes </td> 
   <td> pev2 </td> 
   <td> <p>Downloads de Arquivos </p> <p>Links personalizados </p> <p>Links de saída  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Os links personalizados] se referem a links que enviam dados de rastreamento. The *`linkName`* variable (or the third parameter in the *`tl()`* function) is used to identify the value that appears in the [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report. Se *`linkName`* não estiver preenchida, o URL do link aparecerá no relatório.

**Sintaxe e valores possíveis** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

Não há limitações nas variáveis *`linkName`* além das limitações padrão de variáveis.

**Exemplos** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Configurações** {#section_F15FF429FC274F708D50DF79D4668EA3}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_170A78452A7340B5B229713AC1FB71FA}

* A variável *`linkName`* é substituída pelo terceiro parâmetro na função *`tl()`*.

* Se a variável *`linkName`* e o terceiro parâmetro na função *`tl()`* estiverem em branco, o URL completo do link (com exceção da sequência de consulta) aparecerá no relatório (mesmo se o link for relativo).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

A variável é uma variável opcional usada no rastreamento de link que determina em qual relatório um Nome de link ou URL aparece (links personalizados, de download ou de saída).

<!-- 

linkType.xml

 -->

A variável *`linkType`* normalmente não é necessária porque o segundo parâmetro na função *`tl()`* a substitui.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Um caractere </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>Downloads de Arquivos </p> <p>Links personalizados </p> <p>Links de saída  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Os links personalizados enviam dados ao Analytics. A variável *`linkType`* (ou o segundo parâmetro na função *`tl()`*) é usada para identificar o relatório em que o nome do link ou o URL aparece (relatório de Link [!UICONTROL Personalizado], de [!UICONTROL Download] ou [!UICONTROL Saída]).

Para links de saída e de download, a variável *`linkType`* é preenchida automaticamente, dependendo se o link clicado é um link de saída ou de download. É possível configurar um link personalizado para enviar dados a qualquer um dos três relatórios com essa variável ou com o segundo parâmetro na função *`tl()`*. Ao configurar *`linkType`* para 'o', 'e' ou 'd', o URL *`linkName`* ou link é enviado para o relatório [!UICONTROL Links personalizados], [!UICONTROL Links de saída] ou [!UICONTROL Downloads de arquivo], respectivamente.

**Sintaxe e valores possíveis** {#section_18DB3A8083FB4F75B970055ED336DA4E}

A sintaxe da variável *`linkType`* depende se você usa XML ou uma sequência de consulta.

Se estiver usando XML, a variável somente poderá conter um único caractere, ou seja, “o”, “e” ou “d”.

```js
s.tl(this,'o','Link Name');
```

Se estiver usando a sequência de consulta `pe`, será necessário usar `lnk_d`, `lnk_e` ou `lnk_o`.

**Exemplos** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**Configurações** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* Se *`linkType`* não for especificado, serão assumidos os links personalizados ('o').

## Propriedades de lista {#concept_83ED74232225431F83A796E22FFC75B4}

As list props são uma lista de valores delimitados que são passados para uma variável e, em seguida, reportados como itens individuais. A list prop é implementada normalmente em páginas que contenham valores selecionáveis pelo usuário, como itens listados com caixas de seleção ou botões de opção. Elas são úteis em qualquer circunstância em que você deseje definir vários valores em uma variável sem enviar várias solicitações de imagem.

<!-- 

list_props.xml

 -->

**Considerações**

* Propriedades de lista são habilitados somente em variáveis de tráfego ( [props](../../../implement/js-implementation/c-variables/page-variables.md#concept_0F10FA2DE69B4029A31EA5E9313AA254)).
* Não é possível ativar definição de caminho e correlações para as props de lista.
* O Analytics oferece visitas e visitantes exclusivos em quase todos os relatórios, incluindo todos os relatórios de prop de lista.
* Classificações são suportadas para propriedades de lista.
* Qualquer variável de tráfego personalizado pode se tornar um pro de lista. (Exceções: [pageName](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328), [canal](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D) e [servidor](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2).)

* Na definição de valores duplicados na mesma solicitação de imagem, não ocorre cancelamento de duplicatas nas instâncias.

Um prop pode ser alterado na lista de propriedades, em Ferramentas administrativas &gt; Report Suite &gt; página Variáveis de tráfego, habilitando o Suporte à lista e selecionando o delimitador. Os delimitadores populares são dois pontos, ponto e vírgula, vírgulas ou barra vertical. Tecnicamente, pode ser qualquer um dos primeiros 127 caracteres ASCII.

**Exemplos de implementação** {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

Ao solicitar a habilitação de propriedades de lista, indique o delimitador que deseja usar. Depois que o *`s.prop`* de sua escolha estiver habilitado, vários valores podem ser definidos na variável, como é mostrado nos exemplos a seguir:

Um list prop delimitado por uma barra vertical, passando em dois valores:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

Um list prop delimitado por uma vírgula, passando em vários valores:

```js
s.prop2="cerulean,vermilion,saffron"
```

Propriedades de lista também podem ser enviados com um único valor:

```js
s.prop3="Single value"
```

O delimitador pode ser alterado a qualquer momento. Contudo, a implementação deve corresponder ao novo delimitador. A falha ao utilizar o delimitador correto resulta que o valor do list prop é tratado como um item de linha único concatenado no relatório.

Como a prop de lista ainda é uma variável de tráfego, está sujeita às limitações das Variáveis de tráfego. As props de lista estão limitadas a 100 bytes de dados e são afetadas pelas configurações de diferenciação de maiúsculas e minúsculas.

## Variável de lista {#concept_AC42F2D69B674C02A484137CE5B4E687}

Também conhecidas como List Var. Semelhante a como Propriedades de lista funcionam, a List Vars permitem vários valores na mesma solicitação de imagem. Também atuam de forma semelhante a eVars, que persistem além da solicitação de imagem na qual foram definidas. É possível usar essas variáveis para ver a causa e o efeito entre vários elementos em uma única página, como listas de produtos, listas de desejos, listas de refinamentos de pesquisa ou listas de anúncios de exibição.

<!-- 

listN.xml

 -->

**Considerações**

* List Vars lembram dos valores específicos fazendo referência ao cookie VisitorID no navegador do visitante.
* Um limite máximo de 250 valores é armazenado de uma vez por visitante. Se a quantidade de 250 valores por visitante for excedida, os 250 valores mais recentes serão usados. A expiração desses valores tem por base a expiração configurada da variável.
* Cada valor delimitado pode conter um máximo de 255 caracteres (ou menos se estiver usando caracteres multibyte). Esse é o comprimento máximo para cada elemento.
* Não há limite para o número de caracteres nesta variável. A única exceção a essa limitação está nos navegadores Internet Explorer mais antigos, que impõem uma limitação de 2.083 caracteres a todas as solicitações de URL.
* Um total de três List Vars estão disponíveis por conjunto de relatórios.
* Utilizar List Vars exige código H23 ou superior.
* É possível classificar Vars de lista.
* Se valores duplicados forem definidos na mesma solicitação de página, as vars de lista cancelam a duplicata de todas as instâncias e seus valores.
* As vars de lista mais granulares podem ser segmentadas no nível da ocorrência (ou exibição da página). Se você tiver uma list var com três valores na mesma solicitação de imagem, quaisquer regras de segmento que correspondam a um valor inserirão os três no relatório. Por outro lado, se uma regra de exclusão for definida e corresponder a um único valor, todos os três valores serão excluídos.

**Configuração** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

É possível acessar a configuração no Admin Console e atualizá-la sem precisar envolver o Atendimento ao cliente da Adobe:

1. Vá para **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Conjuntos de relatórios]**
1. Selecione o conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Conversão]** &gt; **[!UICONTROL Listar variáveis]**.

* **Nome**: cada valor delimitado pode conter um máximo de 255 caracteres (ou menos se estiver usando caracteres multibyte). Esse é o comprimento máximo para cada elemento.
* **Delimitador de valor**: O caractere usado para separar valores na List Var. Com maior frequência, são caracteres como vírgulas, dois pontos, barras verticais, ou algo parecido.

   >[!NOTE]
   >
   >Caracteres multibyte não são suportados como delimitadores em Vars de lista. O delimitador deve ser de byte único.

* **Expiração**: Parecida com a expiração de eVar, determina a quantidade de tempo que pode ocorrer entre a List Var e o evento de conversão para que sejam relacionados.

   * **Em uma exibição de página ou nível de visita**: Eventos bem-sucedidos além de exibição de página ou visita não vinculariam a qualquer valor na List Var.
   * **Com base no período, como dia, semana, mês, etc.**: Eventos bem-sucedidos além do período especificado não vinculariam a qualquer valor na List Var. Um número personalizado de dias também pode ser definido aqui.
   * **Eventos de conversão específicos**: Quaisquer outros eventos de bem-sucedidos acionados depois do evento específico designado não vinculariam a qualquer valor na List Var.
   * **Nunca**: Qualquer período pode ser passar entre a List Var e o evento bem-sucedido.

* **Alocação**: Essa configuração determina como os eventos de sucesso dividem crédito entre os valores:

   * **Total**: todos os valores de variável anteriores à expiração da variável obtêm crédito total por eventos bem-sucedidos.
   * **Linear**: todos os valores de variável anteriores à expiração da variável obtêm crédito dividido para eventos bem-sucedidos.
   * Os valores da variável nunca são sobrescritos, mas sim adicionados aos valores que obtêm crédito para eventos bem-sucedidos.

* **Valores máx.**: designa o número de valores ativos permitidos para essa variável de lista. Por exemplo, se for definido como 3, somente os últimos 3 valores capturados são salvos e qualquer valor anterior capturado é descartado. Observe que se diversos valores da mesma var de lista são enviados na mesma ocorrência que você restringiu o uso de valores de máximo, cada valor terá o mesmo carimbo de data e hora e não há garantia de qual valor é salvo.

   Um limite máximo de 250 valores é armazenado de uma vez por visitante. Se a quantidade de 250 valores por visitante for excedida, os 250 valores mais recentes serão usados. A expiração desses valores tem por base a expiração configurada da variável.

   A configuração Valores máx. é útil para limitar a atribuição para um número específico de valores. Por exemplo, se uma var de lista está definida como "A,B,C" na primeira página de uma visita, em seguida, definida como "X,Y,Z" na próxima página, a atribuição é distribuída para esses seis valores com base na alocação. Se você deseja limitar a atribuição somente a "X,Y,Z", você pode definir os valores máximos como três.

Para configurar ou editar Vars de lista, acesse **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Conjuntos de relatórios]** &gt; **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Conversão]** &gt; **[!UICONTROL Variáveis de lista]**.

**Exemplos de implementação** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

Cada um dos exemplos a seguir usam uma vírgula como delimitador de valor.

**Definição de um valor único na List Var:**

```js
s.list1="Cat";
```

**Transmissão de valores múltiplos:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Atribuição de uma receita à List Var:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

Este resultado mostraria três itens de linha com R$ 50 de receita em cada. (Banner publicitário superior; Anúncio na barra lateral e Campanha interna 1.) Observe que o total deste relatório remove a duplicação da receita, de forma que o total também reflete R$ 50.

**Atribuição de receita a uma List Var que tenha sido definida várias vezes durante uma visita:**

**Alocação**: Total

**Expiração**: Visita

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Página 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (não definido) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Resultado**: Todos os valores definidos na list var 1 em qualquer momento durante a visita (valor1, valor2, valor3, valor4, valor5, valor6) obtêm crédito total para a compra.

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

A variável s.maxDelay é usada principalmente nas integrações do Genesis DFA para determinar o período de tempo limite no contato com o host de DFA. Se a Adobe não receber uma resposta dos servidores DFA dentro do período especificado definido na variável, a conexão será interrompida e os dados serão processados normalmente. Implemente esta variável se você estiver preocupado com o tempo de resposta de DFA em cada página. É recomendável experimentar este valor para determinar o período ideal do tempo limite.

<!-- 

maxDelay.xml

 -->

**Exemplo de implementação**

```
s.maxDelay="750";
```

**Propriedades**

* Esta variável é uma métrica de evento opcional preenchida pelo JavaScript implementado em seu site.
* Se o host DFA não responder no tempo determinado, o evento designado como Tempo limite será executado (atribuído pelo assistente de integração do Genesis).
* Essa variável só pode conter valor numérico.
* O tempo especificado é medido em milissegundos.
* O aumento do tempo de espera coleta mais dados de DFA, mas também aumenta o risco de perder dados de ocorrência do Analytics.

   A perda dos dados de hit do Analytics acontece quando o usuário sai da página durante o período de *`s.maxDelay`*.

* A redução do tempo de espera reduzirá o risco de perda de dados de ocorrência do Analytics, mas pode reduzir a quantidade de dados de DFA enviados com os dados de ocorrência.

   A perda de dados de integração do DFA ocorreria quando o período *`s.maxDelay`* não acomodasse tempo suficiente para o host do DFA responder.

> [!NOTE] A Adobe não tem controle sobre o tempo de resposta do DFA. Se você estiver observando problemas consistentes depois de elevar o período máximo de atraso a um prazo razoável, consulte o administrador da conta do DFA de sua organização.

## mediaLength {#concept_F52B1670122C4461824223E525307060}

A variável especifica o tamanho total da mídia reproduzida.

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Não existe tamanho máximo para a solicitação de pev3 inteira. O tamanho é limitado ao limite de comprimento do URL do navegador. </td> 
   <td> pev3 </td> 
   <td> Tempo gasto com o vídeo; <p>Segmentos de vídeo visualizados </p> </td> 
   <td> Nenhum </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxe e valores possíveis** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**Método autoTrack:**

Se você estiver usando o [!UICONTROL s.Media.autoTrack], a variável [!UICONTROL mediaLength] não precisará ser implementada explicitamente. Ela é determinada automaticamente pelo código do AppMeasurement para JavaScript.

**Método de rastreamento manual**

Sintaxe:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valores possíveis:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Exemplos** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Armadilhas, dúvidas e dicas** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* Você só deve chamar os métodos de rastreamento de mídia se não for possível rastrear o player usando [!UICONTROL s.Media.autoTrack] = true.
* Se você não estiver acompanhando com o [!UICONTROL autoTrack], assegure-se de definir o comprimento em segundos.

## mediaName {#concept_A4CB1782DE244C23BA6CBB5E806DDE6A}

Essa variável especifica o nome do vídeo ou item de mídia.

<!-- 

mediaName.xml

 -->

Ela só está disponível pela [!UICONTROL API de inserção de dados] e [!UICONTROL fonte de dados de processamento completo].

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 64 KB | pev3 | Vídeos; Próximo fluxo de vídeo; Fluxo de vídeo anterior, Segmentos de vídeo exibidos, Tempo usado no vídeo | Nenhum |

**Sintaxe e valores possíveis** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**Método autoTrack:**

Se você estiver usando o [!UICONTROL s.Media.autoTrack], a variável *`mediaName`não precisará ser implementada explicitamente.* Ela é determinada automaticamente pelo código do AppMeasurement para JavaScript.

**Método de rastreamento manual**

Sintaxe:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

Valores possíveis:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Exemplos** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Armadilhas, dúvidas e dicas** {#section_941A445BB52E4063B0F6920E61BB90DE}

* Você só deve chamar os métodos de rastreamento de mídia se não for possível rastrear o player usando [!UICONTROL s.Media.autoTrack] = true.
* A variável é armazenada como uma variável mySQL TEXT em vez de VARCHAR(100).

## mediaPlayer {#concept_1932756C093B4B2FBA0484E5A58EF927}

Essa variável especifica o player usado para consumir um item de mídia ou vídeo.

<!-- 

mediaPlayer.xml

 -->

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | pev3 | Reprodutores de vídeo | Nenhum |

**Sintaxe e valores possíveis** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**Método autoTrack:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Método de rastreamento manual**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valores possíveis:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Exemplos** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Armadilhas, dúvidas e dicas** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

Você só deve chamar os métodos de rastreamento de mídia se não for possível rastrear o player usando s.Media.autoTrack = true.

## mediaSession {#concept_19E6C850C3244CB6973140709BDCB0B9}

Esta variável especifica os segmentos de um vídeo ou ativo de mídia consumido.

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 Bytes </td> 
   <td> pev3 </td> 
   <td> Tempo gasto com o vídeo <p>Segmentos de vídeo visualizados </p> </td> 
   <td> Nenhum </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxe e valores possíveis** {#section_9A63266633C4427CB4A6549E4D887B85}

**Método autoTrack:**

If using [!UICONTROL s.Media.autoTrack], the *`mediaName`* does not need to be implemented explicitly. Ela será determinada automaticamente pelo código do AppMeasurement para JavaScript.

**Método de rastreamento manual**

Sintaxe:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Valores possíveis:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Exemplos** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Armadilhas, dúvidas e dicas** {#section_1BCEB037AB724B6EBE87420BD3604B88}

Você só deve chamar os métodos de rastreamento de mídia se não for possível rastrear o player usando [!UICONTROL s.Media.autoTrack] = true.

## Media.trackEvents {#concept_B1C5FF6C437949EBA5D52040AC6BB6D9}

A variável identifica quais eventos devem ser enviados com uma ocorrência de mídia.

<!-- 

media_trackEvents.xml

 -->

Ela só é aplicável com JavaScript e [!UICONTROL ActionSource].

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | s.Media.trackEvents="None" |

**Sintaxe e valores possíveis** {#section_66A978EF56914BEAAE73359A268A1B4A}

Nomes de eventos como event1 ou purchase.

**Exemplos** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**Armadilhas, dúvidas e dicas** {#section_030B11C64EE84D46A85CA550DB732D28}

Não deixe de preencher [!UICONTROL trackVars] com "events" sempre que essa variável for preenchida.

## Media.trackVars {#concept_4350CA9A892148AE93C8133AB3B4BEA4}

A variável identifica quais variáveis devem ser enviadas com uma ocorrência de mídia.

<!-- 

media_trackVars.xml

 -->

Ela só é aplicável com JavaScript e [!UICONTROL ActionSource].

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | s.Media.trackVars="None" |

**Sintaxe e valores possíveis** {#section_7374684A7EB34AE685E8C40A66CFD289}

Nomes de variáveis, como [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`* e assim por diante.

**Exemplos** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**Armadilhas, dúvidas e dicas** {#section_615AE1B696124B00B78F651B03813EAB}

* Mesmo se eVar3 for especificada no [!UICONTROL trackVars], ela será enviada com a ocorrência de mídia.

## dispositivo móvel {#concept_0CEE045F57B444138C0EAA015FC7EA70}

A variável controla a ordem em que os cookies e as IDs do assinante são usados para identificar visitantes.

<!-- 

mobile.xml

 -->

Consulte [Protocolos de rede móvel](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | /5/ ou /1/ no caminho do url da imagem | N/A | Nenhum |

**Sintaxe e valores possíveis** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Armadilhas, dúvidas e dicas** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Use a identificação entre visitantes para atenuar possíveis picos no tráfego de visitantes, ao usar a variável *`s.mobile`* com a implementação do cookie JavaScript.

## pageName {#concept_5827B499DAC34B5D8445F9D9140CC328}

A variável contém o nome de cada página de seu site.

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 bytes </td> 
   <td> pageName </td> 
   <td> <p>Páginas </p> <p>Caminhos </p> </td> 
   <td> URL da página </td> 
  </tr> 
 </tbody> 
</table>

A variável *`pageName`* deve ser preenchida com um valor que os usuários da empresa reconheçam. Na maioria dos casos, o valor *`pageName`* não é o URL ou o caminho para o arquivo. Os valores comuns *`pageName`* incluem nomes como "Página inicial", "Check-out", "Compra Obrigado" ou "Registro".

Tenha cuidado para não permitir que caracteres de nova linha, travessões com -em ou -en ou qualquer caractere HTML sejam exibidos no nome da página e outras variáveis. Alguns navegadores enviam caracteres de linha nova, outros não, o que faz com que os dados no Analytics sejam divididos entre dois nomes de página aparentemente idênticos. Muitos processadores de texto e clientes de email convertem automaticamente um hífen em um travessão -en ou -em durante a digitação. Como os travessões -en e -em são caracteres inválidos nas variáveis do Analytics (caracteres ASCII com códigos acima de 127), o Analytics não registrará o nome de página contendo o caractere inválido e mostrará a URL em vez disso.

Se *`pageName`* for deixado em branco, o URL será usado para representar o nome da página. Deixar *`pageName`* em branco geralmente é problemático porque o URL nem sempre pode ser o mesmo para uma página `www.mysite.com` e `mysite.com` são a mesma página com URLs diferentes).

**Sintaxe e valores possíveis** {#section_7A61EE70F1A84D26B414404998C84BA8}

A variável *`pageName`* deve conter um identificador útil para os usuários corporativos do Analytics.

```js
s.pageName="page_name"
```

Não há limitações nas variáveis *`pageName`* além das limitações padrão de variáveis.

**Exemplos** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**Configurações** {#section_58CBC68C805344A999EB47455FEBA8D5}

Os administradores têm a capacidade de alterar o nome de página visível no Analytics com a ferramenta [!UICONTROL Nomear páginas], que é potencialmente perigosa e pode afetar negativamente seus relatórios. Entre em contato com o Atendimento ao cliente da Adobe antes de usar a ferramenta [!UICONTROL Nomear páginas].

**Armadilhas, dúvidas e dicas** {#section_BB41DC9682C34385B9CAA80D5257C113}

O *`pageName`* não deve conter caracteres ilegais.

## pageType {#concept_F67870238EF74491B5D3909A33CDB985}

A variável só é usada para designar uma página de erro 404, Página não encontrada.

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 20 bytes </td> 
   <td> pageType </td> 
   <td> Caminhos &gt; Páginas &gt; Páginas <p>Não encontrada </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. Configure a variável *`pageType`* na página de erro exatamente como mostrado abaixo.

Não use a variável de nome de página em páginas de erro 404. A variável *`pageType`* é usada apenas para a de erro 404.

Na maioria dos casos, a página de Erro 404 é uma página estática codificada. Nesses casos, é importante que a referência ao arquivo .JS seja definida em um caminho/diretório global ou relativo apropriado.

**Sintaxe e valores possíveis** {#section_C1C59968226446559B05F6EE7374D525}

O único valor permitido de *`pageType`* é "errorPage", como mostrado abaixo.

```js
s.pageType="errorPage"
```

**Exemplos** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Configurações** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_943681AB01FE47BEAC72E93CB60C53C8}

Para capturar outros erros do lado do servidor (como erros 500), use uma prop para obter a mensagem de erro e insira "`500 Error: <URL>`", onde `<URL>` é o o URL solicitado na variável *`pageName`*. Seguindo esta orientação, você poderá usar os relatórios de [!UICONTROL Definição de caminho] para ver quais caminhos fizeram com que usuários gerassem os erros 500. A prop explica qual mensagem de erro é fornecida pelo servidor.

## pageURL {#concept_A15F710CD0174297A2286BF3E7452113}

A variável substitui a URL real da página.

<!-- 

pageURL.xml

 -->

Em casos raros, a URL da página não é a URL que você deseja reportar no Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Sem limite* </td> 
   <td> <p>G </p> </td> 
   <td> Tráfego &gt; Segmentação &gt; Caminhos de página mais comuns </td> 
   <td> URL da página </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE]Embora a Adobe permita valores *`pageURL`* de até 64k, alguns navegadores impõem um limite de tamanho no URL das solicitações de imagem. Para impedir o truncamento de outros dados, os URLs de página com mais de 255 bytes são divididos. Os primeiros 255 bytes aparecem no parâmetro `g=` e os bytes restantes aparecem posteriormente em uma sequência de consulta no parâmetro de consulta `-g=`.

**Sintaxe e valores possíveis** {#section_22AF3BF7C2F743549967B0C760A095C0}

A variável *`pageURL`* deve ser um URL válido, com um protocolo válido. O domínio é forçado a ser exibido em letras minúsculas antes de ser preenchido em relatórios, e a string de consulta pode ser eliminada, dependendo das configurações do Analytics.

```js
s.pageURL="proto://domain/path?query_string"
```

São permitidos somente caracteres compatíveis com URL como a URL da página.

> [!NOTE] É extremamente recomendável entrar em contato com o consultor da Adobe ou o Atendimento ao cliente, antes de usar a variável *`pageURL`* para fins personalizados.

**Exemplos** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**Configurações** {#section_A8F77DAD88164528ACC5C16C066B47DF}

Nenhum

## plugins {#concept_B570F04FEDA34EB7A9826687FE633953}

Nos navegadores Netscape e baseados em Mozilla, a variável lista os plug-ins instalados no navegador.

<!-- 

plugins.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo | Relatórios afetados |
|---|---|---|---|
| p | Plug-ins reconhecidos | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Windows Media Player Plug-in Dynamic Link Library;Microsoft® DRM; | Tráfego &gt; Tecnologia &gt; Plug-ins |

## products {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

A variável é usada para rastrear produtos e categorias de produto, assim como quantidade e preço da compra. Ela geralmente é definida em conjunto com um evento de carrinho ou um evento.

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>Em janeiro de 2016, atualizamos a lógica que define o evento *`prodView`* automaticamente, o que acontece quando há *`product`*, mas não há *`event`*. Esta atualização pode causar um aumento nos eventos no *`prodView`*. *`prodViews`* só aumentarão quando:
>
>1. A variável de eventos não contém nada além de um evento não reconhecido, como *`shoppingCart`* ou *`cart`*, que não são eventos válidos.
   >
   >
1. A variável *`products`* não está vazia.
>
>
Um possível efeito colateral é que eVars de merchandising acionadas por eventos *`prodView`* podem ser associadas a um *`product`* vazio, mas somente se *`product list`* contiver apenas um produto inválido (como um ponto e vírgula sem produto listado).

A variável *`products`* rastreia a forma como os usuários interagem com os produtos do site. Por exemplo, a variável products pode rastrear quantas vezes um produto é exibido, adicionado ao carrinho, passado pelo checkout e adquirido. Ela também pode rastrear a eficácia relativa de categorias de comercialização de seu site. Os cenários abaixo são comuns para uso da variável products.

A variável *`products`* deve ser sempre definida juntamente com um evento bem-sucedido. 

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>A string " <span class="wintitle"> products </span>" tem um tamanho máximo de 64k. </p> </td> 
   <td> products </td> 
   <td> Produtos <p>Categorias (opcional) </p> <p>Receita (opcional) </p> <p>Unidades (opcional) </p> <p>Eventos personalizados (opcional) </p> <p>eVars (opcional) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxe** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| Campo | Definição |
|---|---|
| Categoria | Contém a categoria associada do produto. Na versão 15, os produtos podem ser associados à várias categorias. Isso cria a limitação presente na versão 14. Se você não gravava as categorias do produto, recomendamos popular a área com os conjuntos de relatórios presentes na versão 15. |
| Produto | (obrigatório) O identificador usado para rastrear um produto. O identificador é usado para preencher o relatório [!UICONTROL Produtos]. Não deixe de usar o mesmo identificador por meio do processo de checkout. |
| Quantidade | O número de unidades compradas. Este campo deve ser definido com um evento de [!UICONTROL compra] a ser gravado. |
| Preço | Refere-se ao custo total de quantidade adquirida (unidades vs preço unitário), e não o valor individual. Este campo deve ser definido com um evento de [!UICONTROL compra] a ser gravado. |
| Eventos | eventos de moeda associados ao produto em questão. Consulte [eventos de moeda do produto em questão](../../../implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C) e [eventos de moeda do pedido](../../../implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0). |
| eVars | Valores eVar de merchandising associados a um produto específico. Consulte [Variáveis de merchandising](/help/components/c-variables/c-merch-variables/var-merchandising.md). |

As valores inclusos na *`products`* variável são baseados no tipo de evento que está sendo gravado. O delimitador (;) de categoria/produto é necessário como espaço reservado na omissão de Categoria. O uso de outros delimitadores só é necessário para diferenciar o parâmetro que está sendo incluído, conforme exibido nos exemplos desta página.

**Configuração de products com eventos que não são de compra** {#section_D5E689D4AAE941EC851CA9B98328A4DE}

A variável *`products`* deve ser definida juntamente com um evento bem-sucedido.

**Configuração de products com um evento de compra** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

O evento *`purchase`* deve ser definido na confirmação final ("Obrigado.") página do processo do pedido. O nome do produto, a categoria, quantidade e o preço são capturados na variável *`products`*. Embora a variável *`purchaseID`* não seja obrigatória, ela é extremamente recomendável para evitar pedidos duplicados.

**Evento de moeda do produto em questão** {#section_F814DF053C0D463A97DA039E6323720C}

Se um evento de moeda receber um valor na variável *`products`*, em vez da variável de eventos, ele se aplica somente a esse valor. Isso é útil para rastrear descontos em produtos, envio de produtos e outros valores similares. Por exemplo, se você configurou o evento 1 para rastrear o envio do produto, um produto com uma carga de envio de "4,50" deverá ser exibido da seguinte maneira:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

Neste exemplo, o valor 4,50 está associado diretamente ao produto "Tênis de corrida". Se você adicionar evento 1 ao relatório de produtos, verá "4,50" listado para o item de linha "Tênis de corrida". Assim como o Preço, este valor deve refletir a soma total para a quantidade listada. Caso tenha 2 itens com uma taxa de envio de 4,50 cada, o evento 1 deverá ser "9,00".

**eventos de moeda do pedido** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

Se um evento de moeda receber um valor na lista de eventos, em vez da variável *`products`*, ele se aplica a todos os produtos na variável *`products`*. Isso serve para rastrear descontos, frete e valores similares de todo o pedido sem alterar o preço do produto ou rastreando na lista de produtos separadamente.

evento 10 para incluir os descontos de todos os produtos, poderá aparecer uma compra com um desconto de 10% semelhante à compra a seguir:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

Nos relatórios de moeda, o total do relatório representa o total do evento com duplicação eliminada (neste exemplo, a quantidade total de descontos durante o período do relatório) e não a soma dos valores do evento para cada produto. Por exemplo, você verá "9,95" listado tanto para "Tênis de corrida" como para "Meias de corrida", e o total ainda será de "9,95".

> [!NOTE] se um valor para o mesmo Evento numérico/de moeda for especificado na variável *`products`* e na variável *`events`*, o valor do evento *`events`* será usado.

**Armadilhas, dúvidas e dicas** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* A variável *`products`* deve ser sempre definida juntamente com um evento [!UICONTROL bem-sucedido] (eventos). Se nenhum evento [!UICONTROL bem-sucedido] for especificado, o evento padrão será [!UICONTROL prodView].

* Retire todas as vírgulas e pontos-e-vírgulas dos nomes de produto e categoria antes de preencher os produtos.
* Retire todos os caracteres HTML (símbolos registrados, marcas comerciais e assim por diante).
* Retire símbolos de moedas ($) do preço.

**Exemplos** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## propN {#concept_0F10FA2DE69B4029A31EA5E9313AA254}

As variáveis de propriedade ([!UICONTROL prop]) são usadas para criar relatórios personalizados dentro do [!UICONTROL Módulo de Tráfego].

<!-- 

propN.xml

 -->

A variável props pode ser usada como contadores (para contar o número de vezes que uma exibição de página é enviada), para relatório de definição de caminho ou em relatórios de correlação.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | c1-c75 | Tráfego personalizado | "" |

**Sintaxe e valores possíveis** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

Não há limitações nas variáveis [!UICONTROL property] além das limitações padrão de variáveis.

**Exemplos** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Configurações** {#section_25FDEB6ECA8242A2A44EE540C083078A}

Entre em contato com o Atendimento ao cliente da Adobe para saber como mostrar as métricas de [!UICONTROL Visita], [!UICONTROL Visitante] e [!UICONTROL Caminho] para variáveis [!UICONTROL prop].

## purchaseID {#concept_21937434E63F413CB469007623B933AE}

A é usada para impedir que um pedido seja contado várias vezes na geração de relatórios.

<!-- 

purchaseID.xml

 -->

Sempre que o evento de [!UICONTROL compra] for usado em seu site, você deve usar a variável *`purchaseID`*.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 20 bytes | purchaseID | Conversão &gt; Compras &gt; Conversão de Receita | "" |

Quando um visitante compra um item no seu site,  *`purchaseID`* é preenchida na página "Obrigado" no mesmo local que o evento [!UICONTROL purchase] é acionado. Se a *`purchaseID`* for preenchida, os produtos da página "Obrigado" serão contados apenas uma vez de acordo com *`purchaseID`*. Isso é crítico porque muitos visitantes do seu site salvarão a página "Obrigado" ou de "Confirmação" para seus objetivos próprios. A variável *`purchaseID`* impede a contagem das compras sempre que a página é exibida.

Além de impedir que os dados de compra sejam contados duas vezes, o *`purchaseID`*, quando usado, impede que todos os dados de conversão sejam contados duas vezes nos relatórios.

**Sintaxe e valores possíveis** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

O *`purchaseID`* deve ter até 20 caracteres e ser ASCII por padrão.

**Exemplos** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Configurações** {#section_1808631C96674380BF9C4A6D9A2C568E}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

A variável *`purchaseID`* permite que todas as variáveis de conversão da página sejam contadas apenas uma vez nos relatórios.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

A variável pode ser usada para restaurar as informações de referência perdidas.

<!-- 

referrer.xml

 -->

Normalmente, os redirecionamentos do lado do servidor e de JavaScript são usados para rotear visitantes até os locais apropriados. No entanto, quando um navegador é redirecionado, a URL original de referência fica perdida.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 255 bytes | R | Tráfego &gt; Localização de métodos de conversão &gt; Localização de métodos | document.referrer |

Muitas empresas usam redirecionamentos em muitos locais em seus sites. Por exemplo, um visitante pode ser enviado por meio de um redirecionamento de um resultado de pesquisa pago de mecanismo de pesquisa. Quando um navegador é redirecionado, normalmente a referrer fica perdida. A variável A variável *`referrer`* pode ser usada para restaurar o valor original *`referrer`* na primeira página após um redirecionamento. A *`referrer`* pode ser preenchida no lado do servidor ou por meio de JavaScript na sequência de consulta.

Para o Analytics registrar um referenciador, ele deve ser "bem formado", ou seja, deve seguir o formato padrão de URL, com protocolo e localização apropriada.

**Sintaxe e valores possíveis** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

Somente valores compatíveis com URL devem estar na *`referrer`*. Certifique-se de que a string seja codificada para URL (sem espaços).

**Exemplos** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**Configurações** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

A *`referrer`* deve ter a aparência de um URL padrão e incluir um protocolo.

## resolution {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

A variável indica a resolução do monitor do visitante que exibe a página da Web.

<!-- 

resolution.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo | Relatórios afetados |
|---|---|---|---|
| s | L x A | 1680 x 1050 | Tráfego &gt;Tecnologia &gt; Resolução de monitor |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

A variável é uma variável global e deve ser definida no evento [!UICONTROL onClick] de um link.

<!-- 

s_objectID.xml

 -->

Ao criar uma única ID de objeto para um link ou localização de link em uma página, é possível melhorar o rastreamento de atividade do usuário ou usar o [!UICONTROL Activity Map] para fazer um relatório sobre o tipo ou a localização de link, em vez do URL do link.

> [!NOTE] É necessário um ponto e vírgula (;) ao usar s_objectID com o [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | A URL absoluta de um link clicado |

Há três motivos comuns para usar *`s_objectID`*:

* Para agregar a atividade do visitante que é alterada durante o dia.
* Para separar a atividade do link combinada pelo [!UICONTROL Activity Map].
* Para aprimorar a precisão dos relatórios de dados do [!UICONTROL Activity Map].

**Agregar cliques em links altamente dinâmicos** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

Se o site for extremamente dinâmico e os links em algumas páginas forem alterados durante o dia, *`s_objectID`* poderá ser usado para identificar o local de um link na página. Se *`s_objectID`* estiver definido como "parte superior esquerda 1" ou "parte superior esquerda 2", que representa o primeiro link na parte superior esquerda da página, por exemplo, todos os links que aparecem nesse local (ou onde *`s_objectID`* estão definidos como o mesmo valor) são reportados juntamente com o mapa de cliques de visitante. Se vocÊ não usar *`s_objectID`*, verá o número de vezes que um link foi clicado, mas perderá o insight sobre como todos os outros links desse local foram usados pelos visitantes do site.

**Clique separados combinados** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

Se a variável *`pageName`* do site for usada para mostrar a seção ou o modelo que um visitante está visualizando, em vez da página específica que o visitante está visualizando, você pode usar *`s_objectID`* para separar os links que aparecem em várias versões desse modelo de página. Por exemplo, se você tiver um modelo de página para todos os produtos do seu site, provavelmente há um link para sua homepage e para a caixa de pesquisa desse modelo em todas as páginas. Se você quiser ver como esses links são usados em uma base de produtos individuais (em vez de uma base de modelo), poderá preencher *`s_objectID`* com valor do produto específico, como "prod 123789 página inicial" ou "prod 123789 pesquisa". Após a conclusão, o [!UICONTROL Activity Map] emite relatórios sobre os links em relação a cada produto.

**Melhore a[!UICONTROL Precisão do Activity Map]** {#section_08B3406821294DCCABEEB99C90CF5C52}

Em alguns casos, os navegadores diferentes do Internet Explorer, Firefox, Netscape, Opera e Safari não são suportados. Embora seja um percentual pequeno, ele conta para alguns cliques e outras métricas. Use *`s_objectID`* nos links para identificar unicamente os endereços do navegador que relata o problema. Este é um exemplo de como atualizar seus links para usar a *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Sintaxe e valores possíveis** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID pode conter qualquer identificador de texto.

```js
s_objectID="unique_id" 
```

Não há limitações nas variáveis *`s_objectID`* além das limitações padrão de variáveis.

**Exemplos** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**Configurações** {#section_95396657D55B41ECB66B83D0534EA827}

Nenhum

## server {#concept_BF77952603BA454BAFC9A0A81D06A7D2}

A variável é usada para mostrar o domínio de uma página da Web (para mostrar a quais domínios as pessoas vão) ou o servidor que atende a página (para uma referência rápida de balanceamento de carga).

<!-- 

server.xml

 -->

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | server | Servidores | "" |

Se seu site tiver mais que um domínio atendendo o mesmo conteúdo, a variável *`server`* poderá ser usada para rastrear quais desses domínios os visitantes estão usando. O JavaScript a seguir preencherá o domínio da página na variável do servidor.

```js
s.server=window.location.hostname
```

Se você estiver usando a variável do servidor para oferecer uma orientação rápida sobre balanceamento de carga, poderá inserir um nome ou número de servidor na variável do servidor. Considere o exemplo a seguir:

```js
s.server="server 14"
```

Embora o relatório [!UICONTROL Servidores Mais Populares] possam ser usados como referência rápida para o balanceamento de carga, ele não é uma medida precisa de carga do servidor. Por exemplo, o tráfego do botão voltar não aumenta a carga de servidor, mas é mostrado nos relatórios. O relatório não mostra quais servidores estão promovendo imagens ou downloads grandes.

**Sintaxe e valores possíveis** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

Não há limitações na variável *`server`* além das limitações padrão de variáveis.

**Exemplos** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Configurações** {#section_969DB379D5BD469FBEE8D505D3000E49}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_42A28F9B01574F38891D9D54B411D8FE}

A variável *`server`* pode ser usada para mostrar quais domínios são mais populares ou quais servidores estão promovendo mais páginas.

## state {#concept_82295D22888947BF8B1C76182C635C6C}

As variáveis e são variáveis de conversão.

<!-- 

state.xml

 -->

Elas são semelhantes a eVars, pois capturam eventos capture, mas diferente das eVars, não persistem. A variável *`zip`* são semelhantes a *`state`* eVars, pois expiram imediatamente.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 50 bytes | state | Conversão &gt; Perfil do visitante &gt; Estado do visitante | "" |

Como as variáveis *`state`* e *`zip`* expiram imediatamente, os únicos eventos associados a elas são eventos que são acionados na mesma página em que são preenchidos. Por exemplo, se estiver usando *`state`* para comparar as taxas de conversão por estado, você de preencher a variável *`state`* em cada página do processo de finalização. Para sites de conversão, a Adobe recomenda usar o endereço de cobrança como fonte do código, mas você pode optar por usar o endereço de entrega (supondo que exista apenas um endereço de entrega para o pedido). Um site de mídia pode ser escolhido para usar *`zip`* para registro ou *`state`* rastreamento de click-throughs no anúncio.

**Sintaxe e valores possíveis** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

A variável *`state`* não impõe restrições especiais de valor ou formato. Não há limitações nas variáveis *`state`* além das limitações padrão de variáveis.

**Exemplos** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**Configurações** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Preencha *`state`* em todas as páginas em que um evento relevante é acionado (como cada página do processo de finalização).
* As variáveis cep e estado atuam como eVars que expiram na Exibição da página.*`zip`**`state`*

## timestamp {#concept_D997A2FF4D134C80A614C0BC7A4D7507}

Esta variável permite personalizar a marca de data e hora de uma ocorrência semelhante às bibliotecas AppMeasurement para outras plataformas.

<!-- 

timestamp.xml

 -->

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 4 bytes | Data/Hora | Não informado diretamente. | Definido por servidores de coleta de dados. |

**Sintaxe** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

A variável *`timestamp`* deve estar no formato explicado na próxima seção.

>[!IMPORTANT]
>
>O Atendimento ao cliente deve ativar o carimbo de data e hora do conjunto de relatórios, antes que você possa usar a variável *`timestamp`*. Após ativar o suporte ao carimbo de data e hora, todos os hits enviados para esse conjunto de relatórios do JavaScript devem ter um carimbo de data e hora definido manualmente (usando *`s.timestamp`*) ou os hits não serão registrados.
>
>Além disso, se você ativar o suporte ao carimbo de data e hora em um conjunto de relatório para suporte ao rastreamento offline, todas as ocorrências enviadas para este conjunto de relatórios do JavaScript também devem ter um carimbo de data e hora definido manualmente (usando *`s.timestamp`*). Não é possível enviar ocorrências com e sem carimbo de data e hora para o mesmo conjunto de relatórios.
>
>Também é possível usar a configuração [Carimbos opcionais de data e hora](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F) para combinar dados com e sem carimbos de data e hora no mesmo conjunto de relatórios global, enviar dados com carimbos de data e hora de um aplicativo para dispositivos móveis para um conjunto de relatórios global ou atualizar aplicativos para usar carimbos de data e hora sem precisar criar um novo conjunto de relatórios.

**Formatos de marcas de data e hora** {#section_C12CBCECCD7047D38EF63A5800761CE9}

As marcas de data e hora devem estar em formato UNIX (segundos desde 1 de janeiro de 1970) ou ISO-8601, com as seguintes restrições sobre o formato ISO-8601 aceito:

* A data e a hora devem ser fornecidas, separadas por "T"
* A data deve ser uma data de calendário com total precisão (dia, mês e ano). . Não há suporte para datas semanais e datas ordinais.
* A data pode estar em formato padrão ou estendido (`YYYY-MM-DD` ou `YYYYMMDD`), mas deve sempre incluir a hora e o minuto. Os segundos são opcionais (`HH:MM`, `HH:MM:SS`, `HHMM` ou `HHMMSS`). Os minutos e os segundos fracionais podem ser mencionados, mas a parte fracional será omitida.

* Pode-se especificar um fuso horário opcional no formato padrão ou estendido (`±HH`, `±HH:MM`, `±HH`, `±HHMM` ou Z)

As marcas de data e hora UNIX continuam sendo suportados (segundos desde 1° de janeiro de 1970).

**Exemplos** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

A lista a seguir contém exemplos de marcas de data e hora válidas no formato ISO-8601:

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Configurações** {#section_5275D206F2CB4009B3681E8C4457124A}

É necessário ativar um conjunto de relatórios para aceitar carimbos de data e hora personalizados pelo Atendimento ao cliente antes de usar essa variável. Depois que as marcas de data e hora personalizadas são ativadas, todas as ocorrências enviadas para o conjunto de relatórios devem conter uma marca de data e hora ou são descartadas.

**Armadilhas, dúvidas e dicas** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* As marcas de data e hora são usadas principalmente para rastrear os dados offline em plataformas móveis. As marcas de data e hora personalizadas geralmente ficam desativadas, a menos que você colete dados da Web e do aplicativo offline no mesmo conjunto de relatórios.
* Os dados recebem carimbo de data e hora quando os dados offline são ativados no SDK móvel (configuração padrão) ou sempre que um conjunto de relatórios é configurado para aceitar os dados com carimbo de data e hora. Os dados coletados offline em dispositivos móveis podem ser enviados horas ou semanas após a data na qual ocorreram. Essas ocorrências podem ser consultadas na plataforma do Analytics para minutos ou horas superiores às ocorrências, sem carimbos de data e hora:

   * Para dados com carimbos de data e hora enviados próximos do horário atual, o atraso provável é de 10 a 15 minutos.
   * Para dados com carimbo de data e hora enviados ontem, o atraso provável é de aproximadamente 2 horas.
   * Para dados com carimbo de data e hora anteriores a ontem, cada dia adiciona aproximadamente 1 hora de atraso, a até 15 dias, quando o atraso para de aumentar.

* Os dados de uma sessão com carimbo de data e hora são mantidos por até 92 dias.

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

A variável é usada para a implementação de cookies primários para especificar o domínio em que a solicitação de imagem e o cookie são gravados.

<!-- 

trackingServer.xml

 -->

Usada para páginas não seguras. Se *`trackingServer`* estiver definido, nada vai para 2o7.net. Se *`trackingServer`* não estiver definido (e dc não estiver definido), os dados vão para 112.2o7.net.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | "" |

É possível encontrar uma lista de data centers da Adobe [aqui](https://helpx.adobe.com/analytics/kb/determining-data-center.html).

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

A variável é usada para a implementação de cookies primários para especificar o domínio em que a solicitação de imagem e o cookie são gravados.

<!-- 

trackingServerSecure.xml

 -->

Usada para páginas seguras. Se *`trackingServerSecure`* não estiver definido, os dados SSL vão para *`trackingServer`*.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | "" |

## transactionID {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

As [!UICONTROL Fontes de dados de integração] utilizam uma [!UICONTROL ID de transação ]para unir dados offline para uma transação online (como um cliente em potencial ou compra gerada online).

<!-- 

transactionID.xml

 -->

Cada *`transactionID`* única enviada para a Adobe é registrada em preparação para um upload de [!UICONTROL Fontes de dados ]de informações offline sobre essa transação. Consulte [Origens de Dados](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | xact | n/a | "" |

**Ativar armazenamento da ID de transação** {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Antes de registrar os valores *`transactionID`*, o [!UICONTROL Armazenamento da ID de transação] deve estar ativado para o conjunto de relatórios selecionado no Gerenciador de conjuntos de relatórios. Esta configuração está localizada em

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

Para ver se *`transactionID Storage`* está ativado para um conjunto de relatórios, acesse

```
Analytics > Admin > Data Sources > Manage
```

**Sintaxe e valores possíveis** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

O *`transactionID`* deve conter somente caracteres alfanuméricos. Se for necessário registrar várias [!UICONTROL transactionIDs] em uma única ocorrência, é possível usar uma vírgula para delimitar vários valores.

**Exemplos** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Armadilhas, dúvidas e dicas** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* Se a gravação *`transactionID`* não estiver ativada, os valores *`transactionID`* serão descartados e não estarão disponíveis para uso com as [!UICONTROL Fontes de dados de integração]. Defina uma variável ou um evento de conversão (uma eVar ou a variável de eventos) na página em que *`transactionID`* foi definido. Do contrário, nenhum dado será gravado para *`transactionID`*.

* Se estiver registrando [!UICONTROL transactionIDs] para vários sistemas, como compras e leads, assegure que o valor em *`transactionID`* seja sempre único. Isso pode ser feito se você adicionar um prefixo à ID, como lead_1234 e purchase_1234. As [!UICONTROL Fontes de dados de integração] não funcionarão como esperado (os dados da [!UICONTROL Fonte de dados] se conectam aos dados errados) se um *`transactionID`* único for visualizado duas vezes.

* Por padrão, os valores *`transactionID`* são lembrados por 90 dias. Se o processo de interação offline for superior a 90 dias, entre em contato com o Atendimento ao cliente para ampliar o limite.

> [!NOTE]A variável *`transactionID`* pode conter qualquer caractere diferente de vírgula. Ela deve estar no mesmo local em que o limite de caracteres (100 bytes) é especificado. Se forem usados caracteres multibytes, será necessário ativar suporte a esses caracteres para evitar problemas com caracteres inesperados na *`transactionID`*.

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

Os visitantes podem ser identificados pela variável ou pelo endereço IP/Agente do usuário.

<!-- 

visitorID.xml

 -->

A *`visitorID`* pode conter até 100 caracteres alfanuméricos e não deve conter hífen.

Se você definir explicitamente uma ID personalizada, ela sempre será utilizada antes de outros métodos de ID.

Esta é a ordem de uso: s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** Tamanho máximo** | ** Parâmetro de depuração** | ** Relatórios preenchidos** | ** Valor padrão** |
|---|---|---|---|
| 100 bytes | vid | n/a | "" |

**Sintaxe e valores possíveis** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE] A variável *`visitorID`* não deve conter hífen.

**Exemplos** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Configurações** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

Nenhum

## visitorNamespace {#concept_8369DDB3830C4BF2905F1CFC8C8B0D92}

A variável é usada para identificar o domínio com o qual os cookies são definidos.

<!-- 

visitorNamespace.xml

 -->

*`visitorNamespace`* é usada no seu arquivo JavaScript, não exclua-a ou altere-a. Se *`visitorNamespace`* for alterado, todos os visitantes relatados no Analytics podem se tornar novos visitantes. O histórico do visitante se torna desconectado do tráfego atual e futuro. Não altere essa variável sem aprovação de um representante da Adobe.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | ns | N/A | "" |

O Analytics um cookie para identificar de forma única os visitantes do site. Se *`visitorNamespace`* não for usado, o cookie será associado ao 2o7.net. Se *`visitorNamespace`* for usado, o cookie será associado com um subdomínio de 2o7.net. Todos os visitantes do site devem ter os cookies associados ao mesmo domínio ou subdomínio.

O motivo para usar a variável *`visitorNamespace`* é evitar a possibilidade de sobrecarregar um limite de cookie de um navegador. O Internet Explorer impõe um limite de 20 cookies por domínio. Se você usar a variável *`visitorNamespace`*, os cookies do Analytics de outras empresas não entrarão em conflito com os cookies de seus visitantes.

**Sintaxe e valores possíveis** {#section_EE247FE371784CA4B6058182181F3EA1}

O valor de *`visitorNamespace`* deve ser fornecido pela Adobe e é uma string de caracteres ASCII que não contêm vírgulas, pontos, espaços ou caracteres especiais.

```js
s.visitorNamespace="company_specific_value"
```

**Identificação do visitante nos conjuntos de relatórios** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

Se você não especificar um `visitorNamespace`, cada conjunto de relatórios na empresa recebe o próprio cookie da ID de visitante gravado como `s_vi_[random string]`. Se você especificar `visitorNamespace`, o mesmo cookie `s_vi` será utilizado para todos os conjuntos de relatórios que enviam dados para o `trackingServer` especificado. Se você implementou a marcação multiconjunto, certifique-se de especificar o namespace do visitante para que o cookie seja utilizado por cada conjunto de relatórios.

**Exemplos** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Configurações** {#section_1128A2531ECC43DFA6749ECC21F050A2}

Nenhum

## zip {#concept_C1DF93083553410DA36EAB61FBFDF69A}

As variáveis e são variáveis de conversão.

<!-- 

zip.xml

 -->

Elas são semelhantes a eVars, pois capturam eventos capture, mas diferente das eVars, não persistem. A variável *`zip`* são semelhantes a *`state`* eVars, pois expiram imediatamente.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 50 bytes | zip | Conversão &gt; Perfil do visitante &gt; CEP/Códigos postais | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. Por exemplo, se estiver usando o *`zip`* para comparar taxas de conversão por código postal, você deve preencher o *`zip`* em cada página do processo de finalização. A Adobe recomenda usar o endereço de cobrança como fonte para o CEP. Você pode optar pelo endereço de entrega (supondo que haja apenas um endereço de entrega para o pedido). Um site de mídia pode ser escolhido para usar *`zip`* para registro ou *`state`* rastreamento de click-throughs no anúncio.

**Sintaxe e valores possíveis** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

A variável *`zip`* não impõe restrições de valor ou formato. Não há limitações nas variáveis *`zip`* além das limitações padrão de variáveis.

**Exemplos** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Configurações** {#section_7987084EECC34DD38B643B94F82385CA}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Preencha [!UICONTROL zip] em cada página em que um evento relevante é acionado (cada página do processo de finalização).
* *`zip`* As *`state`* variáveis cep e estado atuam como eVars que expiram na Exibição da página.

