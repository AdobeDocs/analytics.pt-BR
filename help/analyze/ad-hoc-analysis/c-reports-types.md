---
description: Descrições dos tipos de relatórios usados na Experience Cloud.
title: Tipos de relatórios
topic: Ad hoc analysis
uuid: 357102eb-a172-40ec-a302-01c87abaacb5
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tipos de relatórios

Descrições dos tipos de relatórios usados na Experience Cloud.

## Relatório classificados {#concept_E1710FFFBB334F3D9DB63A1626DBCB01}

Exibe uma tabela com itens classificados, usando números e percentuais em métricas. Por exemplo, um [!UICONTROL relatório de páginas] classifica as páginas do site com base no tráfego e a tabela de detalhes mostra os percentuais e os números de métricas como Exibições de página e Receita. O tipo padrão de gráfico é o de barras horizontais. O gráfico exibe uma cor para cada métrica. Os relatórios classificados podem exibir diversas métricas em um mesmo relatório.

<!-- 

c_reports_ranked.xml

 -->

Os gráficos classificados têm, por padrão, cinco itens, mas você pode incluir até trinta nas opções do gráfico.

## Relatórios de tendência {#concept_65FEA92704024232BB21A5952939711F}

Permite examinar como as conversões e os eventos estabelecem tendências ao longo de uma granularidade de tempo selecionada (hora, dia, semana, mês, trimestre ou ano) durante um período de geração de relatório.

<!-- 

c_reports_trended.xml

 -->

No gráfico, o eixo vertical exibe os itens rastreados. O eixo horizontal exibe a granularidade de tempo. Na tabela, é possível estabelecer uma tendência para uma célula específica e gerar um relatório completo para essa célula. A data ou o tempo usado é baseado no valor da célula.

Também é possível selecionar diversas células e gerar um relatório de tendências com base em uma granularidade selecionada. Quando você estabelece tendências em diversas células, as colunas do relatório exibem os dados de todo o período do relatório.

Um [!UICONTROL relatório de produtos] é um exemplo de relatório de tendências. Você pode ver a receita foi gerada por um produto durante o intervalo selecionado. Se o seu período de geração de relatório for uma semana, você poderá ver a receita gerada em cada dia desse período, mostrar um gráfico de tendências para um produto específico em um determinado dia ou abrir um relatório de tendências separado para a seleção.

## Tendência de células {#task_AD9275BED5CE4D61AC25778D144406A4}

Etapas que descrevem como gerar um relatório de tendências em uma ou mais células de uma tabela.

<!-- 

t_trend_row.xml

 -->

**Tendência de células**

1. Abra um relatório classificado.
1. Na tabela, localize a célula e clique em **[!UICONTROL Tendência]**. 

   ![](assets/TrendInspector_Buttcon.png)

1. Para visualizar um relatório completo da célula, clique em **[!UICONTROL Iniciar relatório de tendência]**.

   Ou clique com o botão da direita na célula e depois clique em **[!UICONTROL Célula de tendência]**. Você também pode executar esta tarefa selecionando várias células.

## Relatório de totais {#concept_48E23FB3BCCD43DFB486A048960800A8}

<!-- 

c_reports_totals.xml

 -->

Um relatório de nível executivo que mostra dados de resultado. Ele contém dados de totais de receita, exibições de página e pedidos. É possível segmentar o relatório e adicionar outras métricas para visualizar dados adicionais.

## Relatórios de fluxo {#concept_3E417D018F1B4566973F694B01E6439F}

Os relatórios de fluxo mostram os caminhos mais comuns usados por usuários nas páginas, nas seções do site e nos servidores.

<!-- 

c_reports_flow.xml

 -->

**Próximo fluxo**

O gripo de relatórios [!UICONTROL Próximo fluxo] tem três relatórios: [!UICONTROL Fluxo de próxima página], [!UICONTROL Fluxo de próxima seção] e [!UICONTROL Fluxo de próximo servidor]. Os relatórios desse grupo mostram as páginas, as seções do site e os servidores mais comuns que o visitante acessou após visitar a página, a seção do site ou o servidor especificado por você. Esses relatórios mostram os caminhos mais comuns seguidos no site.

**Fluxo anterior**

Os relatórios de fluxo anteriores são semelhantes aos próximos relatórios de fluxo, exceto que, em vez de ver para onde os visitantes foram após uma página selecionada, é possível ver onde eles estavam antes de visitar uma página especificada. Os controles para usar o relatório são idênticos aos dos relatórios de próximo fluxo.

## Fluxo de próximas páginas {#concept_F7565234927942BEAF75D5D94A7AB47D}

