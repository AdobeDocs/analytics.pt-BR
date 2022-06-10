---
description: Onde as regras de processamento residem no pipeline de dados abrangente do Analytics.
subtopic: Processing rules
title: Ordem de processamento
feature: Processing Rules
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 52%

---

# Ordem de processamento

Para usar regras de processamento com eficácia, é essencial entender quando elas são aplicadas durante a coleta de dados.

![Ordem de processamento](assets/analytics_processing_order.png)

As tabelas a seguir apresentam os dados que normalmente estão disponíveis antes e após a aplicação das regras de processamento.

## Antes das regras de processamento

| Dimensão | Descrição |
|--- |--- |
| [Variáveis dinâmicas](/help/implement/vars/page-vars/dynamic-variables.md) | Variáveis que são preenchidas dinamicamente, puxando informações de cabeçalhos HTTP ou outras variáveis. |
| [AppMeasurement](/help/implement/home.md) | Funções e plug-ins usados nas bibliotecas do AppMeasurement são executados no navegador ou no aplicativo do cliente. |
| [Implementação de tags](/help/implement/launch/overview.md) | Regras definidas na extensão Adobe Analytics na Coleta de dados do Adobe Experience Platform. |
| [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/analytics-overview.html) | Os dados coletados por meio do SDK da Web são enviados para o Adobe Experience Edge e encaminhados para o conjunto de relatórios desejado. |
| [Regras de bot](/help/admin/admin/bot-removal/bot-rules.md) | Permite remover o tráfego gerado pelos spiders e bots conhecidos. |

## Após as regras de processamento

| Dimensão | Descrição |
|--- |--- |
| Dados adicionados pelo VISTA | As regras de processamento são aplicadas antes do VISTA. |
| Número de página da visita | As regras de processamento só estão cientes dos dados contidos na ocorrência atual. O número de página da visita é compilado após a aplicação das regras de processamento. |
| Um URL limpo é adicionado como nome da página se este não tiver sido definido | Após a aplicação das regras de processamento e do VISTA, o URL limpo é adicionado como o nome da página se nenhum nome de página tiver sido definido. Como essa lógica ocorre após a aplicação das regras de processamento, o Adobe recomenda adicionar uma condição para verificar se o nome da página está em branco.  Se você executar a variável **[!UICONTROL Conteúdo do site]** > **[!UICONTROL Páginas]** Se você relatar valores de URL para nomes de página, é provável que a variável de nome de página esteja em branco.  Você pode configurar uma condição para testar um nome de página vazio ou para testar se o nome da página ou o URL da página contém um valor específico. Depois é possível definir o nome da página, conforme necessário. |
| Regras de processamento de canal de marketing | Você pode usar as regras de processamento para preparar os dados para processamento pelas [Regras de processamento de canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=pt-BR). |
| Pesquisa GEO | Inclui os valores Estado do visitante e CEP/código postal do visitante. |
| Persistência de eVars | eVars que foram contidas em ocorrências anteriores não persistem em cada ocorrência durante o processamento das regras. Somente eVars definidas na ocorrência atual que está sendo processada ficam disponíveis. |

## Como as regras de processamento são aplicadas quando se copiam ocorrências usando o VISTA

Se você tiver uma regra VISTA configurada para copiar ocorrências para outro conjunto de relatórios, as ocorrências serão enviadas por meio de quaisquer regras de processamento definidas em outro conjunto de relatórios.

Se você tiver regras de processamento definidas no conjunto de relatórios original, essas regras poderão ou não ser aplicadas com base em como a regra VISTA foi configurada pelos Serviços de engenharia. Para saber, você pode perguntar a seu especialista de implementação se a regra VISTA copia os valores &quot;pré&quot; e &quot;pós&quot; para o conjunto de relatórios adicional. Se o valor &quot;pré&quot; é copiado, as regras de processamento definidas no conjunto de relatórios original não são aplicadas. Se o valor &quot;pós&quot; é copiado, as regras de processamento são aplicadas antes de a ocorrência ser copiada.
