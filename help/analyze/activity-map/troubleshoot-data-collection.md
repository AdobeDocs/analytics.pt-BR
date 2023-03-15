---
title: Solução de problemas de coleta de dados do Activity Map
description: Determine por que não é possível ver os dados do Activity Map em solicitações de imagem
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Solução de problemas de coleta de dados do Activity Map

Se você não vir dados para dimensões de Activity Map, use esta página para ajudar a determinar por quê.

## Confirmar a coleta de dados usando o depurador

Primeiro, verifique se o AppMeasurement coleta dados de Activity Map corretamente.

1. Baixe e instale o [Extensão do Chrome do Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR).
2. Navegue até a página da Web e clique em um link.
3. Quando a página subsequente for carregada, abra o depurador. Verifique se você vê as variáveis de dados de contexto de Activity Map entre `activitymap.` e `.activitymap`:

![Dados do depurador](assets/debugger.png)

## Possíveis motivos pelos quais dados de Activity Map não estão presentes

Verifique cada um dos seguintes itens para ter certeza de que os componentes de Activity Map estão presentes:

* **Versão do AppMeasurement**: Activity Map é compatível com v1.6 e superior. Muitos problemas de caso de borda são resolvidos ao atualizar para a versão estável mais recente do AppMeasurement.
* **módulo Activity Map**: verifique se a variável `AppMeasurement_Module_Activity_Map` o módulo está presente no `AppMeasurement.js` arquivo. Se sua implementação usar o Adobe Experience Platform para coletar dados, verifique se **[!UICONTROL Ativar ClickMap]** é marcado ao configurar a extensão do Analytics em **[!UICONTROL Rastreamento de link]**.
* **A variável `s_sq` cookie**: o Activity Map depende do `s_sq` cookie para coleta de dados.
   * Certifique-se de que a variável `cookieDomainPeriods` estiver definida corretamente, especialmente para domínios regionais, como `*.co.uk` ou `*.co.jp`.
   * Certifique-se de que a variável `linkInternalFilters` é definida com os valores desejados. Se um link clicado não corresponder aos filtros internos, o Activity Map o considerará um link de saída e não coletará dados.
* **sobreposição de Activity Map em execução**: o AppMeasurement não rastreia dados de cliques da página da Web quando a sobreposição de Activity Map está ativada.
