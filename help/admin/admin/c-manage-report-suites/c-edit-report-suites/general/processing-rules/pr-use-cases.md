---
description: Casos de usos comuns de regras de processamento.
subtopic: Processing rules
title: Casos de uso de regras de processamento
feature: Processing Rules
role: Admin
exl-id: 914a0d31-d256-456e-a44a-008490e86a23
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 16%

---

# Casos de uso de regras de processamento

Os aplicativos de como você pode usar as regras de processamento em sua organização são abrangentes. As seções a seguir detalham algumas maneiras comuns de usá-las a seu favor.

+++Copia uma variável de dados de contexto em um eVar

As regras de processamento são usadas para mover valores de [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) para [Props](/help/components/dimensions/prop.md) e [eVars](/help/components/dimensions/evar.md). Sem as regras de processamento, as variáveis de dados de contexto não têm significado e não preenchem nenhum relatório no Analytics.

A lista [!UICONTROL Variáveis de contexto] contém todas as variáveis que foram enviadas para o conjunto de relatórios nos últimos 30 dias. Se você sabe o nome da variável de dados de contexto, mas não a enviou para o conjunto de relatórios atual, é possível adicioná-la manualmente:

![Adicionando manualmente uma variável de dados de contexto a uma regra de processamento](assets/add-context-variable.png)

O exemplo a seguir pega a variável de dados de contexto `search_term` e coloca seu valor na eVar3:

| Conjunto de regras | Valor |
| Condição | `search_term` (Dados de contexto) está definido |
| Ação | [!UICONTROL Substituir o valor de ] eVar3 por `search_term` (Dados de contexto) |

![Captura de tela da interface de regras de processamento mostrando o uso de uma variável de dados de contexto](assets/set-context-data.png)

O exemplo acima funciona perfeitamente quando há apenas algumas eVars a serem preenchidas. Se sua organização tiver centenas de variáveis de dados de contexto em que cada uma precisa de sua própria eVar, você poderá usar declarações condicionais. Dezenas de declarações condicionais podem se encaixar em uma única regra de processamento, permitindo que sua organização preencha todas as eVars em um conjunto de relatórios sem entrar no limite de regras de processamento de 150 regras.

O exemplo a seguir preenche várias variáveis com variáveis de dados de contexto variáveis. Uma ação também contém uma declaração condicional:

| Conjunto de regras | Valor |
| Ação | [!UICONTROL Substituir o valor de ] eVar55 por `spa.billing_customer_name` (Dados de contexto) |
| Ação | [!UICONTROL Substituir o valor de ] Prop7 por `testhierarchy` (Dados de contexto), se `testhierarchy` (Dados de contexto) estiver definido |
| Ação | [!UICONTROL Substituir o valor de ] eVar8 por `spa.ims_org` (Dados de contexto) |

![Captura de tela da interface de regras de processamento mostrando como definir condicionalmente um valor](assets/add-conditional.png)

+++

+++Definir um evento usando uma variável de dados de contexto

As regras de processamento podem acionar eventos com base em [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md).

A lista [!UICONTROL Variáveis de contexto] contém todas as variáveis que foram enviadas para o conjunto de relatórios nos últimos 30 dias. Se você sabe o nome da variável de dados de contexto, mas não a enviou para o conjunto de relatórios atual, é possível adicioná-la manualmente:

![Adicionando manualmente uma variável de dados de contexto a uma regra de processamento](assets/add-context-variable.png)

A definição de regra a seguir define um evento em cada ocorrência que contém uma variável de dados de contexto específica:

| Conjunto de regras | Valor |
| --- | --- |
| Condição | `search_term` (Dados de contexto) está definido |
| Ação | [!UICONTROL Definir evento] Evento1 como [!UICONTROL Valor Personalizado] `1` |

![Captura de tela da interface de regras de processamento mostrando como definir um evento](assets/processing_rule_set_event.png)

+++

+++Preencher uma variável usando um parâmetro da cadeia de caracteres de consulta

