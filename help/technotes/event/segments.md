---
title: Excluir datas específicas na análise
description: Dicas para excluir datas ou intervalos de datas se você não quiser incluí-los nos relatórios.
exl-id: 744666c0-17f3-443b-9760-9c8568bec600
feature: Curate and Share, Segmentation
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 2%

---

# Excluir datas específicas na análise

Se você tiver dados [afetados por um evento](overview.md), poderá usar um segmento para excluir qualquer intervalo de datas que não deseja incluir em seus relatórios. Segmentar as datas afetadas pelo evento pode ajudar a impedir que sua organização tome decisões sobre dados parciais.

## Isolar dias afetados {#isolate}

Crie um segmento que isole o dia ou o intervalo de datas afetado. Esse segmento é útil se você quiser apenas se concentrar nos dias do problema para ver mais informações sobre seu impacto.

1. Abra o construtor de segmentos indo até **[!UICONTROL Componentes]** > **[!UICONTROL Segmentos]** e clique em **[!UICONTROL Adicionar]**.
2. Arraste a dimensão &quot;Dia&quot; para a tela de definição e defina-a como o dia que deseja isolar.
3. Repita a etapa acima para cada dia que deseja isolar no relatório.

![Segmento de dias afetado](assets/affected_days.jpg)

>[!TIP]
>
>Para alterar a instrução OR para uma instrução AND, clique na seta para baixo ao lado de OR e selecione AND.

A Adobe recomenda usar os componentes da dimensão laranja, e não os componentes de intervalo de datas violeta. Se você usar componentes de intervalo de datas violeta, eles substituirão o intervalo de calendário do projeto:

![Excluir tipo de dia do segmento](assets/exclude_segment_day_type.jpg)

## Excluir dias afetados {#exclude}

Crie um segmento que exclua o dia ou intervalo de datas afetado. Esse segmento é útil se você quiser excluir os dias que tiveram problemas para minimizar o impacto nos relatórios gerais.

1. Abra o construtor de segmentos indo até **[!UICONTROL Componentes]** > **[!UICONTROL Segmentos]** e clique em **[!UICONTROL Adicionar]**.
2. Na parte superior direita da tela de definição do segmento, clique em **[!UICONTROL Opções]** > **[!UICONTROL Excluir]**.
3. Arraste a dimensão &quot;Dia&quot; para a tela de definição e defina-a como o dia que deseja remover.
4. Repita a etapa acima para cada dia que desejar remover em seu relatório.

![Excluir dias afetados](assets/exclude_affected_days.jpg)

## Usar estes segmentos em relatórios

Depois de criar o segmento de exclusão, você pode usá-lo exatamente como usaria outros segmentos.

### Comparar segmentos em um relatório de tendências {#compare}

Você pode aplicar o segmento &quot;Dias afetados&quot; e o segmento &quot;Excluir dias afetados&quot; em um relatório para compará-los lado a lado. Arraste ambos os segmentos acima ou abaixo de uma métrica para compará-los:

![Ambos os segmentos](assets/affected_and_exclude.png)

Se não quiser mostrar zeros na tabela ou nas visualizações (causando declínios), habilite a **[!UICONTROL Interpretar zero como nenhum valor]** nas configurações de coluna.

![Interpretar zero](assets/interpret_zero.png)

Se não quiser mostrar zeros na tabela ou nas visualizações (causando declínios), habilite a **[!UICONTROL Interpretar zero como nenhum valor]** nas configurações de coluna.

![Interpretar zero](assets/interpret_zero.png)

### Aplicar o segmento excluído a um projeto {#apply}

Você pode aplicar o segmento &quot;Excluir dias afetados&quot; a um projeto do Workspace. Arraste o segmento excluído para a seção da tela do Workspace rotulada *Solte um segmento aqui*.

>[!TIP]
>
>Inclua uma observação sobre os dados excluídos na descrição do painel para ajudar quem está visualizando o relatório. Clique com o botão direito no título de um painel e clique em **[!UICONTROL Editar descrição]**.

![Segmento aplicado a um painel](assets/exclude_segment_panel.jpg)

### Usar o segmento excluído em um conjunto de relatórios virtual {#use-vrs}

Você pode usar o segmento em um [conjunto de relatórios virtuais](/help/components/vrs/vrs-about.md) para excluir os dados de forma mais conveniente. Essa opção é ideal, pois você não precisa se lembrar de aplicar o segmento para cada relatório que inclua o intervalo de datas afetado. Se você já usa conjuntos de relatórios virtuais como fonte primária de dados, é possível adicionar o segmento a um conjunto de relatórios virtuais existente.

1. Navegue até **[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de relatórios virtuais]**.
2. Clique em **[!UICONTROL Adicionar]**.
3. Insira o nome e a descrição desejados para o conjunto de relatórios virtual.
4. Arraste o segmento excluído para a área rotulada **[!UICONTROL Adicionar segmento]**.
5. Clique em **[!UICONTROL Continuar]** no canto superior direito e em **[!UICONTROL Salvar]**.

![Segmento aplicado ao conjunto de relatórios virtual](assets/exclude_segment_vrs.png)
