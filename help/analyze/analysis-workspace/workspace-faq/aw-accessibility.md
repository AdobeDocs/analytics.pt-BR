---
description: Saiba mais sobre os recursos de suporte de acessibilidade no Analysis Workspace.
title: Acessibilidade No Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 2bacbee8-097c-4fc5-8be4-7e4f284db08c
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 91%

---


# Acessibilidade no Analysis Workspace

Saiba mais sobre o suporte de acessibilidade no [!UICONTROL Analysis Workspace], a principal ferramenta de análise do Customer Journey Analytics.

“Acessibilidade” refere-se à disponibilização adequada de produtos para pessoas com deficiências visuais, auditivas, cognitivas, motoras, entre outras. Alguns exemplos de recursos de acessibilidade para produtos de software incluem:

* suporte a leitores de tela,
* equivalentes de texto para gráficos,
* atalhos de teclado,
* modo de alto contraste para cores de exibição,
* e muito mais.

O [!UICONTROL Analysis Workspace] fornece algumas ferramentas que o tornam acessível para uso, como:

## Navegação pelo teclado

A navegação no [!UICONTROL Analysis Workspace] funciona de cima para baixo e da esquerda para a direita. Os seguintes elementos de navegação facilitam a acessibilidade:

* A tecla **[!UICONTROL Tab]** ativa atalhos de referência, permitindo a movimentação entre seções maiores dentro do espaço de trabalho. No painel esquerdo, **[!UICONTROL Tab]** também permite mover-se de uma opção arrastável para a próxima.
* A ◀︎ e a ▶︎ se movem entre elementos individuais depois que a tecla **[!UICONTROL Tab]** realçou um elemento.
* Pressionar a tecla **[!UICONTROL F6]** leva você até o primeiro painel no projeto e move-se entre as visualizações desse painel. Em seguida, ela leva você até o próximo painel no projeto e o processo se repete.
* Aplicamos indicadores de foco para que os usuários de teclado com visão tenham uma indicação clara de qual elemento da interface está selecionado. O indicador é uma borda azul que realça o painel em foco. Além disso, a funcionalidade recém-selecionada é destacada com um plano de fundo cinza, bem como a seleção dentro da funcionalidade. No exemplo, [!UICONTROL Componentes] e a dimensão Página foram selecionados recentemente.

  ![Tabela de forma livre que mostra um indicador de foco de uma borda azul ao redor da tabela.](assets/focus-indicator.png)

### Navegação do teclado para a barra de menu

1. Pressione até alcançar a barra de menu.
1. Use as teclas de seta para navegar entre menus e itens de menu.
1. Pressione **[!UICONTROL Enter]** para abrir um menu ou selecionar um item de menu.
1. Use **[!UICONTROL Esc]** para fechar um menu.

### Navegação pelo teclado para interações de arrastar e soltar

O [!UICONTROL Analysis Workspace] possui uma interface de arrastar e soltar. No entanto, os usuários podem adicionar componentes usando o teclado:

1. Escolha um componente no painel esquerdo usando a tecla Tab.
1. Pressione **[!UICONTROL Enter]** para selecioná-lo.
1. Use as teclas de seta para navegar até a área onde deseja soltar o componente.
1. Pressione **[!UICONTROL Enter]** para inserir o componente.

### Atalhos de teclado (teclas de atalho)

O [!UICONTROL Analysis Workspace] oferece um conjunto avançado de [atalhos de teclado (teclas de atalho)](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) para um fluxo de trabalho mais simples.

## Suporte para leitores de tela e ampliadores de tela

Um leitor de tela lê o texto que aparece na tela do computador. Ele também lê informações não textuais, como rótulos de botões ou descrições de imagens no aplicativo.

## Paletas de cores e contraste

O [!UICONTROL Analysis Workspace] se esforça para obter a conformidade WCAG 2.1 AA, incluindo os requisitos para contraste de cores.

Além disso, os usuários podem definir sua própria paleta de cores preferencial para um projeto em **[!UICONTROL Projeto]** > **[!UICONTROL Configurações do projeto]** > [Paleta de cores do projeto](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md).

## Validação necessária

Ao criar um componente, uma visualização ou um painel, os campos obrigatórios são validados ao salvar. Se um campo obrigatório não passar na validação, ele será contornado em vermelho com um ícone de erro. Uma descrição escrita explica o que precisa ser corrigido.

![Construtor de segmentos e indicador de validação de erros.](assets/error-validation.png)

## Suporte para recursos de acessibilidade do sistema operacional

