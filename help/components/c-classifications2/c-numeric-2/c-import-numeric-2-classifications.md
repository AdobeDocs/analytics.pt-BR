---
description: A importação e exportação arquivos inclui seis colunas para cada classificação numérica 2.
seo-description: A importação e exportação arquivos inclui seis colunas para cada classificação numérica 2.
seo-title: Importar classificações numéricas 2
solution: Analytics
subtopic: Classificações
title: Importar classificações numéricas 2
topic: Ferramentas administrativas
uuid: 82 a 3034 c-e 002-4991-900 f -22 dd 45 d 54d 54
translation-type: tm+mt
source-git-commit: 49e149fe57d5d66b8eda22b1bdf60e7c6200761c

---


# Importar classificações numéricas 2

>[!IMPORTANT]
>
>A capacidade de importar classificações Numérico 2 e Ativadas por data foi removida da base de código. Essa alteração será aplicada na Versão de manutenção de julho de 2019. Se você tiver colunas Numéricas ou Ativadas por data no arquivo de importação, essas células serão ignoradas silenciosamente e todos os outros dados nesse arquivo serão importados normalmente. As classificações existentes ainda podem ser exportadas por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

A importação e exportação arquivos inclui seis colunas para cada classificação numérica 2.

As definições a seguir pressupõem que o nome de sua classificação numérica 2 é MyCost.

**~MyCost:** Um nome descritivo para a linha.

**~ Mycost ^~id~:** A ID para editar uma linha existente. Quando uma nova linha é adicionada, ela deve estar em branco. Uma ID é automaticamente atribuída quando você exporta a partir do Gerenciador de classificação.

**~MyCost^~value~: **The value for the row. Se a coluna taxa é fixa, então este é um valor fixo distribuído durante todo o período. Se a coluna taxa é um evento, então este é o multiplicador para o evento. Esta entrada não deve conter vírgulas.

**~ Mycost ^~período~:** O período para o qual esta linha corresponde. Isso deve incluir uma data inicial e final, separadas por um traço. O traço deve ficar entre espaços. A definição deve ser formatada da seguinte maneira:

AAAA/MM/DD - AAAA/MM/DD

**~ Mycost ^~rate~:** O evento a ser multiplicado pela [!UICONTROL coluna Valor] . Os valores válidos são:

* fixo - usado para indicar que o valor é um valor fixo a ser distribuídos durante o período.
* receita
* pedido
* unit
* scopen
* scviews
* instance
* click
* checkout
* scadd
* scremove
* event 1
* event 2
* etc.

**~ Mycost ^~hinge~:** O evento a ser usado para distribuir o valor durante uma análise. This value is often the same as [!UICONTROL ~MyCost^~rate~], unless you are using [!UICONTROL fixed]. The valid values for this column are identical to that of [!UICONTROL ~MyCost^~rate~], with the addition of [!UICONTROL none].
