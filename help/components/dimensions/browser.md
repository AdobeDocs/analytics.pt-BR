---
title: Navegador
description: O nome e a versão do navegador usado.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
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
source-wordcount: '310'
ht-degree: 35%
---
# Navegador

O &#39;[!UICONTROL Navegador]&#39; [dimensão](overview.md) informa o nome e a versão do navegador que está enviando a ocorrência. Essa dimensão é útil quando você deseja medir os navegadores mais comuns que os visitantes usam. Ao testar novas versões do site, você pode executar esses testes nos navegadores principais nesta dimensão para maximizar os esforços de controle de qualidade.

## Preencher esta dimensão com dados

A Adobe deriva essa dimensão do cabeçalho HTTP `User-Agent`, comparando-a com uma tabela de pesquisa interna que a Adobe mantém em parceria com o [DeviceAtlas](https://deviceatlas.com/). Não há variável a ser definida.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do agente do usuário) |
| **Web SDK / campo XDM** | Nenhum (derivado do agente do usuário) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do Web SDK, habilite a [!UICONTROL Pesquisa de Dispositivo] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Itens de dimensão

Os itens de dimensão incluem os nomes e as versões do navegador usadas. Diferentes versões do mesmo navegador são itens de dimensão separados.

Alguns itens de dimensão contêm `"(unknown version)"` em vez do número de versão. Esse item de dimensão faz referência a uma versão recente do navegador que a Adobe ainda não adicionou às tabelas de pesquisa. Como os navegadores são atualizados com frequência, o `"(unknown version)"` para um determinado navegador é comum e temporário. A Adobe normalmente atualiza as tabelas de pesquisa durante as versões de manutenção mensais.

Alguns itens de dimensão contêm `.999` como o número de versão secundária, como `"Chrome 148.999"`. Esse valor indica que o Adobe não pôde determinar com confiança a versão secundária do navegador. Quando os navegadores Chrome ou Edge enviam solicitações sem [dicas do cliente](/help/technotes/client-hints.md), a versão secundária na cadeia de agente do usuário não é considerada confiável. Em vez de inflar itens de dimensão com versões secundárias potencialmente imprecisas, o Adobe substitui essas versões secundárias por `.999`. Da mesma forma, se qualquer navegador reportar um número de versão excepcionalmente alto (acima de 99999), o Adobe o normaliza para `999.999`.
