---
title: Variáveis da Lista
description: Crie e configure variáveis de lista para usar em relatórios.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: cf924b337772764b33d750787a0d09b3f11203be
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 25%

---

# Variáveis da Lista

Crie e configure variáveis de lista para usar em relatórios. Defina os valores de delimitador, expiração, alocação e máximo. Colete dados para variáveis de lista usando [`list1` - `list3`](/help/implement/vars/page-vars/list.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Variáveis de lista]**

* **[!UICONTROL Nome]**: o nome da variável de lista. Esse nome é o rótulo da dimensão no Analysis Workspace.

* **[!UICONTROL Status]**: ativar ou desativar a coleta de dados para essa variável. Se uma variável estiver desativada, nenhum dado será coletado, mesmo se a implementação enviar dados para essa variável.

* **[!UICONTROL Delimitador de valor]**: o caractere usado para separar valores na variável de lista. Normalmente, esses são caracteres como vírgulas, dois pontos, barras verticais ou algo semelhante. Caracteres multibyte não são suportados como delimitadores em variáveis de lista.

* **[!UICONTROL Expirar após]**: Semelhante à expiração de eVar, esse campo determina a quantidade de tempo que pode ocorrer entre a variável de lista e o evento de conversão para que eles sejam relacionados.
   * **Em um nível de exibição de página ou visita**: eventos bem-sucedidos além da exibição de página ou visita não vinculavam a nenhum valor na variável de lista.
   * **Com base em um período de tempo, como dia, semana, mês etc**: eventos bem-sucedidos além do período de tempo especificado não eram vinculados a nenhum valor na variável de lista. Um número personalizado de dias também pode ser definido aqui.
   * **Eventos de conversão específicos**: qualquer outro evento bem-sucedido acionado após o evento específico designado não vincularia novamente a nenhum valor na variável de lista.
   * **Nunca**: qualquer quantidade de tempo pode passar entre a variável de lista e o evento bem-sucedido.

* **[!UICONTROL Alocação]**: Essa configuração determina como os eventos de sucesso dividem crédito entre os valores:
   * **Total**: todos os valores de variável anteriores à expiração da variável obtêm crédito total por eventos bem-sucedidos.
   * **Linear**: todos os valores de variável anteriores à expiração da variável obtêm crédito dividido para eventos bem-sucedidos.
   * Os valores da variável nunca são sobrescritos, mas sim adicionados aos valores que obtêm crédito para eventos bem-sucedidos.

* **[!UICONTROL Descrição]**: uma descrição de como sua organização usa a variável de lista.

* **[!UICONTROL Valores máx.]**: designa o número de valores ativos permitidos para essa variável de lista. Por exemplo, se for definido como 3, somente os últimos 3 valores capturados são salvos e qualquer valor anterior capturado é descartado. Observe que se vários valores para a mesma variável de lista forem enviados na mesma ocorrência e você tiver restrito usando valores máximos, cada valor terá o mesmo carimbo de data e hora e não haverá garantia de qual valor será salvo. Se um visitante persistir em mais valores do que o máximo permitido, os valores mais recentes serão usados. São permitidos até 250 valores máximos.

  Essa configuração é útil para limitar a atribuição a um número específico de valores. Por exemplo, se uma variável de lista estiver definida como `"A,B,C"` na primeira página de uma visita, depois defina como `"X,Y,Z"` na próxima página, a atribuição é distribuída a esses seis valores com base em sua alocação. Se você quiser limitar a atribuição a apenas `"X,Y,Z"`, você pode definir valores máximos como três.
