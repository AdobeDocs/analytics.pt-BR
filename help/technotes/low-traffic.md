---
description: Quando um relatório possuir um grande número de valores únicos, a Adobe fornece funcionalidades para assegurar que os valores mais importantes apareçam em seu relatório.
title: Valor de tráfego baixo no Adobe Analytics
feature: Métricas
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 65190776da25437e854e0226cd349e3ba13fc8c9
workflow-type: ht
source-wordcount: '641'
ht-degree: 100%

---

# Valor de tráfego baixo no Adobe Analytics

Quando um relatório tem muitos valores únicos, a Adobe fornece funcionalidade para garantir que os valores mais importantes sejam mostrados em seu relatório. Valores de variáveis únicos coletados após aproximadamente 500.000 valores existentes são listados em um item da linha intitulado **[!UICONTROL Tráfego baixo]**.

## Como o [!UICONTROL Tráfego baixo] funciona

* O relatório não é afetado se a variável não atingir 500.000 valores únicos em um determinado mês.
* Quando uma variável atinge esse primeiro limite de 500.000, os dados começam a ser classificados em Tráfego baixo. Cada valor além desse limite passa pela seguinte lógica:
   * Se um valor já estiver nos relatórios, adicione-o como de costume.
   * Se um valor ainda não for visto nos relatórios, ele aparecerá no item da linha [!UICONTROL Tráfego baixo]. Se um valor que foi incluído no item da linha [!UICONTROL Tráfego baixo] for visto por um número significativo de vezes em um curto período, ele começará a ser reconhecido como seu próprio item da linha. O número significativo de vezes que um item deve ser visualizado tem muitas dependências, como o número de servidores de processamento e daemons que estão processando dados para esse conjunto de relatórios específico.
* Se um conjunto de relatórios atingir mais de 1.000.000 valores únicos, uma filtragem mais agressiva será aplicada:
   * Se um valor já estiver nos relatórios, adicione-o como de costume.
   * Se um valor ainda não for visto nos relatórios, ele aparecerá no item da linha [!UICONTROL Tráfego baixo]. Se um valor que foi incluído no item da linha [!UICONTROL Tráfego baixo] for visto por um número significativo de vezes em um curto período, ele começará a ser reconhecido como seu próprio item da linha. O número significativo de vezes que um item deve ser visualizado tem muitas dependências, como o número de servidores de processamento e daemons que estão processando dados para esse conjunto de relatórios específico.

Por que a Adobe move um item da linha [!UICONTROL Tráfego baixo] para seu próprio item da linha? Por exemplo, esse movimento pode reconhecer uma nova página popular ou um novo item que foi adicionado posteriormente no mês (depois que únicos foram excedidos) e que recebe muitas ocorrências/exibições. A movimentação não tem como objetivo capturar tudo o que recebe um determinado número de ocorrências/exibições por dia ou por mês.

## Alterar limites exclusivos

Os limites são de 500.000 e 1 milhão de valores únicos por padrão. Esses limites podem ser alterados para cada variável. Entre em contato com o gerente de conta de sua organização para solicitar essa alteração. Ao solicitar uma alteração, inclua:

* A ID do conjunto de relatórios
* A variável para a qual você deseja aumentar o limite
* O primeiro e o segundo limites desejados

Alterações nos limites podem afetar o desempenho do relatório. A Adobe recomenda avaliar bem a situação ao solicitar um aumento para valores únicos em uma variável.

Os limites de tráfego baixo não estão visíveis na interface do usuário do Analytics. Solicite a um usuário com suporte em sua organização que entre em contato com o Atendimento ao cliente da Adobe se desejar obter mais informações sobre os limites existentes.

## Tráfego baixo usando componentes e outros recursos

Recursos diferentes tratam valores de tráfego baixo de maneiras diferentes.

* **Data Warehouse:** não há limite para o número de valores únicos nos relatórios do Data Warehouse. Sua arquitetura única permite gerar relatórios para qualquer número de valores únicos.
   * Em alguns cenários limitados, valores de tráfego baixo ainda podem aparecer. Os exemplos incluem vars de lista, props de lista, eVars de merchandising e dimensões detalhadas de canal de marketing.
* **Segmentação:** se os critérios do segmento incluírem uma variável com um número elevado de valores únicos, os valores capturados em Tráfego baixo não serão incluídos.
* **Classificações:** os relatórios de classificação também estão sujeitos a limites únicos. Se o valor da variável pai de uma classificação for incluído em Tráfego baixo, o valor não será classificado.
   * Valores de classificação de tráfego baixo obtidos por meio do importador podem ser visualizados no Data Warehouse. <!-- AN-115871 -->
   * Valores de classificação de tráfego baixo obtidos pelo construtor de regras *não podem* ser visualizados no Data Warehouse. <!-- AN-122872 -->
