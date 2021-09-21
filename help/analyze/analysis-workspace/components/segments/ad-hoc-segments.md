---
description: Use segmentos ad-hoc no Analysis Workspace.
title: Segmentos ad-hoc
feature: Workspace Basics
role: User, Admin
source-git-commit: 27c9a3f8f8faeda934827eac6797dd39ba7dd2ca
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 41%

---


# Segmentos ad-hoc

Este é um vídeo sobre a criação de segmentos ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Você pode criar segmentos ad hoc se quiser explorar rapidamente como um segmento pode afetar seu projeto, sem acessar o Construtor de segmentos. Considere esses segmentos como segmentos temporários em nível de projeto. Normalmente, eles não farão parte da &quot;biblioteca&quot; do segmento, como segmentos de componentes no painel esquerdo. No entanto, é possível torná-las públicas, conforme mostrado abaixo.

1. Solte qualquer tipo de componente (dimensão, item de dimensão, evento, métrica, segmento, modelo de segmento, intervalo de datas) na área de soltar segmentos no topo de um painel. Os tipos de componentes são convertidos automaticamente em segmentos.
Este é um exemplo de como criar um segmento para o domínio de referência do Twitter:

   ![](assets/ad-hoc1.png)

   O painel obtém esse segmento automaticamente e você pode ver os resultados instantaneamente.

1. Adicione até 3 segmentos ad hoc a um painel.
1. Se decidir que deseja salvar esse segmento, consulte a seção &quot;Tornar os segmentos ad-hoc públicos&quot;.

Lembre-se:

* **Não** é possível soltar os seguintes tipos de componentes na zona de segmentos: métricas calculadas e dimensões/métricas; a partir dos quais não pode-se criar segmentos.
* Para dimensões e eventos completos, o Analysis Workspace cria segmentos de ocorrência &quot;existe&quot;. Exemplos: `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Se as opções “não especificado” ou “nenhum” forem soltas na zona de soltar dos segmentos, serão automaticamente convertidas em um segmento “não existe” para que sejam tratadas corretamente na segmentação.

>[!NOTE]
>
>Segmentos criados desse modo são internos no projeto.

## Tornar os segmentos ad-hoc públicos {#ad-hoc-public}

Você pode escolher se deseja tornar os segmentos públicos (globais) seguindo estas etapas:

1. Passe o mouse sobre o segmento no local onde os segmentos são colocados e clique no ícone “i”.
1. No painel de informações que é exibido, clique em **[!UICONTROL Tornar público]**.

   ![](assets/segment-info.png)

