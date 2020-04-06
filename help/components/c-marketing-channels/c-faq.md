---
description: Leia sobre as práticas recomendadas e exemplos de como popular diversas regras que podem ser configuradas para seus canais de marketing.
title: Perguntas frequentes sobre Canais de marketing e exemplos
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Perguntas frequentes sobre Canais de marketing e exemplos

See [Create Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) for definitions of fields displayed on the [!UICONTROL Marketing Channel Processing Rules] page.

## Perguntas frequentes {#faq}

Cada implementação das regras de processamento de canais de marketing pode diferir, dependendo dos códigos de rastreamento. A configuração de regras que fornecem os resultados que você está procurando pode exigir um pouco de pensamento criativo para resolver problemas.

**Pergunta**: Meus códigos de rastreamento não seguem um padrão, e eu tenho milhares que devem ser especificados para meu canal de afiliados.

* Use o processo de eliminação. Se seus canais Email e Afiliados usarem o mesmo parâmetro de sequência de query, mas você tiver apenas alguns códigos de tracking de email, poderá especificar os códigos de tracking de email em um conjunto de regras que define o email. Em seguida, classifique todos os outros códigos de acompanhamento com  *`affiliates.`*
* Em seu sistema de email, inclua um parâmetro da sequência de consulta para todos os URLs de página inicial, como *`&ch=eml`*. Crie um conjunto de regras que detecte se o parâmetro de consulta ch é igual a *`eml`*. Se não contiver *`eml`*, será um afiliado.

**Pergunta**: os domínios de referência contêm mais dados que eu esperava.

* Os domínios de referência podem ser muito altos na lista da regra de processamento. Deve ser um dos últimos (ou os últimos) conjuntos de regras, pois a ordem de processamento é importante.

**Pergunta**: Criei uma regra que corresponde a um parâmetro de string de query e não está funcionando.

* Certifique-se de que o nome do parâmetro esteja especificado nos campos de parâmetro da string de query (normalmente um valor alfanumérico). Além disso, certifique-se de que o valor do parâmetro seja especificado após o operador, conforme mostrado no exemplo a seguir de uma regra de email.

   ![](assets/example_email.png)

**Pergunta**: Por que todo o meu tráfego de último toque é atribuído a um domínio interno?

*  Você possui uma regra que corresponde ao tráfego interno. Observe que essas regras processam todos os acessos de um visitante em seu site, não só a primeira visita. Se você tiver uma regra similar a  *`Page URL exists`* sem outros critérios, o canal é correspondido em cada acesso sucessivo ao site, porque o URL da página sempre existe.

**Pergunta**: Como faço para depurar o tráfego exibido em Nenhum Canal identificado no relatório?

*  As regras são processadas em ordem. Se nenhum critério específico tiver correspondido, as ocorrências se encaixarão em uma das três categorias:

1. Nenhum referenciador (visita direta).

2. Referenciador interno, na primeira página de visita.

3. Erro de processamento na página.

Certifique-se de ter uma canal para essas três possibilidades. Por exemplo, crie regras que indiquem:

1. **[!UICONTROL Referrer]** e **[!UICONTROL Does Not Exist]** e **[!UICONTROL Is First Page of Visit]**. (Consulte [Direto.](/help/components/c-marketing-channels/c-faq.md))

2. **[!UICONTROL Referrer Matches Internal URL Filters]** e **[!UICONTROL Is First page of Visit]**. (Consulte [Interno](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Referrer]** e **[!UICONTROL Exists]** e **[!UICONTROL Referrer Does Not Match Internal URL Filters]**.

Por último, crie um canal *Outro* para capturar as ocorrências restantes, conforme descrito em [Nenhum canal identificado](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## Nenhum Canal Identificado  {#no-channel-identified}

When your rules do not capture data, or if rules are not configured correctly, the report displays the data in the [!UICONTROL No Channel Identified] row on the report. Você pode criar um conjunto de regras chamado *Outros*, por exemplo, no final da ordem de processamento, que também identifica o tráfego interno.

![](assets/example_other.png)

This kind of rule serves as a catch-all to ensure that channel traffic always matches external traffic, and typically does not end up in **[!UICONTROL No Channel Identified]**. Tenha cuidado para não criar uma regra que também identifique o tráfego interno. Setting the channel&#39;s value to **[!UICONTROL Referring Domain]** or to **[!UICONTROL Page URL]** are the most common, useful ways to create an effective Other rule.

>[!NOTE] Ainda pode haver algum tráfego de canal que caiba na categoria Nenhum canal identificado. Por exemplo: Um visitante chega ao site e marca uma página e, na mesma visita, volta à página por meio do marcador. Como essa não é a primeira página da visita, ela não aparecerá no canal Direto nem no canal Outro porque não há domínio de referência.

## Pesquisa paga {#paid-search}

Uma pesquisa paga é uma palavra ou frase pela qual o mecanismo de pesquisa é pago a fim de colocá-la entre os resultados da pesquisa. Para corresponder às regras de detecção de pesquisa paga, o canal de marketing usa as configurações definidas na [!UICONTROL Paid Search Detection] página. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). O URL de destino corresponde à regra de detecção de pesquisa paga existente para esse mecanismo de pesquisa.

Para a regra de canal de marketing, as [!UICONTROL Paid Search] configurações são as seguintes:

![](assets/example_paid_search.png)

Consulte Detecção [de pesquisa](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) paga em Admin para obter mais informações.

## Pesquisa natural  {#natural-search}

Uma pesquisa natural ocorre quando os visitantes encontram seu site por meio de uma pesquisa na Web, onde o mecanismo de pesquisa classificou seu site sem que você pague pela listagem. Você pode controlar o URL de destino que o mecanismo de pesquisa usa para vincular ao site. Esse URL permite que o Analytics identifique se uma pesquisa é natural.

Não existe detecção de pesquisa natural no Analytics. Depois de configurar a Detecção de pesquisa paga, o sistema sabe que se uma quem indicou de pesquisa não for uma quem indicou de pesquisa paga, ela deve ser uma quem indicou de pesquisa natural. Para uma pesquisa natural, o URL de destino não corresponde à regra de detecção de pesquisa paga existente para esse mecanismo de pesquisa.

Para a regra de canal de marketing, as configurações de Pesquisa natural são as seguintes:

![](assets/example_natural_search.png)

Consulte Detecção [de pesquisa](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) paga no Admin para obter mais informações.

## Afiliados  {#afilliates}

Uma regra afiliada identifica os visitantes que se originam de determinado conjunto de domínios de referência. Na regra, você lista os domínios de afiliados que deseja rastrear, da seguinte forma:

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

Esta regra identifica visitantes que não têm domínio de referência. Esta regra inclui visitantes que chegam ao site diretamente, como de um link Favoritos ou colando um link no navegador.

![](assets/example_direct.png)

