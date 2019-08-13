---
description: As regras de bot permitem que você remova o tráfego que é gerado pelos spiders e bots conhecidos de seu conjunto de relatórios. A remoção do tráfego de bot pode proporcionar uma medida mais precisa da atividade do usuário em seu site.
seo-description: As regras de bot permitem que você remova o tráfego que é gerado pelos spiders e bots conhecidos de seu conjunto de relatórios. A remoção do tráfego de robô pode proporcionar uma medida mais precisa da atividade do usuário em seu site.
seo-title: Regras de bot
solution: Analytics
subtopic: Regras de bot
title: Regras de bot
topic: Ferramentas administrativas
uuid: 3 cb 9 e 29 d -1 c 37-43 de-b 7 ac -34441093 a 60 e
translation-type: tm+mt
source-git-commit: 92ac6c03013bd68326e4136a5d512171fc831689

---


# Regras de bot

As Regras do robô permitem remover o tráfego do conjunto de relatórios gerado pelos spiders e bots conhecidos. A remoção do tráfego de bot pode proporcionar uma medida mais precisa da atividade do usuário em seu site.

Após a definição das regras de bot, todo o tráfego de entrada é comparado às regras definidas. O tráfego que corresponde a qualquer uma dessas regras não é coletado no conjunto de relatórios e não está incluído nas métricas de tráfego.

To update or upload bot rules, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Select the correct Report Suite, and then go to **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

Remover o tráfego de bot normalmente reduz o volume do tráfego e as métricas de conversão. Muitos clientes acreditam que a remoção do tráfego de bot resulta em maiores índices de conversão e aumentos em outras métricas de usabilidade. Antes de remover o tráfego de bot, você deve entrar em contato com as partes interessadas para garantir que elas possam fazer os ajustes necessários nos principais indicadores de desempenho, como resultado dessa mudança. Se possível, recomendamos primeiro remover o tráfego de bot de um conjunto de relatórios pequeno, para estimar o potencial impacto.

>[!NOTE] Recomendamos definir não mais do que 500 regras de bot por conjunto de relatórios. A interface de usuário permite a definição manual de 500 regras. Quando esse limite é alcançado, as regras precisam ser gerenciadas em massa por meio das opções [Importar arquivo](../../../admin/admin/bot-rules/t-upload-bot-rules.md#task_95868D8564564E6A996163335C119806) e Exportar regras de bot.

Os dados do tráfego de bot são armazenados em um repositório separado para exibição nos relatórios de [!UICONTROL Páginas de bots] e [!UICONTROL Bots].

| Tipo de regra | Descrição |
|--- |--- |
| IAB | Selecting [!UICONTROL Include IAB] uses the IAB's (International Advertising Bureau's) International Spiders &amp; Bots List to remove bot traffic. Essa lista é mensalmente atualizada pela IAB. <br>Para enviar um robô para a lista IAB, acesse [IAB](https://www.iab.net/sites/spiders/form.php). <br>O Adobe não é capaz de fornecer a lista detalhada de bots da IAB para os clientes, no entanto você pode usar o Relatório de bots para ver uma lista de bots que acessaram seu site. |
| Regras de bot personalizadas | See [Create a custom bot rule](../../../admin/admin/bot-rules/t-create-bot-rules.md). |

## Impacto das regras de bot na coleção de dados {#section_F01A3130E7A04A9993371CF26F6586F2}

As regras de bot são aplicadas a todos os dados de análises. Os dados removidos pelas regras de bot são visíveis apenas nos Relatórios de Páginas de bots e Bots.

VISTA rules are applied after Bot Rules (see [Processing Order](../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E)).

**Processamento de visita de alta ocorrência:** se houver mais de 100 ocorrências em uma visita, o relatório determinará se o tempo da visita em segundos é menor que ou igual ao número de ocorrências na visita. Nessa situação, devido ao custo de processar visitas longas e intensas, o relatório recomeçará com uma nova visita. Visitas de alta ocorrência são normalmente causadas por ataques de bot e não são consideradas como uma navegação do visitante normal.

>[!NOTE]
>
>Ocorrências marcadas como *`bots`* faturadas como [chamadas do servidor](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/overage-overview.html).

## Impacto da ofuscação de IP na filtragem de bot {#section_92E60B95BE8940D983F28C79E0CD6B12}

A lista de bots IAB é baseada unicamente no agente do usuário; portanto, a filtragem com base na lista não é afetada por configurações de ofuscação de IP. Para a filtragem de bots não IAB (regras personalizadas), o IP pode fazer parte dos critérios de filtragem. Se os bots de filtragem utilizam IP, a filtragem de bots ocorre depois que o último octeto é removido (se a configuração está ativada), mas antes de outras opções de ofuscação de IP, como excluir o IP ou substituí-lo por uma ID exclusiva

Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP.

Se o último octeto for removido, isso ocorrerá antes da filtragem de IP. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. A correspondência de * deve corresponder a 0.
