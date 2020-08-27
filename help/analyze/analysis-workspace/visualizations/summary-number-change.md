---
description: Use o Número do resumo e as visualizações de Alteração para exibir pontos de dados importantes em um projeto.
title: Número do resumo e alteração do resumo
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 0a3c4a6839d0c6ee2d8a98394ed38c433ea811d1
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 52%

---


# Número do resumo e alteração do resumo

## Visualização do número de resumo {#summary-number}

Use a visualização Número do resumo para realçar um grande número que é importante em um projeto. Essa visualização se comporta das seguintes maneiras:

* Seleciona o total da coluna caso nenhuma célula esteja selecionada.
* Se alguma célula estiver selecionada, mostra o resumo dessa célula.
* Se mais de uma célula estiver selecionada, mostra a primeira célula selecionada.
* Se a coluna estiver selecionada, escolhe o primeiro valor de célula na coluna.

![](assets/summary-number.png)

Clique na engrenagem de configurações **de** visualização na parte superior direita para definir as configurações de Número do resumo:

| Configuração | Definição |
|--- |--- |
| Porcentagens | Exibe porcentagens em vez de números brutos. |
| Legenda visível | Exibe informações sobre a métrica exibida. |
| Abreviar valor | Escolha abreviar valores e mostrar até 3 casas decimais. |
| Resumir valor por | Opte por exibir o máximo, mínimo, médio, mediano ou soma para uma seleção de dados. |

## Visualização da alteração do resumo {#summary-change}

Use a visualização de Alteração de resumo para mostrar o delta (alteração) entre dois números. As cores verde e vermelho da Alteração do resumo podem ser controladas por meio da polaridade [do evento](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/success-events/success-event.html) personalizado ou da opção [Mostrar tendência para](https://docs.adobe.com/content/help/pt-BR/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) cima de uma métrica calculada.

Essa visualização se comporta das seguintes maneiras:

* Se nenhuma célula estiver selecionada, compara os dois primeiros valores de célula na coluna.
* Se uma célula estiver selecionada, exibe 0, pois compara o valor da célula a ele mesmo.
* Se duas células estiverem selecionadas, a primeira célula selecionada é tomada como o numerador e a segunda como o denominador.
* Se mais de duas células estiverem selecionadas, considera apenas as duas primeiras para comparação.
* Se um intervalo de células estiver selecionado, compara a primeira com a última célula selecionada no intervalo.
* Se a coluna estiver selecionada, compara o primeiro valor a si mesmo, mostrando uma alteração de 0.

![](assets/summary-change.png)

Clique na engrenagem de configurações **de** visualização na parte superior direita para definir as configurações de Alteração de resumo:

| Configuração | Definição |
|--- |--- |
| Porcentagens | Exibe porcentagens em vez de números brutos. |
| Legenda visível | Exibe informações sobre a métrica exibida. |
| Mostrar alteração de porcentagem | Mostra a alteração percentual entre os 2 números. |
| Mostrar diferença bruta | Mostra a diferença bruta entre 2 números. Também é possível abreviar valores e mostrar até 3 casas decimais com essa opção. |
