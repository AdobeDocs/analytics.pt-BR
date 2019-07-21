---
description: Para usar regras de processamento com eficácia, é essencial compreender quando elas são aplicadas durante a coleta dos dados.
seo-description: 'Para usar regras de processamento com eficácia, é essencial compreender quando elas são aplicadas durante a coleta dos dados. '
seo-title: Processando Ordem
solution: Analytics
subtopic: Regras de processamento
title: Ordem de processamento
topic: Ferramentas administrativas
uuid: cea 01 d 13-dfd 5-40 f 7-8 b 2 f-b 6 e 2 fe 8354 df
translation-type: tm+mt
source-git-commit: 9942536df7c7ee4fc8da9ae4189063ca4e543b7d

---


# Ordem de processamento

Para usar regras de processamento com eficácia, é essencial compreender quando elas são aplicadas durante a coleta dos dados.

![](assets/analytics_processing_order_test.png)

As tabelas a seguir apresentam os dados que normalmente estão disponíveis antes e após a aplicação das regras de processamento:

## Antes das regras de processamento

| Dimensão | Descrição |
|--- |--- |
| Pesquisa de variável dinâmica | As variáveis são preenchidas de maneira dinâmica, puxando informações de cabeçalhos HTTP ou outras variáveis. For example, `s.eVar5="D=c1"` will put the value of prop1 into eVar5. |
| AppMeasurement | Funções e plug-ins usados no AppMeasurement são executados no navegador ou no aplicativo do cliente. |
| Dynamic Tag Management | As regras definidas no Dynamic Tag Management são executadas conforme definido. |
| Regras de bot | [As regras](../../../../admin/admin/bot-rules/bot-rules.md) do robô permitem remover o tráfego que é gerado pelos spiders e bots conhecidos do conjunto de relatórios. |

## Após as regras de processamento

| Dimensão | Descrição |
|--- |--- |
| Dados adicionados pelo VISTA | As regras de processamento são aplicadas antes do VISTA. |
| Número de página da visita | Via de regra, as regras de processamento estão cientes apenas dos dados que estão contidos na ocorrência atual. O número de página da visita é compilado após a aplicação das regras de processamento. |
| Um URL limpo é adicionado como nome da página se este não tiver sido definido | Após a aplicação das regras de processamento e do VISTA, o URL limpo é adicionado como o nome da página se nenhum nome de página tiver sido definido. Porque isso acontece após a aplicação das regras de processamento, recomendamos adicionar uma condição para verificar se o nome da página está em branco.  Se você executar o Conteúdo do site &gt; Relatório de páginas e vir os valores https:// para nomes de página, provavelmente o nome da página está em branco e o URL está sendo usado. Você pode definir uma condição para testar se o nome da página está em branco ou testar se o nome da página ou o URL da página contém um valor específico. Depois é possível definir o nome da página, conforme necessário. |
| Regras de processamento de canal de marketing | Você pode usar as regras de processamento para preparar os dados para processamento pelas [Regras de processamento de canal de marketing](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html?f=c_rules). |
| Pesquisa GEO | Isso inclui os valores de código Estado do visitante e Código postal/CEP do visitante. |
| Persistência de eVars | eVars que foram contidas em ocorrências anteriores não persistem em cada ocorrência durante o processamento das regras. Somente eVars definidas na ocorrência atual que está sendo processada ficam disponíveis. |

## Como as regras de processamento são aplicadas quando se copiam ocorrências usando o VISTA {#section_576EE8C240A24CBA979BD614E8D5338D}

Se você tem uma regra VISTA configurada para copiar ocorrências para outro conjunto de relatórios, as ocorrências são enviadas por meio de quaisquer regras de processamento definidas em outro conjunto de relatórios.

Se você tem regras de processamento definidas no conjunto de relatórios original, elas podem ou não ser aplicadas com base em como a regra VISTA foi configurada pelos Serviços de Engenharia. Para saber, você pode perguntar a seu especialista de implementação se a regra VISTA copia os valores "pré" e "pós" para o conjunto de relatórios adicional. Se o valor "pré" é copiado, as regras de processamento definidas no conjunto de relatórios original não são aplicadas. Se o valor "pós" é copiado, as regras de processamento são aplicadas antes de a ocorrência ser copiada.
