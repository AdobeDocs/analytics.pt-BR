---
description: Permite usar o segmento em atividades de marketing na biblioteca de público-alvo, no Target e no Audience Manager.
title: Publicar segmentos na Experience Cloud
feature: Segmentation
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
exl-id: 0215f896-d3f8-42cc-ac8d-8a94b009927b
source-git-commit: 38fb7ec39495b2b8cde4955bd1b3c1d3487632c3
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 99%

---

# Publicar segmentos na Experience Cloud

A publicação de um segmento do Adobe Analytics na Experience Cloud permite que você use o segmento para atividade de marketing no [!DNL Audience Manager] e em outros canais de ativação, incluindo o [!DNL Advertising Cloud], [!DNL Target] e [!DNL Campaign] da Adobe. Atualizações recentes otimizaram significativamente o fluxo de trabalho de publicação. Agora você pode publicar segmentos do Analytics na Experience Cloud em menos de 8 horas. Use esses segmentos para ativar públicos-alvo no Audience Manager para todos os destinos downstream.

Também aumentamos o número máximo de segmentos do Adobe Analytics publicáveis para 75 (de 20). É possível visualizar segmentos publicados em [!UICONTROL Analytics > Componentes > Segmentos].

Assista a este vídeo para obter mais detalhes:

>[!VIDEO](https://video.tv.adobe.com/v/32842/?quality=12)

>[!NOTE]
>
>O Adobe Campaign (Classic e Standard) se comporta de forma diferente, pois incorre em uma latência adicional de 24 horas acima da latência de 8 horas.

## Pré-requisitos

* Verifique se o conjunto de relatórios em que você está salvando este segmento está [habilitado para a Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-publish-audience-segment.html?lang=pt-BR). Caso contrário, não será possível publicar na Experience Cloud.
* Verifique se sua organização está usando Experience Cloud IDs.
* Antes de publicar segmentos, o Administrador precisa atribuir a permissão [!UICONTROL Publicação de segmentos] a um perfil de produto no [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR) e adicionar você ao perfil de produto.

## Considerações

* **Limites do conjunto de relatórios**: você pode publicar até 75 segmentos por conjunto de relatórios. Este limite é aplicado. Se você já tiver 75 segmentos publicados, não poderá publicar segmentos adicionais até cancelar a publicação de segmentos suficientes para ficar abaixo do limite de 75 segmentos.
* **Limites de associação**: públicos-alvo compartilhados com a [!DNL Experience Cloud] a partir do Adobe Analytics não podem exceder 20 milhões de membros únicos.
* **Privacidade dos dados**: os públicos-alvo não são filtrados com base no estado de autenticação de um visitante. Se um visitante consegue navegar em seu site em estados de autenticação e de não autenticação, as ações que ocorrem quando um visitante não está autenticado podem fazer com que um visitante seja incluído em um público-alvo. Revise a [privacidade da Adobe Experience Cloud](https://www.adobe.com/br/privacy/experience-cloud.html) para entender todas as implicações de privacidade do compartilhamento de público-alvo.
* Para uma discussão sobre as **diferenças entre segmentos em [!DNL Adobe Analytics] e [!DNL Audience Manager]**, acesse [aqui](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=pt-BR).

## Linha do tempo de publicação do segmento

| O que está disponível | Quando está disponível | Onde está disponível |
|---|---|---|
| Metadados (título e definição do segmento) | Imediatamente após a publicação | [!DNL Audience Manager], [!UICONTROL Biblioteca de público-alvo da Experience Cloud], [!DNL Target] |
| Segmento utilizável com associação | ~ 8 horas após a publicação | Visualizador de perfil do visitante em [!DNL Audience Manager] |
| Características e população de associação | Em 24-48 horas | [!DNL Audience Manager] |

>[!NOTE]
>Uma vez por semana, todos os dados serão sincronizados completamente para levar em conta qualquer delta ou discrepância não capturada na semana anterior.

## Publicar segmentos no [!UICONTROL Construtor de segmentos]

1. Navegue até **[!UICONTROL Analytics > Workspace > Componentes > Segmentos] > +**
1. Crie um segmento no [!UICONTROL Construtor de segmentos].
1. Forneça um título e uma descrição para o segmento - caso contrário, você não poderá salvá-lo.
1. Marque **[!UICONTROL Publicar este segmento na Experience Cloud (para *conjunto de relatórios*)]**.

![](assets/publish-ec.png)

>[!IMPORTANT]
>Use &quot;Visitantes com Experience Cloud ID&quot; ao consultar as visualizações de segmentos no Analytics, em vez da visualização do segmento do total de &quot;visitantes únicos&quot;, ao comparar os números do Adobe Analytics com os números do Audience Manager:
>
>![](assets/seg-vis-ecid.png)

| Elemento | Descrição |
|---|---|
| **[!UICONTROL Publicar este segmento na Experience Cloud (para *`<report suite>`*)]** | Quando essa opção está ativada, o título e a definição do segmento (ou seja, o público-alvo da shell, como muitas vezes é usado em plataformas de anúncios) são compartilhados com a Experience Cloud instantaneamente, enquanto a associação do segmento é avaliada e compartilhada a cada quatro horas. <br> Quando esse público-alvo é associado a uma atividade no [!DNL Target], por exemplo, o [!DNL Analytics] começa a enviar IDs para os visitantes que se qualificaram para esse público-alvo da Experience Cloud e do [!DNL Target]. Nesse momento, o nome do público-alvo e os dados correspondentes começam a ser exibidos na página Públicos-alvo da Experience Cloud. </br> |
| **[!UICONTROL Janela de criação de público-alvo]** | O período selecionado é usado para criar o público-alvo com base no calendário rotativo. Por exemplo, &quot;Últimos 30 dias&quot; (padrão) inclui visitantes que se qualificaram para o público-alvo nos últimos 30 dias a partir da data de hoje (NÃO a partir da data original quando o segmento foi criado). |
| **[!UICONTROL Criar na biblioteca de público-alvo]** | Os segmentos criados e publicados podem ser disponibilizados sem latência na Biblioteca de público-alvo da Experience Cloud. Eles não dependem das atualizações do Analytics. Esses segmentos não contam com o limite de 75 segmentos publicados. |
| **[!UICONTROL x de 75 Publicados]** | Mostra o número de segmentos publicados na Experience Cloud. Clique no link para ver uma lista de segmentos publicados e seu conjunto de relatórios associado e o proprietário. |
| **[!UICONTROL Salvar]** | Salva este segmento. |

## Cancelar a publicação ou excluir segmentos

Para excluir um segmento publicado na Experience Cloud, é necessário cancelar a publicação primeiro. Para cancelar a publicação de um segmento, basta **desmarcar** a caixa de seleção usada para publicá-lo.

>[!NOTE]
>
>**Não é possível** cancelar a publicação de um segmento que está em uso por qualquer uma das seguintes soluções da Adobe: [!DNL Analytics] (no [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (para cliente do [!DNL Core Service] e [!DNL Audience Manager]) e todos os outros parceiros externos (para clientes do [!DNL Audience Manager]). Você **pode** cancelar a publicação de um segmento em uso pelo [!DNL Target].

## Exibir o status de publicação do segmento no [!UICONTROL Gerenciador de segmentos]

1. Navegue até [!UICONTROL Analytics > Componentes > Segmentos].
1. Observe a nova coluna [!UICONTROL Publicado]. Sim/Não refere-se a se o segmento foi publicado na Experience Cloud ou não.

![](assets/publish-status.png)

## Recuperar a [!DNL Audience Manager] UUID

Há duas maneiras de capturar a UUID do AAM associada ao navegador no momento:

* Adobe Experience Cloud Debugger
* Ferramenta de desenvolvedor nativa nos navegadores (por exemplo, Ferramentas de desenvolvedor do Chrome)

As capturas de tela a seguir mostram como recuperar a UUID do AAM no navegador e usá-la no Visualizador de perfil do visitante do Audience Manager, para validar a característica e a associação do segmento.

**Método 1: usar o Adobe Experience Cloud Debugger**

1. Baixe e instale o [Adobe Experience Cloud Debugger](/help/implement/validate/debugger.md) na loja na Web do Chrome.
1. Inicie o depurador ao carregar uma página.
1. Role até a seção Audience Manager e localize a UUID do AAM definida na página atual do navegador (`50814298273775797762943354787774730612` no exemplo abaixo)

![](assets/debugger.jpg)

**Método 2: usar as ferramentas de desenvolvedor do Chrome (ou as ferramentas de desenvolvedor de outro navegador)**

1. Inicie as Ferramentas de desenvolvedor do Chrome antes de carregar uma página
1. Carregue a página e marque Aplicativos > Cookies. A UUID do AAM deve ser definida no cookie Demdex de terceiros ([adobe.demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=pt-BR) no exemplo abaixo). O demdex de campo é a configuração de UUID do AAM no navegador (`50814298273775797762943354787774730612` no exemplo abaixo).

![Ferramentas de desenvolvedor do Google Chrome](assets/ggogle-uuid.png)

## Usar [!UICONTROL Visualizador de perfil do visitante] do Audience Manager

A UUID do AAM no navegador será usada por padrão quando o [!UICONTROL Visualizador de perfil do visitante] for carregado. Se verificar as realizações de características de outros usuários, insira uma UUID no campo UUID e clique em [!UICONTROL Atualizar]. Consulte o [Visualizador de perfil do visitante](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/visitor-profile-viewer.html?lang=pt-BR) para obter mais informações.

![](assets/aam-vpv.png)

## Exibir as características do segmento em [!DNL Audience Manager]

No AAM, a lista de visitantes com ECIDs para um segmento específico é avaliada continuamente, à medida que o Analytics compartilha segmentos com a Experience Cloud.

1. Em [!DNL Audience Manager], vá para [!UICONTROL Dados de público-alvo > Características > Características do Analytics]. Você verá uma pasta para cada conjunto de relatórios do Analytics mapeada para a organização da Experience Cloud. Essas pastas (para Características, Segmentos e Fontes de Dados) são criadas quando os serviços principais de Perfis e Públicos-alvo/Pessoas são iniciados ou provisionados.
1. Selecione a pasta do conjunto de relatórios em que você criou o segmento com o qual deseja compartilhar [!DNL Audience Manager]. Você verá o segmento/público-alvo criado. Quando você compartilha um segmento, duas coisas acontecem em [!DNL Audience Manager]:
* Uma característica é criada, primeiro sem dados. Aproximadamente. oito horas após o segmento ser publicado no [!DNL Analytics], a lista de ECIDs é atualizada e compartilhada com [!DNL Audience Manager] e outras soluções da Experience Cloud.

![](assets/aam-traits.png)

* Um segmento com uma única característica é criado. Ele usa a fonte de dados associada ao conjunto de relatórios em que você publicou o segmento.
* A expiração da característica agora está definida para 16 dias (antes eram 2 dias).

## Exibir o segmento em [!DNL Adobe Target]

A caixa de seleção [!UICONTROL Publicar este segmento na Experience Cloud] durante o processo de criação de segmento no Adobe Analytics permite que o segmento fique disponível na biblioteca de público-alvo personalizado no Adobe Target. Um segmento criado no Analytics ou no Audience Manager pode ser usado em atividades no Target. Por exemplo, é possível criar atividades de campanha baseadas nas métricas de conversão do Analytics e nos segmentos de público-alvo criados no Analytics.

1. Clique em [!UICONTROL Públicos-alvo].
1. Na página [!UICONTROL Públicos-alvo], localize o público-alvo proveniente da [!DNL Experience Cloud]. Esses públicos-alvo estão disponíveis para uso em atividades [!DNL Target].
