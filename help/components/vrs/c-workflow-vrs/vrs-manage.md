---
description: O gerenciador de Conjuntos de relatórios virtuais permite que os administradores editem, adicionem, marquem, excluam, renomeiem, aprovem, copiem, exportem e filtrem conjuntos de relatórios virtuais. Não é visível para usuários não administrativos.
keywords: Conjunto de relatórios virtuais
title: Gerenciar conjuntos de relatórios virtuais
feature: VRS
exl-id: b6d58456-bd07-4d97-aff8-216e8440fdc0
TQID: https://experienceleague.adobe.com/ty0vdByiytUJcbNpBMqyp10S2wDRCVllzxbY99r3coA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 481
ht-degree: 31%

---

# Gerenciar conjuntos de relatórios virtuais

O gerenciador de Conjuntos de relatórios virtuais permite que os administradores editem, adicionem, marquem, excluam, renomeiem, aprovem, copiem, exportem e filtrem conjuntos de relatórios virtuais. Não é visível para usuários não administrativos.

**[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de relatórios virtuais]**

![](assets/vrs-manage.png)

>[!NOTE]
>
>No gerenciador de Conjunto de relatórios virtual, você pode visualizar apenas seus próprios conjuntos de relatórios virtuais. É necessário clicar em **[!UICONTROL Mostrar tudo]** para exibir o restante.

| Tarefa | Descrição |
| --- | --- |
| Adicionar | Direciona para o construtor de conjuntos de relatórios virtuais, onde é possível criar novos conjuntos de relatórios virtuais. |
| Tag | Todos os usuários podem criar tags para conjuntos de relatórios virtuais e aplicar uma ou mais tags a um conjunto de relatórios virtual. Entretanto, só é possível ver as tags dos seus conjuntos de relatórios. Que tipos de tags você deve criar? Estas são algumas sugestões de tags úteis:<ul><li>Tags baseadas em nomes de equipe, como Marketing social, Marketing móvel</li><li>Tags de projeto (tags de análise), como Análise de entrada de página</li><li>Tags de categoria: Masculino; geografia</li><li>Tags de fluxo de trabalho: organizado para (uma unidade de negócio específica); Aprovado</li></ul> |
| Excluir | Se você excluir um conjunto de relatórios virtual, os relatórios agendados e os painéis que têm esse conjunto de relatórios virtual aplicado continuarão a funcionar normalmente. O relatório ou painel continua a usar o conjunto de relatórios virtuais excluído até que você salve novamente o relatório agendado.  Os relatórios agendados não são atualizados ao editar um conjunto de relatórios virtuais com o mesmo nome.<br>Por exemplo: suponha que você tem dois conjuntos de relatórios virtuais com o mesmo nome e conjuntos de relatórios primários diferentes:<br>você tem um marcador que faz referência ao conjunto de relatórios virtual para o conjunto de relatórios principal. Em seguida, você exclui o conjunto de relatórios virtuais porque é uma duplicata. O marcador continua a ser executado, fazendo referência à definição dos Conjuntos de relatórios virtuais excluídos. Se você alterar a definição dos conjuntos de relatórios virtuais restantes, o conjunto de relatórios virtuais aplicado ao marcador não será alterado. Ele usa a definição antiga. Para corrigir isso, atualize o marcador para fazer referência à nova definição. Se você não tiver certeza se um marcador, painel ou relatório agendado está usando um conjunto de relatórios virtual excluído, é possível alterar o nome dos conjuntos de relatórios virtuais restantes para que fique mais claro se o marcador usa os conjuntos de relatórios virtuais restantes. |
| Renomear | Em todos os locais em que o conjunto de relatórios virtual é exibido, como no seletor de conjunto de relatórios, ele mostra o novo nome. |
| Aprovar/Cancelar aprovação | Aprove conjuntos de relatórios virtuais para torná-los &quot;oficiais&quot; ou &quot;canônicos&quot;. Você pode reverter o processo cancelando a aprovação. |
| Copiar | Cria uma cópia distinta com sua própria ID de conjunto de relatórios nova, mas com o mesmo nome e definição. |
| Exportar para CSV | Exporte a definição do conjunto de relatórios virtual para um arquivo .csv. |
| Filtro | Filtre por tags, conjunto de relatórios principal, proprietários e outros filtros (Mostrar tudo, Meus, Favoritos e Aprovados). |
