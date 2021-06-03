---
title: Remoção de bot no Adobe Analytics
description: Como remover bots no Adobe Analytics
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 52%

---

# Remoção de bot no Adobe Analytics

No Adobe Analytics, você tem várias opções para remover o tráfego de bot dos relatórios:

## Usar regras de bot

Os métodos padrão e personalizados de filtragem de bots são compatíveis em **[!UICONTROL Analytics]** > **[!UICONTROL Administração]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de bot]**:

| Tipo de regra | Descrição |
|--- |--- |
| Regras de bot IAB padrão | Selecionar **[!UICONTROL Ativar regras de filtragem de bots IAB]** usa a Lista internacional de spiders e bots (International Advertising Bureau&#39;s) da [IAB](https://www.iab.com/) para remover o tráfego de bot. A maioria dos clientes seleciona essa opção, no mínimo. |
| Regras de bot personalizadas | Você pode definir e adicionar regras de bot personalizadas com base em agentes de usuário, endereços IP ou intervalos IP. |

Para obter mais detalhes, consulte [Visão geral das regras de bot](/help/admin/admin/bot-removal/bot-rules.md).

## Use o plug-in [!UICONTROL siteBot] para identificar bots

O plug-in [!UICONTROL siteBot] permite identificar dinamicamente se os visitantes da área de trabalho são bots. Você pode usar esses dados para impulsionar uma maior precisão em todos os tipos de relatórios, o que oferece uma maneira melhor de medir o tráfego real no site.

Esse plug-in executa duas verificações:

* Primeiro, determina se o dispositivo é um desktop ou dispositivo móvel usando a variável navigator.UserAgent . Dispositivos móveis são ignorados.
* Se for um dispositivo desktop, ele adiciona um ouvinte de evento para movimento do mouse.

Para obter mais informações, consulte o [Guia de Implementação do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html).

## Usar uma combinação de ferramentas da Adobe

Além disso, como os bots estão se modificando rapidamente, a Adobe oferece vários outros recursos avançados que, quando combinados de forma adequada e regular, podem ajudar a remover esses inimigos da qualidade dos dados. Esses recursos são: Serviço da Experience Cloud ID, Segmentação, Data Warehouse, Atributos do cliente e Conjuntos de relatórios virtuais. Esta é uma visão geral de como você pode usar essas ferramentas.

### Etapa 1: transmita a Experience Cloud ID dos seus visitantes para uma nova ID declarada

Para iniciar, crie uma nova ID declarada no [Serviço principal de pessoas](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html). Passe a ID do Experience Cloud do visitante para essa nova ID declarada, que pode ser feita rápida e facilmente com [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html). Vamos usar o nome &quot;ECID&quot; para a ID declarada.

![](assets/bot-cust-attr-setup.png)

Veja como essa ID pode ser capturada por meio do Elemento de dados. Certifique-se de preencher corretamente a Experience Cloud OrgID no Elemento de dados.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Depois que esse Elemento de dados for configurado, siga [estas instruções](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) para transmitir as IDs declaradas para a Ferramenta ECID no Adobe Launch.

### Etapa 2: usar segmentação para identificar bots

Agora que a ECID do visitante foi transmitida para uma ID declarada, você pode usar a [segmentação na Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) para identificar os visitantes que atuam como bots. Os bots são frequentemente definidos pelo seu comportamento: visitas de acesso único, agentes de usuário incomuns, informações desconhecidas do dispositivo/navegador, nenhum referenciador, novos visitantes, páginas de aterrissagem incomuns etc. Use os potenciais de detalhamento e segmentação do Workspace para identificar os bots que escaparam da filtragem IAB e as regras de bot do conjunto de relatórios. Por exemplo, esta é uma captura de tela de um segmento que você pode usar:

![](assets/bot-filter-seg1.png)

### Etapa 3: exportar tudo [!DNL Experience Cloud IDs] do segmento pelo Data Warehouse

Agora que você identificou os bots usando segmentos, a próxima etapa é usar o Data Warehouse para extrair todas as IDs de Experience Cloud associadas a esse segmento. Esta captura de tela mostra como você deve configurar sua solicitação [Data Warehouse](/help/export/data-warehouse/data-warehouse.md):

![](assets/bot-dwh-3.png)

Lembre-se de usar a ID de visitante do Experience Cloud como dimensão e aplicar o segmento &quot;Bots&quot;.

### Etapa 4: transmitir essa lista para a Adobe como um Atributo do cliente

Quando o relatório de Data Warehouse chegar, você terá uma lista de ECIDs que devem ser filtradas dos dados históricos. Copie e cole esses ECIDs em um arquivo .CSV em branco com apenas duas colunas, ECID e Sinalizador de bot.

* **ECID**: Certifique-se de que esse cabeçalho de coluna corresponda ao nome que você deu à nova ID declarada acima.
* **Sinalizador** de bot: Adicione &quot;Sinalizador de bot&quot; como uma dimensão de esquema Atributo do cliente.

Use esse arquivo .CSV como seu arquivo de importação do Atributo do cliente e assine os conjuntos de relatórios no Atributo do cliente, conforme descrito nesta [publicação do blog](https://theblog.adobe.com/link-digital-behavior-customers).

![](assets/bot-csv-4.png)

### Etapa 5: criar um segmento que aproveite o novo Atributo do cliente

Depois que seu conjunto de dados tiver sido processado e integrado ao Analysis Workspace, crie mais um segmento que aproveite sua nova dimensão de atributo de cliente &quot;Sinalizador de bot&quot; e um contêiner [!UICONTROL Excluir]:

![](assets/bot-filter-seg2.png)

### Etapa 6: usar esse segmento como filtro do Conjunto de relatórios virtuais

Finalmente, crie um [Conjunto de relatórios virtuais](/help/components/vrs/vrs-about.md) que use esse segmento para filtrar os bots identificados:

![](assets/bot-vrs.png)

Esse conjunto de relatórios virtuais recém-segmentado resultará em um conjunto de dados mais limpo, com os bots identificados removidos.

### Etapa 7: repita as etapas 2, 3 e 4 regularmente

Defina pelo menos um lembrete mensal para identificar e filtrar novos bots, talvez antes de uma análise programada regularmente.
