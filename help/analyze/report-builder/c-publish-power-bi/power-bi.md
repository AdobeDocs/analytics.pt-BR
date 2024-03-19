---
description: Use o Report Builder com o Microsoft Power BI.
title: Publicar no Power BI - Visão geral
feature: Report Builder
role: User, Admin
exl-id: 3464c153-2db5-41af-9e83-da081ec64ad3
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: ht
source-wordcount: '1175'
ht-degree: 100%

---

# Publicar no Power BI - Visão geral

O Microsoft Power BI é um conjunto de painéis de análise comercial usado para analisar dados e compartilhar insights. A integração do Adobe Analytics com o Power BI permite a visualização dos dados analíticos do Report Builder dentro do Microsoft Power BI e o seu fácil compartilhamento em toda a organização.

Como analista, anteriormente você agendava a distribuição de pastas de trabalho do Report Builder usando o email ou FTP. Agora é possível fornecer o acesso às partes interessadas diretamente de suas contas do Power BI, permitindo que coletem dados precisos e atualizados em um ambiente baseado na web acessível em várias plataformas e dispositivos.

Combinar a capacidade de geração de relatórios do Report Builder com os recursos de visualização do Power BI torna as informações mais acessíveis para todos(as) na organização. Com o Power BI, você também pode integrar o Adobe Analytics com outras fontes de dados, por exemplo, como um ponto de venda ou CRM, para descobrir insights, associações e oportunidades únicas exclusivas de clientes. 

![Diagrama do ícone do Microsoft Power BI juntamente com o ícone do Adobe Analytics.](assets/aaplusbi.png)

## Requisitos do sistema {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 [instalado](/help/analyze/report-builder/setup/t-install-arb.md)
* Ative a conta da Microsoft que permite fazer logon no Power BI

## Publicar pasta de trabalho no Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

As pastas de trabalho agendadas são planilhas formatadas do Excel que são preenchidas com dados do Adobe Analytics e distribuídas regularmente.

**Publicar a pasta de trabalho no Report Builder**

1. No Report Builder, gere e salve uma pasta de trabalho.
1. Na barra de ferramentas do Report Builder, clique em **[!UICONTROL Agendamento]** > **[!UICONTROL Novo]**.

1. No assistente básico de agendamento, clique na caixa próxima a **[!UICONTROL Publicar pasta de trabalho no Microsoft Power BI]**.

   ![Captura de tela do Assistente de agendamento do Report Builder mostrando a possibilidade de marcar a opção Publicar pasta de trabalho no Microsoft Power BI.](assets/simple-schedule-wizard.png)

1. Especifique seu email e envie imediatamente ou especifique a frequência de agendamento (a cada hora, diariamente, etc.).
1. Clique em **[!UICONTROL OK]** para publicar.
1. Agora você deverá fazer logon na sua conta da Microsoft. Forneça suas credenciais.
1. A pasta de trabalho do Report Builder é agendada e publicada no Power BI.

   Com cada instância agendada e após o processo de agendamento do Report Builder ter atualizado a pasta de trabalho com dados atualizados do Analytics, ela será publicada no Microsoft Power BI.

**Exibir dados da pasta de trabalho do Report Builder no Power BI**

1. No Power BI, clique duas vezes na pasta de trabalho no menu [!UICONTROL Pastas de trabalho].

   ![Captura de tela da visualização das pastas de trabalho do Power BI.](assets/workbooks-power-bi.png)

1. Agora você pode ver os dados do painel da pasta de trabalho.  ![Os dados do painel da pasta de trabalho.](assets/view-data-pbi.png)

1. Então é possível recortar uma área dessa pasta de trabalho de forma a incluí-la em qualquer um de seus painéis do Power BI.

## Publicar todas as tabelas formatadas na pasta de trabalho como tabelas de conjuntos de dados do Power BI {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
>Se a pasta de trabalho contiver uma macro, a opção &quot;Publicar todas as tabelas formatadas na pasta de trabalho como tabelas de conjuntos de dados do Power BI&quot; estará desativada.

Ao invés de importar toda a pasta de trabalho, é possível importar apenas o conteúdo de todas as tabelas formatadas dentro dela.

**Caso de uso**: você tem uma pasta de trabalho do Excel que extrai dados de múltiplas solicitações do Report Builder e cria uma tabela de resumo com muitas fórmulas. É possível importar apenas a tabela de resumo para o Power BI e criar uma visualização para ela.

**Publicar uma tabela formatada no Report Builder**

1. No Report Builder, gere uma tabela de dados que inclua um linha de cabeçalho, seguida de uma linha de dados.
1. Selecione a tabela e selecione **[!UICONTROL Formatar como tabela]** no menu [!UICONTROL Início]. A tabela é nomeada por padrão (Tabela 1, Tabela 2, etc.), mas é possível alterar o nome no menu [!UICONTROL Design].

1. Na barra de ferramentas do Report Builder, clique em **[!UICONTROL Agendamento]** > **[!UICONTROL Novo]**.

