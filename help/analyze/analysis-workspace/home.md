---
title: Visão geral do Analysis Workspace
description: O Analysis Workspace é a principal ferramenta de análise do Adobe Analytics. Ele permite usar painéis, tabelas, visualizações e outros componentes para dar vida aos dados, preparar um conjunto de dados, compartilhar e agendar projetos, entre outros recursos.
feature: Workspace Basics
role: User, Admin
exl-id: de95551d-09ea-4461-9bb4-b4ef235e9cd2
source-git-commit: 33e2ca30ec385861c35c9d06e870d5b38d8f2e34
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 36%

---

# Visão geral do Analysis Workspace

O Analysis Workspace permite criar análises rapidamente para coletar insights e compartilhá-los com outras pessoas. Usando a interface do navegador de arrastar e soltar, você pode criar a análise, adicionar visualizações para dar vida aos dados, preparar um conjunto de dados e compartilhar e agendar projetos com qualquer pessoa que você escolher.

O vídeo a seguir fornece uma breve visão geral com exemplos do que é possível.

>[!VIDEO](https://video.tv.adobe.com/v/26266/?quality=12)

## Áreas do Analysis Workspace

A imagem a seguir e a tabela que a acompanha explicam algumas das principais áreas no Analysis Workspace:

![Visão geral do Analysis Workspace](assets/analysis-workspace-overvew.png)

| Localização na imagem | Nome e função |
|---------|----------|
| A | **Trilho à esquerda:** Contém guias para adicionar painéis, visualizações e componentes ao Analysis Workspace. Também contém o ícone do Dicionário de dados usado para abrir o Dicionário de dados. |
| B | **Painel esquerdo:** Dependendo da guia que está selecionada no painel à esquerda, essa área contém painéis, visualizações ou componentes individuais. |
| C | **Tela:** Essa é a área principal na qual você arrasta o conteúdo dos trilhos à esquerda para criar seu projeto. O projeto é atualizado dinamicamente à medida que você adiciona painéis, visualizações e componentes à tela. |
| D | **Menu suspenso do Conjunto de relatórios:** Para cada painel no Analysis Workspace, o menu suspenso do conjunto de relatórios permite escolher o conjunto de relatórios que você deseja usar como fonte de dados. |

## Recursos no Analysis Workspace {#analysis}

Veja a seguir alguns dos principais recursos disponíveis no Analysis Workspace:

### Painéis

**Painéis** são usados para organizar a análise em um projeto e podem conter muitas tabelas e visualizações. Muitos dos painéis fornecidos no Analysis Workspace geram um conjunto completo de análises com base em algumas entradas do usuário. No painel à esquerda, selecione o ícone **[!UICONTROL Painéis]** superior para ver uma lista completa de painéis disponíveis.

Para saber mais sobre painéis, consulte [Visão geral dos painéis](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=pt-BR).

![](assets/build-panels.png)

### Visualizações

**Visualizações**, como um gráfico de barras ou de linhas, pode ser usado para dar vida visualmente aos dados. No painel à esquerda, selecione o ícone do meio de **[!UICONTROL Visualizações]** para ver a lista completa de visualizações disponíveis.

Para saber mais sobre visualizações, consulte [Visão geral das visualizações](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=pt-BR).

![](assets/build-visualizations.png)

### Componentes

Os componentes no Analysis Workspace consistem no seguinte:

* Dimensões

* Métricas

* Segmentos

* Intervalos de datas

Para saber mais sobre cada um desses tipos de componentes, consulte [Visão geral dos componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).

Cada um desses tipos de componentes pode ser adicionado a uma visualização (como uma tabela de forma livre) para começar a responder suas perguntas comerciais.

Após entender a terminologia do componente, é possível arrastar os componentes para as visualizações (incluindo as tabelas de forma livre) para [criar sua análise](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

![](assets/build-components.png)

### Dicionário de dados

O dicionário de dados do Analysis Workspace ajuda os usuários e administradores a acompanhar e compreender melhor os componentes em seu ambiente do Analytics.

Para saber mais sobre o Dicionário de dados, consulte [Visão geral do dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

## Começar a usar o Analysis Workspace

### Faça logon no Adobe Analytics {#login}

Para começar a usar o Analysis Workspace, faça logon no Adobe Analytics acessando [experience.adobe.com/analytics](https://experience.adobe.com/analytics). A página Projetos do Analysis Workspace é exibida por padrão. Se um projeto específico tiver sido selecionado para você, esse projeto será exibido por padrão.

### Crie um projeto {#new-project}

Uma análise no Analysis Workspace é conhecida como uma [projeto](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

Você pode criar um projeto no Analysis Workspace, conforme descrito em [Criar projetos](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

Os projetos podem ser organizados em pastas e subpastas, conforme descrito em [Pastas no Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Salvar e compartilhar um projeto

À medida que você cria uma análise no Analysis Workspace, seu trabalho é [salvo automaticamente](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

Quando você terminar de criar o projeto e ele estiver reunindo insights acionáveis, o projeto estará pronto para ser consumido por outros. Você pode compartilhar o projeto com usuários e grupos em sua organização ou até mesmo com pessoas fora de sua organização. Para obter informações sobre como compartilhar um projeto, consulte [Compartilhar projetos](/help/analyze/analysis-workspace/curate-share/share-projects.md).

<!--

Maybe add this back in if the video isn't too outdated. Otherwise, delete this section.

### Project management in Analysis Workspace

The following video provides an overview of project management in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/24035/?quality=12)

-->

## Use o Virtual Analyst para entender melhor as anomalias

O Virtual Analyst é um conjunto de recursos no Adobe Analytics que usa algoritmos preditivos e aprendizado de máquina para fornecer insights sobre anomalias que afetam sua empresa. Ele permite automatizar os fluxos de trabalho mais comuns e caros da ciência de dados para identificar a causa de comportamentos incomuns em seus dados.

O Virtual Analyst inclui os seguintes recursos:

* [Detecção de anomalias:](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) oferece um método estatístico para determinar como uma determinada métrica foi alterada com relação aos dados anteriores.
* [Análise de contribuição:](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md) ajuda a determinar os fatores que mais contribuem para anomalias em seus dados.
* [Alertas inteligentes:](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) identifica anomalias em seus dados de maneira proativa e envia notificações para você, resultando em insights mais rápidos.

## Recursos adicionais {#resources}

* A Adobe oferece centenas de [tutoriais de treinamento em vídeo do Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/overview.html?lang=pt-BR).
* Consulte [Notas da versão do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR#analytics) para saber mais sobre novos recursos.
* Uma excelente maneira de conhecer o Analysis Workspace é por meio do modelo do tutorial de treinamento do Analysis Workspace. Este modelo aborda a terminologia e as etapas comuns para criar sua primeira análise no Workspace. Para iniciar o tutorial:
   1. No [!UICONTROL **Workspace**] no Adobe Analytics, selecione **[!UICONTROL Aprendizagem]** à esquerda.
   1. Selecionar **[!UICONTROL Abrir tutorial]**.
      ![](assets/training-tutorial.png)

