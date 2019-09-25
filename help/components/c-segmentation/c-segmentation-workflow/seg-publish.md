---
description: Permite usar o segmento para atividades de marketing na Biblioteca de público-alvo, no Target e no Audience Manager.
seo-description: Permite usar o segmento para atividades de marketing na Biblioteca de público-alvo, no Target e no Audience Manager.
seo-title: Publicar segmentos na Experience Cloud
solution: Analytics
title: Publicar segmentos na Experience Cloud
topic: Segmentos
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: bac0b1ae330753cfc537817e8da1ea70fbaaf0d5

---


# Publicar segmentos na Experience Cloud

>[!IMPORTANT]
>
>As melhorias de latência relacionadas à publicação de segmentos e à interface do usuário descritas nesta página ainda não são distribuídas para todos os clientes. O ambiente de produção atual é descrito [aqui](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Atualizações recentes otimizaram significativamente o fluxo de trabalho de publicação. Previously, publishing a usable segment took approximately 48 hours.

Agora, o processamento pode levar até 8 horas, mas dependendo de outro tráfego e do tamanho do segmento, o processamento pode ser ainda mais rápido. No entanto, não temos uma maneira de informá-lo quando o segmento está disponível, portanto, você terá que verificar manualmente. We have also increased the maximum number of publishable segments to 75 (from 20). You can view published segments in Components &gt; Segments.


## Pré-requisitos

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). Otherwise you cannot publish it to the Experience Cloud.
* Make sure you are working in a report suite that is mapped to your Experience Cloud organization.[](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)
* Ensure that your organization is using Experience Cloud IDs.
* Before you can publish segments, your Admin needs to assign the Segment Publishing permission to a product profile in the Admin Console, and add you to the product profile.[](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)


## Considerações

