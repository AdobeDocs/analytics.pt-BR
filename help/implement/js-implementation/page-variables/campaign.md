---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# campaign

A variável identifica campanhas de marketing usadas para trazer visitantes para o site. Normalmente, o valor de é retirado de um parâmetro da string de consulta.
https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables/browserheight.html

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

* O plug-in [!UICONTROL getQueryParam], usado no arquivo JavaScript, recupera um parâmetro da string de consulta do URL. Para obter mais informações sobre o plug-in [!UICONTROL getQueryParam], consulte [Plug-ins de implementação](/help/implement/js-implementation/plugins/impl-plugins.md).

* Atribua um valor à variável *`campaign`* no HTML da página da Web.

Com qualquer método de preenchimento da variável *`campaign`*, o tráfego do botão Voltar pode aumentar o número real de click-throughs de um elemento de campanha.

Por exemplo, um visitante entra em seu site clicando em uma palavra-chave de pesquisa paga. Quando o visitante chega à página inicial, o URL contém um parâmetro da string de consulta identificando o código de rastreamento da palavra-chave. O visitante então clica em um link para outra página, mas imediatamente clica no botão Voltar para retornar à página inicial. Quando o visitante chega à página inicial uma segunda vez, o URL com o parâmetro da string de consulta identifica novamente o código de rastreamento. E um segundo click-through é registrado, aumentando o número de click-throughs de forma falsa.

Para evitar esse aumento de click-throughs, a Adobe recomenda usar o plug-in [!UICONTROL getValOnce] para forçar que cada click-through da campanha seja contado somente uma vez por sessão. Para obter mais informações sobre o plug-in [!UICONTROL getValOnce], consulte [Plug-ins de implementação](/help/implement/js-implementation/plugins/impl-plugins.md).

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

* Para impedir o aumento de click-throughs, use o plug-in [!UICONTROL getValOnce] para que o click-through de uma campanha seja contado somente uma vez por sessão. Para obter mais informações sobre o plug-in [!UICONTROL getValOnce], consulte [Plug-ins de implementação](/help/implement/js-implementation/plugins/impl-plugins.md).

* Para obter mais informações sobre o rastreamento das campanhas de marketing e compras de palavras-chaves, consulte [Campanhas](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Use o [!DNL DigitalPulse Debugger] para ver o valor real de campaigns (v0 no depurador). Se v0 não for exibido no depurador, nenhum dado de campanha será registrado para essa página.
