---
description: 'null'
seo-description: 'null'
seo-title: Conformidade com o RGPD e o encaminhamento pelo lado do servidor
title: Conformidade com o RGPD e o encaminhamento pelo lado do servidor
uuid: 1 b 90 c 567-3321-4 dbd-a 699-38 c 04 e 809 fa 4
translation-type: tm+mt
source-git-commit: 26c3cc9895c27d6abc452e0a4636771fb2415fb3

---


# Conformidade com o RGPD e o encaminhamento pelo lado do servidor

Esta seção explica as melhorias recentes feitas ao encaminhamento pelo lado do servidor que foram solicitadas pelo [regulamento de conformidade de cookies da UE](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm), que entrou em vigor em 30 de setembro de 2017.

Server-side forwarding is used to share data from Adobe Analytics to other [!DNL Experience Cloud Solutions], such as Audience Manager, in real time. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados a outras soluções da Experience Cloud e, consequentemente, que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.

Até recentemente, o encaminhamento pelo lado do servidor não tinha uma maneira de delinear entre eventos/ocorrências de consentimento e pré-consentimento. A partir de 1 de novembro de 2018, você, como o controlador de dados (cliente do Adobe Analytics) tem a opção de restringir o pré-consentimento a dados do Adobe Analytics, e evitar que sejam encaminhados para o AAM. Uma nova variável de contexto de implementação permite sinalizar ocorrências onde o consentimento não foi recebido. A variável, quando definida, evita que tais ocorrências sejam enviadas para o AAM até que o consentimento seja recebido.

When this new context variable, `cm.ssf=1`, exists on a hit, this hit gets flagged and does not get server-side-forwarded to AAM. Caso contrário, se essa sequência de caracteres não for exibida em uma ocorrência, a ocorrência é encaminhada ao AAM.

O Encaminhamento pelo lado do servidor é bidirecional, ou seja, ao ser aplicado a uma ocorrência e esta ser encaminhada ao AAM, o Audience Analytics recebe informações de segmento referentes à ocorrência pelo AAM e as envia de volta para o Analytics. Como resultado, ocorrências que não são encaminhadas pelo lado do servidor do Analytics para o AAM não serão implementadas com a lista de IDs de segmento do AAM. Portanto, haverá um subconjunto de tráfego/ocorrências que não receberão informações de ID de segmento do AAM.

## Detalhes da implementação {#section_FFA8B66085BF469FAB5365C944FE38F7}

Dependendo do seu método de implementação, siga estas etapas.

| Método de implementação | Etapas |
|--- |--- |
| Lançamento da Adobe Experience Platform | Assuming you have the Adobe Analytics extension installed, add the following context data variable definition to the custom code editor within the Action configuration of a Rule: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the `contextdata` variable to *0* for customers who consented to targeted marketing. |
| DTM | Adicione a definição da variável contextdata ao editor de Código de página personalizado: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Observação: defina a variável contextdata e ajuste-a para 1 se um cliente não consentir com marketing direcionado. Ajuste a variável contextdata para 0 para clientes que consentiram com marketing direcionado. |
| AppMeasurement | Adicione a definição da variável contextdata ao arquivo AppMeasurement.js:  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Observação: defina a variável contextdata e ajuste-a para 1 se um cliente não consentir com marketing direcionado. Ajuste a variável contextdata para 0 para clientes que consentiram com marketing direcionado. |

## Criação de relatórios (opcional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Você pode usar o Adobe Analytics para criar relatórios sobre qual porção de seu tráfego é baseada em consentimento e como resultado foi encaminhada pelo lado do servidor, versus qual porção não é baseada em consentimento e não foi encaminhada para o AAM.

Para configurar esse tipo de relatório, mapeie a nova variável de contexto para uma variável personalizada de tráfego (prop) por meio de regras de processamento. Para fazer isso

1. Implemente a variável “cm.ssf” (conforme mostrado acima.)
1. [Habilite a prop.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Use regras de processamento para mapear a variável de contexto para a prop.

   1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** , then select a report suite.
   1. Click  **[!UICONTROL Edit Report Suite]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Processing Rules]** .
   1. Clique em **[!UICONTROL Adicionar regra.]**
   1. Under **[!UICONTROL Always Execute]**, overwrite the value of the prop you had enabled with the context variable “cm.ssf(Context Data)”.
   1. Clique em **[!UICONTROL Salvar]**.

