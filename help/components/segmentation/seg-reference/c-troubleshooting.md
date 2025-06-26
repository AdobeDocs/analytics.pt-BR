---
description: Solucione e corrija problemas relacionados a segmentos.
title: Solução de problemas de segmentação
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 50%

---

# Solução de problemas de segmentação

<!-- Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.

-->

## Por que o meu segmento não retorna dados? {#no-data}

Possíveis motivos:

* Aninhamento reverso - por exemplo, aninhando um contêiner de ![Usuário](/help/assets/icons/User.svg) **[!UICONTROL Visitante]** em um contêiner de ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Visita]**.
* O relatório não oferece suporte para a segmentação.
* Nenhum dado corresponde ao critério de segmentação.

## Por que não consigo ver o segmento que criei no Gerenciador de segmentos? {#invisible}

Possíveis motivos:

* Algumas dimensões estão disponíveis somente no Data Warehouse e não no Gerenciador de segmentos.
* O segmento é marcado somente para um conjunto de relatórios específico.
* Um segmento compartilhado pode ter sido excluído por outro usuário.
* Não foi possível carregar os segmentos devido a um problema no data center ou no cache do navegador.
* O segmento não foi salvo.
* O endereço IP pode estar bloqueado na extremidade do usuário.

## Por que os dados exibidos após a aplicação de um segmento parecem incorretos? {#page-data}

Possíveis motivos:

* As regras ou os operadores estão incorretos para o resultado necessário.
* Uso incorreto de containers no segmento.
* As variáveis de tráfego usadas para segmentar não estão definidas corretamente ou expiraram.
