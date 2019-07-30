---
description: Permite usar o segmento para atividades de marketing na Biblioteca de público-alvo, no Target e no Audience Manager.
seo-description: Permite usar o segmento para atividades de marketing na Biblioteca de público-alvo, no Target e no Audience Manager.
seo-title: Publicar segmentos na Experience Cloud
solution: Analytics
title: Publicar segmentos na Experience Cloud
topic: Segmentos
uuid: e 5 ce 20 c 0-ce 43-423 b-a 29 f-ba 66 e 9 e 24 d 27
translation-type: tm+mt
source-git-commit: 6298c00cf4c74a493b6ba6266763d693897d5299

---


# Publicar segmentos na Experience Cloud

>[!IMPORTANT]
>
>As melhorias de latência relacionadas à publicação de segmentos e à interface de usuário descrita nesta página ainda não são implementadas para todos os clientes. The current production environment is described [here](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Atualizações recentes otimizaram significativamente o fluxo de trabalho de publicação. Anteriormente, a publicação de um segmento utilizável demorava aproximadamente 48 horas.

Agora, o processamento pode levar até 8 horas, mas dependendo de outro tráfego e do tamanho do segmento, o processamento pode ser ainda mais rápido. No entanto, no momento, não temos uma maneira de informá-lo quando o segmento está disponível, portanto, você terá que verificar manualmente. Também aumentamos o número máximo de segmentos publicáveis para 75 (de 20). Você pode exibir segmentos publicados em Componentes &gt; Segmentos.


## Pré-requisitos

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). Caso contrário, não será possível publicá-lo na Experience Cloud.
* Make sure you are working in a report suite that is [mapped to your Experience Cloud organization](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
* Before you can publish segments, your Admin needs to assign the [!UICONTROL Segment Publishing] permission to a product profile in the [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html), and add you to the product profile.


## Considerações

* **Limites do Conjunto de relatórios**: Você pode publicar até 75 segmentos por conjunto de relatórios. Esse limite é aplicado. Se você já tiver 75 segmentos publicados, não será possível publicar nenhum segmento adicional até que você não publique segmentos suficientes para ficarem abaixo do limite de 75 segmentos.
* **Limites de associação**: Os públicos-alvo compartilhados com o [!DNL Experience Cloud] do Analytics não podem exceder 20 milhões de membros únicos.
* **Privacidade de dados**: Os públicos-alvo não são filtrados com base no estado de autenticação de um visitante. Se um visitante consegue navegar em seu site em estados de autenticação e de não autenticação, as ações que ocorrem quando um visitante não está autenticado podem fazer com que um visitante seja incluído em um público-alvo. Review [Adobe Experience Cloud privacy](https://www.adobe.com/privacy/experience-cloud.html) to understand the full privacy implications of audience sharing.
* For a discussion about the differences between segments in [!DNL Adobe Analytics] and [!DNL Audience Manager], go [here](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Linha do tempo de publicação de segmento

| O que há disponível | Quando estiver disponível | Onde está disponível |
|---|---|---|
| Metadados (título e definição do segmento) | Imediatamente após a publicação | [!DNL Audience Manager], [!UICONTROL Biblioteca de público-alvo da Experience Cloud], [!DNL Target] |
| Segmento utilizável com associação | ~ 8 horas após a publicação | Visitor Profile Viewer in [!DNL Audience Manager] |
| População de características e associação | Dentro de 24 horas | [!DNL Audience Manager] |

## Publish segments in [!UICONTROL Segment Builder]

1. Navigate to [!UICONTROL Analytics &gt; Workspace &gt; Components &gt; Segments] &gt; +
1. Create a segment in the [!UICONTROL Segment Builder].
1. Forneça um título e uma descrição para o segmento - caso contrário, não será possível salvá-lo.
1. Check [!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)].

![](assets/publish-ec.png)

| Elemento | Descrição |
|---|---|
| Publicar este segmento na Experience Cloud (para `<report suite>`) | Quando essa opção é ativada, o título e a definição do segmento (ou seja, o público-alvo de shell normalmente utilizado nas plataformas de anúncios) são compartilhados com a Experience Cloud instantaneamente, enquanto a associação de segmento é avaliada e compartilhada a cada 4 horas. <br> Quando o público-alvo é associado a uma atividade no [!DNL Target], [!DNL Analytics] por exemplo, começa a enviar IDs para visitantes que se qualificaram para a Experience Cloud e [!DNL Target] o público-alvo. Nesse momento, o nome do público-alvo e os dados correspondentes começam a ser exibidos na página Públicos-alvo da Experience Cloud. </br> |
| Janela de criação de público-alvo | O intervalo de tempo selecionado é usado para criar o público-alvo com base em calendários. Por exemplo, "Últimos 30 dias" (padrão) inclui visitantes que foram qualificados para o público-alvo nos últimos 30 dias da data de hoje (NÃO da data original quando o segmento foi criado). |
| Criar na biblioteca de público-alvo | Os segmentos criados e publicados podem ser disponibilizados sem latência na Biblioteca de público-alvo da Experience Cloud. Elas não dependem das atualizações do Analytics. Esses segmentos não contam com seu limite de 75 segmentos publicados. |
| x de 75 publicado | Mostra o número de segmentos publicados na Experience Cloud. Clique no link para ver uma lista de segmentos publicados e o conjunto de relatórios e o proprietário associados. |
| Salvar | Salva esse segmento. |

## Cancelar publicação ou excluir segmentos

Para excluir um segmento publicado na Experience Cloud, é necessário cancelá-lo primeiro. To unpublish a segment, just **unclick** the checkbox that you used to publish it.

>[!NOTE]
>
>**Não é possível** cancelar a publicação de um segmento que está em uso por qualquer uma das seguintes soluções da Adobe: [!DNL Analytics] (in [!DNL Audience Analytics]), [!DNL Campaign]( [!DNL Advertising Cloud] para [!DNL Core Service] &amp; [!DNL Audience Manager] clientes) e todos os outros parceiros externos (para [!DNL Audience Manager] clientes). You **can** unpublish a segment that is in use by [!DNL Target].

## View segment publishing status in the [!UICONTROL Segment Manager]

1. Navigate to [!UICONTROL Analytics &gt; Components &gt; Segments].
1. Notice the new [!UICONTROL Published] column. Sim/Não se refere à publicação do segmento na Experience Cloud ou não.

![](assets/publish-status.png)

## Retrieve the [!DNL Audience Manager] UUID

Há 2 maneiras de capturar o AAM UUID atualmente associado ao navegador:

* Adobe Experience Cloud Debugger
* Ferramenta nativa de desenvolvedor em navegadores (por exemplo, Ferramentas do desenvolvedor do Chrome)

As seguintes capturas de tela mostram como recuperar o UUID AAM em seu navegador e usá-lo no Visualizador do perfil do visitante do Audience Manager para validar a associação de características e segmentos.

**Método 1: Usar o Adobe Experieence cloud Debugger**

1. Download and install [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) in the Chrome Web Store.
1. Inicie o depurador ao carregar uma página.
1. Scroll to the Audience Manager section and find the AAM UUID set on the current browser page
(`50814298273775797762943354787774730612` in the example below)

![](assets/debugger.jpg)

**Método 2: Usar ferramentas do desenvolvedor do Chrome (ou outras ferramentas do desenvolvedor do navegador)**

1. Iniciar Ferramentas do desenvolvedor do Chrome antes de carregar uma página
1. Carregue a página e marque Aplicativos &gt; Cookies. The AAM UUID should be set in the 3rd-party
Demdex cookie ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) in the example below). The field demdex is the AAM UUID set
on the browser (`50814298273775797762943354787774730612` in the example below).

