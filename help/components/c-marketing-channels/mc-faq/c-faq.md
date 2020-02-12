---
description: Leia sobre as práticas recomendadas e exemplos de como popular diversas regras que podem ser configuradas para seus canais de marketing.
title: Perguntas frequentes e exemplos de canais de marketing
translation-type: tm+mt
source-git-commit: 8d523d89119fe5e3c1490ecb4efef44f1b99868f

---


# Perguntas frequentes e exemplos de canais de marketing

See [Create Marketing Channel Processing Rules](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md) for definitions of fields displayed on the [!UICONTROL Marketing Channel Processing Rules] page.

## Perguntas frequentes {#faq}

Cada implementação das regras de canal de marketing pode ser diferente, dependendo dos códigos de acompanhamento. Configurar regras que forneçam os resultados que você procura pode exigir pensamento criativo para solucionar problemas.

**Pergunta:** Meus códigos de acompanhamento não seguem um padrão, e existem milhares deles a serem especificados para meu canal Afiliados.

* Use o processo de eliminação. Se os seus canais Email e Afiliados usam o mesmo parâmetro de sequência de consulta, mas você dispõe de apenas alguns códigos de acompanhamento de email, especifique os códigos de acompanhamento de email em um conjunto de regras que definam email. Em seguida, classifique todos os outros códigos de acompanhamento com  *`affiliates.`*
* Em seu sistema de email, inclua um parâmetro da sequência de consulta para todos os URLs de página inicial, como *`&ch=eml`*. Crie um conjunto de regras que detecte se o parâmetro de consulta ch é igual a *`eml`*. Se não contiver *`eml`*, será um afiliado.

**Pergunta**: os domínios de referência contêm mais dados que eu esperava.

* Os domínios de referência podem estar próximos demais do topo da lista de regras de processamento. Eles devem ser um dos últimos (ou os últimos) conjuntos de regras, porque a ordem de processamento é importante.

**Pergunta**: Criei uma regra que corresponde a um parâmetro de sequência de consulta e que não está funcionando.

* Certifique-se de que o nome do parâmetro esteja especificado nos campos de parâmetro da sequência de consulta (normalmente um valor alfanumérico). Além disso, certifique-se de que o valor de parâmetro está especificado após o operador, conforme mostrado no exemplo a seguir em uma regra de email.

   ![](assets/example_email.png)

**Pergunta**: Por que todo o meu tráfego de último toque é atribuído a um domínio interno?

*  Você possui uma regra que corresponde ao tráfego interno. Observe que essas regras processam todos os acessos de um visitante em seu site, não só a primeira visita. Se você tiver uma regra similar a  *`Page URL exists`* sem outros critérios, o canal é correspondido em cada acesso sucessivo ao site, porque o URL da página sempre existe.

**Pergunta**: Como faço para depurar o tráfego exibido em Nenhum Canal Identificado no relatório?

*  As regras são processadas em ordem. Se não houver correspondência com critérios específicos, as ocorrências são incluídas em uma de três categorias:

1. Nenhum referenciador (visita direta).

2. Referenciador interno, na primeira página de visita.

3. Erro de processamento na página.

Verifique se você dispõe de canais para essas três possibilidades. Por exemplo, criar regras que indiquem:

1. **[!UICONTROL Referrer]** e **[!UICONTROL Does Not Exist]** e **[!UICONTROL Is First Page of Visit]**. (Consulte [Direto.](/help/components/c-marketing-channels/mc-faq/c-faq.md))

2. **[!UICONTROL Referrer Matches Internal URL Filters]** e **[!UICONTROL Is First page of Visit]**. (Consulte [Interno](/help/components/c-marketing-channels/mc-faq/c-faq.md).)

3. **[!UICONTROL Referrer]** e **[!UICONTROL Exists]** e **[!UICONTROL Referrer Does Not Match Internal URL Filters]**.

