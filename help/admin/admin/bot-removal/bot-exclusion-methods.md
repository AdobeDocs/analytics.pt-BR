---
title: Comparação de diferentes métodos de exclusão de bots
description: Permite comparar diferentes métodos de exclusão de bots.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '325'
ht-degree: 100%

---

# Comparação de diferentes métodos de exclusão de bots

A tabela a seguir mostra diferentes métodos de exclusão de bots e como eles se comparam.

| Método | Regras de bot | Excluir por endereço IP | Atributos do cliente | Segmentação | Pontuação de terceiros + Segmentação | Suprimir Chamada de servidor para bots no tempo de execução | Regra VISTA DB personalizada |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Descrição do método de exclusão de dados** | Excluir com base no agente do usuário, endereço IP ou intervalo de endereços IP | Endereço IP | Um sinalizador nos atributos do cliente que identifica a ECID como um bot | Critérios em um segmento do Analytics que identifica bots conhecidos com base no comportamento do bot | Terceiros, como [Perímetro X](https://www.perimeterx.com) ou [Akamai Bot Manager](https://www.akamai.com/br/pt/products/security/bot-manager.jsp) atribuem a cada exibição de página uma pontuação em relação à probabilidade de ser um bot. A pontuação é enviada para o Analytics e os segmentos podem ser usados para filtrar dados com base na pontuação. | A lógica do lado do cliente impede que a chamada de servidor do Analytics seja executada para bots. | Uma regra VISTA moverá o tráfego de bots que atendem a determinados critérios para um conjunto de relatórios separado. |
| **Os nomes de bot estão disponíveis para relatórios?** | Sim | Não | Não | Não | Não | Não | Sim |
| **É possível ver quais páginas estão sendo visitadas por bots?** | Sim | Não | Não | Não | Sim | Não | Sim |
| **Representa o custo de chamada de servidor para bots?** | Sim | Sim | Sim | Sim | Sim | Não | Sim |
| **Dados de bot disponíveis nos feeds de dados?** | Não | Não | Sim | Sim | Sim | Não | Sim |
| **É possível relatar o tráfego de bots como se fossem chamadas de servidor reais?** | Não | Não | Sim | Sim | Sim | Sim | Não |
| **É possível remover dados retroativamente de um conjunto de dados?** | Não | Não | Sim, depois que as IDs declaradas são implementadas | Sim | Sim, depois que as pontuações são implementadas | Não | Não |
| **Está sujeito a limites únicos nos critérios?** | Não | Não | Não | Sim | Não | Não | Não |
| **Está sujeito a custo adicional?** | Não | Não | Possivelmente, dependendo da SKU do Analytics | Não | Sim | Não | Sim, custo para implementar e manter uma regra VISTA |
