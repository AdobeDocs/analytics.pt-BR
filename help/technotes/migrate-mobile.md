---
description: Saiba como migrar regras de processamento do Mobile Services para a Adobe Analytics
title: Migrar regras de processamento do Mobile Services para o Adobe Analytics
translation-type: tm+mt
source-git-commit: c2610bf25c960039ca8638cecbd05f3a8b28376f
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 18%

---


# Migrar regras de processamento do Mobile Services para o Adobe Analytics

Com o lançamento futuro (ainda não anunciado) da funcionalidade do Adobe Mobile Services, este documento fornece instruções sobre como migrar quaisquer regras de processamento adicionais - além das Medições de ciclo de vida - que você criou na interface do usuário do Mobile Services para a Adobe Analytics.

As regras de processamento são usadas para mover valores das variáveis de Dados de contexto para props e eVars. Por exemplo, você pode colocar o valor de uma variável de dados de contexto de &quot;termo de pesquisa&quot; no valor de um eVar de variável de comércio e substituir esse valor em cada ocorrência. Sem as regras de processamento, as variáveis de dados de contexto não têm significado e não preenchem nenhum relatório no Analytics.

Este documento também aborda o relatórios de uso móvel no Analysis Workspace e discute a viabilidade da migração de outras funcionalidades do Mobile Services.

## Migrar regras de processamento

Se você estiver aproveitando o Mobile Services para obter funcionalidades complementares, como regras de processamento e recursos de uso do relatórios, poderá alternar para a interface do usuário do Analytics (regras de processamento, interface do usuário ou Analysis Workspace) para realizar essas funções. Para Medições de ciclo de vida, ou regras que foram configuradas na interface do usuário das regras de processamento AA, você não precisa fazer nenhuma migração. As Medições de ciclo de vida são métricas &quot;predefinidas&quot; que são automaticamente coletadas quando o SDK móvel é implementado pela primeira vez no aplicativo.

No entanto, se você configurar quaisquer regras de processamento adicionais na interface do usuário do Mobile Services (além das Medições de ciclo de vida), deverá migrá-las para que você possa editá-las ou excluí-las no Analytics depois de perder o acesso ao Mobile Services.

1. Faça logon em experience.adobe.com e vá para Mobile Services.
1. Clique no ícone de engrenagem de um aplicativo móvel cujos mapeamentos de variável de contexto você deseja migrar para o Adobe Analytics.
1. Clique no item de menu **[!UICONTROL Gerenciar variáveis e métricas]** e clique na guia Variáveis **** personalizadas. Aqui, você pode ver quais mapeamentos de Variável de contexto (dados de contexto) foram adicionados à configuração. Anote essas configurações (ou faça uma captura de tela). Exemplo:

   ![Variável de contexto](assets/context-var.png)

1. No Experience Cloud, alterne para a Adobe Analytics e verifique se você está no mesmo conjunto de relatórios móvel que estava procurando no Mobile Services.
1. Vá até Admin > Conjuntos de relatórios > Editar configurações > Geral > Regras de processamento.
1. Clique em Adicionar regra.
1. Ignore as condições e prossiga para adicionar as mesmas variáveis de contexto que existem no Mobile Services.

   ![Regra de processamento](assets/proc-rule.png)

## Relatórios de uso de dispositivos móveis no Analysis Workspace

Além das métricas e dimensões móveis (se o conjunto de relatórios estiver habilitado para o Mobile Services), a Analysis Workspace contém vários modelos de projeto do Mobile que podem facilitar a análise:

* Mensagens: focaliza o desempenho das mensagens no aplicativo e por push.
* Localização: inclui um mapa que exibe os dados de localização.
* Métricas principais: permite o controle das métricas principais do seu aplicativo.
* Uso do aplicativo: quantos usuários, inicializações e primeiras inicializações o aplicativo teve e qual foi a duração média das sessões?
* Aquisição: Como os links de aquisição móvel estão se saindo?
* Desempenho: como está o desempenho do aplicativo e que problemas os usuários estão tendo?
* Retenção: quem são meus usuários fiéis e o que eles fazem?
* Jornadas: quais são os principais padrões de uso do meu aplicativo?

Este é um trecho do modelo de uso do aplicativo móvel:

![Uso do aplicativo móvel](assets/mobile-app-usage.png)

Para acessar os modelos:

1. Faça logon em experience.adobe.com e selecione Analytics.
1. Verifique se você está em um conjunto de relatórios habilitado para o Mobile Services.
1. Clique na guia Espaço de trabalho.
1. Clique em Criar novo projeto.
1. Selecione qualquer um dos modelos móveis e clique em Criar.

## Migrar outros recursos do Mobile Services

A seguinte funcionalidade do Mobile Services também tem vínculos com o Adobe Analytics, mas requer um SKU Adobe Analytics adquirido:

* Links de aquisição
* Mensagens por push
* Mensagens no aplicativo
* Gerenciamento de pontos de interesse de localização

Se você estiver aproveitando o Mobile Services para a funcionalidade paga, não terá um caminho de migração viável para outras ferramentas internas/externas:

* Para links de aquisição, podemos direcioná-lo para parceiros de Adobe para atender às suas necessidades.
* Embora as opções de Mensagens de push e Mensagens no aplicativo sejam encontradas no Adobe Campaign Standard e no Adobe Campaign Classic (somente push), o conjunto de dados subjacente usado para definição de metas é diferente e nenhuma migração de dados ou mensagens de atividade é possível.
* Para a funcionalidade Local, é recomendável adotar o novo Serviço [de Localização da](https://www.adobe.com/experience-platform/location-service.html)Adobe Experience Platform, que é gratuito para todos os clientes do AEP.
