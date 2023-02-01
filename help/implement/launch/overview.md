---
title: Implementar o Adobe Analytics usando a extensão Analytics
description: Saiba como implementar o Adobe Analytics usando tags e extensão Analytics
feature: Launch Implementation
source-git-commit: 472faef9c6ef99d4e58f2f5a9a71ca8d058f0ee2
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 48%

---

# Implementar o Adobe Analytics usando a extensão Analytics

Durante a vida útil do Adobe Analytics, a Adobe ofereceu vários diferentes métodos de implementação do código no site para a coleta de dados. Adobe recomendado é por meio de tags

Tags na Adobe Experience Platform é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site.

Todos os clientes com um contrato ativo da Adobe Experience Cloud podem usar tags. Se não tiver certeza se tem acesso, entre em contato com um dos administradores de sistema da Experience Cloud na organização.

Uma visão geral de alto nível das tarefas de implementação:

![Adobe Analytics usando o fluxo de trabalho de extensão do Analytics](../assets/analytics-extension-annotated.png)

| | Tarefa | Mais Informações | |-| —| | 1 | Certifique-se de que **definiu um conjunto de relatórios**. | [Gerenciador do Conjunto de relatórios](../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Criar uma camada de dados** para gerenciar o rastreamento dos dados no seu site. | [Criar uma camada de dados](../prepare/data-layer.md) | | 3 | **Criar uma propriedade de tag**. As propriedades são contêineres abrangentes usados para fazer referência aos dados do gerenciamento de tags.| [Criar uma propriedade de tag do Adobe Analytics](../launch/create-analytics-property.md) | | 4 | **Instalar a extensão Analytics** na propriedade da tag. Configure a extensão Analytics para enviar dados para o Adobe Analytics. | [Visão geral da extensão do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en) | | 5 | **Implantar em um ambiente de desenvolvimento**. Tenha um ambiente em que possa interagir com o desenvolvimento de tags. | [Implantar uma implementação do Analytics em um ambiente de desenvolvimento](./deploy-dev.md) | | 6 | **Validar e publicar na produção**. Adicione a propriedade da tag ao seu site. Em seguida, use elementos de dados, regras e assim por diante, para personalizar sua implementação.| [Validar uma implementação de desenvolvimento e publicar na produção](./validate-publish-prod.md) |

## Recursos adicionais

As tags podem ser altamente personalizadas. Saiba mais sobre como aproveitar ao máximo o Adobe Analytics, incluindo os dados corretos na implementação.

- [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR#): saiba como a interface funciona e quais extensões estão disponíveis.

- [Variáveis de implementação](../vars/overview.md): determine quais variáveis você deseja enviar para os servidores de coleta de dados.
