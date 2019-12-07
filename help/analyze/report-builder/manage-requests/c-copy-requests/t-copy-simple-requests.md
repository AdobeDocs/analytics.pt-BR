---
description: Copie uma solicitação simples em vez de uma solicitação referencial. Uma solicitação simples não contém referências a outra solicitação nem ao conteúdo de uma célula.
title: Copiar solicitações simples
topic: Report builder
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Copiar solicitações simples

Copie uma solicitação simples em vez de uma solicitação referencial. Uma solicitação simples não contém referências a outra solicitação nem ao conteúdo de uma célula.

A [referential request](/help/analyze/report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) uses values from cells as input for parameters, such as a data filter or relational filter. Estes filtros usam correspondências ou tendências e são baseados em resultados de uma solicitação anterior ou no conteúdo inserido pelo usuário em uma célula, chamada célula de entrada.
1. Crie uma solicitação válida.
1. Clique com o botão direito do mouse em uma das células onde a solicitação está mapeada ou selecione uma região de células que contém solicitações.

   Seja consistente ao escolher, no grupo de células cobertas pela solicitação, uma célula da qual copiar. A escolha preferencial é a primeira célula do topo mais à esquerda do conjunto de células coberto pela solicitação, trabalhando então da esquerda para a direita. Isso se deve ao fato de a planilha do Excel ter centenas de colunas e milhares de linhas disponíveis para expansão para a direita e para baixo. Se você optar por iniciar a cópia de uma solicitação na última célula de baixo à direita em um conjunto de células associadas à solicitação, o sistema não permitirá que você cole a solicitação se as células a serem coladas se estenderem além da borda esquerda ou superior da planilha.
1. Select **[!UICONTROL Copy Request]**.
1. Em outra parte da planilha, clique com o botão direito do mouse em uma célula vazia (uma célula que não contenha nenhuma solicitação).

   Para impedir que você perca ou corrompa solicitações já criadas, não é possível colar células contendo solicitações em células mapeadas com solicitações. Se você copiar ou recortar células que contêm solicitações, o menu de atalho não disponibilizará a opção [!UICONTROL Colar solicitações] quanto você clicar nas células (ou no conjunto de células) que contêm solicitações com o botão direito do mouse. Você precisa selecionar uma célula diferente como destino da operação de colagem, de modo que as solicitações não se sobreponham. Isso se aplica se você selecionar uma única célula com uma solicitação para colagem ou uma região de células que contenha solicitações.
1. Click **[!UICONTROL Paste Request]**.

   Uma cópia da solicitação original é colocada na(s) célula(s), em uma posição ou posições relativas à solicitação original.

   >[!NOTE]
   >
   >Somente as solicitações são copiadas, não o conteúdo das células. Se você tiver outras informações que não se baseie em solicitações, mas que sejam relevantes à compreensão dos dados exibidos nas células (como cabeçalhos de colunas de tabelas ou identificadores de linhas), use os comandos padrão Copiar e Colar do Excel.

   Visto que o Excel usa diferentes áreas de transferência para copiar conteúdos de células e para copiar solicitações, você pode copiar tanto conteúdos de células que não sejam solicitações quanto solicitações executando comandos Copiar/Colar e Copiar solicitações/Colar solicitações em série. No entanto, se você aplicar formatação a solicitações na planilha e, em seguida, copiar e colar, o construtor de relatórios reproduzirá a formatação original (como bordas, fontes, etc.) na região de colagem.

   Modificar uma solicitação que você tenha copiado ou recortado para a área de transferência antes de colá-la remove a solicitação da área de transferência. Portanto, para manter a solicitação em seu estado original, não a modifique entre o momento de sua cópia e o de sua colagem.
