---
title: Visão geral da implementação com lançamento
description: Saiba como implementar o Adobe Analytics usando o Adobe Experience Platform Launch
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Visão geral da implementação com lançamento

Durante a vida útil do Adobe Analytics, a Adobe ofereceu vários métodos diferentes para implementar o código no seu site para a coleta de dados. O método recomendado atual da Adobe é o Adobe Experience Platform Launch.

O Launch é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite que você implante código personalizado. Todas essas tarefas podem ser realizadas sem depender de nenhuma equipe de desenvolvimento em sua organização para atualizar o código em seu site.

Todos os clientes com um contrato ativo da Adobe Experience Cloud podem usar o Launch. Se você não tiver certeza se tem acesso, entre em contato com um dos administradores de sistema da Experience Cloud de sua organização.

## Fluxo de trabalho geral

A execução de uma implementação usando o Launch segue estas etapas:

1. **Obtenha acesso ao Launch**: Você pode obter acesso ao Launch por meio de um administrador de sistema em sua organização.
2. **Criar uma propriedade**: As propriedades são contêineres abrangentes usados para fazer referência aos dados do gerenciamento de tags.
3. **Implantar em um ambiente** de desenvolvimento: Tenha um ambiente em que você possa interagir com o desenvolvimento de tags.
4. **Validar e publicar na produção**: Certifique-se de que tudo está funcionando e publique-o ao vivo.

Consulte [Criar uma propriedade do Analytics no Adobe Experience Platform Launch](create-analytics-property.md) para começar.

## Recursos adicionais

O lançamento pode ser altamente personalizado. Saiba mais sobre como aproveitar ao máximo o Adobe Analytics, incluindo os dados corretos na implementação.

* [Iniciar documentação](https://docs.adobe.com/content/help/en/launch/using/overview.html): Saiba como a interface funciona e quais extensões estão disponíveis.
* [Extensão](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html)do Adobe Analytics: Use a extensão do Analytics para enviar dados ao Adobe Analytics.
* [Variáveis](../vars/overview.md)de implementação: Determine quais variáveis você deseja enviar para os servidores de coleta de dados.
