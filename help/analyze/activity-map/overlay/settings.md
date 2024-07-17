---
description: O painel Configuração do Activity Map permite modificar as configurações e propriedades para todos os tipos de visualizações de sobreposição.
title: Definir configurações do Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: ba10ceb73d953ff495613d02dd1ff825b6e518df
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 48%

---

# Definir configurações do Activity Map

O painel Configuração do Activity Map permite modificar as configurações e propriedades para todos os tipos de visualizações de sobreposição.

Acesse o painel Configurações do Activity Map, clicando no ícone de engrenagem na barra de ferramentas do Activity Map.

## Configurações gerais {#section_697A12F099494D699A4BF498598178C5}

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Empresas]** | Selecione a empresa de logon aplicável. |
| **[!UICONTROL Conjunto de relatórios]** | A lista de conjuntos de relatórios que você pode acessar não é mais limitada aos conjuntos de relatórios definidos na tag de página da web. Agora você pode substituir o conjunto de relatórios selecionado (correspondente a uma das tags na página) por outro conjunto de relatórios. Não é necessário que o novo conjunto de relatórios corresponda a uma tag na página. Se você alterar o conjunto de relatórios selecionado nas Configurações de Activity Map, o processo para Salvar fará com que todos os relatórios do Analytics afetados sejam atualizados.<br>**Importante**: [!UICONTROL Os conjuntos de relatórios virtuais] não são compatíveis com o [!UICONTROL Modo Online], somente com o [!UICONTROL Modo Padrão]. Se você estiver no [!UICONTROL Modo Online] para um Conjunto de Relatórios Padrão, mas selecionar um [!UICONTROL Conjunto de relatórios virtuais] nesta caixa de diálogo, após clicar em **[!UICONTROL OK]** aqui, o Modo Padrão será exibido. Além disso, o controle Calendário é reinicializado para corresponder ao tipo de calendário do conjunto de relatórios (gregoriano, varejo, personalizado...). |
| **[!UICONTROL Nome da página]** | A página à qual essas configurações se aplicam. |
| **[!UICONTROL Idioma]** | A seleção corresponde aos idiomas oferecidos para o Adobe Analytics. |
| **[!UICONTROL Sobreposições de Rótulo com]** | <ul><li>**[!UICONTROL Sem Rótulo]**: aplicável somente para a sobreposição de gradiente. Nesse caso, a cor da sobreposição transmite um sentido para a classificação do link</li><li>**[!UICONTROL Valor]**: o total bruto da métrica para esse link</li><li>**[!UICONTROL Porcentagem]**: a porcentagem da métrica para esse link na métrica total da página.</li><li>**[!UICONTROL Classificação]**: classificação desse link em todos os links presentes na página renderizada</li></ul> |
| **[!UICONTROL Tamanho da fonte do rótulo]** | Permite aumentar/diminuir o tamanho da fonte do rótulo de sobreposição, usando um controle deslizante para melhorar a leitura. |
| **[!UICONTROL Cor de Gradiente/Bolha]** | Para exibir as classificações do link de sobreposição para as visualizações de sobreposição de Gradiente ou em Bolha, selecione entre uma variedade de cores. |
| **[!UICONTROL Gradiente colorido com base em]** | <ul><li>**[!UICONTROL 30 principais classificações]**: a intensidade da cor é normalizada para os 30 valores principais.</li><li>**[!UICONTROL Valor absoluto da métrica]**: a intensidade da cor é uma função do valor absoluto da métrica.</li></ul> |
| **[!UICONTROL Transparência do gradiente]** | Selecione o nível de transparência para as sobreposições de Gradiente. Esta configuração não afeta as sobreposições de [!UICONTROL Bolha]. |

## Configurações padrão {#section_24DB95376E1A448494ECF3F57743FC19}

Essas configurações se aplicam à sobreposição de modo padrão.

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Filtragem Dinâmica de Dados]** | Essa lista suspensa permite mostrar sobreposições para<ul><li>(padrão) Todos os links na página</li><li>O número superior (mais alto) ou inferior (mais baixo) de links classificados na página, em que # pode ser uma opção de 1, 10, 50 ou 100.</li></ul> |
| **[!UICONTROL Ocultar as sobreposições para links que não receberam visitas]**. | Uma caixa de seleção que alterna a visibilidade de sobreposições para links sem dados.<ul><li>(padrão) Se a caixa de seleção estiver marcada, nenhuma sobreposição será exibida quando um link não tiver dados de link do Activity Map.</li><li>Se a caixa de seleção estiver desmarcada, e um link não tiver dados de link do Activity Map, uma sobreposição será exibida e terá um rótulo &quot;-&quot;, o que significa N/D (não aplicável). |

## Configurações em tempo real {#section_D30F6E62FB5D404090B588F396A460AF}

Essas configurações se aplicam à sobreposição em modo Online.

| Configuração | Descrição |
|---|---|
| **[!UICONTROL Exibir os principais]** | Para exibir os **[!UICONTROL Ganhadores]** ou **[!UICONTROL Perdedores]** (ou ambos) como sobreposições, selecione o número de links. |
| **[!UICONTROL Excluir os inferiores (%)]** | Selecione para eliminar os links de Ganhadores-Perdedores com dados insuficientes. Para mostrar ganhos ou perdas relevantes, filtre a porcentagem inferior das alterações do link para exibir apenas os links com dados suficientes. A porcentagem é calculada com base no número de links na página. Por exemplo, filtrar os 10% inferiores de uma lista de 200 links filtraria os 20 links inferiores. |
| **[!UICONTROL Atualização automática de dados]** | Permite decidir se os dados do Analytics mostrados na interface são atualizados automaticamente quando um novo período é calculado. |
| **[!UICONTROL Período de atualização automática]** | Quando selecionado, atualiza a página da Web a cada nova recuperação de dados para que os links na página possam ser sincronizados juntamente com os dados coletados. |