Por último, crie um canal *Outro* para capturar as ocorrências restantes, conforme descrito em [Nenhum canal identificado](/help/components/c-marketing-channels/mc-faq/c-faq.md#no-channel-identified).

## Nenhum Canal Identificado  {#no-channel-identified}

When your rules do not capture data, or if rules are not configured correctly, the report displays the data in the [!UICONTROL No Channel Identified] row on the report. É possível criar um conjunto de regras chamado *Outros*, por exemplo, no fim da sua ordem de processamento, que também identifica o tráfego interno, como segue.

![](assets/example_other.png)

This kind of rule serves as a catch-all to ensure that channel traffic always matches external traffic, and typically does not end up in **[!UICONTROL No Channel Identified]**. Tenha cuidado para não criar uma regra que também identifique o tráfego interno. Setting the channel&#39;s value to **[!UICONTROL Referring Domain]** or to **[!UICONTROL Page URL]** are the most common, useful ways to create an effective Other rule.

> [!NOTE] Ainda pode haver algum tráfego de canal que caiba na categoria Nenhum canal identificado. Por exemplo: um visitante entra no site, marca uma página e, na mesma visita, retorna à página por meio do marcador. Como não é a primeira página da visita, o tráfego não irá para o canal Direto nem para o canal Outro, pois não há um domínio de referência.

## Pesquisa paga {#paid-search}

Uma pesquisa paga é uma palavra ou frase pela qual o mecanismo de pesquisa é pago a fim de colocá-la entre os resultados da pesquisa. To match paid search detection rules, the marketing channel uses settings configured on the [!UICONTROL Paid Search Detection] page. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). O URL de destino corresponde à regra de detecção de pesquisa paga existente para o mecanismo de pesquisa.

For the marketing channel rule, the [!UICONTROL Paid Search] settings are as follows:

![](assets/example_paid_search.png)

Consulte [Detecção de pesquisa paga](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) em Admin para obter mais informações.

## Pesquisa natural  {#natural-search}

A pesquisa natural ocorre quando os visitantes encontram seu Web site por meio de uma pesquisa na Web, onde o mecanismo de pesquisa classifica seu site sem que você pague para entrar na listagem. É possível controlar o URL de destino usado pelo mecanismo de pesquisa para vincular a seu site. Esse URL permite que o Analytics identifique se uma pesquisa é natural.

Não existe detecção de pesquisa natural no Analytics. Após configurar a Detecção de pesquisa paga, o sistema saberá que se um referenciador de pesquisa não for do tipo pago, ele deve ser um referenciador de pesquisa natural. Para uma pesquisa natural, o URL de destino não corresponde à regra de detecção de pesquisa paga existente para esse mecanismo de pesquisa.

Para a regra de canal de marketing, as configurações de Pesquisa natural são as seguintes:

![](assets/example_natural_search.png)

Consulte [Detecção de pesquisa paga](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) em Admin para obter mais informações.

## Afiliados  {#afilliates}

Uma regra afiliada identifica os visitantes que se originam de determinado conjunto de domínios de referência. Na regra, você relaciona os domínios de afiliados que gostaria de acompanhar, como segue:

![](assets/example_affiliates.png)

## Redes sociais {#social-networks}

Esta regra identifica os visitantes que se originam de uma rede social, como o Facebook*. As configurações podem ser as seguintes:

![](assets/example_social.png)

## Exibir {#display}

Essa regra identifica visitantes que se originam de anúncios em banners. Ela é identificada por um parâmetro de sequência de consulta na URL de destino, neste caso  *`Ad_01`*.

![](assets/example_display.png)

## Interno {#internal}

Esta regra identifica visitantes que se originam de um referenciador que corresponde aos filtros de URL interna do conjunto de relatório.

![](assets/example_internal.png)

## Email  {#email}

Para configurar esta regra, forneça o parâmetro de sequência de consulta para sua campanha de email. Neste exemplo, o parâmetro é  *`eml`*:

![](assets/example_email.png)

Se sua regra contém Códigos de acompanhamento, insira um valor por linha, como mostrado aqui:

![](assets/tracking_code.png)

## Direta  {#direct}

Esta regra identifica visitantes que não têm domínio de referência. Essa regra inclui visitantes que vêm ao seu site diretamente, como a partir de um link dos Favoritos ou colando o link no navegador.

![](assets/example_direct.png)

