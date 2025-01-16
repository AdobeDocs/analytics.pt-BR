---
description: Use o Número do resumo e as Visualizações de alteração para exibir pontos de dados importantes em um projeto.
title: Número do resumo e alteração do resumo
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: c0855c6bed6a9762c0440e1a8e004ee11020808e
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 93%

---

# [!UICONTROL Número do resumo] e [!UICONTROL Alteração do resumo]

*Este artigo documenta o número do Resumo e a visualização de alteração do Resumo no **Adobe Analytics**.<br/>Consulte [Número do resumo e alteração do resumo](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change) para a versão **Customer Journey Analytics**deste artigo.*

Veja um vídeo sobre essas duas visualizações:

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## Visualização do [!UICONTROL Número do resumo] {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Número do resumo"
>abstract="Crie uma visualização que mostre totais e subtotais."

<!-- markdownlint-enable MD034 -->

Use a visualização do [!UICONTROL Número do resumo] para realçar um número grande que seja importante em um projeto. Essa visualização se comporta das seguintes maneiras:

* Seleciona o total da coluna caso nenhuma célula esteja selecionada.
* Se alguma célula estiver selecionada, mostra o resumo dessa célula.
* Se mais de uma célula estiver selecionada, mostra a primeira célula selecionada.
* Se a coluna estiver selecionada, escolhe o primeiro valor de célula na coluna.

Clique na engrenagem **Configurações de visualização** no canto superior direito para definir as configurações de Número do resumo:

| Configuração | Definição |
|--- |--- |
| [!UICONTROL Porcentagens] | Exibe porcentagens em vez de números brutos. |
| [!UICONTROL Legenda visível] | Exibe informações sobre a métrica mostrada. |
| [!UICONTROL Abreviar valor] | Escolha abreviar valores e mostrar até 3 casas decimais. |
| [!UICONTROL Resumir valor por] | Opte por exibir o máximo, mínimo, médio, mediano ou soma para uma seleção de dados. |

## Visualização do [!UICONTROL Alteração do resumo] {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Alteração de resumo"
>abstract="Crie uma visualização que mostre o delta (alteração) entre dois números"

<!-- markdownlint-enable MD034 -->

Use a visualização [!UICONTROL Alteração do resumo] para mostrar o delta (alteração) entre dois números. As cores verde e vermelha da [!UICONTROL Alteração do resumo] podem ser controladas por meio da [polaridade de evento personalizada](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) ou da opção de métrica calculada [Mostrar tendência ascendente como](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=pt-BR).

Essa visualização se comporta das seguintes maneiras:

* Se nenhuma célula estiver selecionada, compara os dois primeiros valores de célula na coluna.
* Se uma célula estiver selecionada, exibe 0, pois compara o valor da célula a ele mesmo.
* Se duas células estiverem selecionadas, a primeira célula selecionada é tomada como o numerador e a segunda como o denominador.
* Se mais de duas células estiverem selecionadas, considera apenas as duas primeiras para comparação.
* Se um intervalo de células estiver selecionado, compara a primeira com a última célula selecionada no intervalo.
* Se a coluna estiver selecionada, compara o primeiro valor a si mesmo, mostrando uma alteração de 0.


![](assets/summary-change.png)


Clique na engrenagem **Configurações de visualização** no canto superior direito para definir as configurações de Alteração de resumo:

| Configuração | Definição |
| --- | --- |
| [!UICONTROL Porcentagens] | Exibe porcentagens em vez de números brutos. |
| [!UICONTROL Legenda visível] | Exibe informações sobre a métrica mostrada. |
| [!UICONTROL Mostrar variação percentual] | Mostra a variação percentual entre os dois números. |
| [!UICONTROL Mostrar diferença bruta] | Mostra a diferença bruta entre 2 números. Também é possível abreviar valores e mostrar até 3 casas decimais com essa opção. |
