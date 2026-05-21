---
title: Relatórios de comportamento no Adobe Analytics
description: Saiba como criar relatórios de comportamento no Adobe Analytics
feature: Third-party Integration
exl-id: ea441afa-e595-4ffa-b446-d67e87f8a7c9
TQID: https://experienceleague.adobe.com/pNdyXgcpZ9TWU2WFnXTlkDeeFv3exefKSJRF6CbB2Nc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: dcae653e-62c6-4cc8-84e6-ee110b848296id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 805
ht-degree: 95%

---

# Relatórios de comportamento

Os Relatórios de comportamento mostram informações sobre como os usuários interagem com o site.

Esta página supõe que o usuário tenha um conhecimento básico sobre o uso do Analysis Workspace. Consulte [Criar um relatório básico no Analysis Workspace para usuários do Google Analytics](create-report.md) se ainda não estiver familiarizado com a ferramenta no Adobe Analytics.

## Fluxo de comportamento

O relatório de fluxo de comportamento pode ser recriado usando a exibição Fluxo.

1. Clique no ícone Exibições à esquerda e arraste uma exibição Fluxo até o espaço de trabalho acima da tabela de forma livre
2. Localize a dimensão **Página** e clique no ícone Seta para revelar os valores da página. Os itens de dimensão têm cor amarela.
3. Localize o valor da página desejada para começar e arraste-o para o espaço chamado &#39;Dimensão ou item&#39; no centro
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

![Relatório de fluxo](/help/technotes/ga-to-aa/assets/flow.png)

## Conteúdo do site - Todas as páginas

O relatório de páginas mostra o desempenho de páginas individuais no site.

1. No menu Componentes, localize a dimensão **Páginas** e arraste-a até a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o [Guia de tradução de métricas](common-metrics.md) para saber detalhes sobre como obter cada respectiva métrica.

Como alternativa, a Adobe fornece vários espaços de trabalho pré-criados chamados de modelos. O modelo Consumo de conteúdo (Web) fornece um valor semelhante ao relatório de todas as páginas.

1. Clique em *[!UICONTROL Projeto] > [!UICONTROL Novo]*, que abre uma janela modal com opções de projeto.
2. Clique no modelo Consumo de conteúdo (Web) e em Criar.

## Conteúdo do site - Detalhamento do conteúdo

O relatório de detalhamento de conteúdo permite observar o tráfego da página por estrutura de URL. É necessária uma implementação adicional para uso na Analysis Workspace. A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados sejam coletados com precisão.

## Conteúdo do site - Páginas de destino

O relatório de páginas de destino mostra as principais páginas de destino do site. As páginas de destino estão disponíveis na Analysis Workspace como a dimensão **Página de entrada**.

1. No menu Componentes, localize a dimensão **Página de entrada** e arraste-a até a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o [Guia de tradução de métricas](common-metrics.md) para saber detalhes sobre como obter cada respectiva métrica.

A Adobe recomenda usar a métrica **Visitas** para essa dimensão.

## Conteúdo do site - Páginas de saída

O relatório Páginas de saída mostra as páginas principais que se tornaram a última página da visita de uma pessoa. Ele está disponível na Analysis Workspace com o mesmo nome.

1. No menu Componentes, localize a dimensão **Página de saída** e arraste-a até a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o [Guia de tradução de métricas](common-metrics.md) para saber detalhes sobre como obter cada respectiva métrica.

A Adobe recomenda usar a métrica **Visitas** para essa dimensão.

## Relatórios de velocidade do site

Os relatórios Velocidade do site mostram quão rapidamente as páginas são carregadas, revelando oportunidades para aumentar o tempo de carregamento da página.

Esse recurso exige implementação adicional em ambas as plataformas. A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados estejam configurados corretamente na Analysis Workspace. O [plug-in getPageLoadTime](/help/implement/vars/plugins/getpageloadtime.md) geralmente é atribuído a uma eVar para obter dados de desempenho no Adobe Analytics.

## Relatórios de pesquisa do site

Os relatórios Pesquisa do site fornecem informações sobre como os visitantes usam os recursos de pesquisa interna do site.

Esse recurso exige implementação adicional em ambas as plataformas. A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados estejam configurados corretamente na Analysis Workspace. Normalmente, um termo de pesquisa interno é extraído de um parâmetro de cadeia de caracteres de consulta e colocado em uma eVar para relatório.

## Relatórios de eventos

Os eventos têm algumas diferenças estruturais importantes entre o Google e o Adobe Analytics. Ambos exigem mudanças adicionais na implementação para funcionarem corretamente nas respectivas plataformas.

* No Google Analytics, os eventos são definidos na implementação como texto. Os eventos têm categorias, ações e rótulos.
* No Adobe Analytics, os eventos são configurados pela primeira vez no Admin Console, onde um identificador é atribuído. Esse identificador é usado no código de implementação. Por exemplo:
   1. Você pode definir event1 no Admin Console como &quot;Registros&quot;.
   2. Na implementação, você incluiria event1 na variável events na página de confirmação de registro. Toda vez que a página de confirmação de registro é exibida, event1 aumenta.
   3. Na Analysis Workspace, &quot;Registros&quot; é exibido como uma métrica para uso em qualquer relatório.

Como esse recurso requer alterações de implementação, a Adobe recomenda trabalhar com um consultor de implementação para garantir que os dados estejam configurados corretamente na Analysis Workspace.

## Relatórios do editor

Semelhante ao modo como o Google requer uma conexão com o Google Ad Manager, o Adobe oferece um produto dedicado para fornecer o insight chamado Adobe Advertising. Se a organização estiver interessada em usar esse produto, entre em contato com a equipe de conta da Adobe.
