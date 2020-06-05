---
description: O rastreamento determina como os dados do mecanismo de pesquisa são rastreados por sua implementação do Adobe Analytics. Essa é uma etapa obrigatória para aumentar adequadamente os dados do Adobe Analytics com os dados do Mecanismo de pesquisa.
title: 'Rastreamento: modo manual e modo automático'
translation-type: tm+mt
source-git-commit: b92beee43756a3c5ec3902eee4ffaab0bcd43ce9
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 90%

---


# Rastreamento: modo manual e modo automático

O rastreamento determina como os dados do mecanismo de pesquisa são rastreados por sua implementação do Adobe Analytics. Essa é uma etapa obrigatória para aumentar adequadamente os dados do Adobe Analytics com os dados do Mecanismo de pesquisa.

Dois modos de rastreamento são compatíveis: Modo automático e Modo manual.

## Rastreamento no modo automático {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

No modo automático, o mecanismo da Advertising Cloud fica responsável por decidir como os dados do mecanismo de pesquisa devem ser tratados. Essa é a abordagem mais simples, mas pode não resultar no melhor conjunto de dados integrado.

Como consequência, é necessário marcar uma caixa de seleção de confirmação ao selecionar o Modo automático, antes que você possa salvar a configuração da conta.

Observe que, para configurar uma conta de mecanismo de pesquisa no “Modo automático”, você será responsável pelas seguintes ações:

* The `s_kwcid` parameter and value will be added to the account tracking templates or landing page URLs in the account being added. Ele será inserido ao final do URL. Pode ser necessária uma ação adicional de sua parte se o servidor da Web solicitar um determinado par chave=valor ao final do URL OU uma atualização para dar suporte a um novo par chave=valor no URL. **É sua responsabilidade garantir que os parâmetros de URL adicionados persistam corretamente na página de aterrissagem final.**
* In addition, keywords can be inserted into the landing URL as part of the `s_kwcid` value. Se elas apresentarem caracteres especiais ou símbolos, confirme se seu servidor da Web suporta esses caracteres. Exemplo: um caractere especial é o “+”, que pode ser usado em palavras-chave de “Grande correspondência modificada”.

>[!IMPORTANT]
>
>Saiba mais sobre se você deve adicionar o `s_kwcid` parâmetro à sua Política [de segurança de](https://docs.adobe.com/content/help/en/id-service/using/reference/csp.html)conteúdo.

## Rastreamento no modo manual  {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

No modo Manual, é necessário especificar como os dados do mecanismo de pesquisa devem ser tratados pelo processo de integração de dados do Advertising Analytics.

### Adicionar rastreamento manual à conta do Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

A sequência de caracteres que precisa ser adicionada a sua conta do Google é mostrada abaixo. É necessário adicionar a sequência de caracteres em todos os modelos de rastreamento usados em sua conta.

>[!IMPORTANT]
>
>O `<Advertising Analytics ID>` valor (em **negrito** abaixo) é genérico e **deve ser substituído por sua sequência de caracteres da ID de conta específica**. É possível obter sua sequência de caracteres da ID de conta específica na tela de configuração da conta, na seção “Rastreamento”.

**Sequência de caracteres de rastreamento de campanhas:**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![](assets/Google.png)

Exemplos de códigos de rastreamento em vários formatos de modelo de rastreamento:

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`com parâmetro de URL adicional **

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**Terceiros (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**Terceiros (DoubleClick)`{lpurl}`**

Se o URL passar por um redirecionamento e não estiver usando um valor “unescapedlpurl”, será preciso codificar a sequência de caracteres tantas vezes quanto for necessário para que ela persista pelo redirecionamento para o URL da página de aterrissagem final.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Adicionar rastreamento manual à conta do Bing {#section_094F8ACA493C4D65B1F54A695558EBF2}

A sequência de caracteres que precisa ser adicionada a sua conta do Bing é mostrada abaixo. É necessário adicionar a sequência de caracteres em todos os sufixos de URL final usados em sua conta.

>[!IMPORTANT]
>
>O `<Advertising Analytics ID>` valor (em **negrito** abaixo) é genérico e **deve ser substituído por sua sequência de caracteres da ID de conta específica**. É possível obter sua sequência de caracteres da ID de conta específica na tela de configuração da conta, na seção “Rastreamento”.

**Sequência de caracteres de rastreamento de campanhas:**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/Bing.png)

Exemplos de códigos de rastreamento em vários formatos de sufixos de URL final:

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}`
```

**`{lpurl}`com parâmetro de URL adicional **

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Terceiro (DoubleClick) &#39;{unescape edlpurl}**

```https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}

```

**Terceiros (DoubleClick)`{lpurl}`**

Se o URL passar por um redirecionamento e não estiver usando um valor “unescapedlpurl”, será preciso codificar a sequência de caracteres tantas vezes quanto for necessário para que ela persista pelo redirecionamento para o URL da página de aterrissagem final.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
