---
description: Crie intervalos de datas personalizados na Analysis Workspace e os salve como componentes de Tempo.
keywords: Analysis Workspace
seo-description: Crie intervalos de datas personalizados na Analysis Workspace e os salve como componentes de Tempo.
seo-title: Criar intervalos de datas personalizados
solution: Analytics
title: Criar intervalos de datas personalizados
topic: Reports and Analytics
uuid: c8873d41-454d-4f22-ad1f-38cacec5a3bc
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Criar intervalos de datas personalizados

Crie intervalos de datas personalizados na Analysis Workspace e os salve como componentes de Tempo.

**[!UICONTROL Componentes]** &gt; **[!UICONTROL Novo intervalo de datas]**

Um intervalo de datas é aplicado ao nível de painel. To add a date range to your project, click **Panels** &gt; *`<select panel>`*, and specify a new date range.

## Date range for "two months ago" {#section_C4109C57CB444BB2A79CC8082BD67294}

O intervalo de datas personalizado a seguir mostra um intervalo de datas para “dois meses atrás” com uma visualização de Alteração do resumo, que mostra a alteração direcional.

![](assets/date-range-two-months-ago.png)

O intervalo de datas personalizado é exibido na parte superior do painel do componente [!UICONTROL Intervalo de datas] no seu projeto:

![](assets/date-range-panel-two-months-ago.png)

Você pode arrastar esse intervalo de datas personalizado para uma coluna ao lado do intervalo de datas personalizado, acumulado mensalmente, usando o Último mês predefinido para uma comparação. Adicione uma visualização de Resumo de alterações e selecione os totais de cada coluna para mostrar a alteração direcional:

![](assets/date-range-two-months-table.png)

## Usar um intervalo de datas em andamento de 7 dias {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

Um intervalo de datas é aplicado ao nível de painel. Para adicionar um intervalo de datas para o seu projeto, clique em **Ações** &gt; **Adicionar painel** e especifique um novo intervalo de datas.

No Construtor de intervalo de datas, você pode criar um intervalo de datas personalizado que é exibido no painel Componentes com outros intervalos de datas.

Por exemplo, você pode criar um intervalo de datas que especifica uma janela de acumulado de 7 dias, que terminou há uma semana:

![](assets/create_date_range.png)

Use *`rolling daily`*.

* As configurações de Início seriam do *`current day minus 14 days`*.

* As configurações de Finais seriam do *`current day minus 7 days`*.

Esse intervalo de datas pode ser um componente que você arrasta para qualquer tabela de forma livre.
