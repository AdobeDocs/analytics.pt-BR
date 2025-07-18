---
description: Saiba mais sobre a extensão do Activity Map e como navegar em sua interface.
title: Interface de extensão do Activity Map
uuid: f6734b60-0b77-4f50-a45a-6a6936d1524e
feature: Activity Map
role: User, Admin
exl-id: 461abda1-3238-4a32-b9d3-5a57b00cf0d3
source-git-commit: 19c2c1abd7f1799598597c0e696d0b001c1ef0ea
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 1%

---

# Interface de extensão do Activity Map

A interface de extensão do Activity Map é composta de duas partes:

* Um painel superior que permite configurar a extensão e os relatórios
* Uma sobreposição que exibe os links mais populares
* Um painel inferior que mostra métricas para os links mais populares

## Painel superior

O painel superior contém os controles básicos para a sobreposição do Activity Map.

![Sobreposição](../assets/overlay.png)

Ele oferece as seguintes configurações:

* **Modo de exibição Padrão/Dinâmico**: alterna entre modo de exibição padrão e modo de exibição dinâmico.
   * Exibição padrão: mostra a sobreposição com base em dados históricos.
   * Visualização em tempo real: mostra a sobreposição com base nos dados em tempo real. O seletor de datas muda para um menu suspenso que permite alterar a granularidade dos dados em tempo real.
* **Seletor de métrica**: permite alterar a métrica relatada pela sobreposição. Apenas [!UICONTROL Cliques de link] estarão disponíveis se você tiver a exibição em tempo real selecionada.
* **Seletor de segmentos**: permite selecionar um [segmento](/help/components/segmentation/seg-overview.md), exibindo um subconjunto de dados dentro da sobreposição. Os segmentos não estão disponíveis na visualização em tempo real.
* **Tipo de visualização de sobreposição**: permite que você altere como a sobreposição visualiza a classificação dos links.
   * **[!UICONTROL Bolha]**: os links principais recebem uma bolha verde mostrando sua classificação numérica durante o período do relatório. Você pode alterar a cor da bolha em [Configurações](settings.md).
   * **[!UICONTROL Gradiente]**: os links principais aparecem sombreados em vermelho transparente. Os links mais populares são o vermelho mais escuro. Você pode alterar a cor do gradiente em [Configurações](settings.md).
   * **[!UICONTROL Desativado]**: Desabilitar sobreposições de links.
* **Seletor de datas**: permite alterar o período do relatório.

O cabeçalho desse painel contém as seguintes configurações:

* **Expandir/recolher o painel superior**: alterna o painel superior para mostrar as configurações na horizontal ou na vertical (ícone de seta dupla).
* **[!UICONTROL Alternar detalhes da página]**: mostrar ou ocultar o painel inferior (ícone de olho).
* **[!UICONTROL Mostrar configurações]**: abre um menu para configurações que você pode alterar (ícone de engrenagem):
   * **[!UICONTROL Configurações]**: abre as [Configurações](settings.md) da extensão.
   * **[!UICONTROL Ajuda]**: abre a documentação para o Experience League (esta página).
   * **[!UICONTROL Comunidade Adobe]**: abre a [comunidade Experience League](https://experienceleaguecommunities.adobe.com/?profile.language=pt).
   * **[!UICONTROL Sobre]**: exibe a versão da extensão.
   * **[!UICONTROL Logout]**: encerra sua sessão da extensão, exigindo que você entre novamente.
* **[!UICONTROL Sair do Activity Map]**: fecha todas as sobreposições da extensão (ícone X).

## Sobreposição de página

A sobreposição de página contém o conteúdo do site com uma sobreposição que mostra o local dos links mais populares clicados durante o período dos relatórios. Você pode configurar essas sobreposições de link para serem exibidas como bolhas ou gradientes no **[!UICONTROL Tipo de visualização de sobreposição]** do painel superior.

Se você clicar em uma bolha ou gradiente, poderá exibir os detalhes desse link específico.

![Bolha de link](../assets/link-bubble.png)

## Painel inferior

O painel inferior mostra uma exibição agregada dos links exibidos na sobreposição.

* **Tipo de relatório**: alterne o painel inferior para mostrar o relatório **[!UICONTROL Links na página]** ou o relatório **[!UICONTROL Detalhes da página]**.
* **[!UICONTROL Nome da página]**: o nome da dimensão [Página](/help/components/dimensions/page.md) atual.
* **[!UICONTROL Pesquisa]**: filtre o relatório para exibir somente nomes de links correspondentes ao texto inserido.
* **[!UICONTROL Baixar]**: exporta o relatório para CSV. Você pode incluir o relatório [!UICONTROL Links na página], o relatório [!UICONTROL Página] e o relatório [!UICONTROL Fluxo de página] no mesmo arquivo de download.
* **[!UICONTROL Alterar posição de encaixe do relatório]**: alterna a posição deste painel para aparecer na parte inferior ou superior da janela do navegador.
* **[!UICONTROL Fechar o relatório]**: fecha este painel. Você pode abrir o painel novamente usando o botão **[!UICONTROL Alternar detalhes da página]** no painel superior (o ícone de olho).

O relatório **[!UICONTROL Links na página]** mostra um relatório básico do espaço de trabalho com as seguintes configurações:

* A dimensão [Link do Activity Map](/help/components/dimensions/activity-map-link.md)
* A métrica [Ocorrências](/help/components/metrics/occurrences.md) (rotulada como **[!UICONTROL Cliques de link]**)
* O valor de [Página](/help/components/dimensions/page.md) atual aplicado como um segmento

![Links no painel da página](../assets/links-on-page.png)

O relatório **[!UICONTROL Detalhes da página]** mostra uma visualização de [Fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) usando a dimensão [Página](/help/components/dimensions/page.md), com foco na página atual. As seguintes métricas da página atual são exibidas à esquerda:

* Total de [exibições de página](/help/components/metrics/page-views.md)
* [!UICONTROL % de todas as exibições de página]
* Contagem de [Entradas](/help/components/metrics/entries.md)
* Contagem de [Saída](/help/components/metrics/exits.md)
* [Visitas em única página](/help/components/metrics/single-page-visits.md)
* [!UICONTROL Média de cliques para a página]
* Tempo médio [gasto na página](/help/components/metrics/time-spent.md)
* Número de [Recargas](/help/components/metrics/reloads.md)
* [Taxa de rejeição](/help/components/metrics/bounce-rate.md)
* [!UICONTROL Cliques em links]

![Detalhes da página](../assets/page-details.png)
