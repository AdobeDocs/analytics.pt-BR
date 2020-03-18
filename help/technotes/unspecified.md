---
description: Vários relatórios do Adobe Analytics podem mostrar Não especificado, Outros ou Desconhecido, dependendo do relatório específico visualizado. Em geral, esse item da linha significa que a variável não foi definida ou não está disponível.
title: Não especificado, Outro e Desconhecido nos relatórios
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# “Não especificado”, “Outro” e “Desconhecido” nos relatórios

Vários relatórios do Adobe Analytics podem mostrar “Não especificado”, “Outros” ou “Desconhecido”, dependendo do relatório específico visualizado. Em geral, esse item da linha significa que a variável não foi definida ou não está disponível. A lista a seguir mostra como cada relatório pode ter um destes itens de linha.

## “Não especificado” nos relatórios

“Não especificado” é um item de linha bastante comum nos relatórios.

* **Um evento é acionado sem uma variável de conversão:** por exemplo, um usuário entra em seu site e efetua uma compra sem nenhum valor em eVar1. Se você exibir os pedidos usando a dimensão eVar1, não há um valor para ao pedido. Portanto, é atribuído automaticamente a “Não especificado”.
* **Dados não classificados nos relatórios de classificação:** ao exibir dados de classificação, qualquer valor sem dados associados à classificação específica retorna “Não especificado”. Para resolver esse problema, classifique o valor da variável pai.
* **Relatórios de detalhamento nos quais somente uma variável foi acionada:** quando você aplica um detalhamento a uma variável, cada instância dessa variável deve ser contabilizada. Se a segunda variável não foi vista ou se persistiu em um hit anterior, o valor da dimensão é &quot;Não especificado&quot;.
* **Ocorrências não móveis em relatórios móveis:** quaisquer hits não móveis em relatórios para dispositivos móveis são listadas como “Não especificado” (“Não móvel” no Reports and Analytics).

## “Outros” em relatórios

Embora seja de certa forma incomum em relatórios, “Outros” pode ocorrer em várias circunstâncias:

* **As páginas são acionadas fora dos filtros internos de URL:** esse valor está existe para ajudar a proteger contra fraude de dados, como no caso de outra organização roubar seu código fonte e o implementá-lo no próprio site. Para corrigir esse problema, verifique se todos os URLs nos quais seu código está implementado correspondem aos filtros de URL nas configurações do conjunto de relatórios.
* **Visitante usando um navegador não utilizado frequentemente:** no relatório Tipos de navegador, “Outros” aparece como um detalhamento de visitantes usando um navegador de tipo incomum. Existem diversas organizações que produzem navegadores. Todos os navegadores que organizações maiores não criaram são classificados em “Outros” para evitar a desorganização do relatório.

## “Desconhecido” nos relatórios

“Desconhecido” pode ocorrer sob diversas circunstâncias:

* **Ocorrências que não são de navegador na visualização dos relatórios de Tecnologia:** se uma biblioteca do AppMeasurement não puder determinar se um recurso é compatível, &quot;Desconhecido&quot; será exibido no relatório.
* **Uso de segmentos onde os componentes não estão acessíveis:** verifique se as variáveis usadas em um segmento estão ativadas e se os usuários podem acessá-las. Se um usuário não tiver acesso a um componente de segmento, ou se uma variável estiver desativada, “Desconhecido” será exibido.

## Filtragem desses valores em relatórios {#section_5536E2B419D445D39C932E8F12C0070C}

Na maioria das circunstâncias, é seguro ignorar esses itens de linha. O filtro de pesquisa pode ser usado para removê-los, se desejado.

Algumas variáveis de dados de back-end usam o valor `::unspecified::` nos relatórios, embora não apareça na interface. Se um filtro de pesquisa não conseguir excluir dados, tente usar esse valor (incluindo os dois pontos).
