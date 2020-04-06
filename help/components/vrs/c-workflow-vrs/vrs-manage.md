---
description: O Gerenciador de conjunto de relatórios virtuais permite que os administradores editem, adicionem, marcem, excluam, renomeiem, aprovem, copiem, exportem e filtrem conjuntos de relatórios virtuais. Não é visível para usuários não administrativos.
keywords: Virtual Report Suite
title: Gerenciar conjuntos de relatórios virtuais
topic: Reports and analytics
uuid: ce683c01-2d7d-4f2a-98db-946f68eda99b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gerenciar conjuntos de relatórios virtuais

O Gerenciador de conjunto de relatórios virtuais permite que os administradores editem, adicionem, marcem, excluam, renomeiem, aprovem, copiem, exportem e filtrem conjuntos de relatórios virtuais. Não é visível para usuários não administrativos.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]**

![](assets/vrs-manage.png)

>[!NOTE] No Gerenciador de conjunto de relatórios virtuais, você pode exibir apenas seus próprios conjuntos de relatórios virtuais. You have to click **[!UICONTROL Show All]** to see everyone else&#39;s.

| Tarefa | Descrição |
|--- |--- |
| Adicionar | Leva você para o construtor de conjunto de relatórios virtual, onde é possível criar novos conjuntos de relatórios virtuais. |
| Tag | Todos os usuários podem criar tags para segmentos e aplicar uma ou mais tags a um segmento. No entanto, você pode ver tags somente para os segmentos que possui. Que tipos de tags você deve criar? Estas são algumas sugestões para tags úteis:<ul><li>Tags baseadas em nomes de equipe, como Marketing social, Marketing móvel</li><li>Tags de projeto (tags de análise), como análise de página inicial</li><li>Tags de Categoria: Masculino; geografia</li><li>Tags de fluxo de trabalho: Preparado para (uma unidade de negócio específica); Aprovado</li></ul> |
| Excluir | Se você excluir um conjunto de relatórios virtual, os relatórios agendados e painéis com ele aplicado continuam a funcionar normalmente, isto é, o relatório e o painel continuam a usar o conjunto excluído até que o relatório agendado seja salvo novamente.  Os relatórios agendados não são atualizados ao editar um conjunto de relatórios virtuais com o mesmo nome.<br>Por exemplo: suponha que você tem dois conjuntos de relatórios virtuais com o mesmo nome e conjuntos de relatórios primários diferentes:<br>você tem um marcador que faz referência ao conjunto de relatórios virtual para o conjunto de relatórios principal. Em seguida, você exclui o conjunto de relatórios virtuais porque é uma duplicata. O marcador continua a ser executado, referenciando a definição do VRS excluído. Se você alterar a definição do VRS restante, o VRS aplicado ao marcador não será alterado. Usa a definição antiga. Para corrigir isso, atualize o marcador para fazer referência à nova definição. Se você não tiver certeza se um marcador, painel ou relatório agendado está usando um VRS excluído, é possível alterar o nome do VRS restante para que fique mais claro se o marcador usa o VRS restante. |
| Renomear | Em todos os locais em que o conjunto de relatórios virtual é exibido, como no seletor de conjunto de relatórios, ele mostra o novo nome. |
| Aprovar/Cancelar aprovação | Aprove os conjuntos de relatórios virtuais para torná-los &quot;oficiais&quot; ou &quot;canônicos&quot;. É possível reverter o processo ao cancelar a aprovação. |
| Copiar | Cria uma cópia distinta com sua nova ID de conjunto de relatórios, mas com o mesmo nome e a mesma definição. |
| Exportar para CSV | Exporte a definição do conjunto de relatórios virtual para um arquivo .csv. |
| Filtro | Filtre por tags, conjunto de relatórios pai, proprietários e outros filtros (Mostrar tudo, Meu, Favoritos e Aprovado). |
