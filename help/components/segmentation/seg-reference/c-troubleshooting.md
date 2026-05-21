---
description: Saiba como solucionar e corrigir problemas relacionados a segmentos.
title: Solução de problemas
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
TQID: https://experienceleague.adobe.com/-9XPy2cFezGBFnygKW4gbHG2zuNBfn5Z29InEDF58ZM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 181
ht-degree: 6%

---

# Solução de problemas

Este artigo lista alguns problemas comuns com segmentos e como solucionar esses problemas.

<!--
Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.
-->

## Por que o meu segmento não retorna dados? {#no-data}

Possíveis motivos:

* Aninhamento reverso - por exemplo, aninhando um contêiner de ![Usuário](/help/assets/icons/User.svg) **[!UICONTROL Visitante]** em um contêiner de ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Visita]**.
* O relatório não suporta segmentação.
* Não há dados que correspondam aos critérios de segmentação.

## Por que não consigo ver o segmento que criei no Gerenciador de segmentos? {#invisible}

Possíveis motivos:

* Algumas dimensões estão disponíveis somente no Data Warehouse e não no Gerenciador de segmentos.
* O segmento é verificado somente para um conjunto de relatórios específico.
* Um segmento compartilhado pode ter sido excluído por outro usuário.
* Não foi possível carregar os segmentos devido a um problema no data center ou no cache do navegador.
* O segmento não foi salvo.
* O endereço IP pode ser bloqueado no final do usuário.

## Por que os dados exibidos após a aplicação de um segmento parecem incorretos? {#page-data}

Possíveis motivos:

* As regras ou os operadores estão incorretos para o resultado necessário.
* Uso incorreto de containers no segmento.
* As variáveis de tráfego usadas para segmentar não estão definidas corretamente ou expiraram.
