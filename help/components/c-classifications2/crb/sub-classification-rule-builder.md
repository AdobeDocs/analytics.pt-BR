---
description: É possível combinar o Construtor de regras de classificação com subclassificações para simplificar o gerenciamento de classificações e reduzir o número de regras necessário. Você pode querer fazer isso se o código de rastreamento consiste em códigos que você deseja classificar separadamente.
seo-description: É possível combinar o Construtor de regras de classificação com subclassificações para simplificar o gerenciamento de classificações e reduzir o número de regras necessário. Você pode querer fazer isso se o código de rastreamento consiste em códigos que você deseja classificar separadamente.
seo-title: Subclassificações e o Construtor de regras - caso de uso
solution: Analytics
subtopic: Classificações
title: Subclassificações e o Construtor de regras - caso de uso
topic: Ferramentas administrativas
uuid: 6 db 6 a 4 a 9-b 93 c -413 b -8049-1 e 6 cc 1 ba 4 a 38
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Subclassificações e o Construtor de regras - caso de uso

É possível combinar o Construtor de regras de classificação com subclassificações para simplificar o gerenciamento de classificações e reduzir o número de regras necessário. Você pode querer fazer isso se o código de rastreamento consiste em códigos que você deseja classificar separadamente.

## Sub-classifications and the Rule Builder - use case {#concept_6C8672C242544D7487E82886BBFABE6E}

É possível combinar o Construtor de regras de classificação com subclassificações para simplificar o gerenciamento de classificações e reduzir o número de regras necessário. Você pode querer fazer isso se o código de rastreamento consiste em códigos que você deseja classificar separadamente.

See [Sub-Classifications](../../../components/c-classifications2/c-sub-classifications.md#concept_19EE5513A7DC43C38CC396E96F306CFE) for conceptual information about sub-classifications.

**Exemplo**

Assume o seguinte código de rastreamento:

`channel:broad_campaign:creative`

Uma hierarquia de classificação permite aplicar uma classificação a uma classificação (chamada de *`sub-classification`*). Ou seja, você pode utilizar o importador como um banco de dados de relações com várias tabelas. Uma tabela mapeia códigos de rastreamento completos e o outro mapeia essas teclas para outras tabelas.

![](assets/sub_class_table.png)

Depois de colocar essa estrutura no lugar, é possível utilizar [Construtor de regras de classificação](../../../components/c-classifications2/crb/classification-rule-builder.md) para carregar arquivos pequenos que atualizam apenas as tabelas de pesquisa (as tabelas verde e vermelha na imagem anterior). Em seguida, você pode utilizar o construtor de regras para manter a tabela de classificação principal atualizada.

A seguinte tarefa descreve como fazer isso.

## Set up Sub-Classifications using the Rule Builder{#task_2D9016D8B4E84DBDAF88555E5369546F}

<!-- 

t_rule_builder_subclass.xml

 -->

Exemplo de etapas que descrevem como você pode fazer upload de subclassificações usando o Construtor de regras.

>[!NOTE]
>
>These steps describe how to accomplish the use case described in [Sub-Classifications and the Rule Builder](../../../components/c-classifications2/crb/sub-classification-rule-builder.md).

1. Criar classificações e subclassificação no [Gerenciador de classificações](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=classifications).

   Exemplo:

   ![Informações da etapa](assets/sub_class_create.png)

1. In the [Classifications Rule Builder](../../../components/c-classifications2/crb/classification-rule-builder.md#concept_C1F219E622044D43852EF5168FF7192A), classify the sub-classification key from the original tracking code.

   Isso é realizado utilizando uma expressão regular. Nesse exemplo, a regra é preencher *`Broad Campaign code`* usaria essa expressão regular:

   | `#` | Tipo de regra | Correspondência | Definir a classificação | Para |
   |---|---|---|---|---|
   |  | Expressão regular | `[^\:]:([^\:]):([^\:]`) | Código de campanha ampla | `$1` |
   |  | Expressão regular | `[^\:]:([^\:]):([^\:]`) | Código criativo | `$2` |

   >[!NOTE]
   >
   >At this point, you do not populate the sub-classifications *`Campaign Type`* and *`Campaign Director`*.

1. Fazer upload de um arquivo de classificação que inclui somente as subclassificações especificadas.

   See [Multiple-Level Classifications](../../../components/c-classifications2/c-sub-classifications.md#concept_35AD906CDDC4441DAAF70664CF76AA0A).

   Exemplo:

   | Chave | Canal | Código de campanha ampla | Código de campanha ampla e amp; Hat; Tipo de campanha | Código de campanha ampla e amp; Hat; Diretor de campanha | ... |
   |---|---|---|---|---|---|
   | * |  | 111 | Marca | Suzanne |  |
   | * |  | 222 | Marca | Frank |  |

1. Para manter as tabelas de pesquisa, carregue um pequeno arquivo (como mostrado acima).

   You would upload this file, for example, when a new *`Broad Campaign code`* is introduced. Esse arquivo seria aplicado aos valores classificados anteriormente. Da mesma maneira, se você criar uma nova subclassificação (como *`Creative Theme`* como subclassificação de *`Creative code`*), você carrega apenas o arquivo de subclassificação, em vez do arquivo de classificação inteiro.

   Em relatórios, essas subclassificações funcionam exatamente como classificações de nível superior. Isso diminui a responsabilidade administrativa necessária para usá-las. 
