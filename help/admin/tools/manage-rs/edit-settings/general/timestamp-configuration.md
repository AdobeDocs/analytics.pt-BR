---
description: Combine dados com e sem carimbos de data e hora em um único conjunto de relatórios.
title: Configuração de carimbos de data e hora
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 5%

---

# Configuração de carimbos de data e hora

A página de administração &#39;[!UICONTROL Configuração de carimbos de data e hora]&#39; permite habilitar os **[!UICONTROL carimbos opcionais de data e hora]** para um ou mais conjuntos de relatórios. Essa configuração permite combinar dados com e sem carimbos de data e hora em um único conjunto de relatórios.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Carimbos opcionais de data e hora]**

## Configuração de carimbo de data e hora atual

Esta seção mostra a configuração de carimbo de data e hora atual do conjunto de relatórios selecionado. Pode ser um destes três valores possíveis:

* **Carimbos de data/hora não permitidos (configuração `visitorID` com suporte)**
* **Carimbos de data/hora necessários (configuração `visitorID` sem suporte)**
* **Carimbos opcionais de data e hora (configuração `visitorID` compatível, mas não em ocorrências com carimbos de data e hora)**

Abaixo deste texto há uma caixa de seleção denominada **[!UICONTROL Converter conjuntos de relatórios selecionados em Carimbos opcionais de data e hora]**. Selecionar esta caixa de seleção e depois selecionar **[!UICONTROL Salvar]** Habilita [!UICONTROL Carimbos opcionais de data e hora] para os conjuntos de relatórios selecionados.

## Carimbos de data e hora não permitidos

Quando você envia dados para um conjunto de relatórios usando essa configuração de carimbo de data e hora, o carimbo de data e hora é exibido quando os servidores de processamento da Adobe recebem a ocorrência. Se você tentar definir a variável [`timestamp`](/help/implement/vars/page-vars/timestamp.md), a ocorrência será descartada permanentemente.

## Carimbos de data e hora obrigatórios

Ao enviar dados para um conjunto de relatórios usando essa configuração de carimbo de data e hora, cada ocorrência deve incluir a variável [`timestamp`](/help/implement/vars/page-vars/timestamp.md). Se alguma ocorrência não tiver uma variável de implementação `timestamp`, a ocorrência será permanentemente removida.

Os dados de uma sessão com carimbo de data e hora são mantidos por até 92 dias. Em outras palavras, uma visita é &quot;mantida aberta&quot; por 92 dias, permitindo que qualquer ocorrência adicional seja incluída na mesma visita/sessão. Embora seja possível adicionar dados a sessões existentes, a Adobe recomenda adicionar ocorrências em ordem por visitante. As ocorrências recebidas fora de ordem por visitante podem produzir resultados de relatório inesperados, embora muitas dessas limitações sejam atenuadas com o processamento do tempo do relatório.

## Carimbos opcionais de data e hora

A configuração &#39;[!UICONTROL Carimbos opcionais de data e hora]&#39; permite que você integre e relate em vários conjuntos de relatórios com ou sem a variável [`timestamp`](/help/implement/vars/page-vars/timestamp.md). Casos de uso ideais para [!UICONTROL Carimbos opcionais de data e hora] incluem:

* Combinar dados com e sem carimbos de data e hora no mesmo conjunto de relatórios global
* Enviar dados com carimbo de data e hora de um aplicativo móvel para um conjunto de relatórios global
* Atualizar aplicativos para usar o rastreamento offline sem precisar criar um novo conjunto de relatórios

Essa configuração fica habilitada por padrão para todos os novos conjuntos de relatórios, a menos que o novo conjunto de relatórios tenha sido copiado de um conjunto de relatórios com uma configuração de carimbo de data e hora diferente.

>[!WARNING]
>
>Se você usa [!UICONTROL Carimbos opcionais de data e hora], não defina [`visitorID`](/help/implement/vars/config-vars/visitorid.md) nos dados com carimbos de data e hora. Essa ação pode causar dados desorganizados e um impacto negativo aos cálculos de tempo (como tempo gasto), atribuição, número de visitas/contagens de visitas e relatórios de definição de caminho.

Depois de habilitar [!UICONTROL Carimbos opcionais de data e hora], você não poderá desabilitá-los nesta interface. Na situação improvável em que você deseja voltar para outra configuração de carimbo de data e hora, entre em contato com o Atendimento ao cliente da Adobe.
