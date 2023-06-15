---
title: Variáveis da Lista
description: Crie e configure variáveis de lista para usar em relatórios.
feature: Admin Tools
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: 21029930b5cae6acb6bc6a59836ddc1ca33cb27e
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 92%

---

# Variáveis da Lista

Crie e configure variáveis de lista para usar em relatórios. Defina os valores de delimitador, expiração, alocação e máximo.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Buscar métodos]**

* **Nome**: cada valor delimitado pode conter um máximo de 255 caracteres (ou menos se estiver usando caracteres multibyte). Esse é o comprimento máximo para cada elemento.
* **Delimitador de valor**: O caractere usado para separar valores na List Var. Com maior frequência, são caracteres como vírgulas, dois pontos, barras verticais, ou algo parecido.

  >[!NOTE]
  >
  >Caracteres multibyte não são suportados como delimitadores em Vars de lista. O delimitador deve ser de byte único.

* **Expiração**: Semelhante à expiração de eVar, esse campo determina a quantidade de tempo que pode ocorrer entre a Var de lista e o evento de conversão para que eles sejam relacionados.
   * **Em uma exibição de página ou nível de visita**: Eventos bem-sucedidos além de exibição de página ou visita não vinculariam a qualquer valor na List Var.
   * **Com base no período, como dia, semana, mês, etc.**: Eventos bem-sucedidos além do período especificado não vinculariam a qualquer valor na List Var. Um número personalizado de dias também pode ser definido aqui.
   * **Eventos de conversão específicos**: Quaisquer outros eventos de bem-sucedidos acionados depois do evento específico designado não vinculariam a qualquer valor na List Var.
   * **Nunca**: Qualquer período pode ser passar entre a List Var e o evento bem-sucedido.

* **Alocação**: Essa configuração determina como os eventos de sucesso dividem crédito entre os valores:
   * **Total**: todos os valores de variável anteriores à expiração da variável obtêm crédito total por eventos bem-sucedidos.
   * **Linear**: todos os valores de variável anteriores à expiração da variável obtêm crédito dividido para eventos bem-sucedidos.
   * Os valores da variável nunca são sobrescritos, mas sim adicionados aos valores que obtêm crédito para eventos bem-sucedidos.

* **Valores máx.**: designa o número de valores ativos permitidos para essa variável de lista. Por exemplo, se for definido como 3, somente os últimos 3 valores capturados são salvos e qualquer valor anterior capturado é descartado. Observe que se diversos valores da mesma var de lista são enviados na mesma ocorrência que você restringiu o uso de valores de máximo, cada valor terá o mesmo carimbo de data e hora e não há garantia de qual valor é salvo.

Um limite máximo de 250 valores é armazenado de uma vez por visitante. Se a quantidade de 250 valores por visitante for excedida, os 250 valores mais recentes serão usados. A expiração desses valores tem por base a expiração configurada da variável.

A configuração Valores máx. é útil para limitar a atribuição para um número específico de valores. Por exemplo, se uma var de lista está definida como &quot;A,B,C&quot; na primeira página de uma visita, em seguida, definida como &quot;X,Y,Z&quot; na próxima página, a atribuição é distribuída para esses seis valores com base na alocação. Se você deseja limitar a atribuição somente a &quot;X,Y,Z&quot;, você pode definir os valores máximos como três.
