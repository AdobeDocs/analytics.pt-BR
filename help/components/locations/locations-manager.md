---
description: Configurar a conta de importação na nuvem e o local onde os dados de classificação podem ser carregados
keywords: Analysis Workspace
title: Gerenciador de locais
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 273fea86cde8880d9c9e03ac9c6a99b75f70f6cd
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 1%

---

# Gerenciador de locais

O Gerenciador de locais permite exibir, criar, editar ou excluir contas e locais. Eles podem ser usados para qualquer uma das seguintes finalidades:

* Exportação de arquivos usando [Feeds de dados](/help/export/analytics-data-feed/create-feed.md)
* Exportar relatórios usando [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importação de esquemas usando o [Conjuntos de classificações](/help/components/classifications/sets/overview.md)

## Exibir, filtrar e pesquisar locais

O Gerenciador de locais permite exibir todos os locais criados. Os administradores do sistema podem visualizar os locais criados por todos os usuários.

1. Para acessar o Gerenciador de locais no Adobe Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Localizações]**.

1. (Condicional) Se você for um administrador do sistema, poderá ativar a [!UICONTROL **Exibir locais para todos os usuários**] opção para exibir locais criados por todos os usuários em sua organização. <!-- Maybe add a screenshot? This is new functionality -->

1. Filtrar ou pesquisar a lista de locais:

   * **Filtro:** Selecione o ícone Filtro para filtrar a lista de locais.

     Você pode filtrar locais por **[!UICONTROL Tipo de localização]**, **[!UICONTROL Conta]** ou **[!UICONTROL Criado por]**.

     ![Filtros de locais](assets/locations-filters.png)

   * **Pesquisar:** No campo de pesquisa, comece digitando o nome do local que deseja visualizar. Os resultados são filtrados à medida que você digita. As seguintes colunas são pesquisadas: **Nome do local**, **Tipo de localização**, **Conta**, e **Criado por**.

1. (Opcional) Se você tiver mais de 1.000 locais, apenas os primeiros 1.000 serão exibidos. Selecionar [!UICONTROL **Carregar mais**] para carregar mais mil locais.

## Configurar colunas no Gerenciador de locais

As seguintes colunas estão disponíveis no Gerenciador de locais. Para personalizar as colunas exibidas na tabela, selecione o **Personalizar tabela** ícone ![Ícone Personalizar tabela](assets/customize-table-icon.png).

* **[!UICONTROL Nome do local]**: O nome do local. Selecione o menu de 3 pontos ao lado de um nome de local para [editar a localização](/help/components/locations/configure-import-locations.md) ou excluí-lo.
* **[!UICONTROL Tipo de localização]**: o tipo de conta associado à localização.
* **[!UICONTROL Conta]**: a conta específica associada à localização.
* **Aplicativo**: o tipo de aplicativo com o qual o local pode ser usado (como feeds de dados, Data Warehouse ou conjuntos de classificação).
* **[!UICONTROL Usado pela última vez]**: a data em que o local foi usado pela última vez.
* **[!UICONTROL Criado por]**: o usuário que criou o local.
* **[!UICONTROL Data de criação]**: a data em que o local foi criado.

## Criar e gerenciar locais

É possível criar, editar e excluir locais.

### Criar um local

Para obter informações sobre como criar um local, consulte [Configurar locais de importação e exportação na nuvem](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### Editar um local

Para obter informações sobre como editar um local, consulte [Configurar locais de importação e exportação na nuvem](/help/components/locations/configure-import-locations.md).

### Excluir um local

>[!IMPORTANT]
>
>Se um local for excluído, quaisquer arquivos de Feed de dados, relatórios de Data Warehouse ou esquemas de conjunto de classificações associados ao local excluído falharão na próxima vez que forem usados.
>
>Se você excluir um local, deverá [editar os feeds de dados](/help/export/analytics-data-feed/create-feed.md), [Data Warehouse relatórios](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), e [Esquemas de conjuntos de classificação](/help/components/classifications/sets/manage/schema.md) para usar um local funcional.

Para excluir um local no Gerenciador de locais no Adobe Analytics:

1. Selecionar **[!UICONTROL Componentes]** > **[!UICONTROL Localizações]**, em seguida, selecione a [!UICONTROL **Localizações**] guia.

1. Selecione o menu de 3 pontos no [!UICONTROL **Nome do local**] para o local que você deseja excluir.

1. Clique em [!UICONTROL **Excluir**].

## Editar uma conta

1. Para editar contas no Gerenciador de locais no Adobe Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Localizações]**, em seguida, selecione a [!UICONTROL **Contas de localização**] guia.

1. (Condicional) Se você for um administrador do sistema, poderá ativar a [!UICONTROL **Exibir contas para todos os usuários**] opção para exibir locais criados por todos os usuários em sua organização. <!-- Maybe add a screenshot? This is new functionality -->


1. Selecionar [!UICONTROL **Exibir detalhes**] na conta que deseja editar.

1. Faça as alterações desejadas e selecione [!UICONTROL **Salvar**].

## Exibir chaves de conta

Depois de criar uma conta, você poderá exibir todas as chaves de conta associadas a ela. Talvez seja necessário exibir essas informações se você não concluiu a configuração da conta com seu provedor de nuvem quando [configuração original da conta](/help/components/locations/configure-import-accounts.md).

Para exibir chaves associadas a uma conta de exportação:

1. No Adobe Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Localizações]**, em seguida, selecione a [!UICONTROL **Contas de localização**] guia.

1. Selecione o ícone de 3 pontos na conta que deseja editar e selecione [!UICONTROL **Chaves da conta**].

## Excluir uma conta

1. No Adobe Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Localizações]**, em seguida, selecione a [!UICONTROL **Contas de localização**] guia.

1. Selecione o ícone de 3 pontos na conta que deseja editar e selecione [!UICONTROL **Excluir conta**]
