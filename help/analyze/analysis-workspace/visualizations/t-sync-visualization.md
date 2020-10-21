---
description: A sincronização de visualizações permite que você controle qual tabela de dados ou fonte de dados corresponde a uma visualização.
keywords: Analysis Workspace;Synchronize visualization with data source
title: Gerenciar fontes de dados
translation-type: ht
source-git-commit: 519cb7e83e5f49ecacc9c4bd0c12bc59088c662c
workflow-type: ht
source-wordcount: '562'
ht-degree: 100%

---


# Gerenciar fontes de dados

A sincronização de visualizações permite que você controle qual tabela de dados ou fonte de dados corresponde a uma visualização.

**Dica:** saiba quais visualizações têm relação umas com as outras pela cor do ponto ao lado do título. Cores iguais significam que as visualizações têm como base a mesma fonte de dados.

O gerenciamento de uma fonte de dados permite exibir a fonte de dados ou bloquear a seleção. Essas configurações determinam a maneira como a visualização muda (ou não muda) quando chegam novos dados.

1. [Crie um projeto](//help/analyze/analysis-workspace/home.md) com uma tabela de dados e uma [visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. Na tabela de dados, selecione as células (fonte de dados) que você deseja associar à visualização.
1. Na visualização, clique no ponto ao lado do título para abrir a caixa de diálogo **[!UICONTROL Fonte de dados]**. Selecione **[!UICONTROL Exibir fonte de dados]** ou **[!UICONTROL Bloquear seleção]**.

   ![](assets/manage-data-source.png)

   A sincronização de uma visualização a uma célula da tabela cria uma nova tabela (oculta) e coloca códigos de cor na visualização sincronizada à tabela.

| Elemento | Descrição |
|--- |--- |
| Visualizações vinculadas | Se houver visualizações conectadas a uma de forma livre ou tabela de coorte, o ponto no alto à esquerda abre uma lista de visualizações conectadas com uma opção de caixa de seleção “Mostrar” para mostrar/ocultar a tabela.  O enfoque destaca a visualização vinculada; para acessá-la, clique nela. |
| Exibir fonte de dados | Permite exibir (ativando a caixa de seleção) ou ocultar (desativando) a tabela de dados que corresponde à visualização. |
| Bloquear seleção | Ative essa configuração para bloquear a visualização de dados selecionados no momento na tabela de dados correspondente. Uma vez ativada, escolhe entre:  <ul><li>**Posições selecionadas**: escolha essa opção se desejar que a visualização continue bloqueada nas posições selecionadas na tabela de dados correspondente. Essas posições continuarão a ser visualizadas, mesmo se os itens específicos nessas posições forem alterados. Por exemplo, escolha essa opção se desejar mostrar os cinco principais nomes de campanha nessa visualização o tempo todo, não importa quais nomes de campanha apareçam entre as cinco principais.</li> <li>**Itens selecionados**: escolha essa opção se desejar que a visualização continue bloqueada nos itens especificados atualmente selecionados na tabela de dados correspondente. Esses itens continuarão a ser visualizados, mesmo que as suas classificações sejam alteradas na tabela. Por exemplo, escolha essa opção se desejar mostrar os cinco mesmos nomes de campanha específicos nessa visualização o tempo todo, não importa a classificação desses nomes de campanha.</li></ul> |

Essa arquitetura difere da anterior no sentido de que o Analysis Workspace já não cria uma tabela oculta duplicada que armazena a seleção bloqueada para você. Agora, a fonte de dados aponta para a tabela a partir da qual você criou a visualização.

**Exemplo de casos de uso:**

* É possível criar uma visualização de resumo e bloqueá-la a uma célula na tabela a partir da qual você a criou. Ao ativar a opção “Exibir fonte de dados”, ela mostra exatamente de onde vem a informação na tabela. Os dados de origem aparecerão em cinza:

   ![](assets/data-source2.png)>
* É possível adicionar várias visualizações e extraí-las de diferentes células na mesma tabela, como mostrado abaixo. A tabela é igual à mostrada no exemplo acima, mas a célula extraída e a métrica são diferentes:

   ![](assets/data-source3.png)>
* Você pode ver se há visualizações conectadas a uma tabela de forma livre ou tabela coorte ao clicar no ponto esquerdo superior (Configurações da fonte de dados). Passar o mouse destacará a visualização vinculada e clicar nela levará você para o link especificado.

   ![](assets/linked-visualizations.png)>
