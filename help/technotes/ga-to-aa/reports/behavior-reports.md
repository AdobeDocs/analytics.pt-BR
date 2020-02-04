---
title: Relatórios de comportamento no Adobe Analytics
description: Saiba como criar relatórios de comportamento no Adobe Analytics
translation-type: tm+mt
source-git-commit: e1cbdf87140b915dccbb8f64694797bb903d8ab8

---


# Relatórios de comportamento

Relatórios de comportamento mostram informações sobre como os usuários interagem com seu site.

Esta página supõe que o usuário tenha um conhecimento básico sobre o uso da Analysis Workspace. Consulte [Criar um relatório básico na Analysis Workspace para usuários](create-report.md) do Google Analytics se você ainda não estiver familiarizado com a ferramenta no Adobe Analytics.

## Fluxo de comportamento

O relatório de fluxo de comportamento pode ser recriado usando a visualização Fluxo.

1. Clique no ícone de visualizações à esquerda e arraste uma visualização de Fluxo para o espaço de trabalho acima da tabela de forma livre
2. Localize a dimensão **Página** e clique no ícone Seta para revelar os valores da página. Os valores de dimensão têm cor amarela.
3. Localize o valor da página desejada para começar e arraste-o para o espaço chamado &#39;Dimensão ou item&#39; no centro
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

![Relatório de fluxo](/help/technotes/ga-to-aa/assets/flow.png)

## Conteúdo do site - Todas as páginas

O relatório de páginas mostra o desempenho de páginas individuais em seu site.

1. No menu Componentes, localize a dimensão **Páginas** e arraste-a até a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Como alternativa, a Adobe fornece vários espaços de trabalho pré-criados chamados de modelos. O modelo Consumo de conteúdo (Web) fornece um valor semelhante ao relatório de todas as páginas.

1. Clique em *[!UICONTROL Projeto]>[!UICONTROL Novo]*, que abre uma janela modal com opções de projeto.
2. Clique no modelo Consumo de conteúdo (Web) e clique em Criar.

## Conteúdo do site - Detalhamento do conteúdo

O relatório de detalhamento de conteúdo permite observar o tráfego da página por estrutura de URL. A implementação adicional é necessária para uso na Analysis Workspace. A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados sejam coletados com precisão.

## Conteúdo do site - Páginas iniciais

O relatório de páginas iniciais mostra as principais páginas iniciais do site. As páginas iniciais estão disponíveis na Analysis Workspace como a dimensão Página **de** entrada.

1. No menu Componentes, localize a dimensão Página **de** entrada e arraste-a para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

A Adobe recomenda usar a métrica **Visitas** para essa dimensão.

## Conteúdo do site - Páginas de saída

O relatório de páginas de saída mostra as principais páginas que se tornaram a última página da visita de um indivíduo. Ele está disponível na Analysis Workspace com o mesmo nome.

1. No menu Componentes, localize a dimensão Página **de** saída e arraste-a para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

A Adobe recomenda usar a métrica **Visitas** para essa dimensão.

## Relatórios de velocidade do site

Os relatórios de velocidade do site mostram quão rapidamente as páginas são carregadas, revelando oportunidades para aumentar o tempo de carregamento de sua página.

Esse recurso exige implementação adicional em ambas as plataformas. A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados estejam configurados corretamente para a Analysis Workspace. O plug-in [](/help/implement/vars/plugins/getpageloadtime.md) getPageLoadTime geralmente é atribuído a uma eVar para obter dados de desempenho no Adobe Analytics.

## Relatórios de pesquisa do site

Os relatórios de pesquisa do site fornecem informações sobre como os visitantes usam os recursos de pesquisa interna do site.

Esse recurso exige implementação adicional em ambas as plataformas. A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados estejam configurados corretamente para a Analysis Workspace. Normalmente, um termo de pesquisa interno é extraído de um parâmetro de string de consulta e colocado em uma eVar para relatório.

## Relatórios de eventos

Os eventos têm algumas diferenças estruturais importantes entre o Google e o Adobe Analytics. Ambos exigem mudanças adicionais na implementação para funcionarem corretamente em suas respectivas plataformas.

* No Google Analytics, os eventos são definidos em sua implementação como texto. Os eventos têm categorias, ações e rótulos.
* No Adobe Analytics, os eventos são configurados pela primeira vez no Admin Console, onde um identificador é atribuído. Esse identificador é usado no código de implementação. Por exemplo:
   1. Você pode definir event1 no Admin Console como &quot;Registros&quot;.
   2. Em sua implementação, você incluiria event1 na variável events na página de confirmação de registro. Toda vez que a página de confirmação de registro é exibida, event1 aumenta.
   3. Na Analysis Workspace, &quot;Registros&quot; é exibido como uma métrica para uso em qualquer relatório.

Como esse recurso requer alterações de implementação, a Adobe recomenda trabalhar com um consultor de implementação para garantir que os dados estejam configurados corretamente para a Analysis Workspace.

## Relatórios do editor

Semelhante ao modo como o Google exige uma conexão com o Google Ad Manager, a Adobe oferece um produto dedicado para fornecer insight chamado Adobe Advertising Cloud. Se sua organização estiver interessada em usar este produto, entre em contato com o Gerente de conta de sua organização.
