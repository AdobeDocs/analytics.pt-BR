---
description: Lets you use the segment for marketing activity in the Audience Library, Target, and Audience Manager.
seo-description: Lets you use the segment for marketing activity in the Audience Library, Target, and Audience Manager.
seo-title: Publicar segmentos na Experience Cloud
solution: Analytics
title: Publicar segmentos na Experience Cloud
topic: Segmentos
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: 831ae375a90f021feddc6817a2602464be0d8414

---


# Publicar segmentos na Experience Cloud

>[!IMPORTANT]
>
>The latency improvements regarding segment publishing and the user interface that are described on this page are not rolled out to all customers yet. The current production environment is described here.[](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html)

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Recent updates have significantly optimized the publishing workflow. Previously, publishing a usable segment took approximately 48 hours.

Now, processing can take up to 8 hours, but depending on other traffic and on the segment size, processing may be even faster. (However, we currently do not have a way to inform you when the segment is available, so you will have to check manually.) We have also increased the maximum number of publishable segments to 75 (from 20). You can view published segments in Components &gt; Segments.


## Pré-requisitos

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). Caso contrário, não será possível publicá-la na Experience Cloud.
* Verifique se você está trabalhando em um conjunto de relatórios [mapeado para a sua organização](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)da Experience Cloud.
* Ensure that your organization is using Experience Cloud IDs.
* Antes de poder publicar segmentos, seu Administrador precisa atribuir a permissão Publicação de [!UICONTROL segmentos] a um perfil de produto no Console [de](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)administração e adicioná-lo ao perfil de produto.


## Considerações

* **Limites** do conjunto de relatórios: Você pode publicar até 75 segmentos por conjunto de relatórios. Este limite é aplicado. Se você já tiver 75 segmentos publicados, não poderá publicar quaisquer segmentos adicionais até cancelar a publicação de segmentos suficientes para ficar abaixo do limite de 75 segmentos.
* **Limites** de adesão: Os públicos-alvo compartilhados com o Analytics [!DNL Experience Cloud] não podem exceder 20 milhões de membros únicos.
* **Privacidade** de dados: Os públicos-alvo não são filtrados com base no estado de autenticação de um visitante. Se um visitante consegue navegar em seu site em estados de autenticação e de não autenticação, as ações que ocorrem quando um visitante não está autenticado podem fazer com que um visitante seja incluído em um público-alvo. Revise a privacidade [da](https://www.adobe.com/privacy/experience-cloud.html) Adobe Experience Cloud para entender as implicações completas de privacidade do compartilhamento de público-alvo.
* For a discussion about the differences between segments in  and , go here.**[!DNL Adobe Analytics][!DNL Audience Manager]**[](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)

## Linha do tempo de publicação do segmento

| O que está disponível | Quando estiver disponível | Onde está disponível |
|---|---|---|
| Meta data (segment title and definition) | Imediatamente após a publicação | [!DNL Audience Manager], Biblioteca [!UICONTROL de público-alvo da]Experience Cloud, [!DNL Target] |
| Segmento utilizável com associação | ~ 8 hours after publishing | Visualizador de perfil do visitante em [!DNL Audience Manager] |
| Características e população | Dentro de 24 horas | [!DNL Audience Manager] |

## Publicar segmentos no Construtor [!UICONTROL de segmentos]

1. Navegue até **[!UICONTROL Analytics &gt; Área de trabalho &gt; Componentes &gt; Segmentos]&gt; +**
1. Crie um segmento no Construtor [!UICONTROL de segmentos].
1. Forneça um título e uma descrição para o segmento - caso contrário, você não poderá salvá-lo.
1. Check **[!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)]**.

![](assets/publish-ec.png)

>[!IMPORTANT]
>
>Certifique-se de usar "Visitantes com Experience Cloud ID" ao visualizar visualizações de segmento no Analytics em vez da visualização total do segmento "visitantes únicos" ao comparar os números do Adobe Analytics com os números do Audience Manager.

| Elemento | Descrição |
|---|---|
| **[!UICONTROL Publicar este segmento na Experience Cloud (para *<report suite>*)]** | Quando essa opção está ativada, o título e a definição do segmento (isto é, o público-alvo da shell, como muitas vezes é usado em plataformas de anúncios) são compartilhados com a Experience Cloud instantaneamente, enquanto a associação do segmento é avaliada e compartilhada a cada quatro horas. <br> Quando esse público-alvo é associado a uma atividade em, por exemplo, [!DNL Target]o [!DNL Analytics] começa a enviar IDs para visitantes que se qualificam para essa Experience Cloud e [!DNL Target] público-alvo. Nesse momento, o nome do público-alvo e os dados correspondentes começam a ser exibidos na página Públicos-alvo da Experience Cloud. </br> |
| **[!UICONTROL Janela de criação de público-alvo]** | O período selecionado é usado para criar o público-alvo em uma base de calendário rotativo. Por exemplo, "Últimos 30 dias" (padrão) inclui visitantes que se qualificaram para o público nos últimos 30 dias a partir da data de hoje (NÃO a partir da data original quando o segmento foi criado). |
| **[!UICONTROL Criar na biblioteca de público-alvo]** | Os segmentos criados e publicados podem ser disponibilizados sem latência na Biblioteca de público-alvo da Experience Cloud. Eles não dependem das atualizações do Analytics. Esses segmentos não contam com o limite de 75 segmentos publicados. |
| **[!UICONTROL x de 75 Publicado]** | Mostra o número de segmentos publicados na Experience Cloud. Click the link to see a list of published segments and their associated report suite and owner. |
| **[!UICONTROL Save]** | Salva este segmento. |

