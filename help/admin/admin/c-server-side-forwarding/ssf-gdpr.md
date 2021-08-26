---
description: Explica melhorias no encaminhamento pelo lado do servidor que foram solicitadas pelo regulamento de conformidade de cookies da UE.
title: Conformidade com o GDPR/ePrivacy e o encaminhamento pelo lado do servidor
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 79%

---

# Conformidade com o GDPR/ePrivacy e o encaminhamento pelo lado do servidor

Esta seção explica as melhorias no encaminhamento pelo lado do servidor que foram solicitadas pelo [EU cookie Compliance regulation](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+e+similares+tecnologias), que entrou em vigor em 30 de setembro de 2017.

O encaminhamento pelo lado do servidor é usado para compartilhar dados do Adobe Analytics com outras [!DNL Experience Cloud Solutions], como o Audience Manager, em tempo real. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados a outras soluções da Experience Cloud e, consequentemente, que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.

Anteriormente, o encaminhamento pelo lado do servidor não tinha uma maneira de delinear entre eventos/ocorrências de consentimento e pré-consentimento. A partir de 1 de novembro de 2018, você, como o controlador de dados (cliente do Adobe Analytics) tem a opção de restringir o pré-consentimento a dados do Adobe Analytics, e evitar que sejam encaminhados para o AAM. Uma nova variável de contexto de implementação permite sinalizar ocorrências onde o consentimento não foi recebido. A variável, quando definida, evita que tais ocorrências sejam enviadas para o AAM até que o consentimento seja recebido.

Quando esta nova variável de contexto, `cm.ssf=1`, existir em uma ocorrência, tal ocorrência é sinalizada e não é encaminhada pelo lado do servidor ao AAM. Caso contrário, se essa sequência de caracteres não for exibida em uma ocorrência, a ocorrência é encaminhada ao AAM.

O Encaminhamento pelo lado do servidor é bidirecional, ou seja, ao ser aplicado a uma ocorrência e esta ser encaminhada ao AAM, o Audience Analytics recebe informações de segmento referentes à ocorrência pelo AAM e as envia de volta para o Analytics. Como resultado, ocorrências que não são encaminhadas pelo lado do servidor do Analytics para o AAM não serão implementadas com a lista de IDs de segmento do AAM. Portanto, haverá um subconjunto de tráfego/ocorrências que não receberão informações de ID de segmento do AAM.

## Detalhes da implementação {#section_FFA8B66085BF469FAB5365C944FE38F7}

Dependendo do seu método de implementação, siga estas etapas.

| Método de implementação | Etapas |
|--- |--- |
| Tags no Adobe Experience Platform | Supondo que você tenha a extensão Adobe Analytics instalada, adicione a seguinte definição de variável de dados de contexto ao editor de código personalizado na configuração Ação de uma Regra: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Observação:  Defina a variável contextdata e ajuste-a para 1 se um cliente não consentir com marketing direcionado. Ajuste a variável `contextdata` como *0* para clientes que consentiram com marketing direcionado. |
| AppMeasurement | Adicione a definição da variável contextdata ao arquivo AppMeasurement.js:  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/> Observação: defina a variável contextdata e ajuste-a para 1 se um cliente não consentir com marketing direcionado. Ajuste a variável contextdata para 0 para clientes que consentiram com marketing direcionado. |

## Criação de relatórios (opcional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Use o Adobe Analytics para criar relatórios sobre qual porção de seu tráfego é baseada em consentimento e como resultado foi encaminhada pelo lado do servidor, versus qual porção não é baseada em consentimento e não foi encaminhada para o AAM.

Para configurar esse tipo de relatório, mapeie a nova variável de contexto para uma variável personalizada de tráfego (prop) por meio de regras de processamento. Para fazer isso

1. Implemente a variável &quot;cm.ssf&quot; (conforme mostrado acima.)
1. [Habilite a prop.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Use regras de processamento para mapear a variável de contexto para a prop.

   1. Acesse **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** e, em seguida, selecione um conjunto de relatórios.
   1. Clique em **[!UICONTROL Editar conjunto de relatório]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de processamento]**.
   1. Clique em **[!UICONTROL Adicionar regra]**.
   1. Em **[!UICONTROL Sempre executar]**, substitua o valor da prop habilitada anteriormente pela variável de contexto &quot;cm.ssf(Context Data)&quot;.
   1. Clique em **[!UICONTROL Salvar]**.