Mostra exibições de caminho ou o número de vezes e o percentual em que uma página foi visualizada dentro das restrições dos caminhos. Por exemplo, a página Política de privacidade pode ter 10.000 exibições de página no total, mas apenas 500 delas ocorreram imediatamente antes da página inicial. Nesse caso, você veria 500 exibições de caminho. Você pode exibir o relatório no nível da visita ou do visitante. Os percentuais de cada página são exibidos ao lado do nome delas. A largura de uma linha conectada a uma página retrata o percentual relativo das visitas.

<!-- 

c_reports_next_page_flow.xml

 -->

Por padrão, esse relatório exibe as 10 principais páginas acessadas pelos usuários após a página que você selecionou. É possível clicar em uma página sublinhada para expandir ainda mais o gráfico. Não há um limite para o número de páginas que podem ser incluídas no gráfico. Entretanto, é possível passar o mouse sobre uma página para ver seus dados de visita e receita.

Use esse relatório para:

* Entender quais etapas são usadas mais frequentemente após visualizar uma página selecionada.
* Otimizar o design do caminho do site para canalizar o tráfego para uma página de destino desejada.
* Identificar o local para o qual os visitantes estão indo em vez de suas páginas de destino desejadas.

## Fluxo de próximo servidor {#concept_DB8C20E18AEA4051903C47A16C0E9C4E}

Exibe os dados de navegação entre os servidores no site. Ao selecionar um nome de servidor do site, o relatório mostra o número de visitantes que navegaram por esse servidor para cada um dos outros servidores do site em uma única visita ou em várias.

<!-- 

c_reports_next_server_flow.xml

 -->

Por exemplo, se você tem dados específicos sobre diferentes servidores ou dados espelhados em servidores separados, o relatório mostra o caminho entre os servidores que os usuários acessaram. Isso também ocorre com domínios dentro do site. Por exemplo, é possível ver quantos usuários passaram de `https://www.mysite.com` para `https://info.mysite.com`ou `https://sales.mysite.com`.

## Fluxo de próxima seção {#concept_7C9C8567E7DF477DA186E47DD3FD47A4}

O relatório [!UICONTROL Fluxo de próxima de seção] semelhante ao relatório de [!UICONTROL Fluxo de próxima página]. Ele exibe os dados das seções do site (grupos de páginas da Web relacionadas). Se uma página estiver contida em mais de uma seção do site, o relatório exibirá os dados de todas as seções do site.

<!-- 

c_reports_next_section_flow.xml

 -->

Por exemplo, uma loja online talvez tenha seções de site para seus produtos e outras seções para tags de produtos. Nesse caso, uma página da Web de produto pode se encaixar em diversas seções do site. Mesmo que uma página de produtos só tenha sido visualizada uma vez, o relatório de [!UICONTROL Fluxo de próxima seção] mostrará uma exibição de página para cada seção do site associada à página.

## Fluxo de página anterior {#concept_ADEAEBAE3F37401B977A27E03B5A523B}

Semelhante ao relatório de [!UICONTROL Fluxo de próxima página]. O relatório de [!UICONTROL Fluxo de página anterior] mostra diversos níveis das páginas mais populares que seus visitantes visualizaram antes da página selecionada. O relatório também destaca as páginas a partir das quais os visitantes acessam o site.

<!-- 

c_reports_previous_page_flow.xml

 -->

Use esse relatório para:

* Entender quais etapas são seguidas com mais frequência antes de visualizar uma página selecionada.
* Otimizar o design do caminho do site para canalizar o tráfego para uma página de destino desejada.

## Fluxo de seção anterior {#concept_30688D97B48449E1958866BAF376FA8C}

O relatório [!UICONTROL Fluxo de seção anterior] é semelhante o relatório [!UICONTROL Fluxo de página anterior]. Ele exibe os dados das seções do site (grupos de páginas da Web relacionadas). Se uma página estiver contida em mais de uma seção do site, o relatório exibirá os dados de todas as seções do site.

<!-- 

c_reports_previous_section_flow.xml

 -->

Por exemplo, uma loja online talvez tenha seções de site para seus produtos e outras seções para tags de produtos. Nesse caso, uma página da Web de produto pode se encaixar em diversas seções do site. Mesmo que uma página de produto só tenha sido visualizada uma vez, o relatório de [!UICONTROL Fluxo de seção anterior] mostra uma exibição de página para cada seção do site associada à página.

## Fluxo do servidor anterior {#concept_8E43208CAF2C4C358F19D4669B73822F}

Esse relatório mostra dados de navegação entre os servidores do site. Quando você seleciona um nome de servidor do site, o relatório mostra o número de visitantes que navegaram para esse servidor de cada um dos outros servidores do site em uma única visita ou em várias.

<!-- 

c_reports_previous_server_flow.xml

 -->

