---
title: Suavização inteligente de dados
description: Saiba como a Suavização de dados inteligente analisa as tendências históricas para prever o valor de qualquer métrica dentro de um período de tempo afetado.
feature: Ferramentas de IA
role: User, Admin
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 5%

---

# Suavização inteligente de dados

Em raras ocasiões, alguns fatores podem afetar a qualidade dos dados. O tráfego de bot, as alterações de implementação ou as interrupções do serviço podem afetar a integridade dos dados coletados. Eles também complicam a análise de como o evento pode ter afetado a integridade dos dados.

A Suavização de dados inteligente é um protótipo em [Analytics Labs](/help/analyze/tech-previews/overview.md) que pode ajudar a concluir essa visualização ao analisar tendências históricas para prever o valor de qualquer métrica dentro do período afetado. O protótipo aplica algoritmos avançados de aprendizado de máquina para traçar os valores esperados para as métricas durante o período de tempo que está sendo analisado.

## Executar Suavização de Dados Inteligente

1. Navegue até Adobe Analytics Labs:
   ![Labs](assets/labs.png)
1. Inicie o protótipo de Suavização inteligente de dados .
   ![Iniciar protótipo](assets/intelligent-ds.png)
1. Adicione a métrica que deve ser analisada à tabela de forma livre. O protótipo só funciona com granularidade diária, portanto, verifique se a dimensão na tabela é Dia.
   ![Adicionar métrica](assets/add-metric.png)
1. Escolha um intervalo de datas maior que a janela do evento, mas verifique se ele inclui o evento.
   ![Intervalo de datas](assets/date-range.png)
1. Clique no ícone de engrenagem para a métrica na tabela de Forma livre.
   ![Ícone de engrenagem](assets/gear-icon.png)
1. Em [!UICONTROL Data Settings], selecione a opção [!UICONTROL Data smoothing].
   ![Suavização de dados](assets/column-setting.png)
1. Selecione o intervalo de datas/datas correspondente ao evento e clique em [!UICONTROL Aplicar].
Certifique-se de que o intervalo de dados para a suavização de dados seja um subconjunto do intervalo de datas selecionado para o painel. As métricas na tabela e no gráfico são substituídas pelos valores previstos.
   ![Valores previstos](assets/predictive-values.png)