---
description: Explica melhorias no encaminhamento pelo lado do servidor que foram solicitadas pelo regulamento de conformidade de cookies da UE.
title: Conformidade com o RGPD/ePrivacy e o encaminhamento pelo lado do servidor
feature: Report Suite Settings
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 55%

---

# Conformidade com o RGPD/ePrivacy e o encaminhamento pelo lado do servidor

Esta seção explica as melhorias feitas ao encaminhamento pelo lado do servidor que foram solicitadas pelo [regulamento de conformidade de cookies da UE](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+e+tecnologias+semelhantes), que entrou em vigor em 30 de setembro de 2017.

O encaminhamento pelo lado do servidor é usado para compartilhar dados do Adobe Analytics com outras [!DNL Experience Cloud Solutions], como o Audience Manager, em tempo real. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados a outras soluções da Experience Cloud e, consequentemente, que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.

Anteriormente, o encaminhamento pelo lado do servidor não tinha uma maneira de delinear entre eventos/ocorrências de consentimento e pré-consentimento. A partir de 1º de novembro de 2018, você, como controlador de dados (cliente do Adobe Analytics), terá a opção de restringir os dados pré-consentimento do Adobe Analytics e impedir que sejam encaminhados para o Adobe Audience Manager. Uma nova variável de contexto de implementação permite sinalizar ocorrências onde o consentimento não foi recebido. A variável, quando definida, impede que essas ocorrências sejam enviadas para a Adobe Audience Manager até que o consentimento seja recebido.

Quando esta nova variável de contexto, `cm.ssf=1`, existir em uma ocorrência, ela é sinalizada e não é encaminhada pelo lado do servidor ao Adobe Audience Manager. Por outro lado, se essa sequência de caracteres não aparecer em uma ocorrência, a ocorrência será encaminhada para o Adobe Audience Manager.

O encaminhamento pelo lado do servidor é bidirecional, o que significa que quando ele é aplicado a uma ocorrência e essa ocorrência é encaminhada para o Adobe Audience Manager, o Audience Analytics recebe informações de segmento para essa ocorrência do Adobe Audience Manager e a envia de volta para o Analytics. Como resultado, qualquer ocorrência que não seja encaminhada do lado do servidor do Analytics para o Adobe Audience Manager não será enriquecida com a lista de IDs de segmento do Adobe Audience Manager. Dessa forma, haverá um subconjunto de tráfego/ocorrências que não obterá informações de ID de segmento do Adobe Audience Manager.

## Detalhes da implementação {#section_FFA8B66085BF469FAB5365C944FE38F7}

Dependendo do seu método de implementação, siga estas etapas.

| Método de implementação | Etapas |
|--- |--- |
| Tags na Adobe Experience Platform | Supondo que a extensão do Adobe Analytics esteja instalada, adicione a seguinte definição de variável de dados de contexto ao editor de código personalizado na configuração Ação de uma Regra: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Observação: configure a variável de dados de contexto e defina-a como 1 se um cliente não consentir com o marketing direcionado. Ajuste a variável `contextdata` como *0* para clientes que consentiram com marketing direcionado. |
| AppMeasurement | Adicione a definição da variável contextdata ao arquivo AppMeasurement.js: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Observação: defina a variável contextdata e ajuste-a para 1 se um cliente não consentir com marketing direcionado. Ajuste a variável contextdata para 0 para clientes que consentiram com marketing direcionado. |

## Criação de relatórios (opcional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Você pode usar o Adobe Analytics para relatar quanto do seu tráfego é baseado em consentimento e como resultado foi encaminhado pelo lado do servidor, versus quanto do seu tráfego não é baseado em consentimento e não foi encaminhado para o Adobe Audience Manager.

Para configurar esse tipo de relatório, mapeie a nova variável de contexto para uma variável personalizada de tráfego (prop) por meio de regras de processamento. Para fazer isso

1. Implemente a variável &quot;cm.ssf&quot; (conforme mostrado acima.)
1. [Habilite a prop.](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
1. Use regras de processamento para mapear a variável de contexto para a prop.

   1. Acesse **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** e, em seguida, selecione um conjunto de relatórios.
   1. Clique em **[!UICONTROL Editar conjunto de relatório]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de processamento]**.
   1. Clique em **[!UICONTROL Adicionar regra]**.
   1. Em **[!UICONTROL Sempre executar]**, substitua o valor da prop habilitada anteriormente pela variável de contexto &quot;cm.ssf(Context Data)&quot;.
   1. Clique em **[!UICONTROL Salvar]**.
