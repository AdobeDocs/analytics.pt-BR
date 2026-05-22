---
title: Suavização inteligente de dados
description: Saiba como o Suavização inteligente de dados analisa tendências históricas para prever o valor de qualquer métrica em um período afetado.
feature: AI Tools
role: User, Admin
exl-id: b7a2e5d5-99d4-408d-84e6-67abff9e8727
TQID: 'https://experienceleague.adobe.com/iqjuEBGaCRcwmWfZo6rC1DXi8y4iyj9gB87tpvXmJdk'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: b7156124-d291-4de4-ac0c-ed17d8078449
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 50f9ff18816ad88f231762b8b37c1ab9e1787b6f
workflow-type: tm+mt
source-wordcount: 256
ht-degree: 3%

---

# Suavização inteligente de dados

Em raras ocasiões, alguns fatores podem afetar a qualidade dos dados. O tráfego de bot, as alterações de implementação ou as interrupções de serviço podem afetar a integridade dos dados coletados. Elas também complicam a análise de como o evento pode ter afetado a integridade dos dados.

A Suavização Inteligente de Dados é um protótipo no [Analytics Labs](/help/analyze/labs.md) que pode ajudar a concluir esta exibição, analisando tendências históricas para prever o valor de qualquer métrica no período afetado. O protótipo aplica algoritmos avançados de aprendizado de máquina para plotar os valores esperados para métricas durante o período em análise.

## Executar Suavização Inteligente de Dados

1. Navegue até o Adobe Analytics Labs:
   ![Laboratórios](assets/labs.png)
1. Inicie o protótipo Suavização inteligente de dados.
   ![Iniciar protótipo](assets/intelligent-ds.png)
1. Adicione a métrica que deve ser analisada à tabela de Forma livre. O protótipo funciona apenas com uma granularidade diária, portanto, verifique se a dimensão na tabela é Dia.
   ![Adicionar métrica](assets/add-metric.png)
1. Escolha um intervalo de datas mais amplo que a janela do evento, mas verifique se ele inclui o evento.
   ![Intervalo de datas](assets/date-range.png)
1. Clique no ícone de engrenagem da métrica na tabela de Forma livre.
   ![Ícone de engrenagem](assets/gear-icon.png)
1. Em [!UICONTROL Configurações de Dados], selecione a opção [!UICONTROL Suavização de dados].
   ![Suavização de dados](assets/column-setting.png)
1. Selecione a data/intervalo de datas correspondente ao evento e clique em [!UICONTROL Aplicar].
Verifique se o intervalo de dados da Suavização de dados é um subconjunto do intervalo de datas selecionado para o painel. A métrica na tabela e no gráfico é substituída pelos valores previstos.
   ![Valores previstos](assets/predictive-values.png)
