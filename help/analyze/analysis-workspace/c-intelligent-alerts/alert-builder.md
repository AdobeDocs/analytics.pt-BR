---
description: 'null'
title: Criador de alertas
uuid: ebc2d457-4abd-4b1a-9357-489b5aeb3f64
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Criador de alertas

>[!IMPORTANT]
>
>Os Alertas inteligentes estão disponíveis somente para clientes do Adobe Analytics Prime e do Adobe Analytics Ultimate.

## Acessar o Criador de alertas

Acesse o Criador de alertas de uma das quatro maneiras:

* Usando o seguinte atalho no Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* Acessando **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]**.
* By selecting one or more freeform table line items, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**.
* Em um relatório de Relatórios e análises, vá até **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.

## Criar alertas

A interface do Criador de alertas é semelhante àquela que cria segmentos ou métricas calculadas no Analytics:

![](assets/alert_builder.png)

<!--Meike, I edited this table for validation -->

**Nome do Alerta**

Especifique um nome para o alerta. O nome do alerta pode conter o nome do relatório ou o limite de métricas.

**Granularidade de tempo**

Especifique quando você deseja verificar a métrica: por hora, dia, semana ou mês.

>[!NOTE] Para conjuntos de relatórios com um calendário personalizado, não oferecemos suporte à granularidade mensal no Criador de alertas.

**Destinatários**

Especifique para onde o alerta pode ser enviado. Um alerta pode ser enviado para um usuário do Analytics, um grupo do Analytics, um endereço de email bruto ou para um número de telefone.

>[!IMPORTANT]
>
>O telefone deve ser precedido por um “+” e um [código de país](https://countrycode.org/).

O email que um usuário receberia depois que um alerta é acionado é semelhante ao modelo abaixo:

![](assets/alerts-email.PNG)

**Data de expiração**

Defina a data de expiração do alerta.

**Enviar um Alerta quando...**

*... qualquer uma dessas métricas forem acionadas*

* Arraste e solte métricas na tela que adicionará disparadores.

   Será exibida uma mensagem **“componentes incompatíveis”** se nem todos os componentes (métricas/dimensões/segmentos) no alerta forem compatíveis com o conjunto de relatórios selecionado atualmente.
* Determine o limite que a métrica deve exceder antes de um alerta ser definido. É possível definir esse valor como um limite e, em seguida, como uma das seguintes condições:

   * a anomalia existe
   * a anomalia está acima do esperado
   * a anomalia está abaixo do esperado
   * é igual ou superior a
   * é menor ou igual a
   * alterações por
   * Você pode definir um limite de 90%, 95%, 99%, 99,75% e 99,9%.
   Observe que você também pode usar as métricas calculadas.

*... com esses filtros*

* Arraste e solte segmentos ou dimensões para adicionar filtros. Por exemplo, adicionar um segmento &quot;Somente dispositivos móveis&quot; significaria que a regra dispara somente para dispositivos móveis.
* filtros adicionais serão adicionados usando uma instrução E.

**Adicionar uma regra**

Você pode adicionar regras AND ou OR, clicando no ícone de engrenagem.

## Visualizar alertas {#section_10D75BA7B77E4C5FAF58A719C082E070}

A pré-visualização de alerta interativa mostra a frequência com que um alerta será acionado aproximadamente com base na experiência anterior.

Por exemplo, se você definir a granularidade de tempo como diária, a pré-visualização poderá informá-lo que o alerta teria sido disparado para uma determinada métrica x vezes durante os últimos 30 ou 31 dias.

Se você descobrir que muitos alertas teriam sido disparados, poderá ajustar o limite no Gerenciador de [alertas](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
