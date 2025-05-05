---
title: Análise focada (após cada lançamento do site)
description: Siga estas etapas para garantir que sua implementação permaneça sem erros e em conformidade com seus KPIs.
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
role: Admin, Leader
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 68%

---

# Análise focada (após cada lançamento do site)

Por que você deve analisar sua implementação a intervalos de poucos meses? Para que você possa resolver qualquer problema na qualidade dos dados enquanto ele ainda for pequeno. Se fizer essa Análise focada consistentemente após cada lançamento do site, você descobrirá que as [Análises completas](/help/implement/review/full-review.md) bianuais são muito mais fáceis. Você também evitará que pequenos problemas cresçam e se tornem grandes problemas de dados que podem minar a confiança das partes interessadas.

## 1. Comece com seus cinco KPIs principais

Conhecer os cinco principais indicadores de desempenho (KPIs) ajudará a determinar as métricas e dimensões associadas que você precisa examinar. Se você não atualizou seus KPIs nos últimos seis meses ou se sua empresa ainda não criou KPIs, siga [estas instruções](/help/implement/review/define-kpis.md).

## 2. Verifique se suas métricas e variáveis de KPI ainda estão funcionando bem

Lembre-se: as atualizações de código ao longo do tempo podem ter ramificações não intencionais. Verifique se todas as métricas e dimensões associadas aos seus [5 principais KPIs](/help/implement/review/define-kpis.md) ainda estão funcionando corretamente. O momento ideal para se fazer isso é logo após o lançamento de um site; se você não tiver feito isso nos últimos meses, faça *agora*. Para fazer isso:

* Crie painéis para ver as tendências de hora em hora dessas métricas e variáveis críticas (ou configure [alertas](https://experienceleague.adobe.com/pt-br/docs/analytics/components/alerts/intellligent-alerts) para cada métrica). Em seguida, monitore-as por um ou dois dias para garantir que você está obtendo os dados esperados e que os dados estão corretos. Procure pontos de inflexão. Esteja preparado para corrigir imediatamente quaisquer problemas críticos. Se encontrar discrepâncias, verifique a camada de dados, as regras do gerenciador de tags e as regras de processamento para descobrir o motivo.
* Execute novamente o [Painel de integridade do Analytics](https://express.adobe.com/page/tnNQGNlfzta3b/) para monitorar tendências gerais de suas métricas e variáveis de KPI.

*Para obter mais detalhes sobre como verificar se suas métricas e variáveis estão funcionando corretamente, [leia estas dicas](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608?profile.language=pt-BR) de Sarah Owen, que é especialista no Adobe Analytics.*

## 3. Examine minuciosamente os dados da seção atualizada do site

Verifique se a versão mais recente do site não prejudicou a coleção de dados dessa seção do site: analise todos os códigos e variáveis que correspondem a essa seção para garantir que o novo rastreamento esteja funcionando como projetado.

## 4. Atualize sua documentação

Se você tiver adicionado ou alterado alguma métrica ou variável recentemente, será preciso atualizar seu Documento de requisitos de negócios (BRD) e a Referência de design de solução (SDR).

Se você não tiver a documentação de sua implementação, exporte uma lista de variáveis e crie seu BRD ou seu SDR usando [este modelo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=pt-BR#implementation).

## 5. Corrija imediatamente qualquer problema encontrado na qualidade dos dados

Avalie a situação e faça um plano para corrigir os dados. Em seguida, faça as alterações necessárias, atualize sua documentação e informe as partes interessadas sobre as alterações feitas.

*Assista a este vídeo de dois minutos de Sarah Owen, Adobe Analytics Champion, sobre situações naturais em que você pode ajustar as análises de sua implementação à sua programação:*


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analisar a implementação](https://video.tv.adobe.com/v/3440174?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


