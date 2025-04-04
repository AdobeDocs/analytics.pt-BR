---
description: As regras de bot permitem que você remova o tráfego que é gerado pelos spiders e bots conhecidos de seu conjunto de relatórios. A remoção do tráfego de bot pode fornecer uma medida mais precisa da atividade do usuário no seu site.
title: Noções básicas e configuração de regras de bots
feature: Bot Removal
role: Admin
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1668'
ht-degree: 68%

---

# Noções básicas e configuração de regras de bots

As regras de bot permitem remover o tráfego do conjunto de relatórios gerado pelos spiders e bots conhecidos. A remoção do tráfego de bot pode fornecer uma medida mais precisa da atividade do usuário no seu site.

Depois que as regras de bot são definidas, todo o tráfego de entrada é comparado às regras definidas. O tráfego que corresponde a qualquer uma dessas regras não é coletado no conjunto de relatórios e não está incluído nas métricas de tráfego.

Remover o tráfego de robô normalmente reduz o volume do tráfego e as métricas de conversão. Muitos clientes acham que a remoção do tráfego de bot resulta em maiores taxas de conversão e em aumentos em outras métricas de usabilidade.

Os dados do tráfego de bot são armazenados em um repositório separado para exibição nos relatórios de Páginas de bots e Bots.

>[!NOTE]
>
>O Edge Network do Adobe Experience Platform fornece um [serviço de detecção de bot](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=pt-BR) que rotula as ocorrências identificadas como sendo de bots. O processo de detecção de bot usado no Adobe Analytics é separado e não faz referência à pontuação de bot incluída nos dados que chegam pelo Edge Network. No entanto, os dois sistemas usam a mesma lista de bot IAB.

## Atualizar ou carregar regras de bot

>[!IMPORTANT]
>
>Antes de remover o tráfego de bot, você deve entrar em contato com as partes interessadas para garantir que elas possam fazer os ajustes necessários nos principais indicadores de desempenho, como resultado dessa mudança. Se possível, recomendamos que, antes, seja removido o tráfego de robô de um report suite pequeno, para estimar o potencial impacto.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurar regras de bot](https://video.tv.adobe.com/v/335738/?quality=12){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


Para atualizar ou fazer upload de regras de bot:

1. Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]**.

1. Selecione o conjunto de relatórios no qual você deseja atualizar as regras de bot e selecione **[!UICONTROL Editar Configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de bot]**.

