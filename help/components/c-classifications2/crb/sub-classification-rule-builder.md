---
description: É possível combinar o Construtor de regras de classificação com subclassificações para simplificar o gerenciamento de classificações e reduzir o número de regras necessário. Você pode querer fazer isso se o código de rastreamento consiste em códigos que você deseja classificar separadamente.
solution: Analytics
subtopic: Classifications
title: Subclassificações e o construtor de regras - caso de uso
topic: Admin tools
uuid: 6db6a4a9-b93c-413b-8049-1e6cc1ba4a38
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Subclassificações e o construtor de regras - caso de uso

É possível combinar o Construtor de regras de classificação com subclassificações para simplificar o gerenciamento de classificações e reduzir o número de regras necessário. Você pode querer fazer isso se o código de rastreamento consiste em códigos que você deseja classificar separadamente.

## Subclassificações e o construtor de regras - caso de uso {#concept_6C8672C242544D7487E82886BBFABE6E}

É possível combinar o Construtor de regras de classificação com subclassificações para simplificar o gerenciamento de classificações e reduzir o número de regras necessário. Você pode querer fazer isso se o código de rastreamento consiste em códigos que você deseja classificar separadamente.

See [Sub-Classifications](/help/components/c-classifications2/c-sub-classifications.md) for conceptual information about sub-classifications.

**Exemplo**

Assume o seguinte código de rastreamento:

`channel:broad_campaign:creative`

Uma hierarquia de classificação permite aplicar uma classificação a uma classificação (chamada de *`sub-classification`*). Ou seja, você pode utilizar o importador como um banco de dados de relações com várias tabelas. Uma tabela mapeia códigos de rastreamento completos e o outro mapeia essas teclas para outras tabelas.

![](assets/sub_class_table.png)

Depois de colocar essa estrutura no lugar, é possível utilizar [Construtor de regras de classificação](/help/components/c-classifications2/crb/classification-rule-builder.md) para carregar arquivos pequenos que atualizam apenas as tabelas de pesquisa (as tabelas verde e vermelha na imagem anterior). Em seguida, você pode utilizar o construtor de regras para manter a tabela de classificação principal atualizada.

A seguinte tarefa descreve como fazer isso.

## Set up Sub-Classifications using the Rule Builder{#task_2D9016D8B4E84DBDAF88555E5369546F}

<!-- 

t_rule_builder_subclass.xml

 -->

Exemplo de etapas que descrevem como você pode fazer upload de subclassificações usando o Construtor de regras.

>[!NOTE]
>
>Essas etapas descrevem como realizar o caso de uso descrito em [Subclassificações e o Construtor](/help/components/c-classifications2/crb/sub-classification-rule-builder.md)de regras.

1. Criar classificações e subclassificação no [Gerenciador de classificações](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html).

   Exemplo:

   ![Informações da etapa](assets/sub_class_create.png)

1. In the [Classifications Rule Builder](/help/components/c-classifications2/crb/classification-rule-builder.md), classify the sub-classification key from the original tracking code.

   Isso é realizado utilizando uma expressão regular. Nesse exemplo, a regra é preencher *`Broad Campaign code`* usaria essa expressão regular:

   | `#` | Tipo de regra | Correspondência | Definir a classificação | Para |
   |---|---|---|---|---|
   |  | Expressão regular | `[^\:]:([^\:]):([^\:]`) | Código de campanha ampla | `$1` |
   |  | Expressão regular | `[^\:]:([^\:]):([^\:]`) | Código criativo | `$2` |

   >[!NOTE]
   >
   >At this point, you do not populate the sub-classifications *`Campaign Type`* and *`Campaign Director`*.

1. Fazer upload de um arquivo de classificação que inclui somente as subclassificações especificadas.

   Consulte Classificações [](/help/components/c-classifications2/c-sub-classifications.md)de vários níveis.

   Exemplo:

   | Chave | Canal | Código de campanha ampla | Código de Campanha &amp;Ampla;Chapéu;Tipo de campanha | Código de Campanha Amplo &amp;Chapéu;Diretor de Campanha | ... |
   |---|---|---|---|---|---|
   | * |  | 111 | Marca | Suzanne |  |
   | * |  | 222 | Marca | Frank |  |

1. Para manter as tabelas de pesquisa, carregue um pequeno arquivo (como mostrado acima).

   You would upload this file, for example, when a new *`Broad Campaign code`* is introduced. Esse arquivo seria aplicado aos valores classificados anteriormente. Da mesma maneira, se você criar uma nova subclassificação (como *`Creative Theme`* como uma subclassificação de *`Creative code`*), você carrega somente o arquivo de subclassificação, em vez do arquivo de classificação inteiro.

   Em relatórios, essas subclassificações funcionam exatamente como classificações de nível superior. Isso diminui a responsabilidade administrativa necessária para usá-las. 
