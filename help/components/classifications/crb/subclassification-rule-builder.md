---
description: Use subclassificações com o construtor de regras de classificação.
title: Subclassificações e o Construtor de regras
feature: Classifications
exl-id: 745d6149-bcb1-48ad-abbe-63a9d009fa27
TQID: https://experienceleague.adobe.com/Qlqt3scXHVUv6EODq57zzaF2007Vvf5x324CHjrsNE0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 403
ht-degree: 47%

---

# Subclassificações e o construtor de regras (herdado)

{{classification-rulebuilder-deprecation}}

É possível combinar o Construtor de regras de classificação com subclassificações se você garantir que cada subclassificação tenha um valor principal.

É possível combinar o Construtor de regras de classificação com subclassificações para simplificar o gerenciamento de classificações e reduzir o número de regras necessário. Você pode querer fazer isso se o código de rastreamento consiste em códigos que você deseja classificar separadamente.

Consulte [Subclassificação](/help/components/classifications/importer/subclassifications.md) para informações conceituais sobre subclassificações.

## Exemplo

Assume o seguinte código de rastreamento:

`channel:broad_campaign:creative`

Uma hierarquia de classificação permite aplicar uma classificação a uma classificação (chamada de *`sub-classification`*). Ou seja, você pode usar o importador como um banco de dados relacional, com várias tabelas. Uma tabela mapeia os códigos completos de rastreamento para as chaves do e outra mapeia essas chaves para outras tabelas.

![](assets/sub_class_table.png)

Depois que essa estrutura estiver estabelecida, você poderá usar o [Construtor de regras de classificação](/help/components/classifications/crb/classification-rule-builder.md) para carregar arquivos pequenos que atualizam apenas as tabelas de pesquisa (as tabelas verde e vermelha na imagem anterior). Em seguida, você pode usar o construtor de regras para manter a tabela de classificação principal atualizada.

A tarefa a seguir descreve como fazer isso.

## Configurar subclassificações usando o Construtor de regras

Exemplo de etapas que descrevem como você pode fazer upload de subclassificações usando o Construtor de regras.

1. Criar classificações e subclassificações no Gerenciador de classificações.

   Exemplo:

   ![Informações da etapa](/help/admin/tools/assets/sub_class_create.png)

1. No [Construtor de regras de classificações](/help/components/classifications/crb/classification-rule-builder.md), classifique a chave de subclassificação do código de rastreamento original.

   Isso é realizado utilizando uma expressão regular. Neste exemplo, a regra para preencher *`Broad Campaign code`* usaria esta expressão regular:

   | `#` | Tipo de regra | Corresponder | Definir a classificação | Para |
   |---|---|---|---|---|
   |   | Expressão regular | `[^\:]:([^\:]):([^\:])` | Código de campanha ampla | `$1` |
   |   | Expressão regular | `[^\:]:([^\:]):([^\:])` | Código criativo | `$2` |

   >[!NOTE]
   >
   >Nesse ponto, você não preenche as subclassificações *`Campaign Type`* e *`Campaign Director`*.

1. Fazer upload de um arquivo de classificação que inclui somente as subclassificações especificadas.

   Consulte [Classificações de vários níveis](/help/components/classifications/importer/subclassifications.md).

   Exemplo:

   | Chave | Canal | Código de campanha ampla | Código de campanha ampla&amp;Hat;Tipo de campanha | Código de campanha ampla&amp;Hat;Diretor de campanha | ... |
   |---|---|---|---|---|---|
   | &#42; |  | 111 | Marca | Suzanne |  |
   | &#42; |  | 222 | Marca | Frank |  |

1. Para manter as tabelas de pesquisa, carregue um pequeno arquivo (como mostrado acima).

   Esse arquivo é carregado quando, por exemplo, um novo *`Broad Campaign code`* é introduzido. Esse arquivo seria aplicado aos valores classificados anteriormente. Da mesma forma, se você criar uma nova subclassificação (como *`Creative Theme`* como uma subclassificação de *`Creative code`*), você fará upload somente do arquivo de subclassificação, em vez do arquivo de classificação inteiro.

   Para o relatório, essas subclassificações funcionam exatamente como classificações de nível superior. Isso diminui a responsabilidade administrativa necessária para usá-las.
