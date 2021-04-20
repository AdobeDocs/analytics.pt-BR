---
description: Descrições dos tipos de conjunto de relatórios e comparação de conjuntos de relatórios globais e conjuntos de relatórios de rollup.
title: Abordagens do conjunto de relatórios
feature: Admin Tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 27%

---

# Abordagens do conjunto de relatórios

<!-- change filename since page name changed? -->

Você pode configurar seus conjuntos de relatórios como *conjuntos de relatórios globais* ou *conjuntos de relatórios de rollup*.

## Conjuntos de relatórios globais

Um conjunto de relatórios global coleta dados de todos os domínios e aplicativos de sua organização. Ela requer implementação para enviar todas as solicitações de imagem para um único conjunto de relatórios.

A Adobe recomenda implementar um conjunto de relatórios global na maioria dos casos. Consulte &quot;[Considerações do conjunto de relatórios global](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html)&quot; para obter as vantagens de implementar um conjunto de relatórios global.

Você pode fornecer subconjuntos dos dados do conjunto de relatórios global de sua empresa para diferentes usuários finais usando as abordagens *marcação de vários conjuntos* e *conjunto de relatórios virtual*:

* **Marcação** de vários relatórios: A marcação de vários relatórios permite enviar solicitações de imagem não apenas para um conjunto de relatórios global, mas também para conjuntos de relatórios secundários individuais. Os dados globais do relatório são desduplicados em todos os conjuntos de relatórios.

   Por exemplo, é possível coletar todos os dados em um conjunto de relatórios global e também configurar conjuntos de relatórios secundários com base na marca, região ou outro diferencial. As diferentes equipes na empresa podem se concentrar nos dados nos conjuntos de relatórios que são relevantes para eles.

   Para usar a marcação de vários conjuntos, implemente conjuntos de relatórios secundários e um conjunto de relatórios global que inclua todos os dados dos filhos. O código de rastreamento de suas páginas da Web e aplicativos incluirá a ID do conjunto de relatórios (RSID) para o conjunto de relatórios global e também os RSIDs para os conjuntos de relatórios secundários aplicáveis.<!-- Wording/be more specific? And include any links? -->

   É feita uma chamada de servidor separada para cada conjunto de relatórios na solicitação de imagem. As chamadas para os conjuntos de relatórios secundários são chamadas secundárias.

* **Conjunto** de relatórios virtuais: Um conjunto de relatórios  [virtual ](/help/components/vrs/vrs-about.md) é uma consulta em segmentos especificados coletados em um conjunto de relatórios global e disponível para grupos de usuários especificados. Os conjuntos de relatórios virtuais permitem preparar elementos de relatório para diferentes usuários finais sem usar a marcação de vários conjuntos, evitando assim chamadas de servidor secundárias.

   Para usar conjuntos de relatórios virtuais, implemente um conjunto de relatórios global e analise os dados para criar conjuntos de relatórios virtuais com segmentos específicos aplicados e com permissões de grupo específicas. Você pode criar conjuntos de relatórios virtuais no Gerenciador de conjuntos de relatórios virtuais ([!UICONTROL Components] > [!UICONTROL Conjuntos de relatórios virtuais]). Consulte &quot;[Fluxo de trabalho do conjunto de relatórios virtual](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)&quot; para obter mais informações.

