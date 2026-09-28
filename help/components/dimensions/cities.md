---
title: Cidades
description: A cidade de onde o hit se originou.
feature: Dimensions
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
TQID: 'https://experienceleague.adobe.com/tAr9M0IgZcpRzElFfQSJx43JJjIXEtlo-pgDAKpSwq0'
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
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 64%
---
# Cidades

A [dimensão](overview.md) de &quot;Cidades&quot; informa a cidade de onde a ocorrência se originou. Essa dimensão é útil para ajudar a determinar a origem dos visitantes das cidades mais populares ao visitar seu site. Você poderia usar esses dados para se concentrar na publicidade local nessas cidades, como outdoors ou comerciais.

## Preencher esta dimensão com dados

O Adobe deriva essa dimensão do lado do servidor do endereço IP do visitante, comparando-a com uma tabela de pesquisa interna. A Adobe faz parceria com [Digital Element](https://www.digitalelement.com/pt-pt/) para manter pesquisas entre o endereço IP e a cidade. Não há variável a ser definida.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do endereço IP do visitante) |
| **Web SDK / campo XDM** | Nenhum (derivado do endereço IP do visitante) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do Web SDK, habilite a [!UICONTROL Pesquisa Geográfica] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-br).

## Itens de dimensão

Os itens de dimensão incluem cidades do mundo todo. Os valores de exemplo incluem `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"` ou `"London (London, United Kingdom)"`.

Alguns itens de dimensão podem incluir `"AOL"`, um provedor de serviço de acesso telefônico à Internet. Aos assinantes deste serviço é atribuído um ponto de acesso de acordo com o país onde o número da conta está estabelecido. Os usuários da AOL usam o endereço IP desse ponto de acesso. Como essa dimensão se baseia no endereço IP, a localização geográfica do ponto de acesso é usada em vez da localização real do visitante.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Algumas operadoras fazem o backhaul do tráfego IP por meio de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
* **Proxies que obscurecem endereços IP por motivos de privacidade**: serviços como a Retransmissão Privada da Apple ocultam o endereço IP verdadeiro enviando dados aleatoriamente por meio de um intermediário ou proxy. Esse proxy substitui um endereço IP diferente antes de encaminhar para o Adobe.