1. Use qualquer uma das seguintes opções para atualizar ou fazer upload de regras de bot para o conjunto de relatórios:

   * Selecione [!UICONTROL **Habilitar regras de filtragem de bots IAB**] para remover bots na Lista Internacional de spiders e bots (International Advertising Bureau&#39;s) da IAB para remover o tráfego de bot.

     Recomendamos que você selecione essa opção no mínimo.

     Para obter mais informações, consulte a seção abaixo, [Regras de bot IAB padrão](#standard-iab-bot-rules).

   * Selecione [!UICONTROL **Adicionar regra**] para definir e adicionar regras de bot personalizadas com base em agentes de usuário, endereços IP ou intervalos IP.

     Para obter mais informações, consulte a seção abaixo, [Regras de bot personalizadas](#custom-bot-rules).

   * Ao lado da área [!UICONTROL **Selecionar arquivo de bot CSV a ser importado**], selecione [!UICONTROL **Escolher arquivo**] e selecione o arquivo CSV que define as regras de bot.

     Para obter mais informações, consulte a seção abaixo, [Carregar regras de bot](#upload-bot-rules).

1. Selecione [!UICONTROL **Salvar**].

## Regras de bot IAB padrão

As regras de bot IAB padrão podem ser ativadas ao marcar a caixa de seleção [!UICONTROL Ativar regras de filtragem de bot IAB]. Esta seleção removerá bots na Lista Internacional de spiders e bots (International Advertising Bureau&#39;s) da IAB para remover o tráfego de bots. A Adobe atualiza essa lista do IAB todos os meses.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-iab-checkbox.png)

O Adobe não é capaz de fornecer a lista detalhada de bots da IAB para os clientes, no entanto você pode usar o Relatório de bots para ver uma lista de bots que acessaram seu site. Para enviar um bot para a lista IAB, visite [IAB](https://www.iab.com).

Para obter informações sobre como habilitar regras de bot IAB padrão em um conjunto de relatórios, consulte [Atualizar ou carregar regras de bot](#update-or-upload-bot-rules).

## Regras de bot personalizadas

>[!NOTE]
>
>A interface de usuário permite a definição manual de 500 regras. Quando esse limite é alcançado, as regras precisam ser gerenciadas em massa por meio das opções Importar arquivo e Exportar regras de bot.

As regras de bot personalizadas permitem filtrar as condições com base no tráfego que você define. Para iniciar o processo de habilitação de regras de bot personalizadas em um conjunto de relatórios, consulte [Atualizar ou carregar regras de bot](#update-or-upload-bot-rules).

As regras de bot personalizadas são definidas usando os seguintes tipos de condição:

* Agente do usuário
* Endereço IP
* Intervalo de IP

Várias condições podem ser definidas para uma única regra. Várias condições são correspondidas usando &quot;ou&quot;. Por exemplo, se você fornece um valor para Agente do usuário e Endereço IP, o tráfego é considerado tráfego de bot se uma das condições for atendida.

### Agente do usuário

Uma condição Agente do usuário verifica o valor do agente do usuário para ver se ele **[!UICONTROL começa com]** ou **[!UICONTROL contém]** a string especificada. Caso seja selecionado **[!UICONTROL contém]**, a subsequência é encontrada se houver qualquer ocorrência dela no agente do usuário.

Valores opcionais podem ser inseridos na lista **[!UICONTROL não contém]** para definir valores que o agente do usuário não deve conter para uma correspondência acertada. Vários valores podem ser especificados por meio da inclusão de um valor por linha. Se o agente do usuário atender os critérios especificados na string de correspondência, mas também contiver uma string na lista de não contém, não é considerado uma correspondência.

O campo **[!UICONTROL contém]** limita-se a 100 caracteres. A lista de não contém é limitada a 255 caracteres, menos um caractere separador para cada nova linha. (É igual ao número de strings - 1. Se você especificar 4 *não contém* cadeias de caracteres, serão necessários 3 caracteres separadores.) Todas as correspondências de cadeias de caracteres não diferenciam maiúsculas de minúsculas.

### Endereço IP (inclusive correspondências curingas)

Corresponde a um endereço IP ou vários endereços no mesmo bloco usando curingas (&#42;). Forneça os valores numéricos do endereço IP que deseja encontrar. Substitua &#42; por qualquer valor que você deseja encontrar usando um curinga. A lista a seguir contém exemplos de string de correspondência do endereço IP:

```
10.10.10.1
10.10.10.*
```

### Intervalo de endereço IP

Forneça os valores inicial e final do intervalo de endereços IP que deseja encontrar. Substitua &#42; por qualquer valor que você deseja encontrar usando um curinga.

### Definir uma regra de bot personalizada

1. Acesse **[!UICONTROL Analytics]** > **[!UICONTROL Administração]**, selecione um ou mais conjuntos de relatórios e clique em **[!UICONTROL Geral]** > **[!UICONTROL Regras de bot]**.
1. Clique em **[!UICONTROL Adicionar regra]** e defina uma ou mais condições de correspondência.
1. Clique em **[!UICONTROL Salvar]**. A alteração deve ocorrer em 30 minutos.

## Fazer upload de regras de bot

Para as regras de bot de importação em massa, é possível fazer upload do arquivo CSV que define as regras.

1. Para começar o processo de carregar regras de bot para um conjunto de relatórios, consulte [Atualizar ou carregar regras de bot](#update-or-upload-bot-rules).

1. Crie um arquivo CSV com as seguintes colunas, na linha 1 da planilha e na ordem apresentada:

   | Coluna 1, Linha 1 | Coluna 2, Linha 1 | Coluna 3, Linha 1 | Coluna 4, Linha 1 | Coluna 5, Linha 1 | Coluna 6, Linha 1 |
   |--- |--- |---|---|---|---|
   | Nome do bot | Início do IP | IP Fim | Regra<br>(contém ou começa com)</br> | Inclusão do agente do usuário | Exclusão de Agente do Usuário<br>(limite de 255 caracteres)</br> |

   É possível definir três tipos de regras de bot:

   * O agente do usuário contém ou começa com
   * Endereço IP único ou correspondência curinga
   * Correspondência de intervalo de IP

   Cada linha no arquivo de importação pode conter apenas uma das seguintes definições:

   >[!NOTE]
   >
   >   Para encontrar um bot usando uma combinação de regras juntas a um OU (por exemplo, agente do usuário ou endereço IP), forneça um nome idêntico para todas as regras que deseja combinar no campo de nome do bot. Correspondências AND não são suportadas.


   * **O agente do usuário contém ou começa com**: Forneça uma única sequência de agente do usuário para corresponder na coluna Incluir agente. Especifique o tipo de correspondência que deseja fazer colocando *contém* ou *começa com* no campo Regra de correspondência do agente. Um valor opcional pode ser incluído na coluna Excluir agente, o qual define uma ou mais strings delimitadas por traço (`|`) que o agente não contém. As correspondências de string não distinguem maiúsculas de minúsculas. As colunas IP início e IP fim devem estar vazias.

   * **Endereço IP único ou correspondência curinga**: para corresponder a um único endereço IP (`10.10.10.1`) ou endereço IP curinga (`10.10.*.*`), coloque o mesmo valor nas colunas Início de IP e Fim de IP. Regra de correspondência, Incluir agente e Excluir agente devem estar vazios.

   * **Correspondência de intervalo de IP**: Defina um intervalo de endereços IP usando as colunas IP início e IP fim. Os curingas podem ser usados para a correspondência dos intervalos de IP, por exemplo de `10.10.10.*` para `10.10.20.*`. Regra de correspondência, Incluir agente e Excluir agente devem estar vazios.

1. Na página Regras de bot no Gerenciador de conjunto de relatórios, ao lado da área [!UICONTROL **Selecionar arquivo de bot CSV a ser importado**], selecione [!UICONTROL **Escolher arquivo**] e, em seguida, selecione o arquivo CSV que define as regras de bot que você deseja importar.

1. (Opcional) Marque a caixa de seleção **[!UICONTROL Substituir todas as regras]** para excluir todas as regras existentes e substituí-las pelas regras definidas no arquivo de carregamento.

1. Selecione [!UICONTROL **Importar Arquivo**].

1. Na área [!UICONTROL **Conjuntos de Regras**], examine as regras que foram importadas.

1. Selecione [!UICONTROL **Salvar**].

## Exportar regras de bot

Para exportar todas as regras definidas na interface em um formato CSV:

1. Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]**.

1. Selecione o conjunto de relatórios que contém as regras de bot que você deseja exportar e selecione **[!UICONTROL Editar Configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de bot]**.

1. Selecione **[!UICONTROL Exportar regras de bot]** e salve o arquivo CSV no sistema de arquivos.

## Impacto das regras de bot na coleta de dados {#section_F01A3130E7A04A9993371CF26F6586F2}

As regras de bot são aplicadas a todos os dados de análises. Os dados removidos pelas regras de bot são visíveis apenas nos Relatórios de Páginas de bots e Bots.

As regras VISTA são aplicadas após as Regras de bots. Consulte [Pedido de processamento](/help/technotes/processing-order.md) no Guia do usuário da Technotes.

**Processamento de visita de alta ocorrência:** se houver mais de 100 ocorrências em uma visita, o relatório determinará se o tempo da visita em segundos é menor que ou igual ao número de ocorrências na visita. Nessa situação, devido ao custo de processar visitas longas e intensas, o relatório recomeçará com uma nova visita. Visitas de alta ocorrência são normalmente causadas por ataques de bot e não são consideradas como uma navegação do visitante normal.

>[!NOTE]
>
>As ocorrências marcadas como *`bots`* são cobradas como [chamadas do servidor.](/help/admin/admin/c-server-call-usage/overage-overview.md)

## Impacto da ofuscação de IP na filtragem de bot {#section_92E60B95BE8940D983F28C79E0CD6B12}

A lista de bots IAB é baseada unicamente no agente do usuário; portanto, a filtragem com base na lista não é afetada por configurações de ofuscação de IP. Para a filtragem de bots não IAB (regras personalizadas), o IP pode fazer parte dos critérios de filtragem. Se os bots de filtragem utilizam IP, a filtragem de bots ocorre depois que o último octeto é removido (se a configuração está ativada), mas antes de outras opções de ofuscação de IP, como excluir o IP ou substituí-lo por uma ID exclusiva.

Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP.

Se o último octeto for removido, isso ocorrerá antes da filtragem de IP. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. O &#42; correspondente deve corresponder a 0.
