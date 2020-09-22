---
title: Comparação de diferentes métodos de exclusão de bots
description: Permite comparar diferentes métodos de exclusão de bots.
translation-type: tm+mt
source-git-commit: 76ee4a8db49765590e7cca864d6d4b152d7ba112
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 19%

---


# Comparação de diferentes métodos de exclusão de bots

A tabela a seguir mostra métodos diferentes de excluir bots e como eles se empilham uns contra os outros.

| Método | Regras de bot | Excluir por endereço IP | Atributos do cliente | Segmentação | Pontuação de terceiros + Segmentação | Suprimir &#x200B; de Chamada do Servidor para Bots em Tempo de Execução | Regra VISTA personalizada do DB |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Descrição do método de exclusão dos dados** | &#x200B; Excluir com base no agente do usuário, endereço IP ou intervalo de endereços IP | Endereço IP | &#x200B; Um sinalizador nos atributos do cliente que identifica o ECID como um bot | Critérios de &#x200B; em um segmento do Analytics que identifica bots conhecidos com base no comportamento do bot | &#x200B; Um terceiro, como o [Perimeter X](https://www.perimeterx.com) ou o [Akamai Bot Manager](https://www.akamai.com/us/en/products/security/bot-manager.jsp) , atribui a cada visualização de página uma pontuação sobre a probabilidade de ser um robô. A pontuação é enviada para o Analytics e os segmentos podem ser usados para filtrar os dados com base na pontuação. | &#x200B; lógica do cliente impede que a chamada do servidor do Analytics seja executada para bots. | &#x200B; uma regra VISTA moverá o tráfego de bots que atendem a determinados critérios para um conjunto de relatórios separado. |
| **Os nomes dos bots &#x200B; estão disponíveis para o relatórios?** | Sim | Não | Não | Não | Não | Não | Sim |
| **&#x200B; consegue ver quais páginas estão sendo visitadas por bots?** | Sim | Não | Não | Não | Sim | Não | Sim |
| &#x200B;**Incurs server call cost for bots?** | Sim | Sim | Sim | Sim | Sim | Não | Sim |
| **Dados de robô disponíveis em feeds de dados?** | Não | Não | Sim | Sim | Sim | Não | Sim |
| **Pode &#x200B; relatórios sobre o tráfego de robô como se fossem chamadas reais do servidor?** | Não | Não | Sim | Sim | Sim | Sim | Não |
| **É possível remover dados retroativamente de um conjunto de dados?** | Não | Não | &#x200B; Sim, depois que as IDs declaradas forem implementadas | Sim | Sim, uma vez que as pontuações são implementadas | Não | Não |
| **Os critérios estão sujeitos a limites únicos?** | Não | Não | Não | Sim | Não | Não | Não |
| **O &#x200B; está sujeito a custos adicionais?** | Não | Não | &#x200B; possível, dependendo do SKU do Analytics | Não | Sim | Não | &#x200B; Sim - custo para implementar e manter uma regra VISTA |
