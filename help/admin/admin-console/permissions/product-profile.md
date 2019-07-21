---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: tm+mt

---
# Perfis de produtos no Adobe Analytics

Os perfis de produtos são uma predefinição de permissão que os administradores de produtos podem atribuir a usuários em uma organização. Se você criar um perfil de produto e atribuir um usuário da Experience Cloud a esse perfil de produto, herdará os itens de permissão contidos no perfil do produto.

See [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) in the Enterprise user guide for general information on product profiles.

## Administradores de perfil de produto

Os administradores de perfil de produto são um grupo opcional que pode adicionar ou remover usuários para esse perfil de produto. Observe que um administrador de perfil de produto não é o mesmo que um administrador de produto:

* Os administradores de perfil de produto são responsáveis pela lista de usuários de um perfil de produto.
* Os administradores de perfil de produto não têm acesso total ao Adobe Analytics. O acesso completo ao Adobe Analytics é reservado para administradores de produtos.
* Os administradores de perfil de produto não podem ajustar os itens de permissões no perfil de produto; um administrador de produto deve fazer ajustes de item de permissão.
* Os administradores de perfil de produto são ideais para equipes de equipe ou gerentes que simplesmente precisam conceder e gerenciar o acesso ao Adobe Analytics para sua equipe. Os indivíduos não precisariam ignorar administradores do sistema ou administradores de produtos para conceder acesso ao Adobe Analytics.

## Itens de permissão do Adobe Analytics

As permissões mínimas necessárias em um perfil de produto para acessar o Adobe Analytics são as seguintes:

* O perfil do produto deve ter acesso a pelo menos um conjunto de relatórios
* The product profile must belong to the Analytics Tools permission item **Analysis Workspace Access** (or **Reports &amp; Analytics Access**)

### Conjuntos de relatórios

Concede acesso aos conjuntos de relatórios que pertencem à sua organização do Analytics. Um usuário deve pertencer a pelo menos um conjunto de relatórios a ser acessado para usar o Adobe Analytics.

### Métricas

Concede acesso a métricas em seu conjunto de relatórios. As métricas são listadas como seu respectivo componente na Analysis Workspace, ou se a métrica estiver disponível em Relatórios e análises, disponíveis como um item de menu em Métricas do site.

Métricas personalizadas são rotuladas como "Evento personalizado 1-1000" para mantê-las independentes dos conjuntos de relatórios. Se "Evento personalizado 1" for um item de permissão ativado, esse usuário terá acesso ao evento 1 em todos os conjuntos de relatórios no perfil de produto.

### Dimensões

Concede acesso a dimensões em seu conjunto de relatórios. As dimensões são listadas como seu respectivo componente na Analysis Workspace, ou se a dimensão estiver disponível em Relatórios e análises, disponíveis como um item de menu.

Variáveis personalizadas, como evars, são rotuladas como "Conversão personalizada 1-250" para mantê-las independentes dos conjuntos de relatórios. Se "Conversão personalizada 1" for um item de permissão ativado, esse usuário terá acesso à evar 1 em todos os conjuntos de relatórios no perfil de produto.

### Ferramentas do conjunto de relatórios

Os itens de permissão das ferramentas do conjunto de relatórios concedem acesso aos recursos específicos dos conjuntos de relatórios aos quais o usuário tem acesso. See [Report Suite Tools](report-suite-tools.md) for a full list of permission items and descriptions.

### Ferramentas do Analytics

Os itens de permissão das ferramentas do Analytics concedem acesso a recursos independentes das configurações do conjunto de relatórios. See [Analytics Tools](analytics-tools.md) for a full list of permission items and descriptions.

## Desenvolvedores de perfil de produto

Developers are similar to users, except they are granted the ability to use the Experience Cloud API on Adobe I/O. See [Manage Developers](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Enterprise user guide for more information.
