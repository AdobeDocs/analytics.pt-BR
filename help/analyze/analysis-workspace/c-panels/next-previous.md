---
description: Um painel que mostra os itens de dimensão anteriores ou seguintes de uma dimensão específica.
title: Próximo painel de item ou anterior
feature: Panels
role: User, Admin
source-git-commit: 73fa048164c67c6c381ce5e223bb178f9ab1833f
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 8%

---


# Próximo painel de item ou anterior

O [!UICONTROL Item seguinte ou anterior] painel iniciado como um relatório no Reports &amp; Analytics, em [!UICONTROL Relatórios] > [!UICONTROL Mais popular] > [!UICONTROL Próxima página/Página anterior]. Esse painel da Workspace contém várias tabelas e visualizações para identificar facilmente o item de dimensão anterior ou seguinte de uma dimensão específica. Por exemplo, talvez você queira explorar quais páginas os clientes acessaram com mais frequência após visitarem a Página inicial.

## Acessar o painel

Você pode acessar o painel por meio de [!UICONTROL Relatórios] ou [!UICONTROL Workspace].

| Ponto de acesso | Descrição |
| --- | --- |
| [!UICONTROL Relatórios] | <ul><li>O painel já está em um projeto.</li><li>O painel esquerdo está recolhido.</li><li>Se você selecionou [!UICONTROL Próxima página], as configurações padrão já foram aplicadas, como [!UICONTROL Página] para [!UICONTROL Dimension]e a página superior como a [!UICONTROL Dimension Item], [!UICONTROL Próximo] para [!UICONTROL Direção] e [!UICONTROL Visita] para [!UICONTROL Contêiner]. Você pode modificar todas essas configurações.</li></ul>![Painel Próximo/Anterior](assets/next-previous.png) |
| Workspace | Crie um novo projeto e selecione o ícone Painel no painel à esquerda. Em seguida, arraste a [!UICONTROL Item seguinte ou anterior] acima da tabela de Forma livre. Observe que a variável [!UICONTROL Dimension] e [!UICONTROL Dimension Item] são deixados em branco. Selecione uma dimensão na lista suspensa. [!UICONTROL Itens de Dimension] são preenchidas com base no [!UICONTROL dimension] você escolheu. O item de dimensão principal é adicionado, mas você pode selecionar um item diferente. Os padrões são Próximo e Visitante. Novamente, você também pode modificá-los.<p>![Painel Próximo/Anterior](assets/next-previous2.png) |

{style=&quot;table-layout:auto&quot;}

## Entradas do painel {#Input}

Você pode configurar o [!UICONTROL Item seguinte ou anterior] painel usando estas configurações de entrada:

| Configuração | Descrição |
| --- | --- |
| Zona Segmento (ou outro componente) | Você pode arrastar e soltar segmentos ou outros componentes para filtrar ainda mais os resultados do painel. |
| Dimensão | A dimensão para a qual você deseja explorar itens anteriores ou seguintes. |
| Item de dimensão | O item específico no centro de sua próxima pesquisa/pesquisa anterior. |
| Direção | Especifique se você está procurando a variável [!UICONTROL Próximo] ou [!UICONTROL Anterior] item de dimensão. |
| Contêiner | [!UICONTROL Visita] ou [!UICONTROL Visitante] (padrão) determine o escopo de sua pesquisa. |

{style=&quot;table-layout:auto&quot;}

Clique em **[!UICONTROL Criar]** para criar o painel.

## Saída do painel {#output}

O [!UICONTROL Item seguinte ou anterior] painel retorna um conjunto avançado de dados e visualizações para ajudar você a entender melhor o que ocorrências seguem ou precedem itens de dimensão específicos.

![Saída do painel Próximo/Anterior](assets/next-previous-output.png)

![Saída do painel Próximo/Anterior](assets/next-previous-output2.png)

| Visualização | Descrição |
| --- | --- |
| Barra horizontal | Lista os próximos (ou anteriores) itens com base no item de dimensão que você escolheu. Passar o mouse sobre uma barra individual destaca o item correspondente na tabela de Forma livre. |
| Número do resumo | Número do resumo de alto nível de todas as ocorrências de item de dimensão anteriores ou anteriores do mês atual (até agora). |
| Tabela de forma livre | Lista os itens seguintes (ou anteriores) com base no item de dimensão que você escolheu, em um formato de tabela. Por exemplo, quais eram as páginas mais populares (por ocorrências) que as pessoas acessavam depois (ou antes) da página inicial ou da página do espaço de trabalho. |

{style=&quot;table-layout:auto&quot;}
