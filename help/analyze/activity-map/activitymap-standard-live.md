---
description: O Activity Map disponibiliza dois modos básicos para fornecer relatórios complementares da atividade principal.
title: Modo Padrão vs. modo Online
uuid: 8b97b56e-ff20-4a8b-8c37-7f7b45c9a86b
feature: Activity Map
role: User, Admin
exl-id: 2364e7b0-443a-49a8-b084-403501f52360
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 96%

---

# Modo Padrão vs. modo Online

O Activity Map disponibiliza dois modos básicos para fornecer relatórios complementares da atividade principal.

* Modo Padrão, no qual os [Links na página](/help/analyze/activity-map/activitymap-links-report.md) mostram os dados do link, de um único dia a vários dias, agregados ao longo do período integral.
* O modo Online exibe as tendências de atividades em tempo real.

Os dois modos podem ser alternados, clicando no botão Modo na barra de ferramentas.

## Modo Padrão {#section_0C755F30B7EC4A13A62AB9A391AF51E6}

No **Modo padrão**, é possível selecionar o intervalo de datas na barra de ferramentas, como mostrado abaixo.

![](assets/standard_mode.png)

Nesse modo, métricas de Comércio que não tiverem “Participação” ativada são alocadas linearmente. Suponhamos que um usuário clique em um link “iPod mini” na tela inicial, e em seguida navegue por outras 3 páginas. Na quarta página, o usuário compra um iPod mini por US$ 200. O link “iPod mini” receberá $200 de receita de participação e $50 ($200/4) de receita (receita alocada linearmente).

P: E se uma página tiver links com o mesmo nome em regiões separadas? Os links receberão crédito separadamente por estarem em diferentes regiões, mas terem o mesmo nome de link em uma página?

R: Depende de como os dados do link são agregados. No Activity Map, observamos a ID|Região do link referentes a uma certa página, para que os dados alocados sejam referentes à combinação &quot;ID|Região do link&quot;. Nesse caso em que a região é diferente, link|região seriam distintos, e portanto qualquer receita alocada para o primeiro link|região seria diferente de toda a receita alocada referente ao segundo link. Porém, na interface do usuário do Adobe Analytics, pode-se observar somente o relatório de ID do link (em vez do relatório de Link|Região) referente a uma página específica (página detalhada por Link). Nesse outro caso, a receita seria agregada em ambas as regiões.

## Modo Online {#section_D619B77D89A840F0B1C2DEA2715A516A}

No **Modo online**, os dados do Analytics são mostrado em incrementos de 1 a 15 minutos, em uma forma de tendência. Esse modo destina-se à análise e ao acompanhamento das tendências de curto prazo na página da Web.

O modo Online responde às necessidades das empresas de publicação. Essas empresas precisam monitorar as microtendências na popularidade do link dentro de algumas páginas principais. A capacidade de discernir com rapidez quais links estão abaixo do desempenho ou estão se tornando populares é fundamental para os negócios de publicação.

>[!IMPORTANT]
>
>Os conjuntos de relatórios virtuais não são compatíveis com o modo Online, somente com o modo Padrão.

![](assets/live_mode.png)
