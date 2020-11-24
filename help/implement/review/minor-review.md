---
title: Revisão de implementação secundária (após cada lançamento de site)
description: Siga estas etapas para garantir que sua implementação permaneça livre de erros e em conformidade com seus KPIs.
translation-type: tm+mt
source-git-commit: 82064e267729b6995402bd122c6f71b3d38967a3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Revisão de implementação secundária (após cada lançamento de site)

Por que você deve revisar sua implementação após cada lançamento do site? Como é necessário verificar se as atualizações de código não tinham ramificações não intencionais, você deve resolver problemas com a qualidade dos dados enquanto ainda são pequenos. Se você fizer consistentemente essa Minor Review após cada lançamento do site, descobrirá que suas [Principais revisões](/help/implement/review/major-review.md) (a cada 6 meses) são muito mais fáceis. Você também evitará que pequenas questões cresçam em grandes questões de dados que poderiam corroer a confiança dos interessados.

## 1. Como a versão afetou os dados daquela seção do site?

Realize um teste completo da unidade: Revise todos os códigos e variáveis que correspondem à seção do site que você acabou de atualizar para garantir que o novo rastreamento esteja funcionando como esperado.

## 2. Atualize sua documentação

Atualize seu Documento de requisitos de negócios (BRD) e a Referência de design de solução (SDR) com quaisquer variáveis adicionadas/alteradas para acomodar a inicialização.

Não tem documentação de sua implementação? Exporte uma lista de variáveis e crie seu BRD ou SDR usando [este modelo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 3. Start com seus 5 KPIs principais

Conhecer os 5 principais indicadores de desempenho (KPIs) o ajudará a determinar as métricas e dimensões associadas que você precisa examinar. Se você não atualizou seus KPIs nos últimos 6 meses ou se sua empresa ainda não criou KPIs, siga [estas instruções](/help/implement/review/define-kpis.md).

## 4. Todas as métricas e variáveis de KPI ainda estão funcionando bem após o lançamento?

Lembre-se, qualquer atualização de código pode ter ramificações não intencionais. Verifique se todas as métricas e dimensões associadas aos [seus 5 KPIs](/help/implement/review/define-kpis.md) principais ainda estão funcionando corretamente. Para fazer isso:

* **Crie painéis** para ver as visualizações de tendência por hora dessas métricas e variáveis críticas (Você também pode configurar alertas inteligentes para cada métrica) e monitorá-los por um dia ou dois após o lançamento, para garantir que você esteja obtendo os dados esperados e que os dados estejam corretos. Procure pontos de inflexão. Esteja preparado para corrigir imediatamente quaisquer problemas críticos. Se você encontrar discrepâncias que não pareçam corretas, verifique a camada de dados, as regras do gerenciador de tags e as regras de processamento para descobrir o motivo.
* **Execute novamente o Painel** de integridade do Analytics para monitorar as grandes tendências de suas métricas e variáveis de KPI.
Para obter mais detalhes sobre como verificar se suas métricas e variáveis estão funcionando corretamente, leia essas dicas de Adobe Analytics Champion Sarah Owen.

## 5. Há lacunas na qualidade de seus dados?

Avalie a situação e faça um plano para corrigir os dados. Em seguida, faça as alterações necessárias, atualize sua documentação e informe as partes interessadas sobre as alterações feitas.

Assista a este vídeo de Sarah Owen, campeã do Adobe Analytics, sobre os momentos naturais em que você pode ajustar as revisões de sua implementação ao seu agendamento:

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
