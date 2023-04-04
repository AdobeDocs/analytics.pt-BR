---
title: Introdução às fontes de dados
description: Faça upload de dados de exemplo em um conjunto de relatórios de desenvolvimento.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 1%

---

# Introdução às fontes de dados

Você pode seguir essas etapas para fazer upload fácil de dados de amostra em um conjunto de relatórios de desenvolvimento para ver o fluxo de trabalho em ação. Assim que entender o processo, você poderá expandi-lo e ajustá-lo especificamente à implementação de sua organização.

>[!IMPORTANT]
>
>Siga essas etapas usando um conjunto de relatórios de desenvolvimento ou teste. Os dados carregados por meio de fontes de dados são **permanente**. Isso afeta os dados do conjunto de relatórios de produção se forem carregados lá.

1. Faça logon no Adobe Analytics por meio de [https://experience.adobe.com](https://experience.adobe.com).
1. Navegar para **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Fontes de dados]**.
1. Selecione um conjunto de relatórios de desenvolvimento usando a lista suspensa na parte superior direita.
1. Clique no botão **[!UICONTROL Criar]** no canto superior esquerdo.
1. Em [!UICONTROL Selecionar categoria], escolha &quot;[!UICONTROL Genérico]&quot;, e em [!UICONTROL Selecionar tipo], escolha &quot;[!UICONTROL Fonte de dados genérica (somente dados de resumo)]&quot;.
1. Clique em **[!UICONTROL Ativar]**. Uma janela pop-up é aberta revelando o [!UICONTROL Assistente de ativação da fonte de dados].
   1. Etapa 1: Dê um nome à fonte de dados e clique na caixa de seleção aviso.
   1. Etapa 2: Essa etapa foi mais utilizada nas versões anteriores do Adobe Analytics. Clique em uma caixa de seleção e digite qualquer valor no campo de texto ao lado dela.
   1. Etapa 3: Escolha a métrica a ser incluída no arquivo de modelo da fonte de dados. Selecione &quot;Evento 1&quot; na lista suspensa.
   1. Etapa 4: Essa etapa foi mais utilizada nas versões anteriores do Adobe Analytics. Clique em uma caixa de seleção e digite qualquer valor no campo de texto ao lado dela.
   1. Etapa 5: Escolha a dimensão a ser incluída no arquivo de modelo da fonte de dados. Selecione &quot;eVar1&quot; na lista suspensa.
   1. Etapa 6: Revise o resumo, mostrando as dimensões e métricas incluídas no arquivo de modelo.
   1. Etapa 7: Clique no botão **[!UICONTROL Baixar]** para baixar o arquivo de modelo das fontes de dados. Observe também as credenciais de logon no site FTP, pois elas serão usadas em breve.
1. A fonte de dados foi criada; a próxima etapa é fornecer dados para processamento. Abra o arquivo baixado no editor de texto desejado.
1. O arquivo de modelo contém três linhas; duas linhas de comentário (começando com &quot;`#`&quot;) e uma linha de cabeçalho:

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #	eVar1	event1
   Date	Evar 1	Event 1
   ```

1. Insira em várias linhas de dados, separando cada entrada por uma guia. Não use espaços ou vírgulas para separar valores.
   * A primeira coluna é a data no seguinte formato: `MM/DD/YYYY/HH/mm/SS`.
   * A segunda coluna é o valor de texto que você deseja incluir no eVar1.
   * A terceira coluna é o valor que você deseja aumentar para o evento 1.

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #	eVar1	event1
   Date	Evar 1	Event 1
   09/07/YYYY/11/23/00	Data source example value	3
   09/07/YYYY/15/59/00	Another data source value	18
   ```

1. Salve o arquivo. Opcionalmente, é possível fornecer um nome de arquivo diferente, se desejar. Depois que o arquivo for salvo, você poderá fechar o editor de texto.
1. No Windows Explorer, Finder ou cliente FTP de sua escolha, navegue até [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. Quando solicitado a fornecer credenciais de logon, use o nome de usuário e a senha fornecidos na última etapa do assistente de criação da fonte de dados. Você pode referenciá-lo novamente navegando até [!UICONTROL Fontes de dados] e clicando em **[!UICONTROL Informações de FTP]** ao lado da fonte de dados criada.
1. Depois de autenticar, arraste o arquivo editado na janela FTP autenticada.
1. Crie um arquivo de texto vazio em qualquer local fora da janela FTP. Dê a ele o mesmo nome de arquivo do arquivo de fontes de dados que você carregou no site FTP, com uma exceção. Em vez de um `.txt` tipo de arquivo , dê a ele um `.fin` tipo de arquivo. Certifique-se de que as configurações do seu sistema operacional permitam ver e alterar os tipos de arquivo.
1. Arraste o vazio `.fin` para o mesmo local FTP que o arquivo de fonte de dados. A presença do `.fin` informa ao Adobe que o arquivo da fonte de dados está totalmente carregado e pronto para ser assimilado.
1. Após vários minutos, o arquivo desaparece do local do FTP e é visível nos relatórios.
1. Atualize a página de Fontes de dados e verifique se o arquivo foi assimilado com êxito.
1. Navegue até Analysis Workspace e crie um projeto.
1. Arraste o eVar 1 como uma dimensão para a tela do espaço de trabalho e o evento 1 como uma métrica. Certifique-se de que o intervalo de datas do Workspace inclua as datas fornecidas na fonte de dados.

   ![Exemplo de relatório](assets/success-report.png)

## Próximas etapas

[Formato de arquivo](file-format.md): Saiba mais sobre como criar um arquivo de fontes de dados adaptado à sua organização.