Por exemplo, se você tem dados específicos sobre diferentes servidores ou dados espelhados em servidores separados, o relatório mostra o caminho entre os servidores que os usuários acessaram. Isso também ocorre com domínios dentro do site. Por exemplo, é possível ver quantos usuários passaram de `www.mysite.com` para `info.mysite.com`ou `sales.mysite.com`.

## Relatórios de funil de conversão {#concept_35A2EB61E84441CBB670C2E02CA26F81}

Os relatórios de funil de conversão mostram os percentuais de conversão entre eventos de métricas específicas. Você pode usar esse relatório para entender o número de click-throughs que gera vendas e o número de unidades vendidas. Por exemplo, um relatório de [!UICONTROL Conversão de produtos] mostra o percentual de eventos de Carrinhos relacionado a eventos de Visitas e, em seguida, exibe os totais de Pedidos, Receitas e Unidades com base nesses eventos.

<!-- 

c_reports_conversion_funnel.xml

 -->

Os relatórios de funil a seguir estão disponíveis:

* [!UICONTROL Funil de conversão de compra]: mostra as visitas (específicas do relatório), os carrinhos, os pedidos, as unidades e a receita.
* [!UICONTROL Funil de conversão de carrinho]: exibe as visitas (específicas do relatório), os carrinhos, os check-outs, os pedidos e a receita.
* [!UICONTROL Funil de evento personalizado]: exibe os eventos personalizados no site. Por padrão, ele mostra de 1 a 5 eventos personalizados.
* [!UICONTROL Funil de conversão de campanha]: mostra os Click-throughs, Checkouts, Pedidos e a Receita.

A tabela mostra as estatísticas de vendas médias por click-through e a média de unidades vendidas por click-through. Você pode adicionar métricas e eventos personalizados de outros grupos de relatórios a estes relatórios. Esses funis têm muitas similaridades, mas são baseados em diferentes variáveis e eventos. Você pode usar esses relatórios para ver quais percentuais e tendências gerais de usuários ativam eventos especificados. Você pode ver onde os usuários não estão gerando eventos, o que oferece um insight sobre o ponto específico no processo de conversão.

## Relatório de análise do site {#concept_65694C6BDE424714B7975764F95497A4}

A [!UICONTROL análise do site] mostra como os visitantes se movem entre as páginas e os eventos especificados. Por exemplo, você pode ver o fluxo do tráfego entre as páginas, a afinidade entre os produtos e os canais de marketing e como as campanhas e os canais fluem para pedidos de produtos. Você pode arrastar páginas, itens de dimensão (e listas) e eventos de métrica. Cada cilindro representa um ou mais itens de dimensão (páginas) ou um evento. As setas representam o fluxo entre os valores dos cilindros. As métricas são atribuídas às posições dos cilindros (X e Y), à largura do cilindro, à altura do cilindro e à cor. A posição, o tamanho e a cor muda de acordo com os valores das métricas.

<!-- 

c_reports_site_analysis.xml

 -->

Arraste itens dos painéis de ferramentas para adicioná-los ao gráfico ou ao campo de dimensões.

Clique nos cilindros com o botão direito do mouse para editá-los ou removê-los.

<!-- Meike, UICONTROL and DNL stripped from tables. Re-add. -->

| Opção | Descrição |
|--- |--- |
| Exibir análise do site em (visita ou visitante) | Permite alternar entre Visita e Visitante para analisar a definição do caminho do visitante. Essas configurações ajudam você a entender a participação do visitante no nível do visitante e em várias visitas. Os relatórios de análise do site, de fluxo e de saída são ativados para a definição do caminho do visitante. Alterar essa configuração executa o relatório novamente, limitando os dados de acordo com a seleção. |
| Adicionar ponto de verificação | Exibe o Editor de ponto de verificação, no qual você pode selecionar dimensões ou eventos para adicioná-los à exibição. |
| Substituir gráfico | Substitui o gráfico de análise do site pelos pontos de verificação adicionados ao editor. |
| Ajustar à tela | Restaura a exibição original do gráfico. |
| Exibição aérea | Oferece uma exibição de cima do gráfico. |
| Alternar grade | Alterna entre a ativação e a desativação da grade. |
| Dimensão | O item sobre o qual você gera o relatório. Arraste o item de Dimensões. |

| Opção | Descrição |
|--- |--- |
| Editar  | Permite adicionar ou remover páginas de um cilindro. |
| Remover | Permite remover um cilindro. |
| Relatórios | Permite inicializar outro relatório pelo cilindro. |
| Salvar gráfico como | Permite salvar o gráfico como um arquivo .png ou .jpg. Se você alterar os controles do gráfico (ângulo, tamanho) antes de salvar, as alterações são preservadas na saída. |
| Copiar gráfico para a área de transferência | Copia o gráfico para colá-lo em outro aplicativo. Se você alterar os controles do gráfico (ângulo, tamanho) antes de salvar, as alterações são preservadas na saída. |
