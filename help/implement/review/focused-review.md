---
title: Análise focada (após cada lançamento do site)
description: Siga estas etapas para garantir que sua implementação permaneça sem erros e em conformidade com seus KPIs.
translation-type: tm+mt
source-git-commit: 912e5077889a02c3bf0dea9b079d213bb20f9424
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 83%

---


# Análise focada (após cada lançamento do site)

Por que você deve analisar sua implementação a intervalos de poucos meses? Para que você possa resolver qualquer problema na qualidade dos dados enquanto ele ainda for pequeno. Se fizer essa Análise focada consistentemente após cada lançamento do site, você descobrirá que as [Análises completas](/help/implement/review/full-review.md) bianuais são muito mais fáceis. Você também evitará que pequenos problemas cresçam e se tornem grandes problemas de dados que podem minar a confiança dos interessados.

## 1. Comece com seus cinco KPIs principais

Conhecer os cinco principais indicadores de desempenho (KPIs) ajudará a determinar as métricas e dimensões associadas que você precisa examinar. Se você não atualizou seus KPIs nos últimos seis meses ou se sua empresa ainda não criou KPIs, siga [estas instruções](/help/implement/review/define-kpis.md).

## 2. Verifique se suas métricas e variáveis de KPI ainda estão funcionando bem

Lembre-se: as atualizações de código ao longo do tempo podem ter ramificações não intencionais. Certifique-se de que todas as métricas e dimensões associadas aos seus [5 KPIs principais](/help/implement/review/define-kpis.md) ainda estejam funcionando corretamente. Idealmente, isso deve ser feito logo após um lançamento no site; se você não tiver feito isso nos últimos meses, faça-o *agora*. Para fazer isso:

* Crie painéis para ver visualizações de tendência por hora dessas métricas e variáveis críticas (ou configure [alertas inteligentes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace) para cada métrica). Em seguida, monitore-os por um ou dois dias para garantir que você esteja obtendo os dados esperados e que os dados estejam corretos. Procure pontos de inflexão. Esteja preparado para corrigir imediatamente quaisquer problemas críticos. Se encontrar discrepâncias, verifique a camada de dados, as regras do gerenciador de tags e as regras de processamento para descobrir o motivo.
* Execute novamente o [Painel de integridade do Analytics](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) para monitorar as grandes tendências de suas métricas e variáveis de KPI.

*Para obter mais detalhes sobre como verificar se suas métricas e variáveis estão funcionando corretamente, [leia estas dicas](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) de Sarah Owen, Adobe Analytics Champion.*

## 3. Examine minuciosamente os dados da seção atualizada do site

Verifique se a versão mais recente do site não prejudicou a coleção de dados dessa seção do site: analise todos os códigos e variáveis que correspondem a essa seção para garantir que o novo rastreamento esteja funcionando como projetado.

## 4. Atualize sua documentação

Se você tiver adicionado ou alterado alguma métrica ou variável recentemente, será preciso atualizar seu Documento de requisitos de negócios (BRD) e a Referência de design de solução (SDR).

Se você não tiver a documentação de sua implementação, exporte uma lista de variáveis e crie seu BRD ou sua SDR usando [este modelo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=pt-BR#implementation).

## 5. Corrija imediatamente qualquer problema encontrado na qualidade dos dados

Avalie a situação e faça um plano para corrigir os dados. Em seguida, faça as alterações necessárias, atualize sua documentação e informe as partes interessadas sobre as alterações feitas.

*Assista a este vídeo de dois minutos de Sarah Owen, Adobe Analytics Champion, sobre situações naturais em que você pode ajustar as análises de sua implementação à sua programação:*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
