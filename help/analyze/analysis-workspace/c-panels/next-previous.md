---
description: Um painel que mostra os itens de dimensão anteriores ou seguintes de uma dimensão específica.
title: Próximo painel de item ou anterior
feature: Panels
role: User, Admin
source-git-commit: 2a16410a1a9ece301844ef0f242d09e3a16318c0
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 7%

---


# Próximo painel de item ou anterior

O [!UICONTROL Item seguinte ou anterior] painel iniciado como um relatório no Reports &amp; Analytics, em [!UICONTROL Relatórios] > [!UICONTROL Mais popular] > [!UICONTROL Próxima página/Página anterior]. Esse painel da Workspace contém várias tabelas e visualizações para identificar facilmente o item de dimensão anterior ou seguinte de uma dimensão específica. Por exemplo,

## Acessar o painel

Você pode acessar o painel por meio de [!UICONTROL Relatórios] ou [!UICONTROL Workspace].

| Ponto de acesso | Descrição |
| --- | --- |
| [!UICONTROL Relatórios] | <ul><li>O painel já está em um projeto.</li><li>O painel esquerdo está recolhido.</li><li>Se você selecionou [!UICONTROL Próxima página], as configurações padrão já foram aplicadas, como [!UICONTROL Página] para [!UICONTROL Dimension]e a página superior como a [!UICONTROL Dimension Item], [!UICONTROL Próximo] para [!UICONTROL Direção] e [!UICONTROL Visita] para [!UICONTROL Contêiner]. Você pode modificar todas essas configurações.</li></ul>![Painel Próximo/Anterior](assets/next-previous.png) |
| Workspace | Crie um novo projeto e selecione o ícone Painel no painel à esquerda. Em seguida, arraste a [!UICONTROL Item seguinte ou anterior] acima da tabela de Forma livre. Observe que a variável [!UICONTROL Dimension] e [!UICONTROL Dimension Item] são deixados em branco. Selecione uma dimensão no menu suspenso . [!UICONTROL Itens de Dimension] são preenchidas com base no [!UICONTROL dimension] você escolheu. O item de dimensão principal é adicionado, mas você pode selecionar um item diferente.<p>![Painel Próximo/Anterior](assets/next-previous2.png) |

## Entradas do painel {#Input}

Você pode configurar o [!UICONTROL Item seguinte ou anterior] painel usando estas configurações de entrada:

| Configuração | Descrição |
| --- | --- |
| Zona Segmento (ou outro componente) | Você pode arrastar e soltar segmentos ou outros componentes para filtrar ainda mais os resultados do painel. |
| Dimensão | A dimensão para a qual você deseja explorar itens anteriores ou seguintes. |
| Item de dimensão | O item |
| Direção | Especifique se você está procurando a variável [!UICONTROL Próximo] ou [!UICONTROL Anterior] item de dimensão. |
| Contêiner | [!UICONTROL Visita] ou [!UICONTROL Visitante] (padrão) determine o escopo de sua pesquisa. |

Clique em **[!UICONTROL Criar]** para criar o painel.

## Saída do painel {#output}

O [!UICONTROL Item seguinte ou anterior] painel retorna um conjunto avançado de dados e visualizações para ajudar você a entender melhor o que ocorrências seguem ou precedem itens de dimensão específicos.

![Saída do painel Próximo/Anterior](assets/next-previous-output.png)

![Saída do painel Próximo/Anterior](assets/next-previous-output2.png)

