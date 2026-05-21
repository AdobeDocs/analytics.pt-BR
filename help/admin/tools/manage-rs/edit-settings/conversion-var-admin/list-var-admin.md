---
title: Variáveis da Lista
description: Crie e configure variáveis de lista para usar em relatórios.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
TQID: https://experienceleague.adobe.com/22yU-AEfp08-BPNwwC6LrJO7iX7n44mZzP9799l6fmQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 490
ht-degree: 7%

---

# Variáveis da Lista

Crie e configure variáveis de lista para usar em relatórios. Defina os valores de delimitador, expiração, alocação e máximo. Coletar dados para variáveis de lista usando [`list1` - `list3`](/help/implement/vars/page-vars/list.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Listar Variáveis]**

* **[!UICONTROL Nome]**: o nome da variável de lista. Esse nome é o rótulo da dimensão no Analysis Workspace.

* **[!UICONTROL Status]**: habilitar ou desabilitar a coleta de dados para esta variável. Se uma variável estiver desativada, nenhum dado será coletado, mesmo se a implementação enviar dados para essa variável.

* **[!UICONTROL Delimitador de Valor]**: o caractere usado para separar valores dentro da variável de lista. Normalmente, esses são caracteres como vírgulas, dois pontos, barras verticais ou algo semelhante. Caracteres multibyte não são suportados como delimitadores em variáveis de lista.

* **[!UICONTROL Expira após]**: semelhante à expiração do eVar, este campo determina a quantidade de tempo que pode ocorrer entre a variável de lista e o evento de conversão para que eles sejam relacionados.
   * **Em um nível de exibição de página ou visita**: eventos bem-sucedidos além da exibição de página ou visita não seriam vinculados a nenhum valor na variável de lista.
   * **Com base em um período de tempo, como dia, semana, mês etc**: eventos bem-sucedidos além do período de tempo especificado não seriam vinculados a nenhum valor na variável de lista. Um número personalizado de dias também pode ser definido.
   * **Eventos de conversão específicos**: qualquer outro evento bem-sucedido que for acionado após o evento específico designado não será vinculado a nenhum valor na variável de lista.
   * **Nunca**: qualquer quantidade de tempo pode passar entre a variável de lista e o evento bem-sucedido.

* **[!UICONTROL Alocação]**: essa configuração determina como os eventos bem-sucedidos dividem crédito entre valores:
   * **Completa**: todos os valores de variável definidos antes da expiração da variável obtêm crédito total para eventos bem-sucedidos.
   * **Linear**: todos os valores de variável anteriores à expiração da variável obtêm crédito dividido para eventos de conversão.
   * Os valores de variáveis nunca são substituídos, mas adicionados aos valores que recebem crédito por eventos bem-sucedidos.

* **[!UICONTROL Descrição]**: uma descrição de como sua organização usa a variável de lista.

* **[!UICONTROL Valores Máx.]**: designa o número de valores ativos permitidos para esta variável de lista. Por exemplo, se definido como 3, somente os últimos 3 valores capturados serão salvos e quaisquer valores anteriores capturados serão descartados. Observe que se vários valores para a mesma variável de lista forem enviados na mesma ocorrência e você tiver restrito usando valores máximos, cada valor terá o mesmo carimbo de data e hora e não haverá garantia de qual valor será salvo. Se um visitante persistir em mais valores do que o máximo permitido, os valores mais recentes serão usados. São permitidos até 250 valores máximos.

  Essa configuração é útil para limitar a atribuição a um número específico de valores. Por exemplo, se uma variável de lista estiver definida como `"A,B,C"` na primeira página de uma visita, em seguida, definida como `"X,Y,Z"` na próxima página, a atribuição será distribuída para esses seis valores com base em sua alocação. Se você quiser limitar a atribuição a apenas `"X,Y,Z"`, poderá definir valores máximos como três.
