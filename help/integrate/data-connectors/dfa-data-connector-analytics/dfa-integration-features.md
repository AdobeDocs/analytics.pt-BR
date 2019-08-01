---
description: 'Depois de ativada, a integração do DFA dos Conectores de dados oferece as seguintes métricas para seus relatórios do Adobe Analytics '
keywords: DFA
seo-description: 'Depois de ativada, a integração do DFA dos Conectores de dados oferece as seguintes métricas para seus relatórios do Adobe Analytics '
seo-title: Recursos da integração
solution: Analytics
title: Recursos da integração
topic: Conectores de dados
uuid: 4 ad 8 e 6 e 8-3449-498 a -87 c 6-37 c 0 ac 1657 cd
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Recursos da integração{#integration-features}

Depois de ativada, a integração do DFA dos Conectores de dados oferece as seguintes métricas para seus relatórios do Adobe Analytics:

* View-throughs
* Cliques do DFA
* Impressões
* (opcional) Dados de custo do DFA
* (opcional) Erros de consulta do DFA, tempos limite

>[!NOTE]
>
>Essa integração não oferece suporte para rastreadores de cliques (anteriormente comandos de cliques). Os rastreadores de cliques são usados para registrar o número de cliques em links de texto, links em mensagens de email ou outros elementos de código fixo em um site.

A integração do DFA dos Conectores de dados automaticamente constrói códigos de rastreamento do DFA com os dados apresentados pelo DFA. Esses códigos de rastreamento são construídos para identificar exclusivamente um anúncio juntamente com o posicionamento e a criação associados. A seguir temos a descrição da estrutura do código de rastreamento, dependendo da versão da integração. A versão 1.5 é desta forma:

![](assets/DFA_id_struct1_5.png)

A versão 2.0 é desta forma:

![](assets/DFA_id_struct2.png)

Essas IDs servem como a chave compartilhada entre o Genesis e o DFA para associar as classificações e métricas corretas.

| ID do Site | O site de terceiros no qual o anúncio foi hospedado. A classificação do nome do site apresenta um nome descritivo desta ID de site. |
|---|---|
| ID da publicidade | Uma ID da mensagem comercial que é exibida para um usuário. A classificação do nome do anúncio contém o nome do anúncio conforme definido por sua organização no sistema do DFA. Por exemplo: `Hybrid Coup Textlink - Build`. |
| ID de posicionamento | Uma representação em sua conta do DFA de um site, parte de um site ou grupo de sites nos quais você adquiriu espaço para anúncio. |
| ID da criação | A imagem, Flash SWF ou outro recurso que deva ser exibido para o visitante. A classificação do nome da criação contém o nome que você informou para essa criação na interface do DFA. |

As outras duas classificações, Ferramenta de entrega (DoubleClick for Advertisers) e Canal (anúncio de banner), têm os mesmos valores para qualquer campanha do DFA e ajudam a diferenciar os dados importados do DFA.

## Deduplicação do SearchCenter {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

A integração do DFA agora conta com reconhecimento do Adobe SearchCenter. Com a habilitação da deduplicação do SearchCenter pelo assistente dos Conectores de dados, os visitantes direcionados por pesquisa não farão com que os dados sejam obtidos do servidor do Floodlight do DFA e *`s.campaign`* não será preenchido pelo DFA, permitindo que o SearchCenter o preencha. Além disso, o DFA e o SearchCenter agora preenchem valores de deduplicação nas variáveis de cada produto.

A lista abaixo descreve a lógica que é habilitada quando a deduplicação do SearchCenter é habilitada:

If **[!UICONTROL DFA]** &gt; **[!UICONTROL SearchCenter deduplication]** is selected in the wizard:

* No caso de um click-through do DFA, a integração preencherá a sequência “DFA Clickthrough” na eVar SCM configurada.
* No caso de um view-through do DFA, a integração preencherá a sequência “DFA Viewthrough” na eVar SCM.

If **[!UICONTROL SearchCenter]** &gt; **[!UICONTROL DFA deduplication]** is selected in the wizard:

* No caso de um view-through do DFA, a integração preencherá a sequência “DFA Viewthrough” na eVar SCM.

>[!NOTE]
>
>Se searchcenter &gt; Deduplicação do DFA estiver ativada e o parâmetro da sequência de consulta do searchcenter estiver definido, a visita não será considerada para processamento do DFA. Isso significa que o parâmetro de sequência de consulta do SearchCenter deve ser diferente do parâmetro de click-through do DFA, e nenhum anúncio de exibição deve definir o parâmetro de sequência de consulta do SearchCenter.

