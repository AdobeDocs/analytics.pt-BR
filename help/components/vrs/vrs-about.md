---
description: Os conjuntos de relatórios virtuais segmentam seus dados do Adobe Analytics para que você possa controlar o acesso a cada segmento.
title: Visão geral dos conjuntos de relatórios virtuais
feature: VRS
exl-id: 45d18d14-d95a-42fe-b00a-cfce5f936e37
TQID: https://experienceleague.adobe.com/gEs8c9pIUGbbPx7DBAwFhSvT-C6W2vfosgMkrO-32ic
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e93b8c4c-c5f7-45f8-9abe-9b710f53f502id: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 812
ht-degree: 34%

---

# Visão geral dos conjuntos de relatórios virtuais

Os conjuntos de relatórios virtuais segmentam seus dados do Adobe Analytics para que você possa controlar o acesso a cada segmento.

Muitos clientes têm dados fluindo para um conjunto de relatórios global, mas também têm dados fluindo para conjuntos de relatórios menores. Eles definem uma variável como vários conjuntos de relatórios e enviam seus dados para mais de um conjunto de relatórios. Isso é mencionado como *marcação de vários relatórios* ou *conjuntos de relatórios de base/primários*.

Por exemplo, todos os dados podem ser coletados em um conjunto de relatórios, mas você pode configurar conjuntos de relatórios secundários para que outras pessoas na empresa tenham acesso a parte dos dados, mas não a todos. Os dados podem ser divididos por região. Você pode ter sites diferentes para países diferentes. Outros exemplos podem ser marcas específicas pertencentes a uma empresa maior, mas que tenham suas próprias equipes de marketing.

Um *conjunto de relatórios virtual* permite reproduzir esse conceito de ramificação, usando segmentos em vez de vários conjuntos de relatórios. Os dados são enviados para um conjunto de relatórios, depois são divididos de acordo com os segmentos. Usando o exemplo de várias marcas, você pode definir uma prop para a marca à qual um item pertence. Usando segmentos, você pode relatar os itens atribuídos a cada prop. Cada um desses segmentos torna-se sua própria visualização, criando efetivamente um novo conjunto de relatórios. Você não envia dados especificamente para esse segmento, apenas para o conjunto de relatórios global, mas ele funciona em seus relatórios como se fosse um conjunto de relatórios diferente.

Um conjunto de relatórios virtual herda a maioria dos níveis de serviço do conjunto de relatórios base, como configurações do eVar, Regras de processamento, Classificações etc. As seguintes configurações NÃO foram herdadas:

* ID de conjunto de relatórios (RSID)
* Nome do conjunto de relatórios
* Grupos de permissão (os conjuntos de relatórios virtuais podem ser atribuídos a seus próprios grupos de permissão)

## Benefícios dos conjuntos de relatórios virtuais {#section_3420422FE6DF46EAB151FD9442AAFDC4}

Os clientes pagam pelas chamadas do servidor secundárias, portanto, a eliminação dessas chamadas pode resultar em uma economia significativa. Um conjunto de relatórios virtual também é completamente retroativo. Se o conjunto de relatórios global já tiver dados, os dados relevantes serão incluídos automaticamente em um novo conjunto de relatórios virtual. Um novo conjunto de relatórios secundário só começaria a coletar dados após sua criação, de modo que não incluiria dados históricos. Ao implementar o Analytics, você só precisa enviar dados para um conjunto de relatórios, em vez de precisar criar implementações para o conjunto de relatórios global e cada conjunto de relatórios secundário.

Ajuda dos Conjuntos de relatórios virtuais:

* Simplifique a implementação permitindo que você use uma única ID de conjunto de relatórios (RSID) em todos os sites/domínios. Ter todos os dados em um único conjunto de relatórios permite a análise do cliente conforme avançamos para a próxima geração do Adobe Analytics.
* Os usuários empresariais em sua organização sempre veem somente os segmentos de dados relevantes para eles.
* Melhore a segurança permitindo que os usuários administradores controlem o acesso aos dados de forma mais fácil e granular após a implementação.
* Métrica de pessoas
* Uma visão de dados de um único cliente (no futuro)
* A capacidade de criar conjuntos de relatórios virtuais ilimitados para segmentar dados

## Limitações dos conjuntos de relatórios virtuais {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Os conjuntos de relatórios virtuais têm as seguintes limitações:

* Todas as limitações de segmentos aplicam-se também aos conjuntos de relatórios virtuais

  Um conjunto de relatórios virtual nada mais é do que um segmento aplicado a um conjunto de relatórios. Como cada conjunto de relatórios tem seu próprio data warehouse e seu próprio feed de dados, o uso de vários conjuntos de relatórios resulta em alguns benefícios que os segmentos não fornecem.
* Relatório em tempo real
* Configurações e nomes de variáveis não podem ser personalizados como em um conjunto de relatórios completo

## Conjuntos de relatórios virtuais versus marcação de vários relatórios {#section_317E4D21CCD74BC38166D2F57D214F78}

| Recurso | Conjunto de relatórios virtual | Marcação de vários relatórios |
|--- |--- |--- |
| Oferece relatórios em tempo real ou de &quot;Dados atuais&quot; | Não | Sim |
| Funciona em todas as ferramentas do Analytics (Analysis Workspace, Report Builder etc.) | Sim. **Observação:** você pode editá-los e identificá-los como conjuntos de relatórios virtuais somente em [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Conjuntos de relatórios virtuais]. Entretanto, é possível selecioná-los nos menus suspensos do conjunto de relatórios nas outras ferramentas.<p>**Importante**: os conjuntos de relatórios virtuais com processamento na hora do relatório e personalização de variáveis não são compatíveis com o Adobe Report Builder. | Sim |
| Pode fazer upload de dados para ele (por meio de classificações, feeds de dados etc.) | Não | Sim |
| Oferece suporte à criação de relatórios DL, marcadores, painéis, alvos, alertas, segmentos, métricas calculadas... | Sim | Sim |
| Pode ser adicionado individualmente aos Grupos de permissões | Sim | Sim |
| É possível usar as funções de Administrador para modificar configurações individuais neste conjunto de relatórios (Administrador > Conjuntos de relatórios) | Não (as configurações são herdadas do pai) | Sim |

{style="table-layout:auto"}

## Combine conjuntos de relatórios virtuais e marcação de vários relatórios {#section_026FA3FCD7314DD18220E73EC5702AFF}

Em alguns casos, existem benefícios em usar conjuntos de relatórios virtuais e marcação de vários relatórios.

Por exemplo, uma retailer pode usar um conjunto de relatórios para cada marca e conjuntos de relatórios virtuais para cada marca para dividir os dados por região. Da mesma forma, uma organização atlética pode usar um conjunto de relatórios para cada equipe e, em seguida, conjuntos de relatórios virtuais para dividir os fãs na região da equipe daqueles fora da região.
