---
title: Personalização de relatórios no Adobe Analytics
description: Saiba como personalizar relatórios no Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
TQID: https://experienceleague.adobe.com/vvVKR7JKV12zgIic0rso4OihH5kyAoZBV983R3VmOic
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e3e906cf-5493-4e0a-9a33-bf0ac37393d6
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 609
ht-degree: 94%

---

# Personalizar relatórios

Em plataformas de terceiros, como o Google Analytics, várias opções de personalização estão disponíveis. Essas personalizações permitem que um usuário crie painéis, relatórios personalizados, relatórios salvos e alertas personalizados. Como a Analysis Workspace permite que os usuários criem relatórios a partir de uma tela em branco, a maioria das personalizações é incorporada diretamente à ferramenta.

Esta página supõe que o usuário tenha um conhecimento básico sobre a utilização do [!UICONTROL Analysis Workspace]. Consulte [Criar um relatório básico no Analysis Workspace para usuários do Google Analytics](reports/create-report.md) se ainda não estiver familiarizado com a ferramenta no Adobe Analytics.

## Painéis

A arquitetura do [!UICONTROL Analysis Workspace] é criada de forma semelhante ao conceito de widgets de painel. Os projetos no [!UICONTROL Analysis Workspace] são o equivalente aproximado aos painéis no Google Analytics. As visualizações no [!UICONTROL Analysis Workspace] são o equivalente aproximado dos widgets do Google Analytics.

### Adicionar conteúdo a um projeto

1. Clique no ícone [!UICONTROL Visualizações] à esquerda e arraste a visualização desejada para o espaço de trabalho.
2. Clique no ícone [!UICONTROL Componentes] à esquerda e arraste as dimensões e métricas desejadas para a visualização para preenchê-las com dados
3. Arraste as bordas da exibição para redimensioná-la e arraste o título da exibição para movê-la.

Todos os widgets do Google Analytics estão disponíveis no [!UICONTROL Analysis Workspace]:

* O **widget Métrica** é aproximadamente igual à exibição [!UICONTROL Número do resumo].
* O **widget Linha do tempo** é aproximadamente igual à exibição [!UICONTROL Linha].
* O **widget Geomap** é aproximadamente igual à exibição [!UICONTROL Mapa].
* O **widget Tabela** é aproximadamente igual à exibição [!UICONTROL Tabela de forma livre].
* O **widget Pizza** é aproximadamente igual à exibição [!UICONTROL Rosca].
* O **widget Barra** é aproximadamente igual à exibição [!UICONTROL Barra].

A [!UICONTROL Analysis Workspace] inclui muito mais opções de exibição para apresentar os dados de uma forma mais adequada às necessidades de relatórios. Consulte [Exibições no Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) no guia do usuário Análise para obter mais informações.

### Compartilhamento de projetos

Quando terminar de adicionar conteúdo a um projeto, você poderá compartilhá-lo.

* Para compartilhar o projeto com seus colegas, acesse **[!UICONTROL Compartilhar > Compartilhar projeto]**. Os destinatários são outros usuários da organização que têm contas do Adobe Analytics.
* Para compartilhar o projeto por meio de um link, acesse **[!UICONTROL Compartilhar > Obter link do projeto]**. Observe que isso ainda requer um logon no Adobe Analytics na organização.

### Exportar projetos

Além do PDF, o [!UICONTROL Analysis Workspace] oferece uma exportação de CSV.

1. Clique em *[!UICONTROL Compartilhar]* > *[!UICONTROL Enviar arquivo agora]*, que abre uma janela modal.
2. Especifique o tipo de arquivo e destinatários.
3. Clique em [!UICONTROL Enviar agora].

## Relatórios personalizados

Ao criar um relatório personalizado no Google Analytics, os campos necessários são semelhantes ao fluxo de trabalho na criação de uma exibição no espaço de trabalho. As definições Dimensões, Métricas e Filtro são semelhantes entre plataformas. Na Analysis Workspace, em vez de selecionar dimensões e métricas de uma lista, dimensões e métricas são arrastadas para uma tabela de forma livre.

### Métricas calculadas em relatórios personalizados

Relatórios personalizados são uma das poucas áreas no Google Analytics que permitem o uso de métricas calculadas. Como a Analysis Workspace funciona como uma tela, as métricas calculadas funcionam retroativamente e em qualquer contexto.

Para criar uma métrica calculada:

1. Clique no ícone **+** próximo à lista de métricas para abrir o [!UICONTROL Construtor de métricas calculadas].
2. Dê um nome à métrica calculada e especifique um formato.
3. Arraste os componentes da métrica até a área de definição e use as listas suspensas entre cada componente para designar um operador.
4. Depois que a métrica calculada contiver a fórmula desejada, clique em Salvar para voltar ao espaço de trabalho.
5. Arraste a métrica calculada recém-definida para o espaço de trabalho.

   Saiba mais sobre [Métricas calculadas](/help/components/calculated-metrics/cm-overview.md) no guia do usuário Componentes.

## Alertas personalizados

Os alertas estão disponíveis em ambas as plataformas. No Adobe Analytics, use o menu de navegação do cabeçalho e acesse *[!UICONTROL Componentes]* > *[!UICONTROL Alertas]*. Consulte [Visão geral dos alertas](/help/components/alerts/alerts-overview.md) no Guia do usuário de componentes para obter mais informações.
