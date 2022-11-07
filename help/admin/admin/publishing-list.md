---
description: A publicação de listas fornece uma maneira fácil de enviar vários relatórios específicos de grupos diferentes de sua organização sem criar vários relatórios agendados. As listas de publicação são úteis se você possui conjuntos de relatórios específicos de local e gostaria de oferecer a cada departamento uma cópia de um painel específico. Como alternativa, é possível usar listas de publicação para enviar dados a várias pessoas sem precisar digitar separadamente os endereços de email, se estiver trabalhando com um único conjunto de relatórios.
title: Listas de publicação
feature: Admin Tools
uuid: 07dad661-c302-4981-80d1-3169ad1fe90e
exl-id: 5c9a0ae7-742b-4247-bcbc-2e979af6160c
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 52%

---

# Listas de publicação

A publicação de listas fornece uma maneira fácil de enviar vários relatórios específicos de grupos diferentes de sua organização sem criar vários relatórios agendados. As listas de publicação são úteis se você possui conjuntos de relatórios específicos de local e gostaria de oferecer a cada departamento uma cópia de um painel específico. Como alternativa, é possível usar listas de publicação para enviar dados a várias pessoas sem precisar digitar separadamente os endereços de email, se estiver trabalhando com um único conjunto de relatórios.

Várias listas de publicação podem ser especificadas ao agendar um relatório.

## Fim da vida útil das listas de publicação

Como provavelmente você sabe, o Adobe descontinuará o Reports and Analytics (R&amp;A) e o produto de ponto do Site Catalyst em 31 de dezembro de 2023. [Você pode aprender mais sobre o fim da vida útil e como se preparar para isso aqui](https://express.adobe.com/page/6WnF8JK6IRDhf/).

Um dos recursos em P&amp;R que está programado para atingir o fim da vida útil nessa data é o Publishing Lists. Alguns recursos como Eventos de calendário e Relatório de resumo de página têm uma versão de paridade no Analysis Workspace. No entanto, as Listas de Publicação não são uma delas e serão descontinuadas quando a P&amp;A atingir o fim da vida útil. **Você não poderá criar novas listas de publicação ou acessar listas de publicação existentes para enviar ou agendar projetos do Analysis Workspace.**

Para reduzir qualquer interrupção nos fluxos de trabalho atuais de distribuição de relatórios que dependem das Listas de publicação, solicitamos que você considere as seguintes alternativas:

* Se você usar Listas de publicação para distribuir a mesma versão do relatório para vários usuários (sem aplicar substituições do conjunto de relatórios):

   Depois de recriar seus relatórios no Analysis Workspace como projetos, você pode usar uma combinação de um grupo de contatos ou uma lista de distribuição criada para seu cliente de email e o recurso de Projetos agendados do Workspace para enviar ou agendar a entrega recorrente do projeto. Como as Listas de publicação, uma versão PDF/CSV do projeto é enviada para cada ID de email que faz parte do grupo/lista. Saiba mais sobre [Projetos agendados aqui](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html#:~:text=Scheduled%20Analysis%20Workspace%20projects%20can,options%20in%20the%20left%20rail.).

* Se você usar Listas de publicação para distribuir várias versões do relatório ou painel para vários usuários (por meio do recurso de substituição de conjunto de relatórios):

   A Analysis Workspace não oferece suporte a substituições de conjuntos de relatórios. Também não suporta a capacidade de bloquear conjuntos de relatórios ao compartilhar ou agendar projetos. Para replicar o fluxo de trabalho, talvez seja necessário criar várias versões do mesmo projeto com um conjunto de relatórios diferente aplicado a cada versão e usar o recurso de projeto agendado descrito acima.

Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe.

## Descrições do Gerenciador de lista de publicação {#section_099DF8AC5691495F9B22C71266DD6004}

| Elemento | Descrição |
|--- |--- |
| [!UICONTROL Procurar por] | Permite filtrar a tabela para pesquisar uma lista de publicação. |
| [!UICONTROL Conjuntos de relatórios a serem incluídos] | Substitui o conjunto de relatórios por um relatório agendado ou todos os reportlets em um painel. Não há limite técnico para o número de entradas de conjunto de relatórios separadas, mas é recomendado limitá-lo a aproximadamente 50. Não há limite estabelecido para o número de emails que podem ser incluídos. |
| [!UICONTROL Endereços de email] | Uma lista delimitada por vírgulas de todos os emails que receberão o relatório com o novo conjunto de relatórios.  Clique em **[!UICONTROL Clicar para editar]** para especificar os endereços de email para recebimento. Insira cada endereço de email, separando vários endereços com um ponto-e-vírgula (;). Pressione `<Enter>` quando terminar de inserir os endereços de email. <br>O campo Contagem de email exibe o número de endereços de email associados à entrada de conjunto de relatórios no momento. |
| [!UICONTROL Duplicar] | Cria uma cópia da lista de publicação. |
