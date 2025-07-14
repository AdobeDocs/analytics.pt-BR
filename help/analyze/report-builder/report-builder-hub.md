---
title: O que é o hub do Report Builder no Adobe Analytics
description: Descreve os componentes do Hub do Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: e18381ea-b7d4-4d7a-9ded-23b2d06fa204
source-git-commit: d3d74042f6c282db490483393f4b58cddd6b1525
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 54%

---

# O Hub do Report Builder

Use o hub do Report Builder para criar, atualizar, excluir e gerenciar blocos de dados.

O hub do Report Builder contém os botões Criar, Gerenciar e Agendar, o painel COMANDOS e o painel EDIÇÃO RÁPIDA.

<img src="./assets/hub51.png" alt="O Hub do Report Builder"/>


## Botões Criar, Gerenciar e Agendar

Use os botões Criar, Gerenciar e Programar para criar novos blocos de dados, gerenciar blocos de dados existentes ou programar blocos de dados.

## Painel COMANDOS

Use o painel COMANDOS para acessar comandos compatíveis com as células selecionadas ou uma ação anterior.

### Comandos

| Comandos exibidos | Disponível quando... | Propósito |
|------|------------------|--------|
| Editar bloco de dados | O intervalo de célula ou células selecionado faz parte de apenas um bloco de dados. | Usado para editar um bloco de dados |
| Atualizar bloco de dados | A seleção contém pelo menos um bloco de dados. O comando atualiza somente os blocos de dados na seleção. | Usado para atualizar um ou mais blocos de dados |
| Atualizar todos os blocos de dados | A pasta de trabalho contém um ou mais blocos de dados. | Usado para atualizar TODOS os blocos de dados na pasta de trabalho |
| Enviar pasta de trabalho |   | Envie uma pasta de trabalho de acordo com um agendamento. |
| Copiar bloco de dados | A célula ou o intervalo de células selecionado faz parte de um ou mais blocos de dados. | Usado para copiar um bloco de dados |
| Cortar bloco de dados |   | Usado para recortar um bloco de dados |
| Excluir bloco de dados | O intervalo de célula ou células selecionado faz parte de apenas um bloco de dados. | Usado para excluir um bloco de dados |

## Painel EDIÇÃO RÁPIDA

Ao selecionar um ou mais blocos de dados em uma planilha, o Report Builder exibe o painel EDIÇÃO RÁPIDA. Você pode usar o painel EDIÇÃO RÁPIDA para alterar parâmetros em um único bloco de dados ou alterar parâmetros em vários blocos de dados ao mesmo tempo.

![Painel Edição Rápida no Report Builder](./assets/hub2.png)

As alterações feitas usando as seções Edição rápida se aplicam a todos os blocos de dados selecionados.

### Conjuntos de relatórios

Os blocos de dados extraem dados de um conjunto de relatórios selecionado. Se vários blocos de dados forem selecionados em uma planilha, e caso eles não extraiam dados do mesmo conjunto de relatórios, o link **Conjuntos de relatórios** exibe *Vários*.

Quando você altera o conjunto de relatórios, todos os blocos de dados na seleção adotam o novo conjunto de relatórios. Os componentes no bloco de dados são correspondidos ao novo conjunto de relatórios com base na ID (por exemplo, correspondendo ```evars```). Se um componente não for encontrado em um bloco de dados, uma mensagem de aviso será exibida e o componente será removido do bloco de dados.

Para alterar o conjunto de relatórios, selecione um novo conjunto de relatórios no menu suspenso.

![O Hub do Report Builder mostrando o menu suspenso do conjunto de relatórios.](./assets/image16.png)

### Intervalo de datas

**[!UICONTROL Intervalo de datas]** mostra o intervalo de datas dos blocos de dados selecionados. Se vários blocos de dados forem selecionados com vários intervalos de datas, o link **[!UICONTROL Intervalo de datas]** exibirá *Vários*. [Saiba mais](/help/analyze/report-builder/select-date-range.md)

### Segmentos

O link **Segmentos** exibe uma lista de resumo dos segmentos usados pelos blocos de dados selecionados. Se vários blocos de dados forem selecionados com vários segmentos aplicados, o link **Segmentos** exibirá *Vários*. [Saiba mais](/help/analyze/report-builder/work-with-segments.md)
