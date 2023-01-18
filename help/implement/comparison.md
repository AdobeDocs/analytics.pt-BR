---
title: Comparar métodos de implementação
description: Veja as vantagens de cada método enviar dados para a Adobe Analytics.
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# Comparar métodos de implementação

Veja a comparação entre cada método de implementação do Adobe Analytics. Você pode usar essa tabela para ajudar sua organização a determinar a maneira mais ideal de enviar dados para o Adobe.

|  | AppMeasurement | Extensão do Adobe Analytics | SDK da Web | Extensão do SDK da Web |
| --- | --- | --- | --- | --- |
| Requisitos de implementação | Referência `AppMeasurement.js` em cada página, defina variáveis, envie dados usando `s.t()` | Faça referência ao tag loader em cada página, use a interface do usuário da coleta de dados para definir variáveis e enviar dados para o Adobe | Referência `Alloy.js` em cada página, use `alloy("sendEvent",{})` para enviar um objeto JSON contendo os dados desejados | Faça referência ao tag loader em cada página, use a interface do usuário da coleta de dados para estabelecer o objeto JSON para enviar dados |
| Destino dos dados | Enviado diretamente para o Adobe Analytics | Enviado diretamente para o Adobe Analytics | Enviado para o Adobe Experience Platform Edge, que encaminha dados para o Adobe Analytics | Enviado para o Adobe Experience Platform Edge, que encaminha dados para o Adobe Analytics |
| Dificuldade em fazer ajustes de implementação | Requer acesso ao código do site para cada alteração de implementação | O código do site só precisa ser alterado uma vez para instalar a tag loader; todas as atualizações de implementação adicionais podem ser feitas na interface do usuário da coleta de dados | Requer acesso ao código do site para cada alteração de implementação | O código do site só precisa ser alterado uma vez para instalar a tag loader; todas as atualizações de implementação adicionais podem ser feitas na interface do usuário da coleta de dados |
| Como o A4T é tratado | As chamadas de A4T são incluídas nas ocorrências enviadas para o Adobe | As chamadas de A4T são incluídas nas ocorrências enviadas para o Adobe | Chamadas A4T são enviadas como ocorrências separadas | Chamadas A4T são enviadas como ocorrências separadas |
| Como o referenciador é tratado |