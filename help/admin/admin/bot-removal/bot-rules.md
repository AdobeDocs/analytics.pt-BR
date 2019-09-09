---
description: As regras de bot permitem que você remova o tráfego que é gerado pelos spiders e bots conhecidos de seu conjunto de relatórios. A remoção do tráfego de bot pode proporcionar uma medida mais precisa da atividade do usuário em seu site.
seo-description: As regras de bot permitem que você remova o tráfego que é gerado pelos spiders e bots conhecidos de seu conjunto de relatórios. A remoção do tráfego de robô pode proporcionar uma medida mais precisa da atividade do usuário em seu site.
seo-title: Regras de bot
solution: Analytics
subtopic: Regras de bot
title: Visão geral das regras de bot
topic: Ferramentas administrativas
uuid: 3 cb 9 e 29 d -1 c 37-43 de-b 7 ac -34441093 a 60 e
translation-type: tm+mt
source-git-commit: 5574b9e37e68971f7ecaa05056a30dab0b3d5d47

---


# Visão geral das regras de bot

As Regras do robô permitem remover o tráfego do conjunto de relatórios gerado pelos spiders e bots conhecidos. A remoção do tráfego de bot pode proporcionar uma medida mais precisa da atividade do usuário em seu site.

Após a definição das regras de bot, todo o tráfego de entrada é comparado às regras definidas. O tráfego que corresponde a qualquer uma dessas regras não é coletado no conjunto de relatórios e não está incluído nas métricas de tráfego.

To update or upload bot rules, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Select the correct Report Suite, and then go to **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

Remover o tráfego de bot normalmente reduz o volume do tráfego e as métricas de conversão. Muitos clientes acreditam que a remoção do tráfego de bot resulta em maiores índices de conversão e aumentos em outras métricas de usabilidade. Antes de remover o tráfego de bot, você deve entrar em contato com as partes interessadas para garantir que elas possam fazer os ajustes necessários nos principais indicadores de desempenho, como resultado dessa mudança. Se possível, recomendamos que, antes, seja removido o tráfego de robô de um report suite pequeno, para estimar o potencial impacto.

Os dados do tráfego de bot são armazenados em um repositório separado para exibição nos relatórios de Páginas de bots e Bots. Há duas opções para ativar a filtragem de bots:

| Tipo de regra | Descrição |
|--- |--- |
| Regras do robô padrão IAB | A seleção [!UICONTROL de Ativar regras de filtragem de bot IAB] usa a [lista internacional Spiders &amp; Bots da IAB](https://www.iab.com) (International Advertising Bureau) para remover o tráfego de robô. A maioria dos clientes seleciona essa opção no mínimo. |
| Regras do robô personalizadas | Você pode definir e adicionar regras de robô personalizadas com base em agentes do usuário, endereços IP ou intervalos IP. |

## Regras do robô padrão IAB

As regras do robô padrão IAB podem ser ativadas ao marcar a caixa [!UICONTROL de seleção Ativar regras] de filtragem de bot IAB. Essa seleção removerá bots na lista internacional Spiders &amp; Bots da IAB (International Advertising Bureau) para remover o tráfego de robô. O IAB atualiza essa lista mensalmente.

![](assets/bot-iab-checkbox.png)

O Adobe não é capaz de fornecer a lista detalhada de bots da IAB para os clientes, no entanto você pode usar o Relatório de bots para ver uma lista de bots que acessaram seu site. Para enviar um robô para a lista IAB, acesse [IAB](https://www.iab.com).

## Regras do robô personalizadas

>[!Note]
>A interface de usuário permite a definição manual de 500 regras. Quando esse limite é alcançado, as regras precisam ser gerenciadas em massa por meio das opções Importar arquivo e Exportar regras de bot.

As regras de bot personalizadas permitem que você filtre o tráfego com base nas condições que definiu.

As regras de bot personalizadas são definidas usando os seguintes tipos de condição:

* Agente do usuário
* Endereço IP
* Intervalo de IP

Várias condições podem ser definidas para uma única regra. Várias condições são correspondidas usando "ou". Por exemplo, se você fornece um valor para Agente do usuário e Endereço IP, o tráfego é considerado tráfego de bot se uma das condições for atendida.

### Agente do usuário

Uma condição Agente do usuário verifica o valor do agente do usuário para ver se ele **[!UICONTROL começa com]** ou **contém]a string especificada.[!UICONTROL ** Caso seja selecionado **[!UICONTROL contém], a subsequência é encontrada se houver qualquer ocorrência dela no agente do usuário.**

Valores opcionais podem ser inseridos na lista **[!UICONTROL não contém]para definir valores que o agente do usuário não deve conter para uma correspondência acertada.** Vários valores podem ser especificados por meio da inclusão de um valor por linha. Se o agente do usuário atender os critérios especificados na string de correspondência, mas também contiver uma string na lista de não contém, não é considerado uma correspondência.

O campo **[!UICONTROL contém]limita-se a 100 caracteres.** A lista de não contém é limitada a 255 caracteres, menos um caractere separador para cada nova linha. (É igual ao número de strings - 1. Se você especificar 4 sequências *não contém*, 3 caracteres separadores serão necessários.) As correspondências de string não distinguem maiúsculas de minúsculas.

### Endereço IP (inclusive correspondências curingas)

Corresponde a um endereço IP ou vários endereços no mesmo bloco usando curingas (*). Forneça os valores numéricos do endereço IP que deseja encontrar. Substitua * por qualquer valor que deseja encontrar usando um curinga. A lista a seguir contém exemplos de string de correspondência do endereço IP:

```
10.10.10.1
10.10.10.*
```

### Intervalo de endereço IP

Forneça os valores inicial e final do intervalo de endereços IP que deseja encontrar. Substitua * por qualquer valor que deseja encontrar usando um curinga.

### Definir uma regra de robô personalizada

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]**, select one or more report suites and click **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.
1. Click **[!UICONTROL Add Rule]** and define one or more match conditions.
1. Clique em **[!UICONTROL Salvar]**. A alteração deve ocorrer em 30 minutos.

## Fazer upload de regras de bot

Para as regras de bot de importação em massa, é possível fazer upload do arquivo CSV que define as regras.

Crie um arquivo CSV com as seguintes colunas, na ordem apresentada:

| Coluna 1 | Coluna 2 | Coluna 3 | Coluna 4 | Coluna 5 |
|--- |--- |---|---|---|
|  Nome do bot |  IP Início  |  IP Fim  | Agent Match Rule<br>(contains or starts with)</br> | Excluir agente<br>(limite de 255 caracteres)</br> |

É possível definir três tipos de regras de bot:

* O agente do usuário contém ou começa com
* Endereço IP único ou correspondência curinga
* Correspondência de intervalo de IP

Cada linha no arquivo de importação pode conter apenas uma das seguintes definições:

* **O agente do usuário contém ou começa com**: Forneça uma única sequência de agente do usuário para corresponder na coluna Incluir agente. Especifique o tipo de correspondência que deseja fazer colocando *contém* ou *começa com* no campo Regra de correspondência do agente. An optional value can be included in the Agent Exclude column that defines one or more pipe-delimited ( `|` ) strings that the Agent does not contain. As correspondências de string não distinguem maiúsculas de minúsculas. As colunas IP início e IP fim devem estar vazias.

* **Endereço IP único ou correspondência curinga**: Para corresponder a um único endereço IP ( `10.10.10.1`) ou endereço IP curinga ( `10.10.*.*`), coloque o mesmo valor nas colunas IP início e IP fim. Regra de correspondência, Incluir agente e Excluir agente devem estar vazios.

* **Correspondência de intervalo de IP**: Defina um intervalo de endereços IP usando as colunas IP início e IP fim. Wildcards can be used to match IP ranges, for example `10.10.10.*` to `10.10.20.*`. Regra de correspondência, Incluir agente e Excluir agente devem estar vazios.

### Vária regras combinadas com OU

Para encontrar um bot usando uma combinação de regras juntas a um OU (por exemplo, agente do usuário ou endereço IP), forneça um nome idêntico para todas as regras que deseja combinar no campo de nome do bot. Correspondências E não são suportadas.

### Substituir todas as regras com um arquivo de upload

Marque a caixa de seleção **[!UICONTROL Substituir todas as regras]para excluir todas as regras existentes e substituí-las pelas regras definidas no arquivo de upload.**

### Exportar regras

O botão **[!UICONTROL Exportar o arquivo de bot carregado]exporta todas as regras definidas na interface do usuário em um formato CSV.**


## Impact of bot rules on data collection {#section_F01A3130E7A04A9993371CF26F6586F2}

As regras de bot são aplicadas a todos os dados de análises. Os dados removidos pelas regras de bot são visíveis apenas nos Relatórios de Páginas de bots e Bots.

VISTA rules are applied after Bot Rules (see [Processing Order](../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E)).

**Processamento de visita de alta ocorrência:** se houver mais de 100 ocorrências em uma visita, o relatório determinará se o tempo da visita em segundos é menor que ou igual ao número de ocorrências na visita. Nessa situação, devido ao custo de processar visitas longas e intensas, o relatório recomeçará com uma nova visita. Visitas de alta ocorrência são normalmente causadas por ataques de bot e não são consideradas como uma navegação do visitante normal.

>[!NOTE]
>
>Ocorrências marcadas como *`bots`* faturadas como [chamadas do servidor](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/overage-overview.html).

## Impact of IP Obfuscation on bot filtering {#section_92E60B95BE8940D983F28C79E0CD6B12}

A lista de bots IAB é baseada unicamente no agente do usuário; portanto, a filtragem com base na lista não é afetada por configurações de ofuscação de IP. Para a filtragem de bots não IAB (regras personalizadas), o IP pode fazer parte dos critérios de filtragem. Se os bots de filtragem utilizam IP, a filtragem de bots ocorre depois que o último octeto é removido (se a configuração está ativada), mas antes de outras opções de ofuscação de IP, como excluir o IP ou substituí-lo por uma ID exclusiva

Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP.

Se o último octeto for removido, isso ocorrerá antes da filtragem de IP. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. A correspondência de * deve corresponder a 0.
