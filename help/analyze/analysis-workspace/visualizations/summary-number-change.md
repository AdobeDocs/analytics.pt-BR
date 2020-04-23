---
description: 'null'
title: Número do resumo e alteração do resumo
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Número do resumo e alteração do resumo

## Visualização do número de resumo

* Seleciona o total da coluna se nenhuma célula estiver selecionada.
* Se uma única célula estiver selecionada, mostra o resumo dessa célula.
* Se mais de uma célula estiver selecionada, mostra a primeira célula selecionada.
* Se a coluna estiver selecionada, escolhe o primeiro valor de célula na coluna.

![](assets/summary-number.png)

## Visualização da alteração do resumo

* Se nenhuma célula estiver selecionada, compara os dois primeiros valores de célula na coluna.
* Se uma célula estiver selecionada, mostra 0, pois compara o valor da célula a si mesma.
* Se duas células forem selecionadas, a primeira célula selecionada será tomada como numerador e a segunda como denominador.
* Se mais de duas células estiverem selecionadas, considera apenas as duas primeiras para comparação.
* Se um intervalo de células for selecionado, compara a primeira com a última célula selecionada no intervalo.
* Se a coluna for selecionada, ela compara o primeiro valor a si mesma, o que mostra uma alteração de 0.
* A cor verde e vermelha da alteração de resumo pode ser controlada por meio de:
   * [Polaridade](https://marketing.adobe.com/resources/help/pt_BR/reference/success_event.html)personalizada do evento.
   * A opção [Mostrar tendência ascendente como](https://marketing.adobe.com/resources/help/pt_BR/analytics/calcmetrics/cm_build_metrics.html) da métrica calculada.

## Configurações de alteração de resumo {#section_2581AC0107634FB4990AB8347E5897AA}

Clique no ícone de engrenagem ao lado da visualização para definir as configurações de Resumo:

| Configuração | Definição |
|--- |--- |
| Porcentagens | Use porcentagens em vez de números brutos. |
| Legenda visível | Mostra as métricas usadas. |
| Opções de Número de resumo: Abreviar valor | Você pode escolher de 0 a 3 casas decimais para valores abreviados. |
| Opções de Alteração de resumo: Mostrar alteração de porcentagem | Mostra a alteração, em porcentagem, entre os 2 números. |
| Opções de Alteração de resumo: Mostrar diferença bruta | Mostra a diferença bruta entre os 2 números. |
