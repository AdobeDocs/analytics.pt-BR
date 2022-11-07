---
title: Remoção de bot no Adobe Analytics
description: Como remover bots no Adobe Analytics
feature: Bot Removal
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 100%

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

## Use o plug-in [!UICONTROL websiteBot] para identificar bots

O plug-in [!UICONTROL websiteBot] permite identificar dinamicamente se os visitantes do desktop são bots. Você pode usar esses dados para impulsionar uma maior precisão em todos os tipos de relatórios, o que oferece uma maneira melhor de medir o tráfego real no site.

Esse plug-in executa duas verificações:

* Primeiro, determina se o dispositivo é um desktop ou um dispositivo móvel usando a variável navigator.UserAgent. Dispositivos móveis são ignorados.
* Se for um dispositivo desktop, ele adiciona um ouvinte de evento para movimento do mouse.

Para obter mais informações, consulte o [Manual de implementação do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html?lang=pt-BR).

## Usar uma combinação de ferramentas da Adobe

Além disso, como os bots estão se modificando rapidamente, a Adobe oferece vários outros recursos avançados que, quando combinados de forma adequada e regular, podem ajudar a remover esses inimigos da qualidade dos dados. Esses recursos são: Serviço da Experience Cloud ID, Segmentação, Data Warehouse, Atributos do cliente e Conjuntos de relatórios virtuais. Esta é uma visão geral de como você pode usar essas ferramentas.

### Etapa 1: transmita a Experience Cloud ID dos seus visitantes para uma nova ID declarada

Para iniciar, crie uma nova ID declarada no [Serviço principal de pessoas](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR). Transmita a Experience Cloud ID do visitante para esta nova ID declarada, o que pode ser feito de forma rápida e fácil com [tags na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=pt-BR). Vamos usar o nome &quot;ECID&quot; para a ID declarada.

![](assets/bot-cust-attr-setup.png)

Veja como essa ID pode ser capturada por meio do Elemento de dados. Preencha corretamente a Experience Cloud OrgID no Elemento de dados.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Depois que esse elemento de dados for configurado, siga [estas instruções](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) para transmitir IDs declaradas para a ferramenta ECID usando tags na Adobe Experience Platform.

### Etapa 2: usar segmentação para identificar bots

Agora que a ECID do visitante foi transmitida para uma ID declarada, você pode usar a [segmentação na Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=pt-BR) para identificar os visitantes que atuam como bots. Os bots são frequentemente definidos pelo seu comportamento: visitas de acesso único, agentes de usuário incomuns, informações desconhecidas do dispositivo/navegador, nenhum referenciador, novos visitantes, páginas de aterrissagem incomuns etc. Use os potenciais de detalhamento e segmentação do Workspace para identificar os bots que escaparam da filtragem IAB e as regras de bot do conjunto de relatórios. Por exemplo, esta é uma captura de tela de um segmento que você pode usar:

![](assets/bot-filter-seg1.png)

### Etapa 3: exportar tudo [!DNL Experience Cloud IDs] do segmento pelo Data Warehouse

Agora que você identificou os bots usando segmentos, a próxima etapa é usar o Data Warehouse para extrair todas as Experience Cloud IDs associadas a esse segmento. Esta captura de tela mostra como você deve configurar a solicitação do [Data Warehouse](/help/export/data-warehouse/data-warehouse.md):

![](assets/bot-dwh-3.png)

Lembre-se de usar a ID de visitante da Experience Cloud como dimensão e aplicar o segmento &quot;Bots&quot;.

### Etapa 4: transmitir essa lista para a Adobe como um Atributo do cliente

Quando o relatório do Data Warehouse chegar, você terá uma lista de ECIDs que precisam ser filtradas dos dados históricos. Copie e cole esses ECIDs em um arquivo .CSV em branco com apenas duas colunas, ECID e Sinalizador de bot.

* **ECID**: verifique se este cabeçalho de coluna corresponde ao nome que você deu à nova ID declarada acima.
* **Sinalizador de bot**: adicione &quot;Sinalizador de bot&quot; como uma dimensão de esquema de Atributo do cliente.

Use esse arquivo .CSV como seu arquivo de importação do Atributo do cliente e assine os conjuntos de relatórios no Atributo do cliente, conforme descrito nesta [publicação do blog](https://theblog.adobe.com/link-digital-behavior-customers).

![](assets/bot-csv-4.png)

### Etapa 5: criar um segmento que aproveite o novo Atributo do cliente

Assim que o conjunto de dados for processado e integrado ao Analysis Workspace, crie mais um segmento que aproveita a nova dimensão de atributo de cliente &quot;Sinalizador de bot&quot; e um container [!UICONTROL Excluir]:

![](assets/bot-filter-seg2.png)

### Etapa 6: usar esse segmento como filtro do Conjunto de relatórios virtuais

Por fim, crie um [Conjunto de relatórios virtuais](/help/components/vrs/vrs-about.md) que usa esse segmento para filtrar os bots identificados:

![](assets/bot-vrs.png)

Esse conjunto de relatórios virtuais recém-segmentado resultará em um conjunto de dados mais limpo, com os bots identificados removidos.

### Etapa 7: repita as etapas 2, 3 e 4 regularmente

Defina pelo menos um lembrete mensal para identificar e filtrar novos bots, talvez antes da análise programada regularmente.
