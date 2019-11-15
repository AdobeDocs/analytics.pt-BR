---
description: O rastreamento determina como os dados do mecanismo de pesquisa são rastreados por sua implementação do Adobe Analytics. Essa é uma etapa obrigatória para aumentar adequadamente os dados do Adobe Analytics com os dados do Mecanismo de pesquisa.
title: Modo Manual de Acompanhamento e Modo Automático
uuid: c6ce7901-7b65-48b6-b65f-f29cc47b7454
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Rastreamento: modo manual e modo automático

O rastreamento determina como os dados do mecanismo de pesquisa são rastreados por sua implementação do Adobe Analytics. Essa é uma etapa obrigatória para aumentar adequadamente os dados do Adobe Analytics com os dados do Mecanismo de pesquisa.

Dois modos de rastreamento são compatíveis: Modo automático e Modo manual.

## Rastreamento no modo automático {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

No modo automático, o mecanismo da Advertising Cloud fica responsável por decidir como os dados do mecanismo de pesquisa devem ser tratados. Essa é a abordagem mais simples, mas pode não resultar no melhor conjunto de dados integrado.

Como consequência, é necessário marcar uma caixa de seleção de confirmação ao selecionar o Modo automático, antes que você possa salvar a configuração da conta.


Observe que para configurar uma conta de mecanismo de pesquisa em 'Modo automático', você é responsável pelas seguintes ações:

* O parâmetro e valor "s_kwcid" será adicionado aos modelos de rastreamento da conta ou aos URLs de página de aterrissagem na conta que está sendo adicionada. Ele será inserido ao final do URL. Pode ser necessária uma ação adicional de sua parte se o servidor da Web solicitar um determinado par chave=valor ao final do URL OU uma atualização para dar suporte a um novo par chave=valor no URL. **É sua responsabilidade garantir que os parâmetros de URL adicionados persistam corretamente na página de aterrissagem final.**
* Além disso, palavras-chave podem ser inseridas no URL de aterrissagem como parte do valor "s_kwcid". Se elas apresentarem caracteres especiais ou símbolos, confirme se seu servidor da Web suporta esses caracteres. Exemplo: um caractere especial é o “+”, que pode ser usado em palavras-chave de “Grande correspondência modificada”.

## Rastreamento no modo manual {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

No modo Manual, é necessário especificar como os dados do mecanismo de pesquisa devem ser tratados pelo processo de integração de dados do Advertising Analytics.

### Adicionar rastreamento manual à conta do Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

A sequência de caracteres que precisa ser adicionada a sua conta do Google é mostrada abaixo. É necessário adicionar a sequência de caracteres em todos os modelos de rastreamento usados em sua conta.

>[!IMPORTANT]
>
>The `<Advertising Analytics ID>` value (in **bold** below) is generic and **must be replaced with your specific account ID string**. É possível obter sua sequência de caracteres da ID de conta específica na tela de configuração da conta, na seção “Rastreamento”.

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

**`{lpurl}`com parâmetro de URL adicional**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**Terceiros (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**Terceiros (DoubleClick)`{lpurl}`**

Se o URL passar por um redirecionamento e não estiver usando um valor "unescapedlpurl", será necessário codificar a string o suficiente para que ela persista pelo redirecionamento para o URL da página inicial final.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Adicionar rastreamento manual à conta do Bing {#section_094F8ACA493C4D65B1F54A695558EBF2}

A sequência de caracteres que precisa ser adicionada a sua conta do Bing é mostrada abaixo. É necessário adicionar a string a todos os sufixos de URL finais usados em sua conta.

>[!IMPORTANT]
>
>The `<Advertising Analytics ID>` value (in **bold** below) is generic and **must be replaced with your specific account ID string**. É possível obter sua sequência de caracteres da ID de conta específica na tela de configuração da conta, na seção “Rastreamento”.

**Sequência de caracteres de rastreamento de campanhas:**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/Bing.png)

Exemplos de códigos de rastreamento em vários formatos de sufixo de URL final:

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}`
```

**`{lpurl}`com parâmetro de URL adicional**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Terceiro (DoubleClick) '{unescape edlpurl}**

```https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}

```

**Terceiros (DoubleClick)`{lpurl}`**

Se o URL passar por um redirecionamento e não estiver usando um valor "unescapedlpurl", será necessário codificar a string o suficiente para que ela persista pelo redirecionamento para o URL da página inicial final.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
