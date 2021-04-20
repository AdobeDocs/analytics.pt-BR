---
title: Solução de problemas de coleta de dados do Activity Map
description: Determine por que você não pode ver dados do Activity Map em solicitações de imagem
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 3%

---


# Solução de problemas de coleta de dados do Activity Map

Se você não vir dados para dimensões do Activity Map, use esta página para ajudar a determinar por quê.

## Confirmar a coleta de dados usando o depurador

Primeiro, verifique se o AppMeasurement coleta os dados de Activity Map corretamente.

1. Baixe e instale a [Extensão do Chrome do Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/pt-BR/debugger/using/experience-cloud-debugger.html).
2. Navegue até a página da Web e clique em um link.
3. Quando a página subsequente for carregada, abra o depurador da . Valide se você vê variáveis de dados de contexto de Activity Map entre `activitymap.` e `.activitymap`:

![Dados do depurador](assets/debugger.png)

## Possíveis motivos pelos quais os dados de Activity Map não estão presentes

Verifique cada um dos itens a seguir para verificar se os componentes de Activity Map estão presentes:

* **Versão** do AppMeasurement: Activity Map é compatível com v1.6 e superior. Muitos problemas de caso de borda são resolvidos ao atualizar para a versão estável mais recente do AppMeasurement.
* **Módulo** Activity Map: Verifique se o  `AppMeasurement_Module_Activity_Map` módulo está presente no  `AppMeasurement.js` arquivo . Se sua implementação usar o Adobe Experience Platform Launch, verifique se a opção **[!UICONTROL Ativar ClickMap]** está marcada ao configurar a extensão do Analytics em **[!UICONTROL Rastreamento de link]**.
* **O  `s_sq` cookie**: O Activity Map depende do  `s_sq` cookie para a coleta de dados.
   * Verifique se a variável `cookieDomainPeriods` está definida corretamente, especialmente para domínios regionais como `*.co.uk` ou `*.co.jp`.
   * Verifique se a variável `linkInternalFilters` está definida com os valores desejados. Se um link clicado não corresponder aos filtros internos, o Activity Map o considerará um link de saída e não coletará dados.
* **Activity Map overlay executando**: O AppMeasurement não rastreia os dados de cliques da página da Web quando a sobreposição de Activity Map está ativada.
