---
title: Configuração da Análise entre dispositivos
description: Learn how to set up Cross-Device Analytics after you meet the prerequisites.
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# Configuração da Análise entre dispositivos

> [!NOTE] Cross-Device Analytics documentation is subject to change as the feature is further developed. Check back regularly for updates.

Once all prerequisites are met, use the following steps to enable Cross-Device Analytics. Você deve pertencer a um grupo Administrador do perfil do produto ou ter privilégios de administrador no Adobe Analytics para seguir essas etapas.

> [!IMPORTANT] Todos os pré-requisitos devem ser atendidos antes de seguir essas etapas. Se todos os pré-requisitos não forem atendidos, o recurso não estará disponível ou não funcionará. Consulte Análises [](cda-home.md) entre dispositivos para obter os pré-requisitos e as limitações.

## Escolha o conjunto de relatórios entre dispositivos que será ativado para CDA

Quando sua organização está provisionada para usar o CDA, você escolhe qual conjunto de relatórios usar. Essa opção pode ser comunicada por meio do seu Gerente de contas da Adobe. A Adobe então ativa seu conjunto de relatórios escolhido para processamento CDA.

## Criar um conjunto de relatórios virtuais entre dispositivos para ver a exibição entre dispositivos

Os administradores com acesso para criar conjuntos de relatórios virtuais podem criar conjuntos de relatórios virtuais CDA da seguinte maneira:

1. Navegue até [experience.adobe.com](https://experiencecloud.adobe.com) e faça logon usando suas credenciais da AdobeID.
2. Click the 9-grid icon at the top, then click Analytics.
3. Hover over Components at the top, then click Virtual Report Suites.
4. Clique em Adicionar.
5. Enter a name for your virtual report suite, and ensure that the CDA-enabled report suite is selected.
6. Click the checkbox 'Enable Report Time Processing', which enables several more options including Cross-Device Analytics.
7. Click the checkbox 'Stitch User Visits Across Devices'.
8. Click Continue, finish configuring the virtual report suite, then click Save.

![CDA checkbox](assets/cda-checkbox.png)

## Adições e alterações em conjuntos de relatórios virtuais entre dispositivos

Quando a Análise entre dispositivos estiver ativada em um conjunto de relatórios virtual, observe as seguintes alterações:

* A new cross-device icon appears next to the virtual report suite name. This icon is exclusive to cross-device virtual report suites.
* Novas métricas chamadas "Pessoas" e "Dispositivos exclusivos" estão disponíveis.
* A métrica "Visitantes únicos" não está disponível, pois é substituída por Pessoas e Dispositivos únicos.
* Ao criar segmentos, o contêiner de segmento "Visitante" é substituído por um contêiner "Pessoa".

## A métrica calculada Compactação

A capacidade do Cross-Device Analytics de unir dispositivos depende de uma grande variedade de fatores. A eficácia da capacidade do recurso de unir dados pode ser medida com uma métrica calculada chamada compactação. Os fatores que contribuem para a compressão incluem:

* Usando o gráfico de cooperativa ou privado: Geralmente, as organizações que usam a cooperativa de dispositivos tendem a ver taxas de compactação melhores do que as organizações que usam o gráfico privado.
* Taxa de logon: Quanto mais usuários fizerem logon em seu site, mais a Adobe poderá identificar e unir visitantes em dispositivos. Os sites com baixa taxa de logon também têm taxas de compactação baixas.
* Cobertura da Experience Cloud ID: Somente os visitantes com uma ECID podem ser agrupados. Uma porcentagem menor de visitantes do site usando um ECID correlaciona-se a taxas de compactação mais baixas.
* Uso de vários dispositivos: Se os visitantes do seu site não usarem vários dispositivos, você poderá ver taxas de compactação mais baixas.
* Granularidade do relatório: A compactação por dia geralmente é menor do que a compactação por mês ou ano. As chances de um indivíduo usar vários dispositivos se tornam menores em um único dia do que em mais de um mês inteiro. A segmentação, filtragem ou uso de dimensões de detalhamento também pode mostrar uma taxa de compactação menor.

Para ver a compactação de sua organização para um determinado período:

1. Click Workspace at the top, then click 'Create New Project'.
2. Start with a Blank Project, then click Create.
3. Drag the Unique Devices metric onto the canvas area labeled 'Drop a Metric Here'.
4. Arraste a métrica de Pessoas para a tela diretamente à direita do cabeçalho da métrica de Dispositivos únicos, para que as duas métricas fiquem lado a lado.
5. Click the '' symbol next to available metrics on the left to open the Calculated Metric builder.`+`
6. Give this calculated metric the following settings:
   * Nome: Cross-Device Compression
   * Formato: Porcentagem
   * Decimal Places: 2
   * Definição: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] Clique em "Adicionar" no canto superior direito da área de definição para adicionar um número estático. Arraste Pessoas e Dispositivos únicos da lista de métricas disponíveis à esquerda.
7. Clique em Salvar.
8. Arraste a nova métrica calculada para a tela diretamente à direita do cabeçalho da métrica de Pessoas, de modo que todas as três métricas fiquem lado a lado.
9. Opcional: O espaço de trabalho carrega a dimensão Dia por padrão. Arraste uma dimensão de data alternativa, como semana ou mês, sobre a dimensão Dia se desejar uma granularidade de tempo diferente.