O uso de conjuntos de relatórios virtuais em vez da marcação de vários conjuntos é geralmente uma prática recomendada, mas os conjuntos de relatórios virtuais têm algumas limitações. Consulte &quot;[Conjuntos de relatórios virtuais e considerações de marcação de vários conjuntos](/help/components/vrs/vrs-considerations.md)&quot; para determinar qual abordagem de conjunto de relatórios é a melhor escolha para suas necessidades comerciais. Para obter uma comparação detalhada dos conjuntos de relatórios virtuais e da funcionalidade de marcação de vários conjuntos, consulte &quot;[Conjuntos de relatórios virtuais vs. Marcação de vários conjuntos](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot;.

## Relatórios de rollup

>[!NOTE]
>
>[!DNL Reports & Analytics] é a única ferramenta que oferece suporte a relatórios de rollup, e o Adobe não recomenda mais usar rollups. Em vez disso, considere usar um conjunto de relatórios global com marcação de vários conjuntos ou conjuntos de relatórios virtuais.

Um relatório de rollup é um simples agregado de dados de vários conjuntos de relatórios, sem desduplicação ou qualquer segmento ou detalhamento de dados. Os rollups não exigem implementação de código. Para usar relatórios de rollup, [implemente conjuntos de relatórios secundários](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) e depois [combine-os em um relatório de rollup](/help/admin/c-manage-report-suites/t-rollups.md) usando [!UICONTROL Ferramentas administrativas].

Relatórios de rollup são gratuitos: os conjuntos de relatórios secundários incorrem em suas próprias chamadas de servidor, mas o rollup não implica chamadas adicionais. Os rollups são um recurso herdado e têm muitas limitações.

### Limitações dos relatórios de rollup {#limitations-rollups}

* Os rollups fornecem dados totais, mas não relatam valores individuais em relatórios. Por exemplo, os valores de eVar1 não são incluídos, mas seu total agregado pode ser incluído.
* Os dados não são desduplicados quando o rollup combina dados em conjuntos de relatórios.
* Os rollups são executados à noite, à meia-noite.
* Quando você adiciona um conjunto de relatórios a um rollup existente, os dados históricos não são incluídos no rollup.
* Todos os conjuntos de relatórios secundários precisam conter dados para que um rollup possa funcionar. Se os novos conjuntos de relatórios forem incluídos em um rollup, certifique-se de enviar pelo menos uma exibição de página para cada um desses conjuntos de relatórios.
* Os conjuntos de relatórios de rollup podem incluir no máximo 40 conjuntos de relatórios secundários.
* Os conjuntos de relatórios de rollup podem incluir no máximo 100 eventos.
* Os dados contidos nos conjuntos de relatórios de rollup não são compatíveis com detalhamentos ou segmentos.
* O relatório Página é substituído pelo relatório Sites mais populares, que usa métricas no nível filho.

## Comparação dos recursos do conjunto de relatórios global e de relatório de rollup

**Chamadas secundárias do servidor**: os rollups não incorrem em chamadas de servidor adicionais além do que um único conjunto de relatórios coleta. Se sua organização usar marcação de vários conjuntos, serão feitas chamadas de servidor secundárias para cada conjunto de relatórios adicional incluído em uma solicitação de imagem.

>[!TIP]
>
>Se você usar apenas um conjunto de relatórios global com [conjuntos de relatórios virtuais](/help/components/vrs/vrs-considerations.md), nenhuma chamada de servidor secundário será necessária.

**Alterações de implementação**: os rollups não exigem alterações de implementação, enquanto os conjuntos de relatórios globais exigem que você inclua a ID do conjunto de relatórios global na implementação.

**Duplicação**: os conjuntos de relatórios globais removem a duplicação de visitantes únicos; os rollups, não. Por exemplo, se um usuário visita três de seus domínios no mesmo dia, os rollups contariam três visitantes únicos diários. Os conjuntos de relatórios globais registrariam um visitante único.

**Intervalo de tempo**: os rollups são processados somente à meia-noite a cada noite, ao passo que os conjuntos de relatórios globais relatam dados com latência padrão.

**Abrangência**: os rollups não possuem uma forma de comunicação entre os conjuntos de relatórios. Os conjuntos de relatórios globais podem atribuir crédito às variáveis de conversão entre conjuntos de relatórios e fornecer a definição de caminho em conjuntos de relatórios.

**Dados históricos**: os rollups podem agregar dados históricos, ao passo que os conjuntos de relatórios globais relatam somente dados a partir do ponto em que foram implementados.

**Relatórios**: todos os conjuntos de relatórios globais fornecem informações adicionais sobre todas as dimensões; os rollups fornecem dados agregados em relatórios de alto nível.

**Produtos compatíveis**: os rollups só podem ser usados no Reports &amp; Analytics. Eles não são compatíveis com o Analysis Workspace ou Data Warehouse. Os conjuntos de relatórios globais podem ser usados em todos os produtos.

**Número de conjuntos de relatórios agregados**: oos rollups suportam apenas um máximo de 40 conjuntos de relatórios secundários. Os conjuntos de relatórios globais podem ser implementados em qualquer número de domínios ou aplicativos de sua propriedade.
