---
title: ID do AMO
description: A ID do Adobe Media Otimizer, usada em integrações da Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 3%

---

# ID do AMO

A **[!UICONTROL ID do AMO]** é uma coleção de identificadores concatenados usados em integrações do Adobe Advertising. Os valores armazenados nessa dimensão são organizados automaticamente em dimensões de classificação separadas e mais legíveis para uso nos relatórios do Analytics. A dimensão é criada automaticamente ao habilitar a integração do [Analytics para Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview).

## Preencher esta dimensão com dados

Essa dimensão coleta seus valores de várias maneiras:

* Para o tráfego de click-through, os dados são coletados do parâmetro da sequência de consulta `s_kwcid` na [URL da página](page-url.md), geralmente na página pela qual o tráfego orientado por anúncio entra no site.
* O tráfego de click-through também pode ser capturado quando o URL não contém códigos de rastreamento, mas o Adobe Advertising JavaScript detecta um clique nos dois minutos anteriores.
* Para tráfego de view-through com suporte, o Adobe Advertising complementa os valores no back-end usando uma ID complementar (`SDID`).

## Itens de dimensão

Os itens Dimension incluem IDs AMO, também chamados de valores `s_kwcid`. O formato exato depende de o tráfego se originar no DSP ou no Search, Social e Commerce. As IDs AMO são menos granulares que as IDs EF e são usadas principalmente para classificações e assimilação de métricas do Adobe Advertising no Analytics.

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`**: indica o canal de exibição.
* **`ad key`**: identificador alfanumérico gerado pela Adobe Advertising para o anúncio.
* **`placement key`**: identificador alfanumérico gerado pela Adobe Advertising para o posicionamento.

Valor de exemplo:

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### Anúncios de Pesquisa, Social e Commerce

As IDs AMO de Pesquisa, Social e Commerce começam com `AL`, seguidas pela ID de usuário do anunciante, a ID da conta de rede do anúncio e os identificadores específicos da rede. As IDs de conta de rede de publicidade compartilhada incluem:

* **`3`**: Anúncios do Google
* **`10`**: Microsoft Advertising
* **`45`**: Meta
* **`86`**: Yahoo! Rede de exibição
* **`87`**: Navegador
* **`88`**: Baidu
* **`90`**: Yandex
* **`94`**: Yahoo! Anúncios no Japão
* **`105`**: Yahoo nativo (desaprovado)
* **`106`**: Pinterest (obsoleto)

#### Google Ads

O Google Ads usa dois formatos relacionados. As contas mais recentes podem incluir a ID da campanha e a ID do grupo de anúncios, o que oferece suporte a relatórios de nível de campanha e grupo de anúncios para as campanhas Desempenho máximo e rascunhos/experimentos.

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`**: ID criativa do Google Ads.
* **`matchtype`**: Tipo de correspondência de palavra-chave (`e` para exato, `p` para frase, `b` para amplo).
* **`placement`**: Domínio no qual o anúncio foi clicado.
* **`network`**: Rede em que o clique ocorreu (`g` para pesquisa no Google, `s` para um parceiro de pesquisa, `d` para exibição).
* **`product partition`**: ID de grupo de produtos para anúncios de produtos.
* **`keyword`**: Acionando palavra-chave em sites de pesquisa ou a melhor palavra-chave correspondente em sites de conteúdo.
* **`campaign id`**: ID da campanha do Google Ads, quando presente.
* **`ad group id`**: ID de grupo de anúncios do Google Ads, quando presente.

Para anúncios de pesquisa dinâmica, o campo de palavra-chave é preenchido com o direcionamento automático.

Exemplo:

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### Microsoft Advertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`**: Microsoft Advertising creative ID.
* **`keyword/order item id`**: ID de palavra-chave do Microsoft Advertising.
* **`campaign id`**: ID de campanha do Microsoft Advertising.
* **`ad group id`**: ID do grupo de anúncios do Microsoft Advertising.

Os formatos herdados do Microsoft ainda podem existir para algumas contas não migradas.

