---
title: Solução de problemas de coleta de dados do Activity Map
description: Determine por que não é possível ver os dados de Activity Map em solicitações de imagem
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---


# Solução de problemas de coleta de dados do Activity Map

Se você não vir dados para dimensões de Activity Map, use esta página para ajudar a determinar por quê.

## Confirmar coleta de dados usando o depurador

Primeiro, certifique-se de que o AppMeasurement colete dados de Activity Map corretamente.

1. Download and install the [Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/pt-BR/debugger/using/experience-cloud-debugger.html).
2. Navegue até sua página da Web e clique em um link.
3. Quando a página subsequente for carregada, abra o depurador. Valide se você vê variáveis de dados de contexto de Activity Map entre `activitymap.` e `.activitymap`:

![Dados do depurador](assets/debugger.png)

## Possíveis motivos pelos quais os dados de Activity Map não estão presentes

Verifique cada um dos seguintes itens para verificar se os componentes do Activity Map estão presentes:

* **Versão** do AppMeasurement: Activity Map é compatível com v1.6 e superior. Muitos problemas de caso de borda são resolvidos ao atualizar para a versão estável mais recente do AppMeasurement.
* **módulo** Activity Map: Verifique se o `AppMeasurement_Module_Activity_Map` módulo está presente no seu `AppMeasurement.js` arquivo. Se sua implementação usar o Adobe Experience Platform Launch, verifique se a opção **[!UICONTROL Ativar ClickMap]** está marcada ao configurar a extensão do Analytics em Rastreamento **[!UICONTROL de]** link.
* **O`s_sq`cookie**: Activity Map depende do `s_sq` cookie para a coleta de dados.
   * Certifique-se de que a `cookieDomainPeriods` variável esteja definida corretamente, especialmente para domínios regionais como `*.co.uk` ou `*.co.jp`.
   * Verifique se a `linkInternalFilters` variável está definida com os valores desejados. Se um link clicado não corresponder aos filtros internos, o Activity Map o considerará um link de saída e não coletará dados.
* **sobreposição de Activity Map em execução**: O AppMeasurement não rastreia os dados de clique da sua página da Web quando a sobreposição de Activity Map está ativada.
