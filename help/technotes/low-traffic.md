---
description: Quando um relatório possuir um grande número de valores únicos, a Adobe fornece funcionalidades para assegurar que os valores mais importantes apareçam em seu relatório.
title: Valor de tráfego baixo no Adobe Analytics
topic: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Valor de tráfego baixo no Adobe Analytics

Quando um relatório possuir um grande número de valores únicos, a Adobe fornece funcionalidades para assegurar que os valores mais importantes apareçam em seu relatório. Valores de variável únicos coletados após aproximadamente 500.000 valores existentes são listados em um item de linha intitulado **(Tráfego baixo)**.

## Como o tráfego baixo funciona

* O relatório não é afetado se a variável não atingir 500.000 valores únicos em um determinado mês.
* Quando uma variável atinge esse primeiro limite de 500.000, os dados começam a ser classificados em Tráfego baixo. Cada valor além desse limite passa pela seguinte lógica:
   * Se um valor já estiver nos relatórios, adicione-o como de costume.
   * Se um valor ainda não estiver no relatório, verifique se esse valor foi visto mais de aproximadamente dez vezes hoje. Se tiver sido, adicione esse valor ao relatório. Se não tiver sido contado mais de dez vezes, deixe-o em Tráfego baixo.
* Se um conjunto de relatórios atingir mais de 1.000.000 valores únicos, uma filtragem mais agressiva será aplicada:
   * Se um valor já estiver nos relatórios, adicione-o como de costume.
   * Se um valor ainda não estiver no relatório, verifique se esse valor foi visto mais de aproximadamente 100 vezes hoje. Se tiver sido, adicione o valor ao relatório. Se não, deixe-o em Tráfego baixo.

> [!NOTE] Se um valor de variável receber tráfego suficiente para deixar a categoria de tráfego baixo, os primeiros valores coletados não serão movidos para o respectivo item de linha. As primeiras 10-100 instâncias ficam em Tráfego baixo.

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
   * Se você classificar os valores antes de serem vistos nos dados, esses valores serão contados de acordo com o limite exclusivo para esse mês.
