---
description: Quando um relatório tem um grande número de valores únicos, a Adobe fornece funcionalidade para garantir que os valores mais importantes sejam exibidos em seu relatório.
seo-description: Quando um relatório tem um grande número de valores únicos, a Adobe fornece funcionalidade para garantir que os valores mais importantes sejam exibidos em seu relatório.
seo-title: Valor de tráfego baixo no Adobe Analytics
solution: Analytics
title: Valor de tráfego baixo no Adobe Analytics
topic: Métricas
uuid: 56 f 723 f 8-94 e 8-478 f -8 ea 3-16 dad 21 dfa 1 f
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Valor de tráfego baixo no Adobe Analytics

Quando um relatório tem um grande número de valores únicos, a Adobe fornece funcionalidade para garantir que os valores mais importantes sejam exibidos em seu relatório. Unique variable values collected after approximately 500,000 existing values are listed under a line item titled **(Low-Traffic)**.

## Como funciona o tráfego baixo

* O relatório não é afetado se a variável não atingir 500,000 valores únicos em um determinado mês.
* Quando uma variável atinge esse primeiro limite de 500,000, os dados começam a ser armazenados sob tráfego baixo. Cada valor além desse limite passa pela seguinte lógica:
   * Se um valor já estiver em relatórios, adicione-o a esse valor como de costume.
   * Se um valor ainda não estiver nos relatórios, verifique se esse valor foi visto mais do que aproximadamente dez vezes hoje. Se tiver, adicione este valor aos relatórios. Se não tiver sido contado mais de dez vezes, deixe-o sob baixo tráfego.
* Se um conjunto de relatórios atingir mais de 1,000,000 valores únicos, a filtragem mais agressiva será aplicada:
   * Se um valor já estiver em relatórios, adicione-o a esse valor como de costume.
   * Se um valor ainda não estiver nos relatórios, verifique se esse valor foi visto mais de aproximadamente 100 vezes hoje. Se tiver, adicione o valor ao relatório. Se não for, deixe sob baixo tráfego.

> [!NOTE] Se um valor de variável receber tráfego suficiente para sair do bucket de baixo tráfego, os primeiros valores coletados não serão movidos para o item de linha correspondente. Essas primeiras 10-100 instâncias permanecem sob baixo tráfego.

## Alteração de limites exclusivos de limite

Os limites são de 500.000 e 1 milhão de valores únicos por padrão. Esses limites podem ser alterados de acordo com cada variável. Entre em contato com o gerente da conta de sua organização para solicitar essa alteração. Ao solicitar uma alteração, inclua:

* A ID do conjunto de relatórios
* A variável que você deseja aumentar o limite para
* O primeiro e o segundo limite desejados

Essa alteração pode receber um custo adicional e depende do contrato. As alterações nos limites também podem afetar o desempenho do relatório. A Adobe recomenda usar um bom discernimento ao solicitar um aumento para valores exclusivos em uma variável.

Os limites de tráfego baixo não estão visíveis na interface do usuário do Analytics. Faça com que um usuário suportado em sua organização entre em contato com o Atendimento ao cliente se desejar mais informações sobre os limites existentes.

## Tráfego baixo usando componentes e outros recursos

Diferentes recursos tratam valores de baixo tráfego de maneiras diferentes.

* **Data Warehouse:** Não há limite para o número de valores únicos nos relatórios do Data Warehouse. A arquitetura exclusiva permite o relatório de qualquer número de valores únicos.
   * Em alguns cenários limitados, os valores de baixo tráfego ainda podem aparecer. Exemplos incluem vars de lista, propriedades de lista, evars de comercialização e dimensões de detalhes do canal de marketing.
* **Segmentação:** Se os critérios do segmento incluírem uma variável com um alto número de valores únicos, os valores capturados sob baixo tráfego não serão incluídos.
* **Classificações:** Os relatórios de classificação também estão sujeitos a limites exclusivos. Se o valor da variável pai de uma classificação estiver incluído sob baixo tráfego, o valor não será classificado.
   * Se você classificar valores antes de serem vistos nos dados, esses valores contam para o limite único para aquele mês.
