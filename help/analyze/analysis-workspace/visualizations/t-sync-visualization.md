---
description: A sincronização de visualizações permite que você controle qual tabela de dados ou fonte de dados corresponde a uma visualização.
keywords: Analysis Workspace; Sincronizar visualização com fonte de dados
seo-description: A sincronização de visualizações permite que você controle qual tabela de dados ou fonte de dados corresponde a uma visualização.
seo-title: Gerenciar fontes de dados
solution: Analytics
title: Gerenciar fontes de dados
topic: Reports and Analytics
uuid: 7 bacf 497-a 933-463 a-bf 9 d-f 6 d 0 c 5 de 0 cba
translation-type: tm+mt
source-git-commit: 0bd28ea64b4e225b33c1fec7f185c7006bdb7f7c

---


# Gerenciar fontes de dados

A sincronização de visualizações permite que você controle qual tabela de dados ou fonte de dados corresponde a uma visualização.

**Dica:** saiba quais visualizações têm relação umas com as outras pela cor do ponto ao lado do título. Cores iguais significam que as visualizações têm como base a mesma fonte de dados.

O gerenciamento de uma fonte de dados permite exibir a fonte de dados ou bloquear a seleção. Essas configurações determinam a maneira como a visualização muda (ou não muda) quando chegam novos dados.

1. [Crie um projeto](../../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md#task_C2C698ACC7954062A28E4784911E6CF2) com uma tabela de dados e [uma visualização](../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276).
1. Na tabela de dados, selecione as células (fonte de dados) que você deseja associar à visualização.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Selecione **[!UICONTROL Exibir fonte de dados]** ou **[!UICONTROL Bloquear seleção]**.

   ![](assets/manage-data-source.png)

   A sincronização de uma visualização a uma célula da tabela cria uma nova tabela (oculta) e coloca códigos de cor na visualização sincronizada à tabela.

| Elemento | Descrição |
|--- |--- |
| Visualizações vinculadas | Se houver visualizações conectadas a uma de forma livre ou tabela coorte, o ponto esquerdo superior será aberto para listar as visualizações conectadas e ter uma opção de caixa de seleção "mostrar" para mostrar/ocultar a tabela.  O enfoque destaca a visualização vinculada; para acessá-la, clique nela. |
| Exibir fonte de dados | Permite exibir (ativando a caixa de seleção) ou ocultar (desativando) a tabela de dados que corresponde à visualização. |
| Bloquear seleção | Ative essa configuração para bloquear a visualização de dados selecionados no momento na tabela de dados correspondente. Uma vez ativada, escolhe entre:  <ul><li>**Posições selecionadas**: escolha essa opção se desejar que a visualização continue bloqueada nas posições selecionadas na tabela de dados correspondente. Essas posições continuarão a ser visualizadas, mesmo se os itens específicos nessas posições forem alterados. Por exemplo, escolha essa opção se desejar mostrar os cinco principais nomes de campanha nessa visualização o tempo todo, não importa quais nomes de campanha apareçam entre as cinco principais.</li> <li>**Itens selecionados**: escolha essa opção se desejar que a visualização continue bloqueada nos itens especificados atualmente selecionados na tabela de dados correspondente. Esses itens continuarão a ser visualizados, mesmo que as suas classificações sejam alteradas na tabela. Por exemplo, escolha essa opção se desejar mostrar os cinco mesmos nomes de campanha específicos nessa visualização o tempo todo, não importa a classificação desses nomes de campanha.</li></ul> |

Essa arquitetura difere da anterior na qual a Analysis Workspace não cria mais uma tabela oculta duplicada que armazena a seleção bloqueada para você. Agora, a fonte de dados aponta para a tabela a partir da qual você criou a visualização.

**Exemplo de casos de uso:**

* É possível criar uma visualização de resumo e bloqueá-la a uma célula na tabela a partir da qual você a criou. Ao ativar a opção “Exibir fonte de dados”, ela mostra exatamente de onde vem a informação na tabela. Os dados de origem aparecerão em cinza:

   ![](assets/data-source2.png)&gt;
* É possível adicionar várias visualizações e extraí-las de diferentes células na mesma tabela, como mostrado abaixo. A tabela é igual à mostrada no exemplo acima, mas a célula extraída e a métrica são diferentes:

   ![](assets/data-source3.png)&gt;
* Você pode ver se há visualizações conectadas a uma tabela de forma livre ou tabela coorte ao clicar no ponto esquerdo superior (Configurações da fonte de dados). Passar o mouse destacará a visualização vinculada e clicar nela levará você para o link especificado.

   ![](assets/linked-visualizations.png)&gt;
