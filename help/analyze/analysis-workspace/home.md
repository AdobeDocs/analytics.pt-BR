---
title: Visão geral do Analysis Workspace
description: Saiba mais sobre o Analysis Workspace, a principal ferramenta de análise do Adobe Analytics. Use projetos, painéis, tabelas, visualizações e outros componentes para dar vida aos dados, bem como preparar e compartilhar a sua análise.
feature: Workspace Basics
role: User, Admin
exl-id: de95551d-09ea-4461-9bb4-b4ef235e9cd2
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '1384'
ht-degree: 99%

---

# Visão geral do Analysis Workspace {#analysis-workspace-overview}

O Analysis Workspace permite criar análises rapidamente para coletar insights e compartilhá-los com outras pessoas. Usando a interface de arrastar e soltar do navegador, você pode criar a análise, adicionar visualizações para dar vida aos dados, preparar um conjunto de dados e compartilhar e agendar [projetos](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) com quem você escolher.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visão geral do Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-overview){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

## Interface

A imagem a seguir e a tabela que a acompanha explicam os principais elementos da interface do Analysis Workspace:

![Janela do Analysis Workspace com destaque para várias seções da interface](assets/analysis-workspace-overview.png)

| Localização | Nome e função |
|:---------:|----------|
| A | Contém o nome do projeto, uma estrutura de menu para acessar a funcionalidade, um botão ![Voltar](/help/assets/icons/ChevronLeft.svg) para retornar à lista de projetos e um botão **[!UICONTROL Compartilhar]** para [compartilhar o projeto do Workspace](/help/analyze/analysis-workspace/curate-share/share-projects.md). <br/>Selecione o nome do projeto (por exemplo: Novo projeto) a qualquer momento para alterar o nome. <br/>Selecione ![Remover dos favoritos](/help/assets/icons/StarOutline.svg) para marcar seu projeto como um favorito ![Adicionar aos favoritos](/help/assets/icons/Star.svg). |
| B | **Painel de botões:** contém botões para acessar os [recursos](#features) principais do Analysis Workspace:<ul><li>![WebPage](/help/assets/icons/WebPage.svg) [[!UICONTROL Painéis]](/help/analyze/analysis-workspace/c-panels/panels.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL Visualizações]](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![Preparar](/help/assets/icons/Curate.svg) [[!UICONTROL Componentes]](/help/components/home.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL Índice]](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![Marcador](/help/assets/icons/Bookmark.svg) [[!UICONTROL Dicionário de dados]](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **Painel esquerdo:** esta área contém painéis individuais, visualizações, componentes ou listas. O conteúdo depende do botão selecionado no painel de botões. |
| D | **Tela:** essa é a área principal onde você arrasta o conteúdo dos painéis à esquerda para criar o projeto. O projeto é atualizado dinamicamente à medida que você adiciona painéis, visualizações a painéis e componentes a visualizações. É possível criar vários painéis, e dentro de cada painel é possível criar várias visualizações.<br/>Cada painel baseia-se em um conjunto de relatórios selecionado. O conjunto de relatórios selecionado determina os componentes disponíveis, como métricas e dimensões. Consulte [Painéis: conjunto de relatórios](/help/analyze/analysis-workspace/c-panels/panels.md#report-suite) para mais informações. |

## Recursos

Os principais recursos do Analysis Workspace estão disponíveis por meio do painel de botões:

| Ícone | Recurso | Descrição |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL Painéis]** | [Painéis](/help/analyze/analysis-workspace/c-panels/panels.md) são usados para organizar a análise em um projeto e podem conter muitas tabelas e visualizações. Muitos dos painéis fornecidos no Analysis Workspace geram um conjunto completo de análises com base em algumas informações inseridas pelo usuário. |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL Visualizações]** | As [visualizações](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) podem ser usadas para dar vida aos dados por meio de um gráfico de barras ou linhas. No painel mais à esquerda, clique no ícone de **[!UICONTROL Visualizações]** na parte central para ver a lista completa de visualizações disponíveis. |
| ![Preparar](/help/assets/icons/Curate.svg) | **[!UICONTROL Componentes]** | Os [Componentes](/help/components/home.md) incluem os seguintes elementos:<ul><li>![Dimensões](/help/assets/icons/Dimensions.svg) [Dimensões](/help/components/dimensions/overview.md)</li><li>![Evento](/help/assets/icons/Event.svg) [Métricas](/help/analyze/analysis-workspace/components/apply-create-metrics.md)</li><li>![Segmentação](/help/assets/icons/Segmentation.svg) [Segmentos](/help/components/segmentation/seg-overview.md)</li><li>![Calendário](/help/assets/icons/Calendar.svg) [Intervalos de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL Índice]** | O [índice](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) organiza todos os painéis e visualizações inclusos no projeto em uma lista que pode ser recolhida, permitindo acessar rapidamente um painel ou uma visualização específica. |
| ![Marcador](/help/assets/icons/Bookmark.svg) | **Dicionário de dados** | O [Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) ajuda usuários e admins a acompanhar e entender melhor os componentes em seus ambientes do Analytics. |


## Menu

A maior parte das funcionalidades do Analysis Workspace está disponível por meio do recurso de arrastar e soltar e por meio de menus de contexto em painéis, visualizações e componentes.

As funcionalidades também estão disponíveis por meio do menu do espaço de trabalho e das teclas de atalho. As teclas de atalho diferem dependendo do sistema operacional em que seu navegador está sendo executado. Consulte as tabelas abaixo para obter uma visão geral.

Observe que é possível usar os seguintes símbolos do teclado:

- **⇧** para **[!UICONTROL *Shift *]**.
- **⌘** para **[!UICONTROL *cmd *]**(command).
- **⌃** para **[!UICONTROL *ctrl *]**(control).
- **⌥** para **[!UICONTROL *opt *]**(option).
- **⎇** para **[!UICONTROL *alt *]**(alternar).

Consulte as tabelas abaixo para obter uma visão geral dos menus disponíveis.

| **[!UICONTROL Projeto]** | Atalho do Mac | Atalho do Windows | Descrição |
|---|---|---|---|
| **[!UICONTROL Criar projeto]** | **[!UICONTROL *shift+cmd+p *]** | **[!UICONTROL *shift+ctrl+p *]** | Criar um novo projeto. |
| **[!UICONTROL Criar um cartão de pontuação para dispositivos móveis]** | | | [Criar um novo cartão de pontuação para dispositivos móveis](/help/analyze/mobile-app/create-scorecard.md). |
| **[!UICONTROL Abrir...]** | **[!UICONTROL *cmd+o *]** | **[!UICONTROL *ctrl+o *]** | [Abrir um projeto existente](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-another-project). |
| **[!UICONTROL Abrir versão anterior...]** | **[!UICONTROL *opt+cmd+o *]** | **[!UICONTROL *alt+ctrl+o *]** | [Abrir versões anteriores do projeto](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version). |
| **[!UICONTROL Salvar]** | **[!UICONTROL *cmd+s *]** | **[!UICONTROL *ctrl+s *]** | [Salve o projeto](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-projects). |
| **[!UICONTROL Salvar com notas...]** | **[!UICONTROL *opt+cmd+s *]** | **[!UICONTROL *alt+ctrl+s *]** | [Adicionar notas à versão do projeto salva](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Salvar como...]** | **[!UICONTROL *shift+cmd+s *]** | **[!UICONTROL *shift+ctrl+s *]** | [Salve o projeto com outro nome e detalhes adicionais](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Atualizar projeto]** | **[!UICONTROL *opt+r *]** | **[!UICONTROL *alt+r *]** | Atualizar o projeto. |
| **[!UICONTROL Download em CSV]** | **[!UICONTROL *shift+cmd+v *]** | **[!UICONTROL *shift+ctrl+v *]** | Baixe o projeto como um arquivo CSV. |
| **[!UICONTROL Baixar o PDF]** | **[!UICONTROL *shift+cmd+b *]** | **[!UICONTROL *shift+ctrl+b *]** | Baixe o projeto como um documento PDF. |
| **[!UICONTROL Informações e configurações do projeto]** | | | Define configurações para seus projetos, como nome, tags, paleta de cores e muito mais. |
| **[!UICONTROL Configurações de usuário]** | | | [Configuração de preferências para o uso do Analysis Workspace](/help/analyze/analysis-workspace/user-preferences.md). |


| **[!UICONTROL Editar]** | Atalho do Mac | Atalho do Windows | Descrição |
|---|---|---|---|
| **[!UICONTROL Desfazer]** | **[!UICONTROL *cmd+z *]** | **[!UICONTROL *ctrl+z *]** | Desfaz a ação anterior. |
| **[!UICONTROL Refazer]** | **[!UICONTROL *cmd+shift+z *]** | **[!UICONTROL *ctrl+shift+z *]** | Refaz a ação anterior. |
| **[!UICONTROL Limpar tudo]** | **[!UICONTROL *opt+w *]** | **[!UICONTROL *alt+w *]** | Limpa todos os painéis no projeto atual. |

| **[!UICONTROL Inserir]** | Atalho do Mac | Atalho do Windows | Descrição |
|---|---|---|---|
| **[!UICONTROL Painel em branco]** | **[!UICONTROL *opt+b *]** | **[!UICONTROL *alt+b *]** | Insere um [painel em branco](/help/analyze/analysis-workspace/c-panels/blank-panel.md). |
| **[!UICONTROL Visualizadores simultâneos de mídia]** | **[!UICONTROL *opt+h *]** | **[!UICONTROL *alt+h *]** | Insere um painel [Visualizadores simultâneos de mídia](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md). |
| **[!UICONTROL Tempo gasto com a reprodução da mídia]** | **[!UICONTROL *opt+i *]** | **[!UICONTROL *alt+i *]** | Insere um painel [Tempo gasto com a reprodução da mídia](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md). |
| **[!UICONTROL Público-alvo médio a cada minuto de mídia]** | **[!UICONTROL *opt+m *]** | **[!UICONTROL *alt+m *]** | Insere um painel [Público-alvo médio por minuto de mídia](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md). |
| **[!UICONTROL Atribuição]** | **[!UICONTROL *opt+e *]** | **[!UICONTROL *alt+e *]** | Insere um painel de [Atribuição](/help/analyze/analysis-workspace/c-panels/attribution.md). |
| **[!UICONTROL Forma livre]** | **[!UICONTROL *opt+a *]** | **[!UICONTROL *alt+a *]** | Insere um painel de [Forma livre](/help/analyze/analysis-workspace/c-panels/freeform-panel.md). |
| **[!UICONTROL Insights rápidos]** | **[!UICONTROL *opt+j *]** | **[!UICONTROL *alt+j *]** | Insere um painel [Insights rápidos](/help/analyze/analysis-workspace/c-panels/quickinsight.md). |
| **[!UICONTROL Tabela de forma livre]** | **[!UICONTROL *opt+1 *]** | **[!UICONTROL *alt+1 *]** | Insere uma visualização de [Tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). |
| **[!UICONTROL Linha]** | **[!UICONTROL *opt+2 *]** | **[!UICONTROL *alt+2 *]** | Insere uma visualização de [Linha](/help/analyze/analysis-workspace/visualizations/line.md). |
| **[!UICONTROL Barra]** | **[!UICONTROL *opt+3 *]** | **[!UICONTROL *alt+3 *]** | Insere uma visualização de [Barra](/help/analyze/analysis-workspace/visualizations/bar.md). |
| **[!UICONTROL Combo]** | **[!UICONTROL *opt+4 *]** | **[!UICONTROL *alt+4 *]** | Insere uma visualização de [Combo](/help/analyze/analysis-workspace/visualizations/combo-charts.md). |


| **[!UICONTROL Componentes]** | Atalho do Mac | Atalho do Windows | Descrição |
|---|---|---|---|
| **[!UICONTROL Criar segmento...]** | **[!UICONTROL *shift+cmd+e *]** | **[!UICONTROL *shift+ctrl+e *]** | Criar um novo [segmento](/help/components/segmentation/segmentation-workflow/seg-create.md). |
| **[!UICONTROL Criar métrica...]** | **[!UICONTROL *shift+cmd+c *]** | **[!UICONTROL *shift+ctrl+c *]** | Cria uma nova [métrica calculada](/help/components/calculated-metrics/cm-overview.md). |
| **[!UICONTROL Criar intervalo de datas...]** | **[!UICONTROL *shift+cmd+d *]** | **[!UICONTROL *shift+ctrl+d *]** | Criar um novo [intervalo de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md). |
| **[!UICONTROL Criar anotação...]** | **[!UICONTROL *shift+cmd+o *]** | **[!UICONTROL *shift+ctrl+o *]** | Cria uma nova [anotação](/help/analyze/analysis-workspace/components/annotations/overview.md). |
| **[!UICONTROL Atualizar componentes]** | **[!UICONTROL *opt+shift+r *]** | **[!UICONTROL *alt+shift+r *]** | Atualiza os componentes no projeto. |

| **[!UICONTROL Compartilhar]** | Atalho do Mac | Atalho do Windows | Descrição |
|---|---|---|---|
| **[!UICONTROL Compartilhar com usuários do espaço de trabalho]** | **[!UICONTROL *cmd+h *]** | **[!UICONTROL *ctrl+h *]** | [Compartilha o projeto com outros usuários do espaço de trabalho](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization). |
| **[!UICONTROL Compartilhar com qualquer pessoa]** | **[!UICONTROL *opt+l *]** | **[!UICONTROL *alt+l *]** | [Compartilha uma versão somente leitura do projeto com qualquer pessoa](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project). |
| **[!UICONTROL Enviar arquivo]** | **[!UICONTROL opt+s]** | **[!UICONTROL *alt+s *]** | [Envia o projeto como um arquivo CSV ou PDF para outros destinatários](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Agendar exportação de arquivo]** | **[!UICONTROL *shift+opt+s *]** | **[!UICONTROL *shift+alt+s *]** | [Envia o projeto como um arquivo CSV ou PDF para outros destinatários conforme o cronograma definido](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Preparar dados do projeto]** | **[!UICONTROL *shift+cmd+g *]** | **[!UICONTROL *shift+ctrl+g *]** | [Prepara os dados do projeto](/help/analyze/analysis-workspace/curate-share/curate.md). |

| Ajuda | Descrição |
|---|---|
| **[!UICONTROL Vídeos]** | Abre o canal do YouTube do Customer Journey Analytics em uma nova guia do navegador. |
| **[!UICONTROL Documentação de ajuda]** | Abre a documentação (a que você está lendo agora) em uma nova guia do navegador. |
| **[!UICONTROL Fórum de ajuda]** | Abre o fórum das comunidades do Adobe Analytics na Experience League em uma nova guia do navegador. |
| **[!UICONTROL Teclas de atalho]** | Mostra uma visão geral das teclas de atalho que você pode usar no espaço de trabalho. |
| **[!UICONTROL Habilitar o depurador]** | Habilita o depurador. Seu projeto será recarregado. |
| **[!UICONTROL Desabilitar depurador]** | Desabilita o depurador. Seu projeto será recarregado. |
| **[!UICONTROL Desempenho]** | Exibe uma caixa de diálogo com métricas de **[!UICONTROL desempenho do Analysis Workspace]**. Use **[!UICONTROL Baixar como CSV]** para baixar um arquivo CSV das métricas de desempenho. |
| **[!UICONTROL Sobre o Workspace]** | Mostra uma caixa de diálogo **[!UICONTROL Sobre o Analysis Workspace]** com informações de versão, níveis de acesso a recursos e sinalizadores de recursos ativos. |

## Fontes de dados

A sincronização de visualizações permite controlar qual tabela de dados ou fonte de dados corresponde a uma visualização. Consulte [Gerenciar fontes de dados](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) para obter mais informações.

## Usar o Analysis Workspace


Para começar a usar o Analysis Workspace:

1. Faça logon na [Adobe Experience Cloud](https://experience.adobe.com).
1. Selecione **[!UICONTROL Customer Journey Analytics]** no alternador de aplicativos ![App](/help/assets/icons/Apps.svg) na parte superior direita da interface.
1. A página **[!UICONTROL Projetos]** do Analysis Workspace é exibida por padrão. Se um projeto específico for selecionado para você ou se você estiver trabalhando nele recentemente, esse projeto será mostrado por padrão.

### Criar um projeto

Uma análise do Analysis Workspace é chamada de [projeto](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

Você pode criar um projeto no Analysis Workspace conforme descrito em [Criar projetos](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

Os projetos podem ser organizados em pastas e subpastas, conforme descrito em [Pastas no Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Salvar e compartilhar um projeto

Conforme você cria uma análise no Analysis Workspace, seu trabalho é [salvo automaticamente](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

Quando você terminar de criar o projeto e a coleta de insights acionáveis começar, outras pessoas desejarão acessar o projeto. Você pode compartilhar o projeto com usuários e grupos em sua organização ou até mesmo com pessoas de fora da organização. Para obter informações sobre como compartilhar um projeto, consulte [Compartilhar projetos](/help/analyze/analysis-workspace/curate-share/share-projects.md).

## Recursos adicionais {#resources}

- A Adobe oferece centenas de [tutoriais de treinamento em vídeo do Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/overview).
- Consulte [Notas da versão do Adobe Experience Cloud](https://experienceleague.adobe.com/pt-br/docs/release-notes/experience-cloud/current) para saber mais sobre novos recursos.
