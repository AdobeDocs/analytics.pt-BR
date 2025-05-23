---
description: Uma explicação de como a página de aterrissagem reúne o Analysis Workspace e o Reports & Analytics em uma única interface e ponto de acesso sob o comando do Workspace.
title: Página de aterrissagem do Adobe Analytics
role: User, Admin
feature: Analytics Basics
exl-id: 0a2fb778-491a-4dc3-aae4-afadb3ab1a1e
source-git-commit: d5bbba7518529befabb8815ac657336326562fd1
workflow-type: ht
source-wordcount: '1463'
ht-degree: 100%

---

# Página de aterrissagem do Adobe Analytics

A página de destino do Adobe Analytics reúne o [!DNL Analysis Workspace] e o [!DNL Reports & Analytics] (descontinuado) em uma única interface e ponto de acesso sob a estrutura do [!DNL Workspace]. Ela apresenta uma página inicial do gerente de projeto, uma seção modelos e uma seção de aprendizado para ajudar a começar de forma eficaz.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Página de destino do Adobe Analytics](https://video.tv.adobe.com/v/3409141/?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]



A página de destino do Adobe Analytics é composta pelas seguintes subguias: Projetos, Modelos e Aprendizagem.

**[!UICONTROL Projetos]** são designs personalizados que combinam componentes de dados, tabelas e visualizações que você criou ou que outra pessoa criou e compartilhou com você. [!UICONTROL Projetos] também se refere a projetos em branco e scorecards para dispositivos móveis em branco.

**[!UICONTROL Modelos]** inclui modelos fornecidos pela Adobe e qualquer modelo específico para sua organização.

A guia **[!UICONTROL Aprendizagem]** contém orientações práticas em vídeo, tutoriais e links para a documentação.

## Navegue até a guia [!UICONTROL Projetos] {#navigate-projects}

A guia [!UICONTROL Projetos] serve como a página inicial do [!UICONTROL espaço de trabalho]. Ela exibe a pasta da empresa, qualquer pasta pessoal criada, projetos e cartões de pontuação móveis. Use esta página para exibir, criar e modificar pastas, projetos e cartões de pontuação para dispositivos móveis. Para obter mais informações, consulte [Sobre pastas no Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

![Exibindo todos](assets/landing-all2.png)

>[!NOTE]
>
>Várias das seguintes configurações persistem durante a sessão e entre sessões. Por exemplo, a guia selecionada, os filtros selecionados, as colunas selecionadas e a direção de classificação da coluna. Os resultados da pesquisa não são persistentes.

### Personalizar colunas da tabela

Para personalizar a largura das colunas, arraste a barra vertical que as separa.

Para adicionar ou remover colunas da lista de projetos, clique no ícone de coluna (![Aterrissando tudo](/help/analyze/assets/select-column.png)) no canto superior direito e selecione ou desmarque os títulos das colunas.

As colunas disponíveis são:

| Nome da coluna | Descrição |
|---------|----------|
| [!UICONTROL **Nome**] | Identifica o nome do projeto. |
| [!UICONTROL **Tipo**] | Indica se é um projeto do Espaço de trabalho, um cartão de pontuação para dispositivos móveis ou uma pasta. |
| [!UICONTROL **Tags**] | Marque projetos para organizá-los em grupos. |
| [!UICONTROL **Programado**] | Defina como [!UICONTROL Ligado] quando um projeto estiver programado ou [!UICONTROL Desligado] quando não estiver. Clicar no link [!UICONTROL Ligado] permite ver informações sobre o projeto agendado. Você também pode [editar o agendamento do projeto](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md) se for o proprietário do projeto. |
| [!UICONTROL **Função do projeto**] | Identifica as funções do projeto: se você é o(a) proprietário(a) do projeto e se tem permissões para editar ou duplicar o projeto. |
| [!UICONTROL **Conjunto de relatórios**] | Identifica os Conjuntos de relatórios associados ao projeto.<br>Tabelas e visualizações em um painel derivam dados do conjunto de relatórios selecionado na parte superior direita do painel. O conjunto de relatórios também determina quais componentes estão disponíveis no painel esquerdo. Em um projeto, você pode usar um ou vários conjuntos de relatórios dependendo dos casos de uso da análise. A lista de conjuntos de relatórios é classificada de acordo com a relevância. A Adobe define a relevância com base no quão recente e frequente é a utilização do conjunto pelo usuário atual e na frequência com que o conjunto é usado na organização. |
| [!UICONTROL **Proprietário**] | Identifica a pessoa que criou o projeto. |
| [!UICONTROL **Compartilhado com**] | Mostra com quem o projeto está sendo compartilhado no momento. |
| [!UICONTROL **Última modificação**] | A data e a hora em que o projeto foi modificado pela última vez. |
| [!UICONTROL **Aberto pela última vez**] | Identifica a data na qual um projeto foi aberto pela última vez pelo usuário que está visualizando a página “Projetos” no momento. |
| [!UICONTROL **Última utilização**] | Ajuda a determinar se um projeto é útil para usuários da sua organização, mostrando a data e a hora em que o projeto foi aberto pela última vez por um usuário da organização.<p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>As informações de uso disponíveis são a partir de setembro de 2023.</li><li>Esta coluna está disponível somente para admins de sistema.</li></ul> |
| [!UICONTROL **ID do projeto**] | Pode ser usada para depurar projetos. |
| [!UICONTROL **Intervalo de datas mais longo**] | Intervalos de datas mais longos aumentam a complexidade do projeto e podem aumentar os tempos de processamento e carregamento. |
| [!UICONTROL **Número de consultas**] | O número total de solicitações feitas no Analytics quando o projeto é carregado. Um número maior de consultas de projeto aumenta a complexidade do projeto e pode aumentar os tempos de processamento e carregamento. Esses dados só estão disponíveis depois que um projeto é carregado ou depois que um projeto agendado é enviado. |
| [!UICONTROL **Localização**] | Mostra a pasta onde se encontra o projeto. |

### Outros elementos de interface na página “Projetos”

| Elemento da interface | Definição |
| --- | --- |
| Editar preferências | Permite [!UICONTROL Exibir Tutoriais] e [Editar preferências de usuário](/help/analyze/analysis-workspace/user-preferences.md). |
| [!UICONTROL Criar novo] | Abre o modal do projeto, onde é possível criar um projeto do Espaço de trabalho ou um Cartão de pontuação para dispositivos móveis ou abrir um modelo de empresa. |
| [!UICONTROL Mostrar menos<br> Mostrar mais] | Alterna entre não mostrar e mostrar o banner: ![Banner superior](assets/top-banner.png) |
| [!UICONTROL Projeto do Espaço de trabalho] | Cria um [Projeto do Espaço de trabalho](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR) em branco para que você desenvolva e crie. |
| [!UICONTROL Cartão de pontuação para dispositivos móveis] | Cria um [cartão de pontuação para dispositivos móveis](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html?lang=pt-BR) para que você desenvolva e crie. |
| [!UICONTROL Abrir tutorial de treinamento] | Abre o tutorial de treinamento do Espaço de trabalho que o orienta pelo processo de criação de um novo projeto inicial em um tutorial passo a passo. |
| [!UICONTROL Abrir notas de versão] | Abre a seção Adobe Analytics das notas de versão mais recentes do Adobe Experience Cloud. |
| Ícone Filtrar | Filtra por tags, conjuntos de relatórios, proprietários, tipos e outros filtros (Meus, Compartilhados comigo, Favoritos e Aprovados) |
| Barra de pesquisa | Pesquisa todas as colunas na tabela. |
| Caixa de seleção | Seleciona um ou mais projetos para exibir as ações de gerenciamento de projetos que você pode executar: **Excluir**, **Compartilhar**, **Renomear**, **Copiar**, **Remover**, **Mover para cima**, **Mover para baixo**, **Tag**, **Aprovar**, **Exportar CSV** e **Mover para**. Talvez você não tenha permissões para executar todas as ações listadas. |
| [!UICONTROL Favoritos] | Adiciona uma estrela ao lado de um projeto ou pasta favorita que pode ser usada como filtro. |
| [!UICONTROL Nome] | Identifica o nome do projeto. |
| Ícone Fixar | Fixa os itens para que eles sempre apareçam na parte superior da lista, mas você pode reajustar a ordem movendo-os para cima ou para baixo. Use o menu de opções de reticências e selecione **Mover para cima** ou **Mover para baixo** na lista. |
| Ícone Informações (i) | Exibe as seguintes informações sobre um projeto: Tipo, Função do projeto, Proprietário, Descrição e com quem ele é compartilhado. Também indica quem pode [editar ou duplicar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=pt-BR) o projeto. |
| Reticências (...) | Exibe as ações de gerenciamento de projeto que você pode executar: **Excluir**, **Compartilhar**, **Renomear**, **Copiar**, **Remover**, **Mover para cima**, **Mover para baixo**, **Tag**, **Aprovar**, **Exportar CSV** e **Mover para**. Talvez você não tenha permissões para executar todas as ações listadas. |
| MOSTRAR: Pastas e projetos ou todos os projetos | Altera a configuração de exibição na tabela para mostrar pastas e projetos de acordo com a organização da pasta **ou** mostrar todos os seus projetos em uma lista não organizada. |
| &lt; (Botão voltar) | Retorna à configuração de página inicial mais recente em um projeto do Espaço de trabalho ou em um relatório. A configuração da página que você tinha quando saiu da página inicial persistirá quando você retornar. |

## Acesse a guia [!UICONTROL Modelos] {#navigate-reports}

Para obter informações sobre como usar modelos no Adobe Analytics, consulte os seguintes recursos:

* [Usar modelos](/help/analyze/analysis-workspace/templates/use-templates.md)

* [Criar e gerenciar modelos](/help/analyze/analysis-workspace/templates/create-templates.md)

## Usar a guia Aprendizagem {#navigate-learning}

A página Aprendizagem contém tours práticos em vídeo, tutoriais e links para a documentação.

Use a página Aprendizagem do Adobe Analytics para saber mais sobre recursos e casos de uso iniciantes, intermediários ou avançados no Adobe Analytics.

### Acessar a página Aprendizagem

1. No Adobe Analytics, selecione [!UICONTROL **Espaço de trabalho**] > [!UICONTROL **Aprendizagem**].

### Recursos da página Aprendizagem

* **Filtrar conteúdo:** o ícone Filtrar no painel à esquerda permite filtrar o conteúdo de aprendizagem por nível de experiência (iniciante, intermediário ou avançado) e por tipo de conteúdo (documento, vídeo ou tours e tutoriais).
* **Rastrear progresso:** após selecionar um conteúdo, uma tag **[!UICONTROL Visualizado]** é exibida. Essa tag ajuda a rastrear o progresso pelo conteúdo de aprendizagem. É possível selecionar a tag **[!UICONTROL Visualizado]** e removê-la de um conteúdo.
* **Exibir conteúdo adicional:** ao visualizar qualquer vídeo, selecione **[!UICONTROL Saiba mais]** para ver a documentação relacionada na Experience League. Ou, na página Aprendizagem, selecione uma das seguintes opções para exibir o conteúdo adicional:
   * **[!UICONTROL Visitar o YouTube]:** veja a lista de reprodução completa do Analysis Workspace no YouTube.
   * [!UICONTROL **Visitar a Experience League**]: veja o conjunto completo de documentação do Adobe Analytics na Experience League.
* **Conceitos básicos para novos usuários:** o tour [!UICONTROL Conceitos básicos do espaço de trabalho] é recomendado para novos usuários. Esse tour leva você diretamente ao espaço de trabalho e explica sobre as ações mais comuns. Esse tour também pode ser reiniciado a qualquer momento diretamente do espaço de trabalho por meio da dica de ferramenta do cabeçalho do painel.

## Definir sua página de destino {#set-landing}

Os usuários podem definir sua página de aterrissagem preferencial.

1. Vá até Analytics > [!UICONTROL Componentes] > [!UICONTROL Preferências] > [!UICONTROL Geral].
1. Marque a página de aterrissagem que você prefere:

   ![Definir página de aterrissagem](assets/landing-pref.png)

## Perguntas frequentes sobre a página de aterrissagem {#landing-faq}

| Pergunta | Resposta |
| --- | --- |
| Onde estão os modelos que estou acostumado a ver no [!UICONTROL Espaço de trabalho]? | Esses modelos estão agrupados na guia [!UICONTROL Modelos]. |
| O trabalho que eu realizo na interface do programa beta é transferido para a experiência do [!UICONTROL Espaço de trabalho] de produção? | Sim, qualquer trabalho realizado no beta é transferido para a experiência antiga/atual do [!UICONTROL Espaço de trabalho.] |
| Meus favoritos anteriores do Reports &amp; Analytics são transferidos? | Não, eles NÃO são transferidos. No entanto, todos os favoritos de projetos do [!UICONTROL Espaço de trabalho] são transferidos. |
| Há um número máximo de projetos que eu posso fixar? | Não, não há limite para o número de projetos que você pode fixar. |
| Os administradores podem designar essa página de aterrissagem para seus usuários? | Não, os administradores não podem designar a página de aterrissagem em nome de seus usuários. Os usuários individuais devem ativar a alternância. |
