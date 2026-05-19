---
title: Perfis de produto para o Adobe Analytics
description: Saiba como os perfis de produtos podem ser usados como predefinições de permissão que os administradores de produtos podem atribuir aos usuários em uma organização.
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
role: Admin
TQID: https://experienceleague.adobe.com/pEMsqMvXmpASV9-DOBoZHzbWp88v5kJioww9H1nJkzY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c67272a6-888e-425e-9e97-a87304637eed
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f570a4d2e66c2af8ad85ab097078dd95c574fc83
workflow-type: tm+mt
source-wordcount: 686
ht-degree: 62%

---

# Perfis de produto para o Adobe Analytics

Os perfis de produtos são predefinições de permissão que os administradores de produtos podem atribuir aos usuários em uma organização. Se você criar um perfil de produto e atribuir um usuário do CX Enterprise a esse perfil, ele herdará os itens de permissão contidos no perfil do produto.

Para obter informações gerais sobre perfis de produtos, incluindo a criação de perfis de produtos e a atribuição de usuários, consulte [Gerenciar perfis de produtos para usuários corporativos](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) no guia do usuário Enterprise.

## Administradores do perfil do produto

Os administradores de perfil de produto são um grupo opcional que pode adicionar ou remover usuários desse perfil de produto. Observe que um administrador de perfil de produto não é o mesmo que um administrador de produto:

* Os administradores de perfil de produto não têm acesso total ao Adobe Analytics. O acesso total ao Adobe Analytics é reservado a administradores de produtos.
* Os administradores de perfis de produtos não podem ajustar itens de permissões em seus perfis de produtos.
* Os administradores de perfis de produtos podem atribuir ou remover perfis de produtos para grupos de usuários.
* Os administradores de perfis de produtos são ideais para líderes ou gerentes de equipes que precisam apenas conceder e gerenciar acesso ao Adobe Analytics para sua equipe. Eles não precisariam incomodar administradores de sistema ou administradores de produtos para conceder acesso ao Adobe Analytics.

Para obter informações sobre como atribuir administradores de perfil de produto, consulte a seção “Gerenciar administradores de perfil de produto” no artigo, [Gerenciar perfis de produto para usuários corporativos](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) no guia do usuário Enterprise.

## Itens de permissão do Adobe Analytics

As permissões mínimas necessárias em um único perfil de produto para acessar o Adobe Analytics são as seguintes:

* O perfil de produto deve ter acesso a pelo menos um conjunto de relatórios
* O perfil de produto deve pertencer ao item de permissão Ferramentas do Analytics **Workspace Project Access**.

### Conjuntos de relatórios

Concede acesso aos conjuntos de relatórios que pertencem a sua organização do Analytics. Um usuário deve pertencer a pelo menos um conjunto de relatórios para ter acesso ao Adobe Analytics.

### Métricas

Concede acesso às métricas em seu conjunto de relatórios. As métricas são listadas como seu respectivo componente no Analysis Workspace.

As métricas personalizadas são rotuladas como &quot;Evento personalizado 1-1000&quot; para mantê-las independentes dos conjuntos de relatórios. Se &#39;Evento personalizado 1&#39; for um item de permissão ativado, esse usuário terá acesso a event1 em todos os conjuntos de relatórios no perfil do produto.

### Dimensões

Concede acesso às dimensões em seu conjunto de relatórios. As dimensões são listadas como seu respectivo componente no Analysis Workspace.

As variáveis personalizadas, como eVars, são rotuladas como &quot;Conversão personalizada 1-250&quot; para mantê-las independentes dos conjuntos de relatórios. Se &#39;Conversão personalizado 1&#39; for um item de permissão ativado, esse usuário terá acesso a eVar1 em todos os conjuntos de relatórios no perfil do produto.

### Ferramentas do conjunto de relatórios

Os itens de permissão das Ferramentas do conjunto de relatórios concedem acesso aos recursos específicos dos conjuntos de relatórios aos quais o usuário tem acesso. Consulte [Ferramentas do conjunto de relatórios](report-suite-tools.md) para obter uma lista completa de itens de permissão e descrições.

### Ferramentas do Analytics

Os itens de permissão das ferramentas do Analytics concedem acesso a recursos que não dependem das configurações do conjunto de relatórios. Consulte [Permissões de perfil de produto para Ferramentas do Analytics](analytics-tools.md) para obter uma lista completa de itens de permissão e descrições.

## Desenvolvedores de perfil do produto

Os desenvolvedores são semelhantes aos usuários, mas eles têm a capacidade de usar a API corporativa do CX no Adobe Developer. Consulte [Gerenciar desenvolvedores](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no guia do usuário Enterprise para obter mais informações. Se um usuário receber acesso de desenvolvedor para qualquer perfil, ele poderá acessar o Dev Console (console.adobe.io) e editar integrações do Adobe Analytics. As chamadas e respostas da API do Analytics autorizadas para o usuário dependem das permissões de rede de todos os perfis aos quais o usuário tem acesso de desenvolvedor.

Por exemplo, com permissões de perfil que incluem todas as métricas, todas as dimensões e um conjunto de relatórios, um desenvolvedor pode tornar as chamadas de API relevantes para qualquer componente nesse conjunto de relatórios. Se o item de permissão Detecção de anomalias for adicionado, as respostas da API poderão incluir dados de anomalias. Como regra geral, se um perfil conceder acesso a um cenário na interface do Adobe Analytics, o acesso do desenvolvedor a um perfil definido de forma semelhante ativará as chamadas e respostas da API correspondentes.
