---
description: 'Depois de ativada, a integração do DFA do Data Connectors oferece as seguintes métricas para seus relatórios do Adobe Analytics '
keywords: DFA
title: Recursos da integração
topic: Data connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Recursos da integração {#integration-features}

Depois de ativada, a integração do DFA dos Data Connectors oferece as seguintes métricas para seus relatórios do Adobe Analytics:

* View-throughs
* Cliques do DFA
* Impressões
* (opcional) Dados de custo do DFA
* (opcional) Erros de consulta do DFA, tempos limite

> [!NOTE] Essa integração não é compatível com rastreadores de cliques (antigos comandos de cliques). Os rastreadores de cliques são usados para registrar o número de cliques em links de texto, links em mensagens de email ou outros elementos de código fixo em um site.

A integração do DFA dos Data Connectors automaticamente constrói códigos de rastreamento do DFA com os dados apresentados pelo DFA. Esses códigos de rastreamento são construídos para identificar exclusivamente um anúncio juntamente com o posicionamento e a criação associados. A seguir temos a descrição da estrutura do código de rastreamento, dependendo da versão da integração. A versão 1.5 é desta forma:

![](assets/DFA_id_struct1_5.png)

A versão 2.0 é desta forma:

![](assets/DFA_id_struct2.png)

Essas IDs servem como a chave compartilhada entre o Genesis e o DFA para associar as classificações e métricas corretas.

| ID do site | O site de terceiros no qual o anúncio foi hospedado. A classificação do nome do site apresenta um nome descritivo desta ID de site. |
|---|---|
| ID do anúncio | Uma ID da mensagem comercial que é exibida para um usuário. A classificação do nome do anúncio contém o nome do anúncio conforme definido por sua organização no sistema do DFA. Por exemplo: `Hybrid Coup Textlink - Build`. |
| ID de posicionamento | Uma representação em sua conta do DFA de um site, parte de um site ou grupo de sites nos quais você adquiriu espaço para anúncio. |
| ID de criação | A imagem, Flash SWF ou outro recurso que deva ser exibido para o visitante. A classificação do nome da criação contém o nome que você informou para essa criação na interface do DFA. |

As outras duas classificações, Ferramenta de entrega (DoubleClick for Advertisers) e Canal (anúncio de banner), têm os mesmos valores para qualquer campanha do DFA e ajudam a diferenciar os dados importados do DFA.

## Desduplicação do SearchCenter {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

A integração do DFA agora conta com reconhecimento do Adobe SearchCenter. Ao ativar a eliminação da duplicação do SearchCenter por meio do assistente do Data Connectors, os visitantes orientados por pesquisa não farão com que os dados sejam obtidos do servidor Floodlight do DFA e *`s.campaign`* não será preenchido pelo DFA, permitindo que o SearchCenter preencha. Além disso, o DFA e o SearchCenter agora preenchem valores de desduplicação nas variáveis de cada produto.

A lista abaixo descreve a lógica que é habilitada quando a desduplicação do SearchCenter é habilitada:

Se **[!UICONTROL DFA]** > **[!UICONTROL Desduplicação do SearchCenter]** é selecionado no assistente:

* No caso de um click-through do DFA, a integração preencherá a cadeia de caracteres “DFA Clickthrough” na eVar SCM configurada.
* No caso de um view-through do DFA, a integração preencherá a cadeia de caracteres “DFA Viewthrough” na eVar SCM.

Se **[!UICONTROL SearchCenter]** > **[!UICONTROL Desduplicação do DFA]** é selecionado no assistente:

* No caso de um view-through do DFA, a integração preencherá a cadeia de caracteres “DFA Viewthrough” na eVar SCM.

> [!NOTE] Se SearchCenter > Desduplicação DFA for habilitado e o parâmetro de cadeia de caracteres de consulta do SearchCenter for definido, a visita não será considerada para processamento no DFA. Isso significa que o parâmetro de cadeia de caracteres de consulta do SearchCenter deve ser diferente do parâmetro de click-through do DFA, e nenhum anúncio de exibição deve definir o parâmetro de cadeia de caracteres de consulta do SearchCenter.

