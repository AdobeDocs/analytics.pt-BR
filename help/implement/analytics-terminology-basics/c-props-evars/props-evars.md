---
description: As variáveis personalizadas de tráfego, também chamadas de props (s.prop) ou variáveis de propriedade, são contadores que contam o número de vezes que cada valor é enviado ao Analytics.
keywords: Implementação do Analytics; Prop de tráfego; prop; conversão; evar; s. prop; insight de conversão personalizado; variável de tráfego
seo-description: As variáveis personalizadas de tráfego, também chamadas de props (s.prop) ou variáveis de propriedade, são contadores que contam o número de vezes que cada valor é enviado ao Analytics.
seo-title: Visão geral de props e evars
solution: Analytics
title: Visão geral de props e evars
topic: Desenvolvedor e implementação
uuid: 522 cab 2 b -1 ef 8-4 f 10-b 216-c 82 b 21431487
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visão geral de props e evars

As variáveis personalizadas de tráfego, também chamadas de props (s.prop) ou variáveis de propriedade, são contadores que contam o número de vezes que cada valor é enviado ao Analytics.

Ao determinar quais variáveis são atribuídas a que local, é importante compreender as diferenças entre a funcionalidade de Prop e de eVar. Compreender essas diferenças permite que sua organização decida que tipo de variável é melhor para ser usada. Para informações detalhadas, consulte [Comparação de Props e eVars](../../../implement/analytics-terminology-basics/c-props-evars/props-vs-evars.md#concept_6E55483C1EC24566B5D3B2736E766EBC).

As props permitem correlacionar os dados personalizados com eventos específicos relacionados ao tráfego. Essas variáveis de prop estão incluídas no código do [!DNL Analytics] em cada página do seu site. Por meio das variáveis [!UICONTROL s.prop], o [!DNL Analytics] permite criar relatórios personalizados, exclusivos para os objetivos de sua organização, setor e empresa.

Por exemplo, se você for um fabricante de automóveis, poderá se interessar em ver "Modelo de carro mais popular" para complementar seu relatório "Páginas". Você poderá fazer isso alocando uma de suas propriedades de tráfego para representar o modelo de carro. Em seguida, implemente o código para passar para o modelo de carro nas páginas apropriadas.

>[!NOTE]
>
>[!DNL Analytics] suporta até 75 [!UICONTROL variáveis s. prop] .

As props são usadas nos relatórios de definição de caminho ou em relatórios de correlação. Por exemplo, as variáveis de [!UICONTROL propriedade] podem ser usadas para mostrar o tipo de conteúdo, a subseção ou o nome do modelo. Os relatórios de [!UICONTROL Tráfego personalizado] resultantes mostram qual tipo de conteúdo, subseção ou modelo é exibido com mais frequência.

Existem inúmeras dúvidas corporativas que podem ser respondidas por meio de variáveis de tráfego personalizado, dependendo do que você está capturando em seu site. A lista a seguir contém algumas das metas e objetivos comuns:

* Compreensão da navegação do usuário por meio do site
* Compreensão do comportamento de pesquisa do usuário interno
* Segmentação de tráfego pela navegação ou categoria
* Segmentação do comportamento do visitante por dados demográficos

As eVars (variáveis de [!UICONTROL Insight de conversão personalizada ]) são usadas para identificar até que ponto os atributos ou ações específicos contribuem para os eventos bem-sucedidos de seu site. Por exemplo, para um site de mídia, as eVars podem ser usadas para identificar o quanto as promoções internas levam os visitantes ao registro. Quando um visitante clica na promoção interna, é possível usar uma eVar para armazenar um identificador exclusivo para essa promoção. Quando o mesmo visitante conclui o registro e um evento bem-sucedido personalizado é acionado, o identificador exclusivo original recebe crédito para o evento de registro.

Em um site de conversão, as eVars podem ser usadas para rastrear como os visitantes conectados se comparam aos não conectados no que diz respeito à conclusão de uma compra. Quando um visitante faz login, uma eVar é definida como "conectada". Quando o visitante chega à página de checkout, o evento de checkout é atribuído ao valor "conectado". Quando um visitante chega à página Obrigado depois da compra, os produtos e valores da compra são atribuídos ao valor "conectado". O relatório da [!UICONTROL eVar personalizada] resultante mostra o número total de checkouts e pedidos de visitantes "conectados" e "não conectados".

Para obter mais informações, consulte [Variável de tráfego](https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html) no guia de Ajuda e referência do Analytics.

Para obter informações sobre a configuração de propriedades no Digital Tag Management, consulte [Criar propriedade da Web](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123).
