---
description: 'null'
seo-description: 'null'
seo-title: Criador de alertas
title: Criador de alertas
uuid: 86 d 00 a 33-dc 99-4 dc 3-a 732-0 b 895 ba 487 bc
translation-type: tm+mt
source-git-commit: 8b2feced9fd503395d06dc12c8e5d7985ca89161

---


# Criador de alertas

>[!IMPORTANT]
>
>Intelligent Alerts are available to Adobe [!DNL Analytics] Prime and Adobe [!DNL Analytics] Ultimate customers only.

Acesse o Criador de alertas de uma das seguintes formas:

* Usando o seguinte atalho na Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* By going to **[!UICONTROL Workspace]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL New Alert]**.
* Selecionando um ou mais itens de linha da tabela de forma livre, clicando com o botão direito do mouse e selecionando **[!UICONTROL Criar alerta a partir da seleção]**.
* From within a [!UICONTROL Reports &amp; Analytics] report, by going to **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.

A interface do Criador de alertas é semelhante àquela que cria segmentos ou métricas calculadas no [!DNL Analytics]:

![](assets/alert_builder.png)

**Nome do Alerta**

Especifique um nome para o alerta. O nome do alerta pode conter o nome do relatório ou o limite da métrica.

**Granularidade de tempo**

Especifique quando você deseja verificar a métrica: por hora, dia, semana ou mês.

>[!NOTE]
>
>Para conjuntos de relatórios com um calendário personalizado, não oferecemos suporte à granularidade mensal no Criador de alertas.

**Destinatários**

Especifique para onde o alerta pode ser enviado. An alert can be sent to an [!DNL Analytics] user, an [!DNL Analytics] group, a raw email address, or to a phone number.

>[!IMPORTANT]
>
>The phone number must be preceded by a "+" and a [country code](https://countrycode.org/).

**Data de validade**

Defina a data de expiração do alerta.

**Enviar um Alerta quando...**

*... qualquer uma dessas métricas forem acionadas*

* Arraste e solte métricas na tela que adicionará disparadores.

   Note that an **"incompatible components”** message will appear if not all the components (metrics/dimensions/segments) in the alert are compatible with the currently selected report suite.

* Determine o limite que a métrica deve exceder antes de definir um alarme. Você pode definir este valor para um limite e, em seguida, para uma das condições a seguir:

   * a anomalia existe
   * a anomalia está acima do esperado
   * a anomalia está abaixo do esperado
   * anomalia excede
   * é igual ou maior que
   * é igual ou menor que
   * alterações por

* “Anomalia excede” é uma nova condição que vai além dos limites existentes (estáticos). Aplica algoritmos de Detecção de anomalias que definem dinamicamente o disparo. Você pode definir um limite de 90%, 95%, 99%, 99,75% e 99,9%.
* As granularidades por hora são definidas em um limite de 99,75%, e as granularidades diárias em 99%.
* Observe que você também pode usar as métricas calculadas.

*... com esses filtros*

Arraste e solte os segmentos ou dimensões para adicionar filtros. Por exemplo, adicionar um segmento “Somente dispositivos móveis” significaria que a regra dispara somente para dispositivos móveis.

Filtros adicionais serão adicionados usando uma declaração AND.

**Adicionar uma regra**

Você pode adicionar regras AND ou OR, clicando no ícone de engrenagem.

## Visualização de alertas {#section_10D75BA7B77E4C5FAF58A719C082E070}

A visualização de alertas interativa mostra a frequência de disparo aproximada de um alerta com base na experiência passada.

Por exemplo, se você definir a granularidade de tempo para diário, a visualização pode informar se o alarme foi disparado para uma determinada métrica x vezes durante os últimos 30 ou 31 dias.

Se achar que muitos alertas podem ter sido disparados, você pode ajustar o limite no [Gerenciador de alertas](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
