---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: ht

---
# Perfis de produto no Adobe Analytics

Os perfis de produtos são uma predefinição de permissão que os administradores de produtos podem atribuir aos usuários em uma organização. Se você criar um perfil de produto e atribuir um usuário da Experience Cloud a esse perfil, ele herdará os itens de permissão contidos no perfil do produto.

Consulte [Gerenciar produtos e perfis](https://helpx.adobe.com/br/enterprise/using/manage-products-and-profiles.html) no Guia do usuário do Enterprise para obter informações gerais sobre perfis de produtos.

## Administradores do perfil do produto

Os administradores de perfil de produto são um grupo opcional que pode adicionar ou remover usuários desse perfil de produto. Observe que um administrador de perfil de produto não é o mesmo que um administrador de produto:

* Os administradores de perfil de produto são responsáveis apenas pela lista de usuários de um perfil de produto.
* Os administradores de perfil de produto não têm acesso total ao Adobe Analytics. O acesso total ao Adobe Analytics é reservado a administradores de produtos.
* Os administradores de perfil de produto não podem ajustar os itens de permissões em seu perfil de produto; um administrador do produto deve fazer ajustes de item de permissão.
* Os administradores de perfil de produto são ideais para líderes ou gerentes de equipes que precisam apenas conceder e gerenciar acesso ao Adobe Analytics para sua equipe. Eles não precisariam incomodar administradores de sistema ou administradores de produtos para conceder acesso ao Adobe Analytics.

## Itens de permissão do Adobe Analytics

As permissões mínimas necessárias em um perfil de produto para acessar o Adobe Analytics são as seguintes:

* O perfil de produto deve ter acesso a pelo menos um conjunto de relatórios
* O perfil de produto deve pertencer ao item de permissão Ferramentas do Analytics **Acesso à Analysis Workspace** (ou **Acesso ao Reports &amp; Analytics**)

### Conjuntos de relatórios

Concede acesso aos conjuntos de relatórios que pertencem a sua organização do Analytics. Um usuário deve pertencer a pelo menos um conjunto de relatórios para ter acesso ao Adobe Analytics.

### Métricas

Concede acesso às métricas em seu conjunto de relatórios. As métricas são listadas como seu respectivo componente na Analysis Workspace, ou se a métrica estiver disponível no Reports &amp; Analytics, disponível como um item de menu em Métricas do site.

As métricas personalizadas são rotuladas como &quot;Evento personalizado 1-1000&quot; para mantê-las independentes dos conjuntos de relatórios. Se &#39;Evento personalizado 1&#39; for um item de permissão ativado, esse usuário terá acesso a event1 em todos os conjuntos de relatórios no perfil do produto.

### Dimensões

Concede acesso às dimensões em seu conjunto de relatórios. As dimensões são listadas como seu respectivo componente na Analysis Workspace, ou se a dimensão estiver disponível no Reports &amp; Analytics, disponível como um item de menu.

As variáveis personalizadas, como eVars, são rotuladas como &quot;Conversão personalizada 1-250&quot; para mantê-las independentes dos conjuntos de relatórios. Se &#39;Conversão personalizado 1&#39; for um item de permissão ativado, esse usuário terá acesso a eVar1 em todos os conjuntos de relatórios no perfil do produto.

### Ferramentas do conjunto de relatórios

Os itens de permissão das Ferramentas do conjunto de relatórios concedem acesso aos recursos específicos dos conjuntos de relatórios aos quais o usuário tem acesso. Consulte [Ferramentas do conjunto de relatórios](report-suite-tools.md) para obter uma lista completa de itens de permissão e descrições.

### Ferramentas do Analytics

Os itens de permissão das ferramentas do Analytics concedem acesso a recursos que não dependem das configurações do conjunto de relatórios. Consulte [Ferramentas do Analytics](analytics-tools.md) para obter uma lista completa dos itens de permissão e descrições.

## Desenvolvedores de perfil do produto

Os desenvolvedores são semelhantes aos usuários, mas eles têm a capacidade de usar a API da Experience Cloud no Adobe I/O. Consulte [Gerenciar desenvolvedores](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no guia do usuário Enterprise para obter mais informações.
