---
description: Quando um relatório tem um grande número de valores únicos, a Adobe fornece funcionalidade para garantir que os valores mais importantes apareçam em seu relatório.
title: Valor de baixo tráfego no Adobe Analytics
topic: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Valor de baixo tráfego no Adobe Analytics

Quando um relatório tem um grande número de valores únicos, a Adobe fornece funcionalidade para garantir que os valores mais importantes apareçam em seu relatório. Valores de variável únicos coletados após aproximadamente 500.000 valores existentes são listados em um item de linha intitulado **(tráfego baixo)**.

## Como o tráfego baixo funciona

* O relatório não é afetado se a variável não atingir 500.000 valores únicos em um determinado mês.
* Quando uma variável atinge esse primeiro limite de 500.000, os dados começam a ser classificados em baixo tráfego. Cada valor além desse limite passa pela seguinte lógica:
   * Se um valor já estiver nos relatórios, adicione-o como de costume.
   * Se um valor ainda não estiver no relatório, verifique se esse valor foi visto mais de aproximadamente dez vezes hoje. Se tiver, adicione esse valor ao relatório. Se não tiver sido contado mais de dez vezes, deixe-o sob baixo tráfego.
* Se um conjunto de relatórios atingir mais de 1.000.000 valores únicos, uma filtragem mais agressiva será aplicada:
   * Se um valor já estiver nos relatórios, adicione-o como de costume.
   * Se um valor ainda não estiver no relatório, verifique se esse valor foi visto mais de 100 vezes hoje. Se tiver, adicione o valor ao relatório. Se não, deixe-o sob baixo tráfego.

> [!NOTE] Se um valor de variável receber tráfego suficiente para deixar o bucket de baixo tráfego, os primeiros valores coletados não serão movidos para o respectivo item de linha. Essas primeiras 10 a 100 instâncias ficam sob baixo tráfego.

## Alterar limites de limite exclusivos

Os limites são de 500.000 e 1 milhão de valores únicos por padrão. Esses limites podem ser alterados para cada variável. Entre em contato com o gerente de conta de sua organização para solicitar essa alteração. Ao solicitar uma alteração, inclua:

* A ID do conjunto de relatórios
* A variável para a qual você deseja aumentar o limite
* O primeiro e o segundo limiar desejados

Alterações nos limites podem afetar o desempenho do relatório. A Adobe recomenda usar uma boa avaliação ao solicitar um aumento para valores únicos em uma variável.

Os limites de baixo tráfego não estão visíveis na interface do usuário do Analytics. Solicite a um usuário suportado em sua organização que entre em contato com o Atendimento ao cliente da Adobe se desejar obter mais informações sobre os limites existentes.

## Baixo tráfego usando componentes e outros recursos

Recursos diferentes tratam valores de baixo tráfego de maneiras diferentes.

* **** Data Warehouse: Não há limite para o número de valores únicos nos relatórios do Data Warehouse. Sua arquitetura exclusiva permite o relatório de qualquer número de valores únicos.
   * Em alguns cenários limitados, valores de tráfego baixo ainda podem aparecer. Os exemplos incluem list vars, list props, eVars de comercialização e dimensões detalhadas de canal de marketing.
* **** Segmentação: Se os critérios do segmento incluírem uma variável com um número elevado de valores únicos, os valores capturados sob baixo tráfego não serão incluídos.
* **** Classificações: Os relatórios de classificação também estão sujeitos a limites únicos. Se o valor da variável pai de uma classificação for incluído em tráfego baixo, o valor não será classificado.
   * Se você classificar os valores antes de serem vistos nos dados, esses valores serão contados em direção ao limite exclusivo para esse mês.
