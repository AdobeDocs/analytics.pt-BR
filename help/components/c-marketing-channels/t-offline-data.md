---
description: Adicione dados offline aos relatórios do Canal de marketing.
seo-description: Adicione dados offline aos relatórios do Canal de marketing.
seo-title: Adicionar dados offline
solution: Analytics
subtopic: Canais de marketing
title: Adicionar dados offline
topic: Reports and Analytics
uuid: bbf4661a-b6b1-4a89-a3cf-ae8dd785d37d
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Adicionar dados offline

Adicione dados offline aos relatórios do Canal de marketing.

Canais online permitem classificar dados de visitantes que chegam por meio de fontes como mecanismo de pesquisa, anúncio na Internet, domínio de referência ou campanha de email. Canais offline se aplicam a visitantes que encontram seu site por meio de anúncios de TV, jornais ou revistas.

**Integrar fontes de dados nos relatórios de Canal de marketing**

Se você deseja integrar [dados de dados fornecidos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_faq.html) nos relatórios de Canal de marketing, tenha em mente o seguinte:

* Toda ocorrência padrão transmitida a relatórios de análise com uma [transactionID](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_Transaction_ID.html) é processada pelas regras de processamento de canal de marketing como normal.
* Todas as origens de dados de `transactionID` transmitidas na análise são associadas automaticamente ao mesmo canal de marketing em que a ocorrência foi processada.
* Todos os outros dados de origem de dados não passam pelas regras de processamento de canal de marketing.

Consulte a ajuda [Origens de dados](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html) para obter mais informações sobre as Origens de dados.

Para classificar os dados do canal offline, é preciso ativar os dados nas Fontes de dados, e depois descarregar e editar o modelo.

Consulte "Trabalhar com fontes de dados" no [Guia do usuário de fontes de dados](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).

**Adicionar dados offline**

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. Na página de Fontes de dados, clique em **[!UICONTROL Criar.]**
1. Under **[!UICONTROL 1. Selecione Categoria]**, selecione **[!UICONTROL Dados do canal offline]**.
1. Under **[!UICONTROL 2. Selecione Tipo]**, selecione **[!UICONTROL Dados do canal offline]**.
1. Click **[!UICONTROL Activate.]**
1. Mapeie as métricas offline para as métricas de relatórios seguindo os avisos do Assistente de ativação da origem de dados.
1. Faça o download e edite o arquivo de modelo em um editor, como o Excel.

   Consulte "Criar um arquivo de origens de dados" no [Guia do usuário de origens de dados](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).

1. Carregue o arquivo descrito em "Carregamento de um arquivo de origens de dados" no [Guia do usuário de origens de dados](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).
