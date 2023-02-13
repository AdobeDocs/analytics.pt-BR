---
title: Comparar métodos de implementação
description: Veja as vantagens de cada método de envio de dados para o Adobe Analytics.
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# Comparar métodos de implementação

Veja a comparação entre cada método de implementação do Adobe Analytics. Você pode usar essa tabela para ajudar sua organização a determinar a melhor maneira de enviar dados para a Adobe.

|  | AppMeasurement | Extensão do Adobe Analytics | SDK da Web | Extensão do SDK da Web |
| --- | --- | --- | --- | --- |
| Requisitos de implementação | Faça referência ao `AppMeasurement.js` em cada página, defina variáveis e envie dados usando o `s.t()` | Faça referência ao tag loader em cada página, use a interface do usuário da coleção de dados para definir variáveis e enviar dados para a Adobe | Faça referência ao `Alloy.js` em cada página, use a `alloy("sendEvent",{})` para enviar um objeto JSON contendo os dados desejados | Faça referência ao tag loader em cada página, use a interface do usuário da coleção de dados para estabelecer o objeto JSON para enviar dados |
| Destino dos dados | Enviado diretamente para o Adobe Analytics | Enviado diretamente para o Adobe Analytics | Enviado para a Adobe Experience Platform Edge, que encaminha dados para o Adobe Analytics | Enviado para a Adobe Experience Platform Edge, que encaminha dados para o Adobe Analytics |
| Dificuldade em fazer ajustes de implementação | Requer acesso ao código do site para cada alteração de implementação | O código do site só precisa ser alterado uma vez para instalar a tag loader; todas as atualizações de implementação adicionais podem ser feitas na interface do usuário da coleção de dados | Requer acesso ao código do site para cada alteração de implementação | O código do site só precisa ser alterado uma vez para instalar a tag loader; todas as atualizações de implementação adicionais podem ser feitas na interface do usuário da coleção de dados |
| Como o A4T é tratado | As chamadas do A4T são incluídas nas ocorrências enviadas para a Adobe | As chamadas do A4T são incluídas nas ocorrências enviadas para a Adobe | Chamadas do A4T são enviadas como ocorrências separadas | Chamadas do A4T são enviadas como ocorrências separadas |
| Como o referenciador é tratado |