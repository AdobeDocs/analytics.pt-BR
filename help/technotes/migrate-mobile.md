---
description: Saiba como migrar regras de processamento do Mobile Services para o Adobe Analytics
title: Migrar regras de processamento do Mobile Services para o Adobe Analytics
exl-id: ea183c1a-a85e-4f4e-a7f6-f947b939e9d9
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '686'
ht-degree: 100%

---

# Migrar regras de processamento do Mobile Services para o Adobe Analytics

Este documento fornece instruções sobre como migrar regras de processamento adicionais, além das Métricas de ciclo de vida, que você criou na interface do usuário do Mobile Services para o Adobe Analytics.

As regras de processamento são usadas para mover valores das variáveis de Dados de contexto para props e eVars. Por exemplo, você pode colocar o valor de uma variável de dados de contexto de &quot;termo de pesquisa&quot; no valor de uma eVar de variável de comércio e substituir esse valor em cada ocorrência. Sem as regras de processamento, as variáveis de dados de contexto não têm significado e não preenchem nenhum relatório no Analytics.

Este documento também mostra como fazer relatórios de uso móvel no Analysis Workspace.

## Migrar regras de processamento

Se você estiver usando o Mobile Services para obter funcionalidades complementares, como regras de processamento e recursos de relatório de uso, será possível migrar facilmente para a interface do Analytics (interface de regras de processamento ou Analysis Workspace) para realizar essas funções. Para Métricas de ciclo de vida, ou regras configuradas na interface das regras de processamento do AA, não é necessário fazer nenhuma migração. As Métricas de ciclo de vida são métricas “predefinidas” que são automaticamente coletadas quando o SDK móvel é implementado pela primeira vez no aplicativo.

No entanto, se você configurar regras de processamento adicionais na interface do Mobile Services (além das Métricas de ciclo de vida), migre-as para poder editá-las/excluí-las no Analytics depois de perder o acesso ao Mobile Services.

1. Faça logon em `experience.adobe.com` e acesse o Mobile Services.
1. Clique no ícone de engrenagem de um aplicativo móvel cujos mapeamentos de variável de contexto você deseja migrar para o Adobe Analytics.
1. Clique no item de menu **[!UICONTROL Gerenciar variáveis e métricas]** e, em seguida, clique na guia **[!UICONTROL Variáveis personalizadas]**. Aqui, você pode ver quais mapeamentos de variável de contexto (dados de contexto) foram adicionados à configuração. Anote essas configurações (ou faça uma captura de tela). Exemplo:

   ![Variável de contexto](assets/context-var.png)

1. Na Experience Cloud, mude para o Adobe Analytics e verifique se você está no mesmo conjunto de relatórios móveis que estava visualizando no Mobile Services.
1. Acesse **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de processamento]**.
1. Clique em **[!UICONTROL Adicionar regra]**.
1. Ignore as condições e prossiga para adicionar as mesmas variáveis de contexto que existem no Mobile Services.

   ![Regra de processamento](assets/proc-rule.png)

1. Clique em **[!UICONTROL Salvar]**.

## Relatórios de uso de dispositivos móveis no Analysis Workspace

Além das métricas e dimensões móveis (se o conjunto de relatórios está habilitado para Mobile Services), o Analysis Workspace contém vários modelos de projeto para dispositivos móveis que podem facilitar a análise:

* **[!UICONTROL Mensagens]**: concentra-se no desempenho de mensagens no aplicativo e por push.
* **[!UICONTROL Localização]**: inclui um mapa que exibe os dados de localização.
* **[!UICONTROL Métricas principais]**: controla as métricas principais do seu aplicativo.
* **[!UICONTROL Uso do aplicativo]**: quantos usuários, inicializações e primeiras inicializações o aplicativo teve e qual foi a duração média das sessões?
* **[!UICONTROL Aquisição]**: como os links de aquisição móvel estão se saindo?
* **[!UICONTROL Desempenho]**: como está o desempenho do aplicativo e onde os usuários estão tendo problemas?
* **[!UICONTROL Retenção]**: quem são meus usuários fiéis e o que eles fazem?
* **[!UICONTROL Jornadas]**: quais são os principais padrões de uso do meu aplicativo?

Este é um trecho do modelo de Utilização de aplicativos móveis:

![Uso de aplicativos móveis](assets/mobile-app-usage.png)

Para acessar os modelos:

1. Faça logon em `experience.adobe.com` e selecione Analytics.
1. Verifique se você está em um conjunto de relatórios habilitado para o Mobile Services.
1. Clique na guia **[!UICONTROL Workspace]**.
1. Clique em **[!UICONTROL Criar novo projeto]**.
1. Selecione qualquer um dos modelos do Mobile e clique em **[!UICONTROL Criar]**.

## Migrar outra funcionalidade do Mobile Services

A seguinte funcionalidade do Mobile Services também tem vínculos com o Adobe Analytics, mas requer uma SKU adquirida do Adobe Analytics:

* Links de aquisição
* Mensagens por push
* Mensagens no aplicativo
* Gerenciamento de pontos de interesse de localização

Se estiver aproveitando o Mobile Services para a funcionalidade paga, você não terá um caminho de migração viável para outras ferramentas internas/externas:

* Para Links de aquisição, podemos direcionar você aos Parceiros da Adobe para atender às suas necessidades.
* As mensagens de push e as mensagens no aplicativo estão disponíveis no Adobe Campaign Standard e no Adobe Campaign Classic (somente para push). No entanto, o conjunto de dados subjacente usado para o direcionamento é diferente. Sugerimos trabalhar com sua equipe de conta da Adobe para determinar as opções de migração para dados de mensagens.
* Para a funcionalidade Localização, é recomendável adotar o novo [Serviço de localização da Adobe Experience Platform](https://www.adobe.com/br/experience-platform/location-service.html), que é gratuito para todos os clientes da AEP.
