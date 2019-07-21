---
description: 'null'
seo-description: 'null'
seo-title: Criador de alertas
title: Criador de alertas
uuid: ebc 2 d 457-4 abd -4 b 1 a -9357-489 b 5 aeb 3 f 64
translation-type: tm+mt
source-git-commit: 4b47e33d964c040cf94dc1c4ad97e43958d9d94a

---


# Criador de alertas

>[!IMPORTANT]
>
>Os Alertas inteligentes estão disponíveis somente para clientes do Adobe Analytics Prime e Adobe Analytics Ultimate.

## Acessar o Criador de alertas

Acesse o Criador de alertas de uma das seguintes formas:

* Usando o seguinte atalho na Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* By going to **[!UICONTROL Workspace]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL New Alert]**.
* Selecionando um ou mais itens de linha da tabela de forma livre, clicando com o botão direito do mouse e selecionando **[!UICONTROL Criar alerta a partir da seleção]**.
* From within a Reports &amp; Analytics report, by going to **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.

## Criar alertas

A interface do Criador de alertas é semelhante àquela que cria segmentos ou métricas calculadas no Analytics:

![](assets/alert_builder.png)

<!--Meike, I edited this table for validation -->

**Nome do Alerta**

Especifique um nome para o alerta. O nome do alerta pode conter o nome do relatório ou o limite da métrica.

**Granularidade de tempo**

Especifique quando você deseja verificar a métrica: por hora, dia, semana ou mês.

>[!NOTE]
>
>Para conjuntos de relatórios com um calendário personalizado, não oferecemos suporte à granularidade mensal no Criador de alertas.

**Destinatários**

Especifique para onde o alerta pode ser enviado. Um alerta pode ser enviado a um usuário do Analytics, a um grupo do Analytics, a um endereço de email bruto ou a um número de telefone.

>[!IMPORTANT]
>
>The phone number must be preceded by a "+" and a [country code](https://countrycode.org/).

O email que um usuário receberia depois que um alerta é acionado é semelhante a:

![](assets/alerts-email.PNG)

**Data de validade**

Defina a data de expiração do alerta.

**Enviar um Alerta quando...**

*... qualquer uma dessas métricas forem acionadas*

* Arraste e solte métricas na tela que adicionará disparadores.

   An **"incompatible components”** message will appear if not all the components (metrics/dimensions/segments) in the alert are compatible with the currently selected report suite.
* Determine o limite que a métrica deve exceder antes de definir um alarme. Você pode definir este valor para um limite e, em seguida, para uma das condições a seguir:

   * a anomalia existe
   * a anomalia está acima do esperado
   * a anomalia está abaixo do esperado
   * é igual ou maior que
   * é igual ou menor que
   * alterações por
   * Você pode definir um limite de 90%, 95%, 99%, 99,75% e 99,9%.
   Observe que você também pode usar as métricas calculadas.

*... com esses filtros*

* Arraste e solte os segmentos ou dimensões para adicionar filtros. Por exemplo, adicionar um segmento “Somente dispositivos móveis” significaria que a regra dispara somente para dispositivos móveis.
* Filtros adicionais serão adicionados usando uma declaração AND.

**Adicionar uma regra**

Você pode adicionar regras AND ou OR, clicando no ícone de engrenagem.

## Preview Alerts {#section_10D75BA7B77E4C5FAF58A719C082E070}

A visualização de alertas interativa mostra a frequência de disparo aproximada de um alerta com base na experiência passada.

Por exemplo, se você definir a granularidade de tempo para diário, a visualização pode informar se o alarme foi disparado para uma determinada métrica x vezes durante os últimos 30 ou 31 dias.

Se achar que muitos alertas podem ter sido disparados, você pode ajustar o limite no [Gerenciador de alertas](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
