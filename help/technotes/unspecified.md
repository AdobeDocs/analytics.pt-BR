---
description: Vários relatórios no Adobe Analytics podem mostrar Não especificado, Outros ou Desconhecido, dependendo do relatório específico visualizado. Geralmente, esse item de linha significa que a variável não foi definida ou não está disponível.
seo-description: Vários relatórios no Adobe Analytics podem mostrar Não especificado, Outros ou Desconhecido, dependendo do relatório específico visualizado. Geralmente, esse item de linha significa que a variável não foi definida ou não está disponível.
seo-title: Não especificado, Outro e Desconhecido no relatório
solution: Analytics
title: Não especificado, Outro e Desconhecido no relatório
translation-type: tm+mt
source-git-commit: 9170eaee2b816280e48901100ac7aaf3b56ec8c5

---


# “Não especificado”, “Outro” e “Desconhecido” nos relatórios

Vários relatórios no Adobe Analytics podem mostrar “Não especificado”, “Outro” ou “Desconhecido”, dependendo do relatório específico visualizado. Geralmente, esse item de linha significa que a variável não foi definida ou não está disponível. A lista a seguir mostra como cada relatório pode ter um destes itens de linha.

## “Não especificado” nos relatórios

“Não especificado” é um item de linha muito comum nos relatórios.

* **Um evento é acionado sem uma variável de conversão:** Por exemplo, um usuário chega ao seu site e efetua uma compra sem qualquer valor de evar 1. Se você exibir pedidos usando a dimensão evar 1, não há valor para atribuir essa ordem. Portanto, é atribuído automaticamente a “Não especificado”.
* **Dados não classificados nos relatórios de classificação:** Ao exibir dados de classificação, qualquer valor que não tenha dados associados a essa classificação específica retorna “Não especificado”. Para resolver esse problema, classifique o valor da variável pai.
* **Relatórios de detalhamento em que somente uma variável é acionada:** Ao aplicar um detalhamento a uma variável, cada instância dessa variável deve ser contabilizada. Se a segunda variável não foi vista ou se persistiu de uma ocorrência anterior, o valor da dimensão é “Não especificado”.
* **Ocorrências não móveis em relatórios móveis:** Quaisquer ocorrências não móveis em relatórios móveis estão listadas como “Não especificado” ("Não móvel" em Reports and Analytics).

## “Outro” em relatórios

Embora um pouco raro nos relatórios, “Outro” pode ocorrer em diversas circunstâncias:

* **As páginas são acionadas fora dos filtros internos do URL:** Esse valor está em vigor para ajudar a proteger contra fraude de dados, como se outra organização rouba o código fonte e o implementa em seu próprio site. Para corrigir esse problema, verifique se todos os urls em que seu código está implementado correspondem aos filtros internos do URL nas configurações do conjunto de relatórios.
* **Visitante usando um navegador não utilizado frequentemente:** no relatório Tipos de navegador, “Outros” aparece como um detalhamento de visitantes usando um navegador de tipo incomum. Existem diversas organizações que produzem navegadores. Todos os navegadores que organizações maiores não criaram são colocados em “Outro” para evitar a desativação do relatório.

## “Desconhecido” nos relatórios

“Desconhecido” pode ocorrer sob diversas circunstâncias:

* **Ocorrências não navegadoras ao visualizar relatórios de Tecnologia:** Se uma biblioteca appmeasurement não conseguir determinar se um recurso é suportado, “Desconhecido” será mostrado nos relatórios.
* **Uso de segmentos em que os componentes não estão acessíveis:** Verifique se as variáveis usadas em um segmento estão ativadas e se os usuários podem acessá-los. Se um usuário não tiver acesso a um componente de segmento, ou se uma variável estiver desativada, “Desconhecido” será mostrado.

## Filtragem desses valores em relatórios {#section_5536E2B419D445D39C932E8F12C0070C}

Na maioria das circunstâncias, é seguro ignorar esses itens de linha. O filtro de pesquisa pode ser usado para removê-los, se desejado.

Some backend data variables use the value `::unspecified::` in reporting, though it is not shown in the interface. Se um filtro de pesquisa falhar na exclusão de dados, tente usar esse valor (incluindo os dois pontos).
