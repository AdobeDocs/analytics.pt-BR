---
title: Detalhes do canal de primeiro contato
description: Detalhes do primeiro canal de marketing após a expiração do engajamento do visitante.
feature: Dimensions
exl-id: a155182d-7bc0-4c7d-9de7-680bfe2d6432
TQID: https://experienceleague.adobe.com/duNfZhq3nb1kAjVkbUEUkuFPixk-FaTZX3-TA25AifQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 73%
---
# Detalhes do canal de primeiro contato

A [dimensão](overview.md) de &quot;Detalhes do canal de primeiro contato&quot; relata detalhes sobre o primeiro canal de marketing com o qual um visitante corresponde durante o período de engajamento (30 dias por padrão). Essa dimensão é importante para entender o que contribuiu para que o hit correspondesse a um canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.

## Preencher esta dimensão com dados

Essa dimensão é derivada das Regras de processamento do canal de marketing, que copiam valores de outras variáveis. A variável utilizada se refere ao valor do canal de cada [Regra de processamento de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Quando um hit corresponde a uma regra de processamento de canal de marketing, a dimensão [Canal de último contato](last-touch-channel.md) é definida como o nome do canal e essa dimensão é definida como o valor do canal definido na regra. Não há variável a ser definida.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado das regras de processamento do Canal de marketing) |
| **Web SDK / campo XDM** | Nenhum (derivado das regras de processamento do Canal de marketing) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

Se você quiser definir essa dimensão com um valor específico, siga os seguintes passos:

* Verifique se o item de dimensão desejado está em um atributo de hit ou em uma variável personalizada.
* Defina uma regra de processamento de canal de marketing que contenha os critérios desejados para a ocorrência.
* Selecione o valor desejado na lista suspensa em [!UICONTROL Definir o valor do canal] dentro da regra de processamento Canal de marketing.
* O hit do visitante no site deve corresponder aos critérios descritos na regra de processamento Canal de marketing _e_ deve ser o primeiro valor do canal de marketing a fazer isso durante o período de engajamento do visitante.

Se uma ocorrência subsequente corresponder aos critérios em um canal de marketing diferente, essa dimensão não será substituída pelo novo canal de marketing.

## Itens de dimensão

Os itens do Dimension dependem do valor do canal listado na lista suspensa para a regra de processamento de canal de marketing aplicável. Por exemplo, se você definir o valor do canal como “URL da página”, os itens de dimensão incluirão URLs de página no site. Se você definir o valor do canal como Domínio de referência, os itens de dimensão incluirão domínios nos quais os visitantes clicaram para acessar seu site. Essa dimensão agrega todos os itens de dimensão de detalhes, independentemente do canal em que estão.

A Adobe recomenda definir valores de canal relacionados ao canal de marketing para obter informações sobre os detalhes do canal.
