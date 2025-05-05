---
description: O tipo de rastreamento determina como a implementação do Adobe Analytics rastreia os dados do mecanismo de pesquisa. Esse tipo de rastreamento é uma etapa necessária para aumentar os dados do Adobe Analytics corretamente com os dados do mecanismo de pesquisa.
title: Tipo de rastreamento
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 243da53fda562c856d95db0f6d13b7ee1a9adae5
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 32%

---

# Tipo de rastreamento

O tipo de rastreamento determina como a implementação do Adobe Analytics rastreia os dados do mecanismo de pesquisa. Esse tipo de rastreamento é uma etapa necessária para aumentar os dados do Adobe Analytics corretamente com os dados do mecanismo de pesquisa.

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://video.tv.adobe.com/v/23120/?quality=12)

-->

Há suporte para dois modos de rastreamento: [!UICONTROL Automático] e [!UICONTROL Manual].

## Acompanhamento [!UICONTROL Automático] {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

O rastreamento [!UICONTROL Automático] permite que o mecanismo do Advertising Cloud decida como os dados do mecanismo de pesquisa devem ser tratados. O rastreamento automático é a abordagem mais simples, mas pode não resultar no melhor conjunto de dados integrado.

Como consequência, você precisa marcar uma caixa de seleção de confirmação ao selecionar **[!UICONTROL Automático]** antes de salvar a configuração da conta.

Observe que, para configurar uma conta de mecanismo de pesquisa com o tipo **[!UICONTROL Auto]**, você será responsável pelas seguintes ações:

* O parâmetro e valor `s_kwcid` são adicionados aos modelos de rastreamento da conta ou às URLs da página de aterrissagem na conta que está sendo adicionada. Esse parâmetro e valor são inseridos no final do URL. Pode ser necessária uma ação adicional de sua parte se o servidor Web exigir um determinado par de `key=value` no final da URL. Ou uma atualização para dar suporte a qualquer novo par `key=value` na URL. É sua responsabilidade garantir que os parâmetros de URL adicionados persistam corretamente na página inicial final.
* Além disso, palavras-chave podem ser inseridas no URL inicial como parte do valor `s_kwcid`. Se elas apresentarem caracteres especiais ou símbolos, confirme se seu servidor da Web suporta esses caracteres. Por exemplo, um caractere especial comum é `+`, que é usado em palavras-chave de &quot;Grande correspondência modificada&quot;.

>[!IMPORTANT]
>
>Saiba se você deve adicionar o parâmetro `s_kwcid` à sua [Política de segurança de conteúdo](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).

## Rastreamento manual {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

O rastreamento manual permite especificar como o processo de integração de dados do Advertising Analytics deve tratar os dados do mecanismo de pesquisa.

### Adicionar rastreamento manual à conta da Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

A sequência de caracteres que precisa ser adicionada a sua conta do Google é mostrada abaixo. É necessário adicionar a sequência de caracteres em todos os modelos de rastreamento usados em sua conta.

>[!IMPORTANT]
>
>O *`<Advertising Analytics ID>`* valor (em **negrito** abaixo) é genérico e **deve ser substituído por sua sequência de caracteres da ID de conta específica**. Você pode obter sua sequência de caracteres da ID de conta específica na tela da conta na seção [!UICONTROL Rastreamento].

**Sequência de caracteres de rastreamento de campanhas:**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![Google](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/google-account.png)

Exemplos de códigos de rastreamento em vários formatos de modelo de rastreamento:

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`com parâmetro de URL adicional**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**Terceiros (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**Terceiros (DoubleClick)`{lpurl}`**

Para garantir que a string persiste por meio do redirecionamento para o URL da página inicial final, é necessário codificar a string de maneira suficiente:

* se o URL passar por um redirecionamento e
* não está usando um valor &quot;unescapedlpurl&quot;.


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Adicionar rastreamento manual à conta do Bing {#section_094F8ACA493C4D65B1F54A695558EBF2}

A sequência de caracteres que precisa ser adicionada a sua conta do Bing é mostrada abaixo. É necessário adicionar a sequência de caracteres em todos os sufixos de URL final usados em sua conta.

>[!IMPORTANT]
>
>O _`<Advertising Analytics ID>`_valor (em **negrito**&#x200B;abaixo) é genérico e **deve ser substituído por sua sequência de caracteres da ID de conta específica**. É possível obter sua sequência de caracteres da ID de conta específica na tela da conta, na seção &quot;Rastreamento&quot;.

**Sequência de caracteres de rastreamento de campanhas:**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![Bing](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

Exemplos de códigos de rastreamento em vários formatos de sufixos de URL final:

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`com parâmetro de URL adicional**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Terceiros (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Terceiros (DoubleClick)`{lpurl}`**

Para garantir que a string persiste por meio do redirecionamento para o URL da página inicial final, é necessário codificar a string de maneira suficiente:

* se o URL passar por um redirecionamento e
* não está usando um valor &quot;unescapedlpurl&quot;.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