O Analysis Workspace oferece suporte a recursos de acessibilidade integrados do Windows e do macOS, como o modo de alto contraste, teclas modificadoras fixas e teclas lentas ou teclas de filtragem. Ele também fornece informações sobre a interface ao sistema operacional para permitir a interação com tecnologias de assistência, incluindo leitores de tela como o VoiceOver para macOS e o NVDA para Windows.


<!--

# Accessibility in Analysis Workspace

Learn about accessibility support in [!UICONTROL Analysis Workspace], the premier analysis tool for Adobe Analytics. 

Accessibility refers to making products usable for people with visual, auditory, cognitive, motor, and other disabilities. Examples of accessibility features for software products include screen reader support, text equivalents for graphics, keyboard shortcuts, change of display colors to high contrast, and so on. 

[!UICONTROL Analysis Workspace] provides some tools that make it accessible to use, including:

## Navigate [!UICONTROL Workspace] using the keyboard

Navigation in [!UICONTROL Analysis Workspace] works top > down, and left > right. The following navigational elements facilitate accessibility:

* The `Tab` key enables landmark shortcuts, moving between larger sections within Workspace. In the left rail, `Tab` also enables you to move from one draggable option to the next.
* The `left/right arrows` move between individual elements after `Tab` has highlighted it. 
* The `F6` navigates to the first panel in the project and  moves between the visualizations within that panel. Then, it moves to the next panel in the project and repeats. 
* We apply focus indicators so that sighted keyboard users have a clear indication of which UI element currently has focus. The indicator is a blue border around the selected element.

    ![Focus Indicator](assets/focus-indicator.png)

### Keyboard navigation for the menu bar 

1. Tab until you have reached the menu bar.
1. Use left/right arrow keys to navigate to the menu you want.
1. Press `Enter` to select the menu and show its options.
1. Use up/down arrow keys to navigate to the menu option you want.
1. Press `Enter` to select the option.

### Keyboard navigation for drag & drop interactions 

[!UICONTROL Analysis Workspace] is a drag & drop user interface. However, users can add components using the keyboard instead:

1. Tab to a component in the left rail.
1. Press `Enter` to select.
1. Use arrow keys to navigate to the area where you want to drop the component.
1. Press `Enter` to place the component.

### Keyboard shortcuts (hotkeys) 

[!UICONTROL Analysis Workspace] offers a rich set of [keyboard shortcuts](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html) for a more seamless workflow. Some common shortcuts for navigation, analysis creation, and insight democratization are listed below. 

#### Navigation

| Shortcut | Action |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Jump to different rails: [!UICONTROL Panels], [!UICONTROL Visualizations], or [!UICONTROL Components] | 
| `[Alt + Left / Right]` | Navigate between panels |
| `[Alt + M]` | Collapse/expand all panels |
| `[Alt + Ctrl + M]` | Collapse/expand active panel |
| `[Ctrl + /]` | Search left rail |

#### Analysis creation

| Shortcut | Action |
| --- | --- |
| `[Alt + 1]` | New freeform table |
| `[Ctrl + Shift + C]` | New calculated metric |
| `[Ctrl + Shift + D]` | New date range |
| `[Ctrl + Shift + E]` | New segment |
| `[Ctrl + Z]` | Undo |
| `[Component drag + Shift]` | Create a drop-down filter |

#### Democratization

| Shortcut | Action |
| --- | --- |
| `[Ctrl + S]` | Save |
| `[Ctrl + Shift + G]` | Curate |
| `[Ctrl + G]` | Share |
| `[Alt + Shift + S]` | Schedule |
| `[Alt + L]` | Get link to project |
| `[Ctrl + Shift + B]` | Download PDF |

## Support for screen readers and screen magnifiers

A screen reader reads text that appears on the computer screen. It also reads non-textual information, such as button labels or image descriptions in the application, provided in accessibility tags or attributes.  

## Color palettes & contrast  

[!UICONTROL Analysis Workspace] strives for WCAG 2.1 AA conformance, including requirements for color contrast. 

In addition, users can set their own preferred color palette for a project under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Project color palette](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html). 

## Required field validation in component builders 

When building a component, required fields are validated when you save. If a required field does not pass validation, it will be outlined in red with an error icon. A written description appears of the issue that needs to be fixed.  

Once a component is fully validated, pressing `Save` closes the builder. 

![Error validation](assets/error-validation.png)

## Support for operating system accessibility features  

Analysis Workspace supports built-in MS Windows and macOS accessibility features like high-contrast mode, sticky keys, and slow keys/filter keys. It also provides information about the user interface to the operating system to enable interaction with assistive technologies, including screen readers such as VoiceOver for macOS and NVDA on Windows.

-->