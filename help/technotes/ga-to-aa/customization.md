---
title: Personalização de relatórios no Adobe Analytics
description: Saiba como personalizar relatórios no Adobe Analytics
translation-type: ht
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Personalizar relatórios

Em plataformas de terceiros, como o Google Analytics, várias opções de personalização estão disponíveis. Essas personalizações permitem que um usuário crie painéis, relatórios personalizados, relatórios salvos e alertas personalizados. Como a Analysis Workspace permite que os usuários criem relatórios a partir de uma tela em branco, a maioria das personalizações é incorporada diretamente à ferramenta.

Esta página supõe que o usuário tenha um conhecimento básico sobre o uso do Analysis Workspace. Consulte [Criar um relatório básico no Analysis Workspace para usuários do Google Analytics](reports/create-report.md) se ainda não estiver familiarizado com a ferramenta no Adobe Analytics.

## Painéis

A arquitetura da Analysis Workspace é criada de forma semelhante ao conceito de widgets de painel. Os projetos na Analysis Workspace são o equivalente aproximado aos painéis no Google Analytics. As exibições na Analysis Workspace são o equivalente aproximado aos widgets do Google Analytics.

### Adicionar conteúdo a um projeto

1. Clique no ícone Exibições à esquerda e arraste a exibição desejada para o espaço de trabalho.
2. Clique no ícone Componentes à esquerda e arraste as dimensões e métricas desejadas para a exibição para preenchê-las com dados.
3. Arraste as bordas da exibição para redimensioná-la e arraste o título da exibição para movê-la.

Todos os widgets do Google Analytics estão disponíveis no Analysis Workspace:

* O **widget Métrica** é aproximadamente igual à exibição Número do resumo.
* O **widget Linha do tempo** é aproximadamente igual à exibição Linha.
* O **widget Geomap** é aproximadamente igual à exibição Mapa.
* O **widget Tabela** é aproximadamente igual à exibição Tabela de forma livre.
* O **widget Pizza** é aproximadamente igual à exibição Rosca.
* O **widget Barra** é aproximadamente igual à exibição Barra.

A Analysis Workspace inclui muito mais opções de exibição para apresentar os dados de uma forma mais adequada às necessidades de relatórios. Consulte [Exibições no Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) no guia do usuário Análise para obter mais informações.

### Compartilhamento de projetos

Quando terminar de adicionar conteúdo a um projeto, você poderá compartilhá-lo.

* Para compartilhar o projeto com seus colegas, vá até Compartilhar > Compartilhar projeto. Os destinatários são outros usuários da organização que têm contas do Adobe Analytics.
* Para compartilhar o projeto por meio de um link, acesse Compartilhar > Obter link do projeto. Observe que isso ainda requer um logon no Adobe Analytics na organização.

### Exportar projetos

Além do PDF, a Analysis Workspace oferece uma exportação CSV.

1. Clique em *[!UICONTROL Compartilhar]* > *[!UICONTROL Enviar arquivo agora]*, que abre uma janela modal.
2. Especifique o tipo de arquivo e destinatários.
3. Clique em [!UICONTROL Enviar agora].

## Relatórios personalizados

Ao criar um relatório personalizado no Google Analytics, os campos necessários são semelhantes ao fluxo de trabalho na criação de uma exibição no espaço de trabalho. As definições Dimensões, Métricas e Filtro são semelhantes entre plataformas. Na Analysis Workspace, em vez de selecionar dimensões e métricas de uma lista, dimensões e métricas são arrastadas para uma tabela de forma livre.

### Métricas calculadas em relatórios personalizados

Relatórios personalizados são uma das poucas áreas no Google Analytics que permitem o uso de métricas calculadas. Como a Analysis Workspace funciona como uma tela, as métricas calculadas funcionam retroativamente e em qualquer contexto.

Para criar uma métrica calculada:

1. Clique no ícone **+** próximo à lista de métricas para abrir o Construtor de métricas calculadas.
2. Dê um nome à métrica calculada e especifique um formato.
3. Arraste os componentes da métrica até a área de definição e use os detalhamentos entre cada componente para designar um operador.
4. Depois que a métrica calculada contiver a fórmula desejada, clique em Salvar para voltar ao espaço de trabalho.
5. Arraste a métrica calculada recém-definida para o espaço de trabalho.

   Saiba mais sobre [Métricas calculadas](/help/components/c-variables/c-metrics/calculated-metric.md) no guia do usuário Componentes.

## Alertas personalizados

Os alertas estão disponíveis em ambas as plataformas. No Adobe Analytics, use o menu de navegação do cabeçalho e acesse *[!UICONTROL Componentes]* > *[!UICONTROL Alertas]*. Consulte [Alertas inteligentes](/help/components/c-alerts/intellligent-alerts.md) no guia do usuário Componentes para obter mais informações.
