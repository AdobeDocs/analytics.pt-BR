---
description: Saiba como migrar regras de processamento do Mobile Services para a Adobe Analytics
title: Migrar regras de processamento do Mobile Services para o Adobe Analytics
translation-type: tm+mt
source-git-commit: d6601640d06f65dd1ddd09cb9bde0267df20eec3
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 6%

---


# Migrar regras de processamento do Mobile Services para o Adobe Analytics

Este documento fornece instruções sobre como migrar quaisquer regras de processamento adicionais - além das Medições de ciclo de vida - que você criou na interface do usuário do Mobile Services para a Adobe Analytics.

As regras de processamento são usadas para mover valores das variáveis de Dados de contexto para props e eVars. Por exemplo, você pode colocar o valor de uma variável de dados de contexto de &quot;termo de pesquisa&quot; no valor de um eVar de variável de comércio e substituir esse valor em cada ocorrência. Sem as regras de processamento, as variáveis de dados de contexto não têm significado e não preenchem nenhum relatório no Analytics.

Este documento também mostra como fazer relatórios de uso móvel no Analysis Workspace.

## Migrar regras de processamento

Se você estiver aproveitando o Mobile Services para obter funcionalidades complementares, como regras de processamento e recursos de uso do relatórios, poderá alternar para a interface do usuário do Analytics (regras de processamento, interface do usuário ou Analysis Workspace) para realizar essas funções. Para Medições de ciclo de vida, ou regras que foram configuradas na interface do usuário das regras de processamento AA, você não precisa fazer nenhuma migração. As Medições de ciclo de vida são métricas &quot;predefinidas&quot; que são automaticamente coletadas quando o SDK móvel é implementado pela primeira vez no aplicativo.

No entanto, se você configurar quaisquer regras de processamento adicionais na interface do usuário do Mobile Services (além das Medições de ciclo de vida), deverá migrá-las para que você possa editá-las ou excluí-las no Analytics depois de perder o acesso ao Mobile Services.

1. Log in to `experience.adobe.com` and go to Mobile Services.
1. Clique no ícone de engrenagem de um aplicativo móvel cujos mapeamentos de variável de contexto você deseja migrar para o Adobe Analytics.
1. Clique no item de menu **[!UICONTROL Gerenciar variáveis e métricas]** e clique na guia Variáveis **** personalizadas. Aqui, você pode ver quais mapeamentos de Variável de contexto (dados de contexto) foram adicionados à configuração. Anote essas configurações (ou faça uma captura de tela). Exemplo:

   ![Variável de contexto](assets/context-var.png)

1. No Experience Cloud, alterne para a Adobe Analytics e verifique se você está no mesmo conjunto de relatórios móvel que estava procurando no Mobile Services.
1. Vá até **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Geral]** > Regras **[!UICONTROL de]** processamento.
1. Clique em **[!UICONTROL Adicionar regra]**.
1. Ignore as condições e prossiga para adicionar as mesmas variáveis de contexto que existem no Mobile Services.

   ![Regra de processamento](assets/proc-rule.png)

1. Clique em **[!UICONTROL Salvar]**.

## Relatórios de uso de dispositivos móveis no Analysis Workspace

Além das métricas e dimensões móveis (se o conjunto de relatórios estiver habilitado para o Mobile Services), a Analysis Workspace contém vários modelos de projeto do Mobile que podem facilitar a análise:

* **[!UICONTROL Mensagens]**: Concentra-se no desempenho de mensagens de push e no aplicativo.
* **[!UICONTROL Localização]**: Inclui um mapa que mostra os dados de localização.
* **[!UICONTROL Principais métricas]**: Mantenha o controle das métricas principais do seu aplicativo.
* **[!UICONTROL Uso]** do aplicativo: Quantos usuários, inicializações e primeiras inicializações do aplicativo tiveram e qual foi a duração média da sessão?
* **[!UICONTROL Aquisição]**: Como os links de aquisição móvel estão se saindo?
* **[!UICONTROL Desempenho]**: Como o aplicativo está funcionando e onde os usuários estão tendo problemas?
* **[!UICONTROL Retenção]**: Quem são meus usuários leais e o que eles fazem?
* **[!UICONTROL Viagens]**: Quais são os padrões de uso proeminentes do meu aplicativo?

Este é um trecho do modelo de uso do aplicativo móvel:

![Uso do aplicativo móvel](assets/mobile-app-usage.png)

Para acessar os modelos:

1. Log in to `experience.adobe.com` and select Analytics.
1. Verifique se você está em um conjunto de relatórios habilitado para o Mobile Services.
1. Click the **[!UICONTROL Workspace]** tab.
1. Clique em **[!UICONTROL Criar novo projeto]**.
1. Selecione qualquer um dos modelos de dispositivos móveis e clique em **[!UICONTROL Criar]**.

## Migrar outros recursos do Mobile Services

A seguinte funcionalidade do Mobile Services também tem vínculos com o Adobe Analytics, mas requer um SKU Adobe Analytics adquirido:

* Links de aquisição
* Mensagens por push
* Mensagens no aplicativo
* Gerenciamento de pontos de interesse de localização

Se você estiver aproveitando o Mobile Services para a funcionalidade paga, não terá um caminho de migração viável para outras ferramentas internas/externas:

* Para links de aquisição, podemos direcioná-lo para parceiros de Adobe para atender às suas necessidades.
* As mensagens de push e as mensagens no aplicativo estão disponíveis no Adobe Campaign Standard e no Adobe Campaign Classic (somente push). No entanto, o conjunto de dados subjacente usado para definição de metas é diferente. Sugerimos trabalhar com sua equipe de conta do Adobe para determinar as opções de migração para dados de mensagens.
* Para a funcionalidade Local, é recomendável adotar o novo Serviço [de Localização da](https://www.adobe.com/experience-platform/location-service.html)Adobe Experience Platform, que é gratuito para todos os clientes do AEP.