* **Report Suite limits**: You can publish up to 75 segments per report suite. This limit is enforced. If you already have 75 segments published, you cannot publish any additional segments until you un-publish enough segments to get below the 75-segment threshold.
* **Limites** de adesão: Os públicos-alvo compartilhados com o Analytics [!DNL Experience Cloud] não podem exceder 20 milhões de membros únicos.
* **Privacidade** de dados: Os públicos-alvo não são filtrados com base no estado de autenticação de um visitante. Se um visitante consegue navegar em seu site em estados de autenticação e de não autenticação, as ações que ocorrem quando um visitante não está autenticado podem fazer com que um visitante seja incluído em um público-alvo. Review Adobe Experience Cloud privacy to understand the full privacy implications of audience sharing.[](https://www.adobe.com/privacy/experience-cloud.html)
* For a discussion about the **differences between segments in[!DNL Adobe Analytics]and[!DNL Audience Manager]**, go [here](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Segment publishing timeline

| What's available | Quando estiver disponível | Where it's available |
|---|---|---|
| Metadados (título e definição do segmento) | Imediatamente após a publicação | [!DNL Audience Manager], Biblioteca [!UICONTROL de público-alvo da]Experience Cloud, [!DNL Target] |
| Segmento utilizável com associação | ~ 8 horas após a publicação | Visualizador de perfil do visitante em [!DNL Audience Manager] |
| Características e população | Dentro de 24 horas | [!DNL Audience Manager] |

## Publicar segmentos no Construtor [!UICONTROL de segmentos]

1. Navegue até **[!UICONTROL Analytics &gt; Área de trabalho &gt; Componentes &gt; Segmentos]&gt; +**
1. Crie um segmento no Construtor [!UICONTROL de segmentos].
1. Forneça um título e uma descrição para o segmento - caso contrário, você não poderá salvá-lo.
1. Check **[!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)]**.
1. Certifique-se de usar "Visitantes com Experience Cloud ID" ao visualizar visualizações de segmento no Analytics em vez da visualização total do segmento "visitantes únicos" ao comparar os números do Adobe Analytics com os números do Audience Manager.

![](assets/publish-ec.png)

| Elemento | Descrição |
|---|---|
| **[!UICONTROL Publicar este segmento na Experience Cloud (para *<report suite>*)]** | Quando essa opção está ativada, o título e a definição do segmento (isto é, o público-alvo da shell, como muitas vezes é usado em plataformas de anúncios) são compartilhados com a Experience Cloud instantaneamente, enquanto a associação do segmento é avaliada e compartilhada a cada quatro horas. <br> Quando esse público-alvo é associado a uma atividade em, por exemplo, [!DNL Target]o [!DNL Analytics] começa a enviar IDs para visitantes que se qualificam para essa Experience Cloud e [!DNL Target] público-alvo. Nesse momento, o nome do público-alvo e os dados correspondentes começam a ser exibidos na página Públicos-alvo da Experience Cloud. </br> |
| **[!UICONTROL Janela de criação de público-alvo]** | O período selecionado é usado para criar o público-alvo em uma base de calendário rotativo. Por exemplo, "Últimos 30 dias" (padrão) inclui visitantes que se qualificaram para o público nos últimos 30 dias a partir da data de hoje (NÃO a partir da data original quando o segmento foi criado). |
| **[!UICONTROL Criar na biblioteca de público-alvo]** | Os segmentos criados e publicados podem ser disponibilizados sem latência na Biblioteca de público-alvo da Experience Cloud. Eles não dependem das atualizações do Analytics. Esses segmentos não contam com o limite de 75 segmentos publicados. |
| **[!UICONTROL x de 75 Publicado]** | Mostra o número de segmentos publicados na Experience Cloud. Clique no link para ver uma lista de segmentos publicados e seu conjunto de relatórios e proprietário associados. |
| **[!UICONTROL Salvar]** | Salva este segmento. |

## Cancelar a publicação ou excluir segmentos

Para excluir um segmento publicado na Experience Cloud, é necessário cancelar a publicação primeiro. Para cancelar a publicação de um segmento, basta **desmarcar** a caixa de seleção usada para publicá-lo.

>[!NOTE]
>
>**Não é possível** cancelar a publicação de um segmento que está em uso por qualquer uma das seguintes soluções da Adobe: [!DNL Analytics] (no [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (para cliente do [!DNL Core Service] e [!DNL Audience Manager]) e todos os outros parceiros externos (para clientes do [!DNL Audience Manager]). Você **pode** cancelar a publicação de um segmento em uso pelo [!DNL Target].

## Exibir o status de publicação do segmento no Gerenciador [!UICONTROL de segmentos]

1. Navegue até [!UICONTROL Analytics &gt; Componentes &gt; Segmentos].
1. Observe a nova coluna [!UICONTROL Publicado] . Sim/Não se refere se o segmento foi publicado na Experience Cloud ou não.

![](assets/publish-status.png)

## Recuperar o [!DNL Audience Manager] UUID

Há duas maneiras de capturar a UUID do AAM atualmente associada ao navegador:

* Adobe Experience Cloud Debugger
* Native developer tool in browsers (e.g., Chrome Developer Tools)

The following screenshots show you how to retrieve the AAM UUID on your browser and use it in Audience Manager Visitor Profile Viewer to validate trait &amp; segment membership.

**Method 1: Use Adobe Experience CLoud Debugger**

1. Download and install Adobe Experience Cloud Debugger in the Chrome Web Store.[](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html)
1. Launch the debugger when loading a page.
1. Scroll to the Audience Manager section and find the AAM UUID set on the current browser page
( in the example below)`50814298273775797762943354787774730612`

![](assets/debugger.jpg)

**Method 2: Use Chrome Developer Tools (or other browser developer tools)**

1. Launch Chrome Developer Tools before loading a page
1. Load the page and check Applications &gt; Cookies. The AAM UUID should be set in the 3rd-party
Demdex cookie (adobe.demdex.net in the example below). [](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) The field demdex is the AAM UUID set
on the browser ( in the example below).`50814298273775797762943354787774730612`

![Ferramentas de desenvolvedor do Google Chrome](assets/ggogle-uuid.png)

## Use Audience Manager Visitor Profile Viewer

The AAM UUID on the browser will be used by default when Visitor Profile Viewer is loaded.  If verifying trait realizations for other users, input a UUID in the UUID field and click Refresh.  Refer to Visitor Profile Viewer for more information.[](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html)

![](assets/aam-vpv.png)

## Exibir as características do segmento em [!DNL Audience Manager]

No AAM, a lista de visitantes com ECIDs para um determinado segmento é avaliada de forma contínua à medida que o Analytics compartilha segmentos com a Experience Cloud.

1. Em [!DNL Audience Manager], vá para Dados de [!UICONTROL público-alvo &gt; Características &gt; Características]do Analytics. Você verá uma pasta para cada conjunto de relatórios do Analytics mapeada para a organização da Experience Cloud. Essas pastas (para Características, Segmentos e Fontes de Dados) são criadas quando o serviço principal Perfis e Públicos-alvo/Pessoas é iniciado ou provisionado.
1. Selecione a pasta do conjunto de relatórios na qual você criou o segmento com o qual deseja compartilhar [!DNL Audience Manager]. Você verá o segmento/público-alvo criado. Quando você compartilha um segmento, duas coisas acontecem em [!DNL Audience Manager]:
* Uma característica é criada, primeiro sem dados nela. Aprox. Oito horas após o segmento ser publicado no, [!DNL Analytics]a lista de ECIDs é atualizada e compartilhada com [!DNL Audience Manager] e outras soluções da Experience Cloud.

![](assets/aam-traits.png)

* Um segmento com um único traço é criado. Ele usa a fonte de dados associada ao conjunto de relatórios no qual você publicou o segmento.

## Exibir o segmento em [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Um segmento criado no Analytics ou no Audience Manager pode ser usado em atividades no Target. Por exemplo, é possível criar atividades de campanha baseadas nas métricas de conversão do Analytics e nos segmentos de público-alvo criados no Analytics.
], clique em [!UICONTROL Públicos].
1. Na página [!UICONTROL Públicos-alvo], localize o público-alvo proveniente da [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.