## Unpublish or delete segments

Para excluir um segmento publicado na Experience Cloud, é necessário cancelar a publicação primeiro. Para cancelar a publicação de um segmento, basta **desmarcar** a caixa de seleção usada para publicá-lo.

>[!NOTE]
>
>**Não é possível** cancelar a publicação de um segmento que está em uso por qualquer uma das seguintes soluções da Adobe: [!DNL Analytics] (no [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (para cliente do [!DNL Core Service] e [!DNL Audience Manager]) e todos os outros parceiros externos (para clientes do [!DNL Audience Manager]). Você **pode** cancelar a publicação de um segmento em uso pelo [!DNL Target].

## View segment publishing status in the Segment Manager

1. Navigate to Analytics &gt; Components &gt; Segments.
1. Notice the new Published column.  Yes/No refers to whether the segment has been published to the Experience Cloud or not.

![](assets/publish-status.png)

## Recuperar o [!DNL Audience Manager] UUID

There are two ways to capture the AAM UUID currently associated with the browser:

* Adobe Experience Cloud Debugger
* Native developer tool in browsers (e.g., Chrome Developer Tools)

The following screenshots show you how to retrieve the AAM UUID on your browser and use it in Audience Manager Visitor Profile Viewer to validate trait &amp; segment membership.

**Method 1: Use Adobe Experience CLoud Debugger**

1. Baixe e instale o [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) na Chrome Web Store.
1. Launch the debugger when loading a page.
1. Role até a seção Audience Manager e localize o UUID do AAM definido na página atual do navegador (`50814298273775797762943354787774730612` no exemplo abaixo)

![](assets/debugger.jpg)

**Método 2: Usar as ferramentas do desenvolvedor do Chrome (ou outras ferramentas do desenvolvedor do navegador)**

1. Inicie as ferramentas do desenvolvedor do Chrome antes de carregar uma página
1. Carregue a página e marque Aplicativos &gt; Cookies. A UUID do AAM deve ser definida no cookie Demdex de terceiros ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) no exemplo abaixo). O demdex de campo é a configuração UUID do AAM no navegador (`50814298273775797762943354787774730612` no exemplo abaixo).

![Ferramentas de desenvolvedor do Google Chrome](assets/ggogle-uuid.png)

## Usar o Visualizador de perfil de [!UICONTROL visitante do Audience Manager]

The AAM UUID on the browser will be used by default when Visitor Profile Viewer is loaded.  If verifying trait realizations for other users, input a UUID in the UUID field and click Refresh.  Consulte o Visualizador [de perfil do](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) visitante para obter mais informações.

![](assets/aam-vpv.png)

## Exibir as características do segmento em [!DNL Audience Manager]

No AAM, a lista de visitantes com ECIDs para um determinado segmento é avaliada de forma contínua à medida que o Analytics compartilha segmentos com a Experience Cloud.

1. In , go to Audience Data &gt; Traits &gt; Analytics Traits. [!DNL Audience Manager] Você verá uma pasta para cada conjunto de relatórios do Analytics mapeada para a organização da Experience Cloud. Essas pastas (para Características, Segmentos e Fontes de Dados) são criadas quando o serviço principal Perfis e Públicos-alvo/Pessoas é iniciado ou provisionado.
1. Selecione a pasta do conjunto de relatórios na qual você criou o segmento com o qual deseja compartilhar [!DNL Audience Manager]. Você verá o segmento/público-alvo criado. When you share a segment, 2 things happen in :[!DNL Audience Manager]
* Uma característica é criada, primeiro sem dados nela. Aprox. Oito horas após o segmento ser publicado no, [!DNL Analytics]a lista de ECIDs é atualizada e compartilhada com [!DNL Audience Manager] e outras soluções da Experience Cloud.

![](assets/aam-traits.png)

* Um segmento com um único traço é criado. Ele usa a fonte de dados associada ao conjunto de relatórios no qual você publicou o segmento.

## Exibir o segmento em [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Um segmento criado no Analytics ou no Audience Manager pode ser usado em atividades no Target. Por exemplo, é possível criar atividades de campanha baseadas nas métricas de conversão do Analytics e nos segmentos de público-alvo criados no Analytics.
], clique em [!UICONTROL Públicos].
1. Na página [!UICONTROL Públicos-alvo], localize o público-alvo proveniente da [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.

