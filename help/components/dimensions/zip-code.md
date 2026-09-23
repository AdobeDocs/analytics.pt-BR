---
title: Código postal
description: O código postal do visitante.
feature: Dimensions
exl-id: 597619f8-a581-4491-beb2-c14b1f7b7bec
TQID: https://experienceleague.adobe.com/XHrUXKHrXiH0wsUr0klmPmA-DEq5T5yu18KLNT7oYeo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 61%
---
# Código postal

O &#39;CEP&#39; [dimensão](overview.md) informa o CEP ou código postal do visitante. Essa dimensão pode ser utilizada para entender melhor o sucesso da publicidade local ou para descobrir em que lugar do mundo o seu site tem melhor repercussão.

## Preencher esta dimensão com dados

Essa dimensão é única, pois contém várias maneiras de preenchê-la com dados. Você pode usar uma ou uma combinação das duas:

* Defina o código postal diretamente utilizando a variável [`zip`](/help/implement/vars/page-vars/zip.md).
* Configure-o para extrair dados de geolocalização. Quando o CEP é usado, nenhuma variável é definida. Para implementações do AppMeasurement, essa dimensão funciona imediatamente. Para implementações do Web SDK, habilite a [!UICONTROL Pesquisa Geográfica] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-br).

A [!UICONTROL Opção código postal] em [Configurações gerais da Conta](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) controla como você pode preencher essa dimensão. A tabela de referência abaixo se aplica quando você define a variável `zip` diretamente.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | [`zip`](/help/implement/vars/page-vars/zip.md) |
| **Web SDK / campo XDM** | [`placeContext.geo.postalCode`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/data-types/geo) |
| **Parâmetro de consulta** | [`zip`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<zip>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 50 bytes |
| **Persistência** | Hit |

## Itens de dimensão

Os itens de dimensão incluem o CEP ou código postal do visitante.

## Países com código postal aceitos

* Ilhas Aland
* Albânia
* Argélia
* Argentina
* Armênia
* Áustria
* Austrália
* Bangladesh
* Barbados
* Bélgica
* Brasil
* Bulgária
* Canadá
* Chile
* China
* Colômbia
* Costa Rica
* Croácia
* República Tcheca
* Dinamarca
* Equador
* Egito
* Estônia
* Finlândia
* França
* Geórgia
* Alemanha
* Gibraltar
* Grécia
* Granada
* Guatemala
* RAE de Hong Kong da China
* Hungria
* Índia
* Indonésia
* Irlanda
* Israel
* Itália
* Japão
* Jordânia
* Cazaquistão
* Quirguistão
* Látvia
* Líbano
* Lituânia
* Luxemburgo
* Malásia
* Malta
* Ilhas Maurício
* México
* Marrocos
* Moçambique
* Nepal
* Holanda
* Nova Zelândia
* Noruega
* Paquistão
* Panamá
* Peru
* Filipinas
* Polônia
* Portugal
* Porto Rico
* Catar
* Romênia
* Federação Russa
* Arábia Saudita
* Senegal
* Sérvia
* Singapura
* Eslovênia
* África do Sul
* Coreia do Sul
* Espanha
* Sri Lanka
* Suécia
* Suíça
* Região de Taiwan
* Tailândia
* Tunísia
* Turquia
* Ucrânia
* Emirados Árabes Unidos
* Reino Unido
* Estados Unidos
* Uruguai
* Uzbequistão
* Venezuela
* Vietnã
