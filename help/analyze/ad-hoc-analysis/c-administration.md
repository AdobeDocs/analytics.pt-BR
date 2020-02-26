---
description: Configure usuários e saiba mais sobre amostra de dados.
title: Administração
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Administração

Configure usuários e saiba mais sobre amostra de dados.

Para obter a ajuda do [!DNL Admin Console], consulte a [Referência do Analytics](https://marketing.adobe.com/resources/help/pt_BR/reference/index.html).

## Licenças de usuário {#concept_C1440741C77C471EB38A243B013EA620}

O usuário precisa receber uma licença de usuário antes de poder efetuar logon. As licenças de usuário são para uso simultâneo. Os usuários podem compartilhar licenças de usuário, mas o número de usuários ao mesmo tempo é limitado ao número de licenças de usuário adquiridas.

<!-- 

c_user_license.html

 -->

Quando o número de usuários conectados ultrapassa o número de licenças disponíveis, uma caixa de diálogo notifica o usuário de que todas as licenças disponíveis estão sendo usadas. A posição do usuário na fila é mostrada juntamente com um link para verificar novamente a posição na fila. Quando uma licença é disponibilizada, o usuário é notificado por email e uma caixa de diálogo pop-up indicando que a Ad Hoc Analysis está disponível para acesso. O usuário tem então 15 minutos para responder antes de perder sua posição na fila.

## Conceder licenças de usuário {#task_22AE669703EC48BA9685414538D8B1FA}

Etapas que descrevem como os administradores locais de Reports and Analytics podem conceder licenças aos usuários por meio do sistema de permissões.

<!-- 

t_user_licenses.xml

 -->

1. Faça logon no [!DNL Experience Cloud].
1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Gerenciamento de Usuário]**.
1. Clique em **[!UICONTROL Editar grupos]**.

   Se a sua empresa adquiriu licenças do usuário, o grupo de [!UICONTROL Usuários da licença da Ad Hoc Analysis] aparece na coluna [!UICONTROL Nome do grupo]. O número de licenças disponíveis para logon de usuários também é mostrado.

1. Clique em **[!UICONTROL Editar]**.
1. Em [!UICONTROL Atribuir logons de usuários], selecione os usuários que deseja adicionar ao grupo e clique em **[!UICONTROL Adicionar.]**
1. Clique em **[!UICONTROL Salvar grupo]**.

   O sistema de licenças não limita o número de usuários que são adicionados a um grupo. Há uma utilização limitada simultânea do número de licenças de usuário adquiridas.

## Gerenciar sessões de usuário {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

Etapas que descrevem como um administrador pode encerrar a sessão de um usuário. Este recurso não evita que um usuário que tenha a sessão encerrada efetue o logon novamente.

<!-- 

t_managing_users.xml

 -->

1. Clique em **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Gerenciamento do usuário]** e clique em **[!UICONTROL Gerenciar usuários]**.
1. Localize o usuário e clique em **[!UICONTROL Encerrar.]**

   Na página [!UICONTROL Sessões ativas da Ad Hoc Analysis], o usuário que estiver inativo por mais tempo aparece no topo da lista.

## Permissões {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

O acesso aos conjuntos de ferramentas de relatório do é configurado no [!DNL Administration Console]. É possível configurar permissões no nível do conjunto de relatórios. Por exemplo, se houver diversos conjuntos de relatórios ativados, mas você não quiser conceder a todos os usuários o acesso a todos eles é possível criar grupos com conjuntos de relatórios específicos e depois designar esses usuários ao grupo aplicável.

## Adicionar um usuário ao grupo Acesso a todos os relatórios {#task_E821BF3B4FDB434D844A98AAB15487A9}

Etapas que descrevem como conceder acesso a todos os conjuntos de relatórios a usuários não administradores.

<!-- 

t_permissions.xml

 -->

1. Faça logon pela **[!UICONTROL Experience Cloud]**.
1. Clique em **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL Gerenciamento de usuário]** > **[!UICONTROL Editar grupos]**.
1. Clique em **[!UICONTROL Acesso a Todos os Relatórios]**.
1. Em [!UICONTROL Usuários Disponíveis], selecione o usuário e clique em **[!UICONTROL Adicionar.]**
1. Clique em **[!UICONTROL Salvar grupo]**.

## Criar grupos de permissão {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

Crie grupos de permissões para usuários não administradores de conjuntos de relatórios específicos.

<!-- 

t_permission_groups.xml

 -->

1. Faça logon pela **[!UICONTROL Experience Cloud]**.
1. Clique em **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL Gerenciamento de usuário]** > **[!UICONTROL Editar grupos]**.
1. Criar um grupo de permissões para usuários não administradores que inclua conjuntos de relatórios ativados por Ad Hoc Analysis os quais você deseja disponibilizar para os usuários.

   Os conjuntos de relatórios disponíveis para o usuário são exibidos no menu [!UICONTROL Report Cloud] ao criar um novo projeto.

## Configurar Políticas de Proxy em Java {#task_3B03F58519544025B55CF54FACF8F4F5}

Etapas que descrevem como configurar as políticas de proxy, se você receber um erro de conexão do servidor.

<!-- 

t_proxy_policies.xml

 -->

A Ad Hoc Analysis usa o HTTP para se comunicar com o servidor. Ele está sujeito às mesmas políticas de proxy que o outro tráfego HTTP.

1. No [!DNL Windows Control Panel], inicie o [!UICONTROL Painel de controle Java].
1. Na aba **[!UICONTROL Geral]**, clique em **[!UICONTROL Configurações de Rede]**.
1. Selecione **[!UICONTROL Usar Configurações do Navegador]** ou configure manualmente as configurações de proxy.
1. Clique em **[!UICONTROL OK]** e em **[!UICONTROL OK]** novamente no [!UICONTROL Painel de Controle de Java].

## Como é feita a amostragem de dados {#concept_8433CFD38E0243849E92DF4F1E743AC3}

Exemplos de dados do visitante são usados para produzir relatórios relevantes e precisos. O intervalo de datas é usado como fatia de dados de um projeto carregado. Uma fatia representa geralmente o mês atual e os dois meses anteriores.

<!-- 

c_overview_data_sampling.xml

 -->

Para processamento otimizado, a Ad Hoc Analysis usa aproximadamente 750 milhões como máximo de ocorrências por fatia. (Ocorrências = exibições de página + eventos.)

Para chegar à taxa de amostragem projetada as ocorrências projetadas são calculadas por conjunto de dados e, em seguida, este valor é dividido por 750 milhões, como mostrado aqui:

* (Média de acessos diários x número de dias na fatia)/750 milhões

Por exemplo, se você tem 10 milhões de ocorrências em um dia, com uma fatia de dados de 90 dias:

* (10.000.000 x 90) / 750.000.000 = 1,2

Portanto, para manter o número de ocorrência para essa fatia de 90 dias abaixo de 750.000.000, os dados podem ser coletados em 1,2:1, mas como são usadas amostras em números inteiros, a taxa de amostragem é de 2:1.

Como outro exemplo, se você tem 10 milhões de ocorrências em um dia, com uma fatia de dados para 365 dias:

* (10.000.000 x 365) / 750.000.000 = 4.8

Então, para manter o número de ocorrências para essa fatia de 365 dias abaixo de 750.000.000, os dados poderiam ser coletados em 4,8:1. Utilizando números inteiros, a taxa de amostragem é 5:1.
