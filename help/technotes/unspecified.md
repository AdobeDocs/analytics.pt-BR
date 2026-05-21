---
description: Vários relatórios do Adobe Analytics podem mostrar Não especificado, Nenhum, Outros ou Desconhecido, dependendo do relatório específico visualizado. Em geral, esse item da linha significa que a variável não foi definida ou não está disponível.
title: Não especificado, Nenhum, Outros e Desconhecido nos relatórios
feature: Analytics Basics
exl-id: 35451239-91f3-400a-981e-8c3fbc0e4185
TQID: https://experienceleague.adobe.com/JWT1oVZ-3Qcg9IxtPcEw9R9b8WHpe0O5GhDb3q-l7jo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 527
ht-degree: 88%

---

# “Não especificado”, “Nenhum”, “Outros” e “Desconhecido” nos relatórios

Vários relatórios do Adobe Analytics podem mostrar “Não especificado”, “Outros” ou “Desconhecido”, dependendo do relatório específico visualizado. Em geral, esse item da linha significa que a variável não foi definida ou não está disponível. A lista a seguir mostra como cada relatório pode ter um destes itens de linha.

## “Não especificado” (ou “Nenhum”) nos relatórios {#reporting}

“Não especificado” é um item de linha bastante comum nos relatórios. Também é frequentemente chamada de “Nenhum”.

* **Um evento é acionado sem uma variável de conversão:** por exemplo, um usuário entra em seu site e efetua uma compra sem nenhum valor em eVar1. Se você exibir os pedidos usando a dimensão eVar1, não há um valor para ao pedido. Portanto, é atribuído automaticamente a “Não especificado”.
* **Dados não classificados nos relatórios de classificação:** ao exibir dados de classificação, qualquer valor sem dados associados à classificação específica retorna “Não especificado”. Para resolver esse problema, verifique se há um valor de classificação associado a cada item de dimensão principal.
* **Relatórios de detalhamento nos quais somente uma variável foi acionada:** quando você aplica um detalhamento a uma variável, cada instância dessa variável deve ser contabilizada. Se a segunda variável não foi vista ou se persistiu em uma ocorrência anterior, o item de dimensão é “Não especificado”.
* **Ocorrências não móveis em relatórios móveis:** quaisquer hits não móveis em relatórios para dispositivos móveis são listadas como “Não especificado” (“Não móvel” no Reports and Analytics).

## “Outros” em relatórios {#other}

Embora seja de certa forma incomum em relatórios, “Outros” pode ocorrer em várias circunstâncias:

* **As páginas são acionadas fora dos filtros internos de URL:** esse valor está existe para ajudar a proteger contra fraude de dados, como no caso de outra organização roubar seu código fonte e o implementá-lo no próprio site. Para corrigir esse problema, verifique se todos os URLs nos quais seu código está implementado correspondem aos filtros de URL nas configurações do conjunto de relatórios.
* **Visitantes que usam um navegador pouco usado:** No relatório de Tipos de Navegador, &quot;Outros&quot; será exibido como um detalhamento se os visitantes estiverem usando um navegador que não é um tipo de navegador popular. Há muitas organizações que produzem navegadores. Todos os navegadores que organizações maiores não criaram são classificados em “Outros” para evitar a desorganização do relatório.

## &quot;Desconhecido&quot; nos relatórios {#unknown}

&quot;Desconhecido&quot; pode ocorrer em várias circunstâncias:

* **Ocorrências que não são de navegador na visualização dos relatórios de Tecnologia:** se uma biblioteca do AppMeasurement não puder determinar se um recurso é compatível, &quot;Desconhecido&quot; será exibido no relatório.
* **Uso de segmentos onde os componentes não estão acessíveis:** verifique se as variáveis usadas em um segmento estão habilitadas e se os usuários podem acessá-las. Se um usuário não tiver acesso a um componente de segmento, ou se uma variável estiver desativada, “Desconhecido” será exibido.

## Filtragem desses valores em relatórios {#filter}

Na maioria das circunstâncias, é seguro ignorar esses itens de linha. O filtro de pesquisa pode ser usado para removê-los, se desejado.

Algumas variáveis de dados de back-end usam o valor `::unspecified::` nos relatórios, embora não apareça na interface. Se um filtro de pesquisa não conseguir excluir dados, tente usar esse valor (incluindo os dois pontos).
