---
description: Saiba como copiar uma solicitação simples.
title: Como copiar solicitações simples
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
feature: Report Builder
role: User, Admin
exl-id: ceed28d5-cb7f-4343-96fd-2ce09f5a3515
TQID: https://experienceleague.adobe.com/Zd6s6l-sW40WlEtk2Z8AFcNLkC-l4wxcmo67XajqAJs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 527
ht-degree: 47%

---

# Copiar solicitações simples

{{legacy-arb}}

Copie uma solicitação simples em vez de uma solicitação referencial. Uma solicitação simples é aquela que não contém referências a outra solicitação ou ao conteúdo de uma célula.

Uma [solicitação referencial](/help/analyze/legacy-report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) usa valores de células como entrada para parâmetros, como um filtro de datas ou relacional. Esses filtros usam correspondências ou tendências e se baseiam nos resultados de uma solicitação anterior ou no conteúdo inserido pelo usuário em uma célula, chamada de célula de entrada.

Para copiar uma solicitação simples

1. Crie uma solicitação válida.
1. Clique com o botão direito do mouse em uma das células onde a solicitação está mapeada ou selecione uma região de células que contém solicitações.

   Seja consistente ao escolher, no grupo de células cobertas pela solicitação, uma célula da qual copiar. A escolha preferencial é a primeira célula do topo mais à esquerda do conjunto de células coberto pela solicitação, trabalhando então da esquerda para a direita. Isso se deve ao fato de a planilha do Excel ter centenas de colunas e milhares de linhas disponíveis para expansão para a direita e para baixo. Se você decidir iniciar uma cópia de solicitação a partir da célula mais à direita ou inferior em um conjunto de células associadas a uma solicitação, o sistema não permitirá que você cole a solicitação se as células a serem coladas se estenderão além da borda esquerda ou superior da planilha.
1. Selecione **[!UICONTROL Copiar solicitação]**.
1. Em outra parte da planilha, clique com o botão direito do mouse em uma célula vazia (uma célula que não contenha nenhuma solicitação).

   Para evitar que você perca ou corrompa solicitações já criadas, não é possível colar células contendo solicitações em células mapeadas com solicitações. Se você copiar ou recortar células que contêm solicitações, o menu de atalho não disponibilizará a opção [!UICONTROL Colar solicitações] ao clicar com o botão direito do mouse nas células (ou no conjunto de células) que contêm solicitações. Você precisa selecionar uma célula diferente como destino da operação de colagem, de modo que as solicitações não se sobreponham. Isso se aplica se você selecionar uma única célula com uma solicitação para colar ou uma região de células contendo solicitações.
1. Clique em **[!UICONTROL Colar solicitação]**.

   Uma cópia da solicitação original é colocada na(s) célula(s), em uma posição ou posições relativas à solicitação original.

   >[!NOTE]
   >
   >Somente as solicitações são copiadas, não o conteúdo das células. Se você tiver outras informações não baseadas em solicitações, mas relevantes para entender os dados exibidos nas células (como cabeçalhos de colunas da tabela ou identificadores de linhas), use os comandos padrão do Excel Copiar e Colar.

   Visto que o Excel usa diferentes áreas de transferência para copiar conteúdos de células e para copiar solicitações, você pode copiar tanto conteúdos de células que não sejam solicitações quanto solicitações executando comandos Copiar/Colar e Copiar solicitações/Colar solicitações em série. No entanto, se você aplicar formatação a solicitações na planilha e, em seguida, copiar e colar, o Report Builder reproduzirá a formatação original (como bordas, fontes etc.) na região de colagem.

   Modificar uma solicitação que você tenha copiado ou recortado para a área de transferência antes de colá-la remove a solicitação da área de transferência. Portanto, para manter a solicitação em seu estado original, não modifique uma solicitação entre o momento em que você a copia e o momento em que a cola.
