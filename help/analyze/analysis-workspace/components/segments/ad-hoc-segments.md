---
description: Use segmentos ad hoc no Analysis Workspace.
title: Segmentos ad hoc
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: 931e9b0bd71abd852c515cd2e7d99dc9ae423a63
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 48%

---

# Segmentos de projeto ad hoc

Segmentos de projeto ad hoc permitem arrastar e soltar qualquer componente diretamente na área de soltar do painel para criar um segmento. O segmento se torna um [segmento no nível do projeto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?#what-are-project-only-segments%3F) local para o projeto atual.

Este é um vídeo sobre como criar segmentos de projetos ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. Solte qualquer tipo de componente (dimensão, item de dimensão, evento, métrica, segmento, modelo de segmento, intervalo de datas) na zona de lançamento do segmento na parte superior de um painel. Os tipos de componentes são convertidos automaticamente em segmentos ad hoc ou [Segmentos rápidos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html) se compatível.
Este é um exemplo de como criar um segmento para o domínio referenciador do Twitter:

   ![](assets/ad-hoc1.png)

   O painel aplica de forma automática esse segmento e você pode ver os resultados instantaneamente.

1. Você pode adicionar um número ilimitado de segmentos a um painel.
1. Se você decidir salvar esse segmento, consulte a seção abaixo.

Lembre-se:

* **Não** é possível soltar os seguintes tipos de componentes na zona de segmentos: métricas calculadas e dimensões/métricas; a partir dos quais não pode-se criar segmentos.
* Para dimensões e eventos completos, o Analysis Workspace cria segmentos de ocorrência &quot;existe&quot;. Exemplos: `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Se as opções “não especificado” ou “nenhum” forem soltas na zona de soltar dos segmentos, serão automaticamente convertidas em um segmento “não existe” para que sejam tratadas corretamente na segmentação.

Para obter uma comparação dos diferentes segmentos que podem ser criados e aplicados em um projeto, acesse [here](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

## Salvar segmentos ad hoc {#ad-hoc-save}

Segmentos ad hoc podem ser disponibilizados para outros projetos ao salvá-los.

1. Passe o mouse sobre o segmento no local onde os segmentos são colocados e clique no ícone “i”.
1. Clique no lápis de edição para acessar o Construtor de segmentos.
1. Verificar **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes]**.
1. Clique em **[!UICONTROL SALVAR]**.

Depois de salvo, o segmento fica disponível na lista de componentes do painel esquerdo e pode ser compartilhado com outros usuários no Gerenciador de segmentos.
