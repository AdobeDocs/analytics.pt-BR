---
title: O que é o hub Report Builder no Adobe Analytics
description: Descreve os componentes do Hub do Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 61%

---

# O Hub do Report Builder

Use o hub do Report Builder para criar, atualizar, excluir e gerenciar blocos de dados.

O hub Report Builder contém os botões Criar e Gerenciar, a lista COMANDOS e os painéis EDIÇÃO RÁPIDA.

<img src="./assets/hub51.png" alt="O Hub do Report Builder"/>


## Botões Criar, Gerenciar e Agendar

Use os botões Criar, Gerenciar e Programar para criar novos blocos de dados, gerenciar blocos de dados existentes ou programar blocos de dados.

## Painel COMANDOS

Use o painel COMANDOS para acessar comandos compatíveis com as células selecionadas ou uma ação anterior.

### Comandos

| Comandos exibidos | Disponível quando... | Propósito |
|------|------------------|--------|
| Criar bloco de dados | Uma ou mais células são selecionadas na pasta de trabalho. | Usado para criar um bloco de dados |
| Editar bloco de dados | O intervalo de célula ou células selecionado faz parte de apenas um bloco de dados. | Usado para editar um bloco de dados |
| Atualizar bloco de dados | A seleção contém pelo menos um bloco de dados. O comando atualizará somente os blocos de dados na seleção. | Usado para atualizar um ou mais blocos de dados |
| Atualizar todos os blocos de dados | A pasta de trabalho contém um ou mais blocos de dados. | Usado para atualizar TODOS os blocos de dados na pasta de trabalho |
| Enviar pasta de trabalho |   | Envie uma pasta de trabalho de acordo com um agendamento. |
| Copiar bloco de dados | A célula ou o intervalo de células selecionado faz parte de um ou mais blocos de dados. | Usado para copiar um bloco de dados |
| Excluir bloco de dados | O intervalo de célula ou células selecionado faz parte de apenas um bloco de dados. | Usado para excluir um bloco de dados |

## Painel EDIÇÃO RÁPIDA

Ao selecionar um ou mais blocos de dados em uma planilha, o Report Builder exibe o painel EDIÇÃO RÁPIDA. Você pode usar o painel EDIÇÃO RÁPIDA para alterar parâmetros em um único bloco de dados ou alterar parâmetros em vários blocos de dados ao mesmo tempo.

![O painel Edição Rápida no Report Builder](./assets/hub2.png)

As alterações feitas usando as seções Edição rápida se aplicam a todos os blocos de dados selecionados.

### Conjuntos de relatórios

Os blocos de dados extraem dados de um conjunto de relatórios selecionado. Se vários blocos de dados forem selecionados em uma planilha, e caso eles não extraiam dados do mesmo conjunto de relatórios, o link **Conjuntos de relatórios** exibe *Vários*.

Quando você altera o conjunto de relatórios, todos os blocos de dados na seleção adotam o novo conjunto de relatórios. Os componentes no bloco de dados são correspondidos ao novo conjunto de relatórios com base na ID (por exemplo, correspondendo ```evars```). Se um componente não for encontrado em um bloco de dados, uma mensagem de aviso será exibida e o componente será removido do bloco de dados.

Para alterar o conjunto de relatórios, selecione um novo conjunto de relatórios no menu suspenso.

![O Hub Report Builder mostrando o menu suspenso do conjunto de relatórios.](./assets/image16.png)

### Intervalo de datas

**[!UICONTROL Intervalo de datas]** mostra o intervalo de datas dos blocos de dados selecionados. Se vários blocos de dados forem selecionados com vários intervalos de datas, o link **[!UICONTROL Intervalo de datas]** exibirá *Vários*.

### Filtros

O link dos **Filtros** exibe uma lista de resumo dos filtros usados pelos blocos de dados selecionados. Se vários blocos de dados forem selecionados com vários filtros aplicados, o link **Filtros** exibirá *Vários*.