É possível preencher uma variável usando um parâmetro da string de consulta. Na maioria dos casos, você normalmente ajusta sua implementação para obter os valores da sequência de consulta desejados. No entanto, se você não conseguir ajustar facilmente sua implementação para coletar esses dados, as regras de processamento serão uma alternativa adequada. Se um erro de digitação ou problema semelhante impedir o preenchimento do valor, a variável poderá ser preenchida por regras de processamento.

Sempre verifique se um valor está vazio ou contém o valor esperado antes de substituí-lo.

| Conjunto de regras | Valor |
| --- | --- |
| Condição | A campanha não está definida |
| Ação | [!UICONTROL Substituir valor de] Campanha por [!UICONTROL Parâmetro de Cadeia de Caracteres de Consulta] `cpid` |

![Captura de tela da interface de regras de processamento mostrando a lógica de campanha condicional](assets/set-campaign-conditionally.png)

| Conjunto de regras | Valor |
| --- | --- |
| Condição | [!UICONTROL Parâmetro Da Cadeia De Caracteres De Consulta] `q` [!UICONTROL Está Definido] |
| Ação | [!UICONTROL Substituir valor de] termos de pesquisa interna por [!UICONTROL Parâmetro da Cadeia de Caracteres de Consulta] `q` |

![Captura de tela da interface de regras de processamento mostrando a lógica interna do termo de pesquisa](assets/populate-internal-search-terms.png)

+++

+++Definir condicionalmente qualquer evento

Eventos podem ser definidos com base em qualquer condição disponível nas regras de processamento. Por exemplo, é possível acionar um evento quando o nome da página é igual a &quot;Visão geral do produto&quot;.

| Conjunto de regras | Valor |
| --- | --- |
| Condição | Se [!UICONTROL Nome Da Página] For Igual A &quot;Visão Geral Do Produto&quot; |
| Ação | [!UICONTROL Definir evento] [!UICONTROL Exibições do Produto] como [!UICONTROL Valor Personalizado] `1` |

![Captura de tela da interface de regras de processamento mostrando um conjunto de eventos condicionalmente](assets/set-product-view-event.png)

+++

+++Adicionar uma subcategoria pela concatenação da categoria e do nome da página

Você pode usar a opção de concatenar para preencher valores combinando outros valores.

| Conjunto de regras | Valor |
| --- | --- |
| Condição | Nenhum (Sempre executar) |
| Ação | [!UICONTROL Substituir o valor de ] eVar1 por [!UICONTROL Valor Concatenado] Categoria + Nome da Página |

![Captura de tela da interface de regras de processamento mostrando um valor concatenado](assets/add-subcategory-using-concat.png)

+++

+++Limpar valores em um relatório

Você pode fazer a correspondência de valores com os erros ortográficos coletados e atualizá-los para exibi-los corretamente nos relatórios.

A Adobe recomenda usar a opção de correspondência mais restritiva possível para evitar substituições indesejadas. Você pode executar um relatório sobre a variável e procurar possíveis condições de regra que deseja usar. As comparações de cadeias de caracteres não diferenciam maiúsculas de minúsculas.

| Conjunto de regras | Valor |
| --- | --- |
| Condição | Se prop1 [!UICONTROL Começa com] &quot;[!DNL Shoping]&quot; |
| Ação | [!UICONTROL Substituir o valor de] Prop1 por [!UICONTROL Valor Personalizado] &quot;[!DNL Shopping]&quot; |

![Captura de tela da interface de regras de processamento mostrando como corrigir um erro de digitação](assets/clean-up-values-in-report.png)

+++

+++Remover um evento de uma ocorrência

Você pode remover ou descartar um evento específico de uma ocorrência usando regras de processamento sem alterar a implementação do. Se você definir o evento com o valor personalizado `0`, o evento não contará.

| Conjunto de regras | Valor |
| Condição | Nenhum (Sempre executar) |
| Ação | [!UICONTROL Definir evento] Evento1 como [!UICONTROL Valor personalizado] `0` |

![Captura de tela da interface de regras de processamento mostrando como remover um evento](assets/remove_event.png)

+++
