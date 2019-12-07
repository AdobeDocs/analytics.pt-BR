---
description: Vários relatórios no Adobe Analytics podem mostrar Não especificado, Outro ou Desconhecido, dependendo do relatório específico exibido. Geralmente, esse item de linha significa que a variável não foi definida ou não está disponível.
title: Não especificado, Outro e Desconhecido nos relatórios
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# "Não especificado", "Outro" e "Desconhecido" nos relatórios

Vários relatórios no Adobe Analytics podem mostrar "Não especificado", "Outro" ou "Desconhecido", dependendo do relatório específico exibido. Geralmente, esse item de linha significa que a variável não foi definida ou não está disponível. A lista a seguir mostra como cada relatório pode ter um destes itens de linha.

## “Não especificado” nos relatórios

"Não especificado" é um item de linha bastante comum nos relatórios.

* **** Um evento é acionado sem uma variável de conversão: Por exemplo, um usuário visita seu site e efetua uma compra sem qualquer valor de eVar1. Se você exibir pedidos usando a dimensão eVar1, não haverá valor para o qual atribuir essa ordem. Portanto, é atribuído automaticamente a "Não especificado".
* **** Dados não classificados nos relatórios de classificação: Ao exibir dados de classificação, qualquer valor que não tenha dados associados a essa classificação específica retorna "Não especificado". Para resolver esse problema, classifique o valor da variável pai.
* **** Relatórios de detalhamento nos quais somente uma variável foi acionada: Quando você aplica um detalhamento a uma variável, cada instância dessa variável deve ser contabilizada. Se a segunda variável não foi vista ou se persistiu em uma ocorrência anterior, o valor da dimensão é "Não especificado".
* **** Ocorrências não móveis em relatórios móveis: Quaisquer ocorrências não móveis em relatórios móveis são listadas como "Não especificado" ("Não móvel" em Relatórios e análises).

## “Outros” em relatórios

Embora um pouco raro no relatório, "Outro" pode ocorrer sob várias circunstâncias:

* **** As páginas são acionadas fora dos filtros internos de URL: Esse valor está em vigor para ajudar a proteger contra fraude de dados, como se outra organização roubasse seu código fonte e o implemente em seu próprio site. Para corrigir esse problema, verifique se todos os URLs nos quais seu código está implementado correspondem aos filtros internos de URL nas configurações do conjunto de relatórios.
* **Visitante usando um navegador não utilizado frequentemente:** no relatório Tipos de navegador, “Outros” aparece como um detalhamento de visitantes usando um navegador de tipo incomum. Existem diversas organizações que produzem navegadores. Todos os navegadores que organizações maiores não criaram são classificados em "Outros" para evitar a desorganização do relatório.

## “Desconhecido” nos relatórios

“Desconhecido” pode ocorrer sob diversas circunstâncias:

* **** Ocorrências que não são de navegador ao visualizar relatórios de Tecnologia: Se uma biblioteca do AppMeasurement não puder determinar se um recurso é suportado, "Desconhecido" será exibido no relatório.
* **** Uso de segmentos onde os componentes não estão acessíveis: Verifique se as variáveis usadas em um segmento estão ativadas e se os usuários podem acessá-las. Se um usuário não tiver acesso a um componente de segmento, ou se uma variável estiver desativada, "Desconhecido" será exibido.

## Filtragem desses valores em relatórios {#section_5536E2B419D445D39C932E8F12C0070C}

Na maioria das circunstâncias, é seguro ignorar esses itens de linha. O filtro de pesquisa pode ser usado para removê-los, se desejado.

Some backend data variables use the value `::unspecified::` in reporting, though it is not shown in the interface. Se um filtro de pesquisa não conseguir excluir dados, tente usar esse valor (incluindo dois pontos).
