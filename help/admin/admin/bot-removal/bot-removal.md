---
title: Remoção de bot no Adobe Analytics
seo-title: Remoção de bot no Adobe Analytics
description: 3 maneiras de remover bots no Adobe Analytics
seo-description: 3 maneiras de remover bots no Adobe Analytics
translation-type: tm+mt
source-git-commit: ef17712b4a8a4a5c13dde9be9fdf2281eeb40091

---


# Remoção de bot no Adobe Analytics

No Adobe Analytics, você tem várias opções para remover o tráfego de robô dos relatórios:

## Usar regras do robô

Os métodos padrão e personalizados de filtragem de bots são suportados em **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; Conjuntos **[!UICONTROL de]** relatórios &gt; **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Geral]** ****&gt; Regras de bot:

| Tipo de regra | Descrição |
|--- |--- |
| Regras de bot IAB padrão | A seleção de **[!UICONTROL Ativar regras]** de filtragem de bots IAB usa a lista internacional Spiders e bots da [](https://www.iab.com/) IAB (International Advertising Bureau's) para remover o tráfego de bot. A maioria dos clientes seleciona essa opção no mínimo. |
| Regras de bot personalizadas | Você pode definir e adicionar regras de bot personalizadas com base em agentes de usuário, endereços IP ou intervalos IP. |

Para obter mais detalhes, consulte Visão geral [das regras do](/help/admin/admin/bot-removal/bot-rules.md)robô.

## Usar o plug-in de `hitGovernor` implementação

Use o plug-in [de implementação](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html)s.hitGovernor, que remove visitantes que se comportam como bots, o que significa que esses visitantes enviam dezenas ou centenas de ocorrências por minuto.

## Usar uma combinação de ferramentas da Adobe

Além disso, como os bots estão se modificando rapidamente, a Adobe oferece vários outros recursos avançados que, quando combinados de forma adequada e regular, podem ajudar a remover esses inimigos da qualidade dos dados. Esses recursos são: Serviço da Experience Cloud ID, Segmentação, Data Warehouse, Atributos do cliente e Conjuntos de relatórios virtuais. Esta é uma visão geral de como você pode aproveitar essas ferramentas.

### Etapa 1: Transmita a Experience Cloud ID dos seus visitantes para uma nova ID declarada

Para iniciar, você desejará criar uma nova ID declarada no Serviço [principal de](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html)pessoas. Você precisará passar a Experience Cloud ID do visitante para essa nova ID declarada, que pode ser feita rápida e facilmente com o [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html). Vamos usar o nome "ECID" para a ID declarada.

![](assets/bot-cust-attr-setup.png)

Veja como essa ID pode ser capturada por meio do elemento de dados. Certifique-se de preencher corretamente sua Experience Cloud OrgID no Elemento de dados.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Depois que esse elemento de dados for configurado, siga [estas instruções](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) para passar as IDs declaradas para a ferramenta ECID no Launch.

### Etapa 2: Usar segmentação para identificar bots

Agora que a ECID do visitante foi passada para uma ID declarada, você pode usar a [segmentação na Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) para identificar os visitantes que atuam como bots. Os bots são frequentemente definidos pelo seu comportamento: visitas de acesso único, agentes de usuário incomuns, informações desconhecidas do dispositivo/navegador, nenhum referenciador, novos visitantes, páginas de aterrissagem incomuns etc. Use os poderes de detalhamento e segmentação do Workspace para identificar os bots que evadiram a filtragem IAB e as regras de bot do conjunto de relatórios. Por exemplo, esta é uma captura de tela de um segmento que você pode usar:

![](assets/bot-filter-seg1.png)

### Etapa 3: Exportar tudo [!DNL Experience Cloud IDs] do segmento pelo Data Warehouse

Agora que você identificou os bots usando segmentos, a próxima etapa é aproveitar o Data Warehouse para extrair todas as Experience Cloud IDs associadas a esse segmento. É assim que você deve configurar sua solicitação do [Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) :

![](assets/bot-dwh-3.png)

Lembre-se de usar a ID de visitante da Experience Cloud como dimensão e aplicar o segmento Bots.

### Etapa 4: Repassar esta lista para a Adobe como um Atributo do cliente

Quando o relatório do Data Warehouse chegar, você terá uma lista de ECIDs que precisam ser filtradas dos dados históricos. Copie e cole esses ECIDs em um arquivo .CSV em branco com apenas duas colunas, ECID e Sinalizador de bot.

* **ECID**: Certifique-se de que esse cabeçalho de coluna corresponda ao nome que você deu à nova ID declarada acima.
* **Sinalizador** do robô: Adicione isso como uma dimensão de esquema Atributo do cliente.

Use esse arquivo .CSV como seu arquivo de importação de Atributo do cliente e assine seu(s) conjunto(s) de relatórios no Atributo do cliente, conforme descrito nesta postagem [do](https://theblog.adobe.com/link-digital-behavior-customers)blog.

![](assets/bot-csv-4.png)

### Etapa 5: Criar um segmento que aproveite o novo Atributo do cliente

Depois que seu conjunto de dados tiver sido processado e integrado à Analysis Workspace, crie mais um segmento que aproveite sua nova dimensão de atributo de cliente "Sinalizador de bot" e um contêiner de [!UICONTROL exclusão] :

![](assets/bot-filter-seg2.png)

### Etapa 6: Usar este segmento como filtro do Conjunto de relatórios virtuais

Por fim, você deve criar um Conjunto [de relatórios](/help/components/vrs/vrs-about.md) virtuais que aproveite esse segmento para filtrar os bots identificados:

![](assets/bot-vrs.png)

Esse conjunto de relatórios virtuais recém-segmentado resultará em um conjunto de dados significativamente mais limpo, com os bots identificados completamente removidos.

### Etapa 7: Repita as etapas 2, 3 e 4 regularmente

Defina pelo menos um lembrete mensal para identificar e filtrar novos bots, talvez antes da análise programada regularmente.
