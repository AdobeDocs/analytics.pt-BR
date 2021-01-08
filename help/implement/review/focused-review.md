---
title: Revisão focada (após cada lançamento do site)
description: Siga estas etapas para garantir que sua implementação permaneça livre de erros e em conformidade com seus KPIs.
translation-type: tm+mt
source-git-commit: a7f1da79bd5a6f78ed1a706ccae01b03a2f5665c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---


# Revisão focada (após cada lançamento do site)

Por que você deve revisar sua implementação a cada poucos meses? Então você pode resolver qualquer problema com a qualidade dos dados enquanto eles ainda são pequenos. Se você fizer essa Revisão Focalizada consistentemente após cada lançamento de site, descobrirá que as [Revisões Completas](/help/implement/review/full-review.md) bianuais são muito mais fáceis. Você também evitará que pequenas questões cresçam em grandes questões de dados que poderiam corroer a confiança dos interessados.

## 1. Start com seus 5 KPIs principais.

Conhecer os 5 principais indicadores de desempenho (KPIs) o ajudará a determinar as métricas e dimensões associadas que você precisa examinar. Se você não atualizou seus KPIs nos últimos 6 meses ou se sua empresa ainda não criou KPIs, siga [estas instruções](/help/implement/review/define-kpis.md).

## 2. Verifique se suas métricas e variáveis de KPI ainda estão funcionando bem.

Lembre-se, as atualizações de código ao longo do tempo podem ter ramificações não intencionais. Verifique se todas as métricas e dimensões associadas a [seus 5 KPIs principais](/help/implement/review/define-kpis.md) ainda estão funcionando corretamente. Idealmente, isso deve ser feito logo após um lançamento no site; se você não tiver feito isso nos últimos meses, faça isso *now*. Para fazer isso:

* **Crie** painéis para ver as visualizações de tendências por hora dessas métricas e variáveis críticas. Você também pode configurar alertas inteligentes para cada métrica e monitorá-los por um ou dois dias para garantir que você obtenha os dados esperados e que os dados estejam corretos. Procure pontos de inflexão. Esteja preparado para corrigir imediatamente quaisquer problemas críticos. Se encontrar discrepâncias, verifique a camada de dados, as regras do gerenciador de tags e as regras de processamento para descobrir o motivo.
* **Execute novamente o** Painel de integridade do Analytics para monitorar as grandes tendências de suas métricas e variáveis de KPI.

Para obter mais detalhes sobre como verificar se suas métricas e variáveis estão funcionando corretamente, [leia essas dicas](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) da Adobe Analytics Champion Sarah Owen.

## 3. Examine minuciosamente os dados da seção atualizada do site.

Certifique-se de que a versão mais recente do site não tenha afetado negativamente a coleta de dados dessa seção do site: analise todos os códigos e variáveis que correspondem a essa seção para garantir que o novo rastreamento esteja funcionando como projetado.

## 4. Atualize sua documentação.

Se você tiver adicionado ou alterado alguma métrica ou variável recentemente, precisará atualizar seu Documento de requisitos de negócios (BRD) e a Referência de design de solução (SDR).

Se você não tiver a documentação de sua implementação, exporte uma lista de variáveis e crie seu BRD ou SDR usando [este modelo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 5. Corrija imediatamente quaisquer lacunas encontradas na qualidade dos dados.

Avalie a situação e faça um plano para corrigir os dados. Em seguida, faça as alterações necessárias, atualize sua documentação e informe as partes interessadas sobre as alterações feitas.

*Assista a este vídeo de 2 minutos da Adobe Analytics Champion Sarah Owen sobre os momentos naturais em que você pode ajustar as revisões de sua implementação ao seu agendamento:*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
