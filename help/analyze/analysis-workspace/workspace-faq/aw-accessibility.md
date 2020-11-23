---
description: Recursos de suporte para acessibilidade no Analysis Workspace
title: Acessibilidade no Analysis Workspace
translation-type: tm+mt
source-git-commit: 97309a5be19912432ca75c7029999085c45ba353
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 82%

---


# Acessibilidade no Analysis Workspace

Saiba mais sobre o suporte de acessibilidade no [!UICONTROL Analysis Workspace], a principal ferramenta de análise do Adobe Analytics.

Acessibilidade refere-se à utilização de produtos para pessoas com deficiências visuais, auditivas, cognitivas, motoras e outras. Exemplos de recursos de acessibilidade para produtos de software incluem suporte a leitores de tela, equivalentes de texto para gráficos, atalhos de teclado, mudança de cores de exibição para alto contraste e assim por diante.

O [!UICONTROL Analysis Workspace] fornece algumas ferramentas que o tornam acessível para uso, como:

## Navegar pelo [!UICONTROL Workspace] usando o teclado

A navegação no [!UICONTROL Analysis Workspace] funciona de cima > para baixo e da esquerda > à direita. Os seguintes elementos de navegação facilitam a acessibilidade:

* A tecla `Tab` ativa atalhos de marcos, alternando entre seções maiores dentro do Workspace. No painel esquerdo, `Tab` também permite que você se mova de uma opção arrastável para a próxima.
* A `left/right arrows` movimentação entre elementos individuais depois `Tab` de realçá-la.
* O `F6` navega até o primeiro painel do projeto e se move entre as visualizações dentro desse painel. Em seguida, ele se move para o próximo painel do projeto e se repete.
* Nós aplicamos indicadores de foco para que os usuários de teclado com visão tenham uma indicação clara de qual elemento de interface do usuário tem foco no momento. O indicador é uma borda azul em torno do elemento selecionado.

   ![Indicador de foco](assets/focus-indicator.png)

### Navegação no teclado para a barra de menus

1. Pressione a tecla até acessar a barra de menus.
1. Use as teclas de seta para a esquerda/direita para navegar até o menu desejado.
1. Pressione `Enter` para selecionar o menu e mostrar suas opções.
1. Use as teclas de seta para cima/para baixo para navegar até a opção de menu desejada.
1. Pressione `Enter` para selecionar a opção.

### Navegação no teclado para interações de arrastar e soltar

O [!UICONTROL Analysis Workspace] é uma interface de usuário de arrastar e soltar. No entanto, os usuários podem adicionar componentes usando o teclado:

1. Escolha um componente no painel esquerdo.
1. Pressione `Enter` para selecionar.
1. Use as teclas de seta para navegar até a área onde deseja soltar o componente.
1. Pressione `Enter` para posicionar o componente.

### Atalhos de teclado (teclas de atalho)

O [!UICONTROL Analysis Workspace] oferece um conjunto avançado de [atalhos de teclado](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=pt-BR) para um fluxo de trabalho mais simples. Alguns atalhos comuns para navegação, criação de análises e democratização do insight estão listados abaixo.

#### Navegação

| Atalho | Ação |
|---|---|
| Alt + Shift + 1 / 2 / 3 | Ir para diferentes painéis: [!UICONTROL Painéis], [!UICONTROL Visualizações] ou [!UICONTROL Componentes] |
| Alt + seta para a esquerda/direita | Navegar entre painéis |
| Alt + M | Recolher/expandir todos os painéis |
| Alt+  Ctrl + M | Recolher/expandir painel ativo |
| Ctrl + / | Pesquisar painel esquerdo |

#### Criação de análise

| Atalho | Ação |
|---|---|
| Alt + 1 | Nova tabela de forma livre |
| Ctrl + Shift + C | Nova métrica calculada |
| Ctrl + Shift + D | Novo intervalo de datas |
| Ctrl + Shift + E | Novo segmento |
| Ctrl + Z | Desfazer |
| Manter shift pressionado (na área do segmento) | Criar um [filtro suspenso](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=pt-BR) |

#### Democratização

| Atalho | Ação |
|---|---|
| Ctrl + S | Salvar |
| Ctrl + Shift + G | Preparar |
| Ctrl + G | Compartilhar |
| Alt + Shift + S | Agendar |
| Alt + L | Obter link para o projeto |
| Ctrl + Shift + B | Baixar o PDF |

## Suporte para leitores de tela e ampliadores de tela

Um leitor de tela lê o texto que aparece na tela do computador. Ele também lê informações não textuais, como rótulos de botões ou descrições de imagens no aplicativo, fornecidas em tags de acessibilidade ou atributos.

## Paletas de cores e contraste

O [!UICONTROL Analysis Workspace] se esforça para obter a conformidade WCAG 2.1 AA, incluindo os requisitos para contraste de cores.

Além disso, os usuários podem definir sua própria paleta de cores preferencial para um projeto em **[!UICONTROL Projeto]** > **[!UICONTROL Configurações do projeto]** > [Paleta de cores do projeto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=pt-BR).

## Validação de campo necessária nos construtores de componentes

Ao criar um componente, os campos obrigatórios são validados ao salvar. Se um campo obrigatório não passar na validação, ele será contornado em vermelho com um ícone de erro. Uma descrição escrita é exibida do problema que precisa ser corrigido.

Depois que um componente é totalmente validado, pressionar `Save` fecha o construtor.

![Validação de erro](assets/error-validation.png)

## Suporte para recursos de acessibilidade do sistema operacional

O Analysis Workspace aceita recursos de acessibilidade do MS Windows e do MacOS incorporados, como modo de alto contraste, teclas adesivas e teclas lentas/teclas de filtro. Ele também fornece informações sobre a interface do usuário para o sistema operacional para permitir a interação com tecnologias de assistência, incluindo leitores de tela como VoiceOver para macOS e NVDA no Windows.
