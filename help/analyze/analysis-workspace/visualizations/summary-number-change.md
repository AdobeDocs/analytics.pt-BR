---
description: Use o Número do resumo e as Visualizações de alteração para exibir pontos de dados importantes em um projeto.
title: Número do resumo e alteração do resumo
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: c4f6a7a3d81160a1c86ebfa70d1e376882ccfee2
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 84%

---

# Número do resumo e alteração do resumo

Aqui está um vídeo sobre essas duas visualizações:

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## [!UICONTROL Visualização do número de resumo] {#summary-number}

Use o [!UICONTROL Número do resumo] visualização para destacar um grande número que é importante em um projeto. Essa visualização se comporta das seguintes maneiras:

* Seleciona o total da coluna caso nenhuma célula esteja selecionada.
* Se alguma célula estiver selecionada, mostra o resumo dessa célula.
* Se mais de uma célula estiver selecionada, mostra a primeira célula selecionada.
* Se a coluna estiver selecionada, escolhe o primeiro valor de célula na coluna.

Clique na engrenagem **Configurações de visualização** no canto superior direito para definir as configurações de Número do resumo:

| Configuração | Definição |
|--- |--- |
| [!UICONTROL Porcentagens] | Exiba porcentagens em vez de números brutos. |
| [!UICONTROL Legenda visível] | Exiba informações sobre a métrica mostrada. |
| [!UICONTROL Abreviar valor] | Escolha abreviar valores e mostrar até 3 casas decimais. |
| [!UICONTROL Resumir valor por] | Opte por exibir o máximo, mínimo, médio, mediano ou soma para uma seleção de dados. |

## [!UICONTROL Visualização da alteração do resumo] {#summary-change}

Use o [!UICONTROL Alteração de resumo] visualização para mostrar o delta (alteração) entre dois números. A cor verde e vermelha da [!UICONTROL Alteração de resumo] pode ser controlado por [polaridade de eventos personalizados](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html?lang=pt-BR) ou de uma métrica calculada [Mostrar tendência para cima como](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=pt-BR) opção.

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
| [!UICONTROL Porcentagens] | Exiba porcentagens em vez de números brutos. |
| [!UICONTROL Legenda visível] | Exiba informações sobre a métrica mostrada. |
| [!UICONTROL Mostrar variação percentual] | Mostra a variação percentual entre os 2 números. |
| [!UICONTROL Mostrar diferença bruta] | Mostra a diferença bruta entre 2 números. Também é possível abreviar valores e mostrar até 3 casas decimais com essa opção. |
