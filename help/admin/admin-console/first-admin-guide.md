---
title: Guia do primeiro administrador do Adobe Analytics
description: Saiba como começar a usar o Adobe Analytics, os tipos de função gerais e como fazer logon na interface do usuário.
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Guia do primeiro administrador do Adobe Analytics

Um primeiro administrador é o ponto de partida para permitir que o restante da organização use cada solução da Experience Cloud. Depois que um contrato for assinado, uma equipe de provisionamento da Adobe se prepara para a criação da conta. O primeiro administrador recebe um email com credenciais de logon antes da data de início do contrato. É altamente recomendado garantir que as informações de contato do primeiro administrador sejam precisas e fornecidas à Adobe antes da assinatura do contrato.

## Principais funções ao usar a Experience Cloud

Se sua organização adquiriu o Adobe Analytics, há várias funções principais a serem consideradas:

- **Administradores do Adobe Analytics:** esses usuários têm acesso total a tudo no Adobe Analytics, incluindo configurações de conjunto de relatórios e permissões de usuário. Dependendo de como sua organização está estruturada, pessoas ou equipes diferentes podem ser responsáveis por diversos aspectos da administração do Analytics. Por exemplo, uma pessoa é responsável por designar quais variáveis usar em uma implementação. Outra pessoa pode ser responsável por permitir que os usuários extraiam os relatórios corretamente, garantindo que todos tenham as permissões corretas. Identifique pelo menos um usuário que possa ser responsável pelas configurações do conjunto de relatórios e pelas permissões de usuário do Analytics, e que possa convidar outros administradores do Analytics a partir daí.
- **Administradores do Adobe Experience Platform Launch:** esses usuários têm acesso total a tudo o que estiver disponível no Experience Platform Launch, incluindo permissões de publicação, criação de contêineres e permissões de usuário. Esses usuários não são necessariamente programadores, mas é útil ter pelo menos um conhecimento iniciante de HTML, CSS e JavaScript. Eles são responsáveis por trabalhar com os proprietários de sites da organização para implementar o código do Experience Platform Launch no site. Identifique pelo menos um usuário que possa ser responsável pela implementação da organização e que possa convidar outros administradores do Experience Platform Launch a partir daí.
- **Proprietários do site:** esses indivíduos ou equipes são responsáveis pela codificação e desenvolvimento do site. Eles não precisam de contas, mas querem trabalhar com os administradores do Experience Platform Launch para obter o código do Experience Platform Launch e implementá-lo no site.
- **Usuários finais:** esses usuários normalmente visualizam relatórios e procuram respostas para perguntas comerciais. Os administradores do Analytics concedem a esses usuários permissões para trabalhar no produto.

Como primeiro administrador, sua função pode se sobrepor em uma ou mais dessas funções. Desde que cada uma dessas responsabilidades básicas esteja atendida, você pode conceder permissões para que outras pessoas trabalhem em sua organização.

## Conceder acesso de administrador de produto ao Analytics

Os administradores de nível de sistema não têm acesso direto aos produtos. No entanto, eles podem dar acesso a si mesmos adicionando-se como um administrador de nível de produto. Se quiser conceder acesso a você ou outras pessoas ao Adobe Analytics, siga estas etapas.

1. Faça logon no [Admin Console](https://adminconsole.adobe.com/) com as credenciais da Adobe ID.
1. Clique na guia Produtos na parte superior. Todos os produtos comprados pela sua organização estão à esquerda. Clique em Adobe Analytics e, em seguida, clique no botão Novo perfil.
1. Nomeie esse perfil como 'Acesso completo ao administrador do Analytics' e clique em Concluído.
1. Na página Perfis de produto, clique no perfil recém-criado e na guia Permissões.
1. Clique em um dos itens de linha de permissão. Se a Inclusão automática estiver disponível, ative-a. Se a Inclusão automática não estiver disponível, clique em Adicionar tudo. Ambas as opções movem todos os itens de permissão para a coluna direita.
1. Clique em Salvar. Repita a etapa acima para todas as categorias de permissão.
1. Quando todas as categorias de permissão forem concedidas ao perfil, volte para a página Visão geral clicando em Visão geral na parte superior.
1. No bloco Adobe Analytics, clique em "Atribuir usuários".
1. Digite o endereço de email ao qual você deseja conceder acesso total ao Analytics e atribua a ele o perfil de acesso completo do administrador recém-criado. Clique em Salvar.
1. O usuário agora tem acesso total ao Adobe Analytics.

## Conceder acesso de administrador de produto no Experience Platform Launch

O acesso do administrador de produto para o Experience Platform Launch é quase idêntico à concessão de acesso do administrador de produto para o Analytics.

1. Faça logon no Admin Console com as credenciais da Adobe ID.
1. Clique na guia Produtos na parte superior. Todos os produtos comprados pela sua organização estão à esquerda. Clique em Experience Platform Launch by Adobe e no botão Novo perfil.
1. Nomeie esse perfil como 'Acesso completo ao administrador do Experience Platform Launch' e clique em Concluído.
1. Na página Perfis de produto, clique no perfil recém-criado e na guia Permissões.
1. Clique em um dos itens de linha de permissão. Se a Inclusão automática estiver disponível, ative-a. Se a Inclusão automática não estiver disponível, clique em Adicionar tudo. Ambas as opções movem todos os itens de permissão para a coluna direita.
1. Clique em Salvar. Repita a etapa acima para todas as categorias de permissão.
1. Quando todas as categorias de permissão forem concedidas ao perfil, volte para a página Visão geral clicando em Visão geral na parte superior.
1. No bloco Experience Platform Launch by Adobe, clique em 'Atribuir usuários'.
1. Digite o endereço de email ao qual você deseja conceder acesso total ao Analytics e atribua a ele o perfil de acesso completo do administrador recém-criado. Clique em Salvar.
1. O usuário agora tem acesso total ao Experience Platform Launch.

## Próximas etapas

[Criar um conjunto de relatórios](create-report-suite.md): faça com que o administrador do Analytics faça logon na ferramenta e crie um conjunto de relatórios para a coleta de dados

[Criar uma propriedade no Experience Platform Launch](/help/implement/implement-with-launch/create-analytics-property.md): faça com que o administrador do Experience Platform Launch faça logon na ferramenta e crie uma propriedade a ser implementada no site
