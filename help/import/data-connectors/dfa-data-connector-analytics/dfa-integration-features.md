---
description: 'Depois de ativada, a integração do DFA do Data Connectors oferece as seguintes métricas para seus relatórios do Adobe Analytics '
keywords: DFA
title: Recursos da integração
topic: Data connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Recursos da integração {#integration-features}

Depois de ativada, a integração do DFA dos Data Connectors oferece as seguintes métricas para seus relatórios do Adobe Analytics:

* Visualizações
* Cliques do DFA
* Impressões
* (opcional) Dados de custo do DFA
* (opcional) Erros de Query do DFA, Tempo limite

>[!NOTE] Essa integração não é compatível com rastreadores de cliques (antigos comandos de cliques). Os rastreadores de cliques são usados para registrar o número de cliques em links de texto, links em mensagens de email ou em outros elementos codificados em um site da Web.

A integração do DFA dos Data Connectors automaticamente constrói códigos de rastreamento do DFA com os dados apresentados pelo DFA. Esses códigos de rastreamento são construídos para identificar exclusivamente um anúncio, juntamente com sua disposição e criação associadas. A seguir, é apresentada a estrutura do código de rastreamento, dependendo da versão da integração. A versão 1.5 é a seguinte:

![](assets/DFA_id_struct1_5.png)

A versão 2.0 é semelhante a:

![](assets/DFA_id_struct2.png)

Essas IDs servem como uma chave compartilhada entre o Genesis e o DFA para associar as classificações e métricas corretas.

| ID do site | O site de terceiros no qual o anúncio foi hospedado. A classificação Nome do site fornece um nome descritivo dessa ID do site. |
|---|---|
| ID do anúncio | Uma ID da mensagem comercial que é entregue a um usuário. A classificação de Nome do anúncio contém o nome do anúncio, conforme definido pela sua organização no sistema do DFA. Por exemplo: `Hybrid Coup Textlink - Build`. |
| ID de posicionamento | Uma representação em sua conta do DFA de um site, parte de um site ou grupo de sites nos quais você adquiriu espaço para anúncios. |
| ID de criação | A imagem, Flash SWF ou outro recurso que deve ser exibido ao visitante. A classificação do Nome Criativo contém o nome que você forneceu a este anúncio na interface do DFA. |

As outras duas classificações, Ferramenta de Delivery (DoubleClick for Advertisers) e Canal (Anúncio de banner) têm os mesmos valores para qualquer campanha do DFA e ajudam a distinguir os dados importados do DFA.

## Desduplicação do SearchCenter {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

A integração do DFA agora conta com reconhecimento do Adobe SearchCenter. Ao ativar a eliminação da duplicação do SearchCenter por meio do assistente do Data Connectors, os visitantes orientados por pesquisa não farão com que os dados sejam obtidos do servidor Floodlight do DFA e *`s.campaign`* não será preenchido pelo DFA, permitindo que o SearchCenter preencha. Além disso, o DFA e o SearchCenter agora preenchem valores de desduplicação nas variáveis de cada produto.

A lista abaixo descreve a lógica que é habilitada quando a desduplicação do SearchCenter é habilitada:

Se **[!UICONTROL DFA]** > **[!UICONTROL SearchCenter deduplication]** estiver selecionado no assistente:

* No caso de um click-through do DFA, a integração preencherá a cadeia de caracteres “DFA Clickthrough” na eVar SCM configurada.
* No caso de um view-through do DFA, a integração preencherá a cadeia de caracteres “DFA Viewthrough” na eVar SCM.

Se **[!UICONTROL SearchCenter]** > **[!UICONTROL DFA deduplication]** estiver selecionado no assistente:

* No caso de um view-through do DFA, a integração preencherá a cadeia de caracteres “DFA Viewthrough” na eVar SCM.

>[!NOTE] Se SearchCenter > Desduplicação DFA for habilitado e o parâmetro de cadeia de caracteres de consulta do SearchCenter for definido, a visita não será considerada para processamento no DFA. Isso significa que o parâmetro de cadeia de caracteres de consulta do SearchCenter deve ser diferente do parâmetro de click-through do DFA, e nenhum anúncio de exibição deve definir o parâmetro de cadeia de caracteres de consulta do SearchCenter.