Exemplo:

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### Baidu

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`**: ID criativa do Baidu.
* **`placement`**: Site no qual o anúncio foi clicado.
* **`keyword id`**: ID de palavra-chave do Baidu.

#### O Yahoo! Anúncios no Japão

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`**: Yahoo! ID criativa da Japan Ads.
* **`matchtype`**: Tipo de correspondência de palavra-chave (`be` exata, `bp` frase, `bb` ampla).
* **`network`**: Rede em que o clique ocorreu (`n` nativo, `s` pesquisa).
* **`keyword`**: Palavra-chave de acionamento.

#### Yandex

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`**: ID criativa do Yandex.
* **`source type`**: Tipo de site no qual o anúncio foi exibido (`b` pesquisa, `c` contexto/conteúdo, `ct` categoria).
* **`phrase id`**: ID da palavra-chave Yandex.

## Classificações

Ao habilitar a integração do [Analytics para Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview), as classificações a seguir são criadas automaticamente. Os valores de classificação são mantidos automaticamente pela integração.

| Classificação | Descrição | DSP | Pesquisar,<br>Social, &amp;<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL Conta]** | O nome da conta. | &verificar; | &verificar; |
| **[!UICONTROL Adicionar URL de exibição]** | O URL exibido no anúncio. | | &verificar; |
| **[!UICONTROL Descrição do anúncio]** | A descrição do anúncio (DSP) ou o corpo do anúncio (Search, Social e Commerce). | &verificar; | &verificar; |
| **[!UICONTROL URL de Destino do Anúncio]** | O URL de destino do anúncio. | | &verificar; |
| **[!UICONTROL Grupo de anúncios]** | O nome do grupo de anúncios. | | &verificar; |
| **[!UICONTROL Plataforma de publicidade]** | O nome do DSP de publicidade ou do mecanismo de pesquisa. | &verificar; | &verificar; |
| **[!UICONTROL Título do anúncio]** | O tipo de anúncio (DSP) ou o título do anúncio (Search, Social e Commerce). | &verificar; | &verificar; |
| **[!UICONTROL Tipo de anúncio]** | O tipo de anúncio, como `text`, `video`, `display` ou `native`. | &verificar; | &verificar; |
| **[!UICONTROL Atributo da AdCloud 1]** -<br>**[!UICONTROL Atributo da AdCloud 5 &#x200B;]** | Classificações de espaço reservado reservadas para atributos personalizados futuros. Não está em uso no momento. | | |
| **[!UICONTROL Campaign]** | O nome da campanha. | &verificar; | &verificar; |
| **[!UICONTROL Nome da Experiência do Creative]** | Nome da experiência criativa associada à interação com o anúncio, representando um grupo de variações criativas usadas em testes ou personalização. | &verificar; | |
| **[!UICONTROL Nome da Ramificação do Creative]** | Nome da ramificação em uma experiência criativa que representa uma variação ou um caminho específico no experimento criativo. | &verificar; | |
| **[!UICONTROL ID da Ramificação do Creative]** | Identificador exclusivo atribuído a uma ramificação criativa em uma experiência criativa. | &verificar; | |
| **[!UICONTROL Nome do Creative]** | Nome do ativo de criação do anúncio específico que foi distribuído ao usuário. | &verificar; | |
| **[!UICONTROL Nome da variante do Creative]** | Nome da variante específica de um criativo usado em uma experiência ou ramificação criativa. | &verificar; | |
| **[!UICONTROL Palavra-chave]** | A palavra-chave. | | &verificar; |
| **[!UICONTROL Tipo de Correspondência de Palavra-chave]** | A palavra-chave e o tipo de correspondência. | | &verificar; |
| **[!UICONTROL Tipo de aterrissagem]** | Se a entrada da página de aterrissagem era uma visualização ou um click-through. | &verificar; | &verificar; |
| **[!UICONTROL Tipo de correspondência]** | O tipo de correspondência da pesquisa. | | &verificar; |
| **[!UICONTROL Rede]** | RTB (DSP) ou o nome da rede de publicidade (Search, Social e Commerce). | &verificar; | &verificar; |
| **[!UICONTROL Otimização]** | O nome do pacote (DSP) ou do portfólio (Search, Social e Commerce). | &verificar; | &verificar; |
| **[!UICONTROL Posicionamento]** | O nome do posicionamento. | &verificar; | |
| **[!UICONTROL Destino do produto]** | O público alvo do produto para um anúncio de lista de produtos. | | &verificar; |
