---
description: Para usar regras de processamento com eficácia, é essencial compreender quando elas são aplicadas durante a coleta dos dados.
subtopic: Processing rules
title: Ordem de processamento
feature: Ferramentas administrativas
uuid: cea01d13-dfd5-40f7-8b2f-b6e2fe8354df
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
source-git-commit: a77fba68de543b51eda8cf4f9a16a0a15271b496
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 97%

---

# Ordem de processamento

Para usar regras de processamento com eficácia, é essencial compreender quando elas são aplicadas durante a coleta dos dados.

![](assets/analytics_processing_order_test.png)

As tabelas a seguir apresentam os dados que normalmente estão disponíveis antes e após a aplicação das regras de processamento:

## Antes das regras de processamento

| Dimensão | Descrição |
|--- |--- |
| Pesquisa de variável dinâmica | As variáveis são preenchidas de maneira dinâmica, puxando informações de cabeçalhos HTTP ou outras variáveis. Por exemplo, `s.eVar5="D=c1"` colocará o valor de prop1 na eVar5. |
| AppMeasurement | Funções e plug-ins-ins usados no AppMeasurement são executados no navegador ou no aplicativo do cliente. |
| Tag Management | As regras definidas na interface do usuário da coleta de dados são executadas conforme definido. |
| Regras de bot | As [regras de bot](/help/admin/admin/bot-removal/bot-rules.md) permitem que você remova o tráfego que é gerado pelos spiders e bots conhecidos de seu conjunto de relatórios. |

## Após as regras de processamento

| Dimensão | Descrição |
|--- |--- |
| Dados adicionados pelo VISTA | As regras de processamento são aplicadas antes do VISTA. |
| Número de página da visita | Via de regra, as regras de processamento estão cientes apenas dos dados que estão contidos na ocorrência atual. O número de página da visita é compilado após a aplicação das regras de processamento. |
| Um URL limpo é adicionado como nome da página se este não tiver sido definido | Após a aplicação das regras de processamento e do VISTA, o URL limpo é adicionado como o nome da página se nenhum nome de página tiver sido definido. Porque isso acontece após a aplicação das regras de processamento, recomendamos adicionar uma condição para verificar se o nome da página está em branco.  Se você executar Conteúdo do site > Relatório de páginas e vir valores https:// como nomes de página, é provável que o nome da página esteja em branco e que o URL esteja sendo usado.  Você pode definir uma condição para testar se o nome da página está em branco ou testar se o nome da página ou o URL da página contém um valor específico. Depois é possível definir o nome da página, conforme necessário. |
| Regras de processamento de canal de marketing | Você pode usar as regras de processamento para preparar os dados para processamento pelas [Regras de processamento de canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=pt-BR). |
| Pesquisa GEO | Isso inclui os valores de código Estado do visitante e Código postal/CEP do visitante. |
| Persistência de eVars | eVars que foram contidas em ocorrências anteriores não persistem em cada ocorrência durante o processamento das regras. Somente eVars definidas na ocorrência atual que está sendo processada ficam disponíveis. |

## Como as regras de processamento são aplicadas quando se copiam ocorrências usando o VISTA {#section_576EE8C240A24CBA979BD614E8D5338D}

Se você tiver uma regra VISTA configurada para copiar ocorrências para outro conjunto de relatórios, as ocorrências serão enviadas por meio de quaisquer regras de processamento definidas em outro conjunto de relatórios.

Se você tem regras de processamento definidas no conjunto de relatórios original, elas podem ou não ser aplicadas com base em como a regra VISTA foi configurada pelos Serviços de Engenharia. Para saber, você pode perguntar a seu especialista de implementação se a regra VISTA copia os valores &quot;pré&quot; e &quot;pós&quot; para o conjunto de relatórios adicional. Se o valor &quot;pré&quot; é copiado, as regras de processamento definidas no conjunto de relatórios original não são aplicadas. Se o valor &quot;pós&quot; é copiado, as regras de processamento são aplicadas antes de a ocorrência ser copiada.
