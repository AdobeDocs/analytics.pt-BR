---
description: A importação e exportação arquivos inclui seis colunas para cada classificação numérica 2.
subtopic: Classifications
title: Importar classificações numéricas 2
topic: Admin tools
uuid: 82a3034c-e002-4991-900f-22dd45d54910
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Importar classificações numéricas 2

>[!IMPORTANT]
>
>A capacidade de importar classificações Numérico 2 e Ativadas por data foi removida da base de código. Essa alteração será aplicada na Versão de manutenção de julho de 2019. Se você tiver colunas Numéricas ou Ativadas por data no arquivo de importação, essas células serão ignoradas silenciosamente e todos os outros dados nesse arquivo serão importados normalmente. As classificações existentes ainda podem ser exportadas por meio do fluxo de trabalho de classificação padrão, e continuarão disponíveis nos relatórios.

A importação e exportação arquivos inclui seis colunas para cada classificação numérica 2.

As definições a seguir pressupõem que o nome de sua classificação numérica 2 é MyCost.

**~MyCost:** Um nome descritivo para a linha.

**~MyCost^~id~:** A ID para editar uma linha existente. Quando uma nova linha é adicionada, ela deve estar em branco. Uma ID é automaticamente atribuída quando você exporta a partir do Gerenciador de classificação.

**~MyCost^~value~:** O valor da linha. Se a coluna taxa é fixa, então este é um valor fixo distribuído durante todo o período. Se a coluna taxa é um evento, então este é o multiplicador para o evento. Esta entrada não deve conter vírgulas.

**~MyCost^~period~:** O período ao qual esta linha corresponde. Isso deve incluir uma data inicial e final, separadas por um traço. O traço deve ficar entre espaços. A definição deve ser formatada da seguinte maneira:

AAAA/MM/DD - AAAA/MM/DD

**~MyCost^~rate~:** O evento a ser multiplicado pela coluna [!UICONTROL Valor]. Os valores válidos são:

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
* evento 1
* evento 2
* etc.

**~MyCost^~hinge~:** O evento a ser usado para distribuir o valor, durante uma análise. Este valor é frequentemente o mesmo que [!UICONTROL ~MyCost^~rate~], a menos que esteja usando [!UICONTROL fixo]. Os valores válidos para esta coluna são idênticos ao do [!UICONTROL ~MyCost^~rate~], com a adição de [!UICONTROL nenhum].