1. No Assistente básico de agendamento, clique em **[!UICONTROL Opções de agendamento avançadas]**.
1. No [!UICONTROL Assistente de programação- Avançado], na guia **[!UICONTROL Opções de publicação]**, marque a caixa próxima a **[!UICONTROL Publicar todas as tabelas formatadas como tabelas de conjunto de dados do Power BI]**.

   ![Captura de tela mostrando o “Assistente de agendamento - Opções de publicação avançadas” com a opção Publicar todas as tabelas formatadas como tabelas de conjunto de dados do Power BI.](assets/advanced-schedule-wizard2.png)

1. (Opcional) É possível personalizar o nome do ativo publicado no Power BI. Isso pode ser útil caso use o controle de versão como parte do nome da pasta de trabalho (como minhapastadetrabalho_v1.1.xlsx) e não queira que o número da versão apareça no nome do ativo publicado no Power BI. Isso possui a vantagem extra de que o ativo publicado não se alterará se a número da versão sofrer alteração. (Consulte as [especificações](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) aqui.)

**Exibir os dados da tabela no Power BI**

1. No Power BI, vá para o menu **[!UICONTROL Espaços de trabalho]** > **[!UICONTROL Conjuntos de dados]**.

   ![Captura de tela mostrando o menu Conjuntos de dados do Power BI com destaque para a opção Criar relatórios.](assets/datasets-menu.png)

1. Selecione o conjunto de dados publicado e clique no ícone [!UICONTROL Criar relatório] próximo a ele. Note que as tabelas aparecerão como Campos.

   ![Captura de tela mostrando o conjunto de dados publicado selecionado, no qual as tabelas estão listadas como Campos.](assets/formatted-tables.png)

1. Selecione uma tabela e suas colunas associadas.

   ![Captura de tela mostrando uma tabela selecionada com as colunas associadas](assets/view-table-dataset.png)

1. No menu [!UICONTROL Visualizações], é possível selecionar como visualizar uma tabela no Power BI. Por exemplo, você pode escolher apresentar seus dados como um gráfico de linhas:

   ![Captura de tela mostrando o menu Visualizações e um gráfico de linhas de dados.](assets/bi-line-graph.png)

1. Aqui é possível criar visualizações dessa tabela de conjunto de dados.

## Publicar todas as solicitações do Report Builder como tabelas de conjuntos de dados do Power BI {#section_0C26057C7DBB4068A643FDD688F6E463}

É possível transformar todas as suas solicitações em tabelas de conjuntos de dados e construir visualizações a partir delas.

>[!IMPORTANT]
>
>Se a pasta de trabalho contiver mais de 100 solicitações, apenas as primeiras 100 serão publicadas no Power BI. Mais, para cada solicitação que é publicada no Power BI, apenas as 10.000 primeiras linhas de dados serão publicadas. Então enquanto essas solicitações forem enviadas com sucesso pelo agendamento, o escopo de publicação para o Power BI é limitado.

1. No Report Builder, abra ou crie uma pasta de trabalho com solicitações do Report Builder.
1. Na barra de ferramentas do Report Builder, clique em **[!UICONTROL Agendamento]** > **[!UICONTROL Novo]**.

1. No Assistente básico de agendamento, clique em **[!UICONTROL Opções de agendamento avançadas]**.
1. No [!UICONTROL Assistente de agendamentos - Avançado], na guia **[!UICONTROL Opções de publicação]**, marque a caixa ao lado de **[!UICONTROL Publicar todas as solicitações do Report Builder como tabelas de conjunto de dados do Power BI]** ![Captura de tela mostrando o Assistente de agendamentos com destaque para a opção Publicar todas as solicitações do Report Builder como tabelas de conjunto de dados do Power BI.](assets/advanced-schedule-wizard2.png)

1. Clique em **[!UICONTROL OK]**.

**Exibir os dados das solicitações no Power BI**

Cada solicitação agendada do Report Builder será publicada como uma tabela no conjunto de dados. Cada tabela de solicitações é nomeada segundo a dimensão principal na solicitação e possui uma coluna [!UICONTROL Conjunto de relatórios] e uma coluna [!UICONTROL Segmentos].

1. No Power BI, vá para o menu **[!UICONTROL Espaços de trabalho]** > **[!UICONTROL Conjuntos de dados]**.

1. Selecione a solicitação que você publicou e clique no ícone [!UICONTROL Criar relatório] próximo a ela.

   Note que as solicitações aparecem como tabelas no menu [!UICONTROL Campos].

   ![Captura de tela mostrando uma solicitação selecionada publicada em um formato bidimensional de linhas com um cabeçalho único.](assets/published-requests.png)

   >[!NOTE]
   >
   >Não importa como você configurou sua solicitação do Report Builder para aparecer na planilha (layout dinâmico, layout personalizado, algumas colunas invisíveis), o Report Builder sempre publicará sua solicitação no mesmo formato bidimensional com apenas uma linha de cabeçalho: Data, Dimensões, Métricas, Conjuntos de relatórios, Segmentos.

1. Também note que existe uma tabela adicional chamada **[!UICONTROL Legenda]**. Caso retire uma solicitação do contexto do Report Builder, pode ser difícil se lembrar o que cada solicitação significa. O propósito da tabela Legenda é, por exemplo, mostrar o nome de cada solicitação na ID da tabela. Também é possível adicionar as outras colunas da Legenda para obter uma perspectiva completa da solicitação.

   ![Captura de tela mostrando a tabela Legenda com o nome de cada solicitação na ID da tabela.](assets/legend-table.png)
