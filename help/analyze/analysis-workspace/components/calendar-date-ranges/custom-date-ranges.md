---
description: Crie intervalos de datas personalizados na Analysis Workspace e os salve como componentes de Tempo.
keywords: Analysis Workspace
seo-description: Crie intervalos de datas personalizados na Analysis Workspace e os salve como componentes de Tempo.
seo-title: Criar intervalos de datas personalizados
solution: Analytics
title: Criar intervalos de datas personalizados
topic: Reports and Analytics
uuid: c 8873 d 41-454 d -4 f 22-ad 1 f -38 cacec 5 a 3 bc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

## Use a 7-day rolling date range {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

Um intervalo de datas é aplicado ao nível de painel. Para adicionar um intervalo de datas para o seu projeto, clique em **Ações** &gt; **Adicionar painel** e especifique um novo intervalo de datas.

No Construtor de intervalo de datas, você pode criar um intervalo de datas personalizado que é exibido no painel Componentes com outros intervalos de datas.

Por exemplo, você pode criar um intervalo de datas que especifica uma janela de acumulado de 7 dias, que terminou há uma semana:

![](assets/create_date_range.png)

Use *`rolling daily`*.

* As configurações de Início seriam do *`current day minus 14 days`*.

* As configurações de Finais seriam do *`current day minus 7 days`*.

Esse intervalo de datas pode ser um componente que você arrasta para qualquer tabela de forma livre.
