---
title: Visão geral da implementação com o Launch
description: Saiba como implementar o Adobe Analytics usando o Adobe Experience Platform Launch
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Visão geral da implementação com o Launch

Durante a vida útil do Adobe Analytics, a Adobe ofereceu vários diferentes métodos de implementação do código no site para a coleta de dados. O método recomendado atual da Adobe é o Adobe Experience Platform Launch.

O Launch é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site.

Todos os clientes com um contrato ativo da Adobe Experience Cloud podem usar o Launch. Se não tiver certeza se tem acesso, entre em contato com um dos administradores de sistema da Experience Cloud na organização.

## Fluxo de trabalho geral

A execução de uma implementação usando o Launch segue estas etapas:

1. **Obter acesso ao Launch**: você pode obter acesso ao Launch por meio de um administrador de sistema na organização.
2. **Criar uma propriedade**: as propriedades são contêineres abrangentes usados para fazer referência aos dados do gerenciamento de tags.
3. **Implantar em um ambiente de desenvolvimento**: tenha um ambiente em que possa interagir com o desenvolvimento de tags.
4. **Validar e publicar na produção**: certifique-se de que tudo está funcionando e publique em tempo real.

Consulte [Criar uma propriedade do Analytics no Adobe Experience Platform Launch](create-analytics-property.md) para começar.

## Recursos adicionais

O Launch pode ser altamente personalizado. Saiba mais sobre como aproveitar ao máximo o Adobe Analytics, incluindo os dados corretos na implementação.

* [Documentação do Launch](https://docs.adobe.com/content/help/pt-BR/launch/using/overview.html): saiba como a interface funciona e quais extensões estão disponíveis.
* [Extensão do Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html): use a extensão do Analytics para enviar dados ao Adobe Analytics.
* [Variáveis de implementação](../vars/overview.md): determine quais variáveis você deseja enviar para os servidores de coleta de dados.
