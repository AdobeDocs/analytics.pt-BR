---
title: Implementar o Adobe Analytics com tags no Adobe Experience Platform
description: Saiba como implementar o Adobe Analytics usando tags
feature: Launch Implementation
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 94%

---

# Implementar o Adobe Analytics com tags no Adobe Experience Platform

Durante a vida útil do Adobe Analytics, a Adobe ofereceu vários diferentes métodos de implementação do código no site para a coleta de dados. O método recomendado atual da Adobe é por meio de tags na Adobe Experience Platform.

Tags na Adobe Experience Platform é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site.

Todos os clientes com um contrato ativo da Adobe Experience Cloud podem usar tags. Se não tiver certeza se tem acesso, entre em contato com um dos administradores de sistema da Experience Cloud na organização.

## Fluxo de trabalho geral

A execução de uma implementação usando tags segue estas etapas:

1. **Obter acesso a tags**: você pode obter acesso às tags da Platform por meio de um administrador do sistema em sua organização.
2. **Criar uma propriedade de tag**: propriedades são recipientes abrangentes usados para referenciar dados de gerenciamento de tags.
3. **Implantar em um ambiente de desenvolvimento**: tenha um ambiente em que possa interagir com o desenvolvimento de tags.
4. **Validar e publicar na produção**: certifique-se de que tudo está funcionando e publique em tempo real.

Consulte [Criar uma propriedade de tag do Analytics](create-analytics-property.md) para começar.

## Recursos adicionais

As tags podem ser altamente personalizadas. Saiba mais sobre como aproveitar ao máximo o Adobe Analytics, incluindo os dados corretos na implementação.

* [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR#): saiba como a interface funciona e quais extensões estão disponíveis.
* [Extensão do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=pt-BR): use a extensão do Analytics para enviar dados ao Adobe Analytics.
* [Variáveis de implementação](../vars/overview.md): determine quais variáveis você deseja enviar para os servidores de coleta de dados.
