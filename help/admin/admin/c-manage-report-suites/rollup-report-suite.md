---
description: Descrições dos tipos de conjunto de relatórios e comparação entre conjuntos de relatórios globais e de rollup.
title: Abordagens do conjunto de relatórios
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 93%

---

# Abordagens do conjunto de relatórios

<!-- change filename since page name changed? -->

É possível configurar seus conjuntos de relatórios como *conjuntos de relatórios globais* ou *conjuntos de relatórios de rollup*.

## Conjuntos de relatórios globais

Um conjunto de relatórios global coleta dados de todos os domínios e aplicativos que a organização possui. Ele requer implementação para enviar todas as solicitações de imagem para um único conjunto de relatórios.

A Adobe recomenda implementar um conjunto de relatórios global na maioria dos casos. Consulte “[Considerações sobre o conjunto de relatórios global](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=pt-BR)” para conhecer as vantagens de implementar um conjunto de relatórios global.

É possível fornecer subconjuntos dos dados do conjunto de relatórios global da sua empresa para diferentes usuários finais usando as abordagens *marcação de vários relatórios* e *conjunto de relatórios virtual*:

* **Marcação de vários relatórios**: permite enviar solicitações de imagem não apenas para um conjunto de relatórios global, mas também para conjuntos de relatórios secundários individuais. Os dados do relatório global são desduplicados em todos os conjuntos de relatórios.

  Por exemplo, é possível coletar todos os dados em um conjunto de relatórios global e também configurar conjuntos de relatórios secundários com base na marca, região ou outro diferencial. As diferentes equipes na empresa podem então se concentrar nos dados dos conjuntos de relatórios que são relevantes para elas.

  Para usar a marcação de vários relatórios, implemente conjuntos de relatórios secundários e um conjunto de relatórios global que inclua todos os dados dos secundários. O código de rastreamento de suas páginas da web e aplicativos incluirá a ID de conjunto de relatórios (RSID) do conjunto de relatórios global e também as RSIDs dos conjuntos de relatórios secundários aplicáveis.<!-- Wording/be more specific? And include any links? -->

  É feita uma chamada de servidor separada para cada conjunto de relatórios na solicitação de imagem. As chamadas para os conjuntos de relatórios secundários são chamadas secundárias.

* **Conjunto de relatórios virtual**: um [conjunto de relatórios virtual](/help/components/vrs/vrs-about.md) é uma consulta de segmentos especificados coletados em um conjunto de relatórios global e disponível para grupos específicos de usuários. Os conjuntos de relatórios virtuais permitem preparar elementos de relatório para diferentes usuários finais sem usar a marcação de vários relatórios, evitando assim chamadas de servidor secundárias.

  Para usar conjuntos de relatórios virtuais, implemente um conjunto de relatórios global e analise os dados para criar conjuntos de relatórios virtuais com segmentos específicos aplicados e com permissões de grupo específicas. É possível criar conjuntos de relatórios virtuais no Gerenciador de conjuntos de relatórios virtuais ([!UICONTROL Componentes] > [!UICONTROL Conjuntos de relatórios virtuais]). Consulte “[Fluxo de trabalho dos conjuntos de relatórios virtuais](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)” para obter mais informações.

O uso de conjuntos de relatórios virtuais em vez da marcação de vários relatórios é geralmente uma prática recomendada, mas conjuntos de relatórios virtuais têm algumas limitações. Consulte “[Considerações sobre os conjuntos de relatórios virtuais e a marcação de vários relatórios](/help/components/vrs/vrs-considerations.md)” para determinar qual abordagem de conjunto de relatórios é a melhor opção para suas necessidades comerciais. Para obter uma comparação detalhada entre os conjuntos de relatórios virtuais e a funcionalidade de marcação de vários relatórios, consulte &quot;[Conjuntos de relatórios virtuais versus marcação de vários conjuntos](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78).&quot;

## Relatórios de rollup

>[!NOTE]
>
>[!DNL Reports & Analytics] O é a única ferramenta que oferece suporte a relatórios de rollup. O Reports &amp; Analytics foi encerrado em 17 de janeiro de 2024.

### Limitações dos relatórios de rollup {#limitations-rollups}

* Os rollups fornecem os dados totais, mas não informam valores individuais nos relatórios. Por exemplo, os valores de eVar1 não são incluídos, mas o seu total agregado pode ser.
* Os dados não são desduplicados quando o rollup combina dados através de conjuntos de relatórios.
* Os rollups são executados todas as noites, à meia-noite.
* Ao adicionar um conjunto de relatórios a um rollup existente, os dados históricos não são incluídos no rollup.
* Todos os conjuntos de relatórios secundários precisam conter dados para que um rollup possa funcionar. Se os novos conjuntos de relatórios forem incluídos em um rollup, certifique-se de enviar pelo menos uma exibição de página para cada um desses conjuntos de relatórios.
* Os conjuntos de relatórios de rollup são limitados a, no máximo, 40 conjuntos de relatórios secundários.
* Os conjuntos de relatórios de rollup podem incluir no máximo 100 eventos.
* Os dados contidos nos conjuntos de relatórios de rollup não são compatíveis com detalhamentos ou segmentos.
* O relatório de Páginas é substituído pelo relatório de Sites mais populares, que usa métricas no nível do conjunto secundário.

## Comparação dos recursos do conjunto de relatórios global e do relatório de rollup

**Chamadas secundárias do servidor**: os rollups não incorrem em chamadas de servidor adicionais além do que um único conjunto de relatórios coleta. Se sua organização usar marcação de vários conjuntos, serão feitas chamadas de servidor secundárias para cada conjunto de relatórios adicional incluído em uma solicitação de imagem.

>[!TIP]
>
>Se você usar apenas um conjunto de relatórios global com [conjuntos de relatórios virtuais](/help/components/vrs/vrs-considerations.md), nenhuma chamada de servidor secundário será necessária.

**Alterações de implementação**: os rollups não exigem alterações de implementação, enquanto os conjuntos de relatórios globais exigem que você inclua a ID do conjunto de relatórios global na implementação.

**Duplicação**: os conjuntos de relatórios globais removem a duplicação de visitantes únicos; os rollups, não. Por exemplo, se um usuário visita três de seus domínios no mesmo dia, os rollups contariam três visitantes únicos diários. Os conjuntos de relatórios globais registrariam um visitante único.

**Intervalo de tempo**: os rollups são processados somente à meia-noite a cada noite, ao passo que os conjuntos de relatórios globais relatam dados com latência padrão.

**Abrangência**: os rollups não possuem uma forma de comunicação entre os conjuntos de relatórios. Os conjuntos de relatórios globais podem atribuir crédito às variáveis de conversão entre conjuntos de relatórios, bem como fornecer a definição de caminho entre conjuntos de relatórios.

**Dados históricos**: os rollups podem agregar dados históricos, ao passo que os conjuntos de relatórios globais relatam somente dados a partir do ponto em que foram implementados.

**Relatórios**: todos os conjuntos de relatórios globais fornecem informações adicionais sobre todas as dimensões; os rollups fornecem dados agregados em relatórios de alto nível.

**Produtos suportados**: os rollups só podem ser usados no Reports &amp; Analytics. Eles não são compatíveis com o Analysis Workspace ou Data Warehouse. Os conjuntos de relatórios globais podem ser usados em todos os produtos.

**Número de conjuntos de relatórios agregados**: oos rollups suportam apenas um máximo de 40 conjuntos de relatórios secundários. Os conjuntos de relatórios globais podem ser implementados em qualquer número de domínios ou aplicativos de sua propriedade.
