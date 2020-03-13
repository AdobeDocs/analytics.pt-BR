---
description: 'null'
title: Mapear objetos de camada de dados para elementos de dados
uuid: null
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Mapear objetos de camada de dados para elementos de dados


Depois de [criar uma camada](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html) de dados para sua implementação, é possível mapear objetos nela para elementos [de dados no Launch](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element). Os elementos de dados são blocos de construção para seu mapa de dados que podem ser aproveitados de várias maneiras. Você pode usar elementos de dados para coletar, organizar e fornecer dados nas soluções do Adobe Platform, incluindo seus relatórios do Analytics.

Para mapear objetos de camada de dados para Iniciar elementos de dados:

1. Em Iniciar, clique no nome da propriedade à qual deseja adicionar o elemento de dados. Se você ainda não tiver configurado uma propriedade, consulte as instruções para [Criar uma propriedade](https://docs.adobe.com/content/help/en/core-services-learn/implementing-in-websites-with-launch/configure-launch/launch.html)de inicialização.

2. Click **Data Elements** and then click **Create New Data Element**.

   ![criar elemento de dados](assets/createelement.png)


3. Insira um nome para seu elemento de dados. Esse nome deve ser um rótulo simples que corresponda a uma variável JavaScript na camada de dados que você deseja rastrear.

4. Para Extensão, selecione **Principal.** Essa extensão inclui todas as variáveis de que você precisará.

5. For **Data Element Type**, select **JavaScript Variable**. Digite o nome **da variável** Javascript no campo aplicável. Isso deve corresponder ao nome exato do objeto na camada de dados JavaScript.

6. Para Valor **** Padrão, digite qualquer valor que você deseja estabelecer por padrão ou deixe-o em branco, se apropriado.

7. De acordo com suas práticas, você pode selecionar as opções para forçar valores em minúsculas e impor texto limpo (o Launch aplicará o espaçamento convencional).

8. Especifique a duração que você deseja para ter valores de armazenamento do Launch para o novo elemento de dados.

9. Clique em **Salvar**.

O exemplo a seguir mostra um elemento de dados Nome da página no Launch criado para a variável JavaScript ``pageName`` na camada de dados:

![Especificar elemento](assets/new_element.png)


Com os objetos da camada de dados mapeados para elementos de dados, é possível aproveitá-los para preencher as variáveis do Analytics. Para obter mais informações, consulte [Mapear elementos de dados para variáveis](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)do Analytics.
