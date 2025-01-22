---
description: Modifique as configurações e propriedades para todos os tipos de visualizações de sobreposição no Activity Map.
title: Definir configurações do Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: 13ad9d40ad74a8dffe05d899db54f4d77cbcc34c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 4%

---

# Definir configurações do Activity Map

O painel Configuração de Activity Map permite modificar as configurações e propriedades para todos os tipos de visualizações de sobreposição.

**[!UICONTROL Sobreposição de Activity Map]** > **Mostrar configurações (ícone de engrenagem)** > **[!UICONTROL Configurações]**

## Configurações gerais

Altere as configurações gerais da extensão e as sobreposições.

* **[!UICONTROL Empresas]**: mostra a organização atual do Analytics na qual você está conectado.
* **[!UICONTROL Nome da página]**: mostra o nome da página atual.
* **[!UICONTROL Idioma]**: altera o idioma para rótulos de extensão do Activity Map. Essa configuração não altera o conteúdo do site nem os nomes dos links nos relatórios. Os idiomas suportados incluem inglês, francês, chinês (simplificado), chinês (tradicional), alemão, japonês, coreano, espanhol e português.
* **[!UICONTROL Sobreposições de rótulo com]**: determina o texto da bolha ou do gradiente. A configuração padrão é [!UICONTROL Rank]. As opções incluem: 
   * **[!UICONTROL Nenhum rótulo]**: nenhum texto nos rótulos, tornando-os caixas coloridas
   * **[!UICONTROL Valor]**: exibe o número de cliques em links ([Ocorrências](/help/components/metrics/occurrences.md))
   * **[!UICONTROL Percentual]**: exibe a proporção de cliques em links em comparação ao número total de cliques em links na página
   * **[!UICONTROL Classificação]**: a classificação numérica do link por número de cliques no link.
* **[!UICONTROL Tamanho da fonte do rótulo]**: determina o tamanho do texto dentro da bolha ou do gradiente.
* **[!UICONTROL Cor do gradiente]**: permite alterar a cor do gradiente quando o tipo de visualização é [!UICONTROL Gradiente].
* **[!UICONTROL Cor da bolha]**: permite alterar a cor da bolha quando o tipo de visualização é [!UICONTROL Bolha].
* **[!UICONTROL Gradiente de cor com base em]**: determina em qual métrica a intensidade de cor de um link se baseia quando o tipo de visualização é [!UICONTROL Gradiente].
   * **[!UICONTROL 30 principais classificações]**: a intensidade da cor é normalizada para os 30 links principais.
   * **[!UICONTROL Valor absoluto da métrica]**: a intensidade da cor é uma função do valor absoluto da métrica.
* **[!UICONTROL Transparência do gradiente]**: determina a transparência das sobreposições do gradiente quando o tipo de visualização é [!UICONTROL Gradiente]. Esse controle deslizante permite que você torne a sobreposição de cor totalmente transparente, completamente opaca ou em qualquer lugar intermediário.

## Configurações padrão

Ajuste as configurações para a exibição padrão.

* **[!UICONTROL Filtragem dinâmica de dados]**: permite alterar os links exibidos.
   * **[!UICONTROL Superior]**: exibe os links mais populares. Use a lista suspensa numérica à direita para determinar o número de links principais a serem exibidos. As opções incluem 1, 10, 50 e 100.
   * **[!UICONTROL Inferior]**: exibe os links menos populares com base na lista suspensa de números. Use a lista suspensa numérica à direita para determinar o número de links inferiores a serem exibidos. As opções incluem 1, 10, 50 e 100.
   * **[!UICONTROL Todos os links]**: não aplicar a filtragem de dados dinâmicos. A lista suspensa numérica não se aplica quando essa opção é selecionada.
* **[!UICONTROL Ocultar as sobreposições para links que não receberam visitas]**: os links na página com zero cliques em links não mostram uma sobreposição. Esses links são excluídos da filtragem de dados dinâmicos.

## Configurações em tempo real

* **[!UICONTROL Exibir primeiros]**: exibe o primeiro número de ganhadores ou perdedores com base na lista suspensa numérica à esquerda.
* **[!UICONTROL Excluir inferior (%)]**: filtre a porcentagem inferior das alterações de link para exibir somente os links com dados suficientes para mostrar ganhos ou perdas relevantes. A porcentagem é calculada com base no número de links na página. Por exemplo, filtrar os 10% inferiores de uma lista de 200 links filtraria os 20 links inferiores.
* **[!UICONTROL Dados de atualização automática]**: determina se os dados do Analytics mostrados na sobreposição são atualizados automaticamente quando um novo período é calculado.
* **[!UICONTROL Período de atualização automática]**: quando marcado, atualiza a página a cada nova recuperação de dados para que os links na página sejam sincronizados mais estreitamente com os dados coletados.