![Ferramentas de desenvolvedor do Google Chrome](assets/ggogle-uuid.png)

## Use Audience Manager [!UICONTROL Visitor Profile Viewer]

The AAM UUID on the browser will be used by default when [!UICONTROL Visitor Profile Viewer] is loaded. If verifying trait realizations for other users, input a UUID in the UUID field and click [!UICONTROL Refresh]. Refer to [Visitor Profile Viewer](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) for more information.

![](assets/aam-vpv.png)

## View the segment traits in [!DNL Audience Manager]

No AAM, a lista de visitantes com ecids para um determinado segmento é avaliada de maneira automatizada, já que o Analytics compartilha segmentos com a Experience Cloud.

1. In [!DNL Audience Manager], go to [!UICONTROL Audience Data &gt; Traits &gt; Analytics Traits]. Você verá uma pasta para cada conjunto de relatórios do Analytics mapeado para a organização da Experience Cloud. Essas pastas (para Características, Segmentos e Fontes de Dados) são criadas quando os Perfis e públicos-alvo/o serviço principal Pessoas são iniciados ou provisionados.
1. Select the folder for the report suite in which you previously created the segment you wanted to share with [!DNL Audience Manager]. Você verá o segmento/público-alvo que criou. When you share a segment, 2 things happen in [!DNL Audience Manager]:
* Uma característica é criada, primeiro sem dados nela. Mais adequado. 8 hours after the segment gets published in [!DNL Analytics], the list of ECIDs gets onboarded and shared with [!DNL Audience Manager] and other Experience Cloud solutions.

![](assets/aam-traits.png)

* Um segmento de uma característica é criado. Ele usa a fonte de dados associada ao conjunto de relatórios onde você publicou o segmento.

## View the segment in [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Um segmento criado no Analytics ou no Audience Manager pode ser usado em atividades no Target. Por exemplo, é possível criar atividades de campanha baseadas nas métricas de conversão do Analytics e nos segmentos de público-alvo criados no Analytics.
], click [!UICONTROL Audiences].
1. Na página [!UICONTROL Públicos-alvo], localize o público-alvo proveniente da [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.
