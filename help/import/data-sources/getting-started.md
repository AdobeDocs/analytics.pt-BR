---
title: Introdução às fontes de dados
description: Faça upload de dados de exemplo em um conjunto de relatórios de desenvolvimento.
exl-id: d9f74f55-abbb-4ceb-b4db-8d3c32aacd4a
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# Introdução às fontes de dados

Você pode seguir essas etapas para fazer upload fácil de dados de amostra em um conjunto de relatórios de desenvolvimento para ver o fluxo de trabalho em ação. Depois de entender o processo, você pode expandi-lo e personalizá-lo especificamente para a implementação de sua organização.

>[!IMPORTANT]
>
>Siga estas etapas usando um conjunto de relatórios de desenvolvimento ou de teste. Os dados carregados pelas fontes de dados são **permanente**. Isso afetará os dados do conjunto de relatórios de produção se forem carregados lá.

1. Fazer logon no Adobe Analytics por meio de [https://experience.adobe.com](https://experience.adobe.com).
1. Navegue até **[!UICONTROL Admin]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Fontes de dados]**.
1. Selecione um conjunto de relatórios de desenvolvimento na lista suspensa na parte superior direita.
1. Clique em **[!UICONTROL Criar]** no canto superior esquerdo.
1. Em [!UICONTROL Selecionar categoria], escolha &quot;[!UICONTROL Genérico]&quot; e em [!UICONTROL Selecionar tipo], escolha &quot;[!UICONTROL Fonte de dados genérica (somente dados de resumo)]&quot;.
1. Clique em **[!UICONTROL Ativar]**. Uma janela pop-up é aberta, revelando a [!UICONTROL Assistente de ativação da fonte de dados].
   1. Etapa 1: nomeie a fonte de dados e clique na caixa de seleção aviso.
   1. Etapa 2: essa etapa foi mais usada em versões anteriores do Adobe Analytics. Clique em uma caixa de seleção e digite qualquer valor no campo de texto ao lado dele.
   1. Etapa 3: escolha a métrica a ser incluída no arquivo de modelo de fonte de dados. Selecione &quot;Evento 1&quot; na lista suspensa.
   1. Etapa 4: essa etapa foi mais usada em versões anteriores do Adobe Analytics. Clique em uma caixa de seleção e digite qualquer valor no campo de texto ao lado dele.
   1. Etapa 5: escolha a dimensão que será incluída no arquivo de modelo de fonte de dados. Selecione &quot;eVar 1&quot; na lista suspensa.
   1. Etapa 6: revise o resumo, mostrando as dimensões e métricas incluídas no arquivo de modelo.
   1. Etapa 7: clique no botão **[!UICONTROL Baixar]** botão para baixar o arquivo de modelo de fontes de dados. Observe também as credenciais de logon para o site FTP, pois elas serão usadas em breve.
1. A fonte de dados agora é criada; a próxima etapa é fornecer dados para o processamento. Abra o arquivo baixado no editor de texto desejado.
1. O arquivo de modelo contém três linhas; duas linhas de comentário (começando com &quot;`#`&quot;) e uma linha de cabeçalho:

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #    eVar1    event1
   Date    Evar 1    Event 1
   ```

1. Insira várias linhas de dados, separando cada entrada por uma guia. Não use espaços ou vírgulas para separar valores.
   * A primeira coluna é a data no seguinte formato: `MM/DD/YYYY/HH/mm/SS`.
   * A segunda coluna é o valor de texto que você deseja incluir no eVar 1.
   * A terceira coluna é a quantidade que você deseja aumentar no evento 1.

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #    eVar1    event1
   Date    Evar 1    Event 1
   09/07/YYYY/11/23/00    Data source example value    3
   09/07/YYYY/15/59/00    Another data source value    18
   ```

1. Salve o arquivo. Como opção, você pode dar a ele um nome de arquivo diferente, se desejar. Depois que o arquivo for salvo, você poderá fechar o editor de texto.
1. No Windows Explorer, Finder ou no cliente FTP preferido, navegue até [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. Quando solicitado a fornecer credenciais de login, use o nome de usuário e a senha fornecidos na última etapa do assistente de criação da fonte de dados. Você pode fazer referência a ela novamente navegando até [!UICONTROL Fontes de dados] e clicando em **[!UICONTROL Informações de FTP]** ao lado da fonte de dados criada.
1. Depois de autenticar, arraste o arquivo que você editou para a janela do FTP autenticado.
1. Crie um arquivo de texto vazio em qualquer local fora da janela do FTP. Dê a ele o mesmo nome de arquivo das fontes de dados que você carregou no site FTP, com uma exceção. Em vez de um `.txt` tipo de arquivo, dê a ele um `.fin` tipo de arquivo. Verifique se as configurações do sistema operacional permitem que você veja e altere tipos de arquivos.
1. Arraste o espaço vazio `.fin` para o mesmo local FTP que o arquivo de fonte de dados. A presença da `.fin` O arquivo informa ao Adobe que o arquivo de fonte de dados foi enviado por upload e está pronto para ser assimilado.
1. Após vários minutos, o arquivo desaparece do local FTP e fica visível no relatório.
1. Atualize a página Fontes de dados e valide se o arquivo foi assimilado com sucesso.
1. Navegue até Analysis Workspace e crie um projeto.
1. Arraste eVar 1 como uma dimensão para a tela do espaço de trabalho e evento 1 como uma métrica. Certifique-se de que o intervalo de datas do Espaço de trabalho inclua as datas fornecidas na fonte de dados.

   ![Exemplo de relatório](assets/success-report.png)

## Próximas etapas

[Formato de arquivo](file-format.md): saiba mais sobre como criar um arquivo de fontes de dados personalizado para sua organização.
