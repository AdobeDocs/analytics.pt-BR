---
description: Classificações são usadas para categorizar valores em grupos e relatórios no nível de grupo. Por exemplo, você pode classificar todas as campanhas de Pesquisa paga em uma categoria como termos de música pop e relatar o sucesso dessa categoria com relação a métricas como Instâncias (click-throughs) e a conversão para eventos bem-sucedidos.
title: Classificações de conversão
feature: Classifications
role: Admin
exl-id: b4855000-adf3-4e3b-af36-f4803383126d
TQID: https://experienceleague.adobe.com/k8wtT-XfijkEOgPHw4j78mm8Da4BA4V3TVVfW6fpCp4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 526
ht-degree: 74%

---

# Classificações de conversão

Classificações são usadas para categorizar valores em grupos e relatórios no nível de grupo. Por exemplo, você pode classificar todas as campanhas de [!UICONTROL Pesquisa paga] em uma categoria como *termos de música pop* e relatar o sucesso dessa categoria com relação a métricas como Instâncias (click-throughs) e a conversão para eventos bem-sucedidos. É possível adicionar até 255 classificações a uma variável.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Classificações de Conversão]**

As classificações de conversão permitem classificar variáveis de conversão. Depois de classificado, qualquer relatório que você gerar usando os dados principais também poderá ser gerado usando as propriedades dos dados associados.

>[!WARNING]
>
>Renomear uma classificação pode causar problemas com as regras existentes criadas no [Construtor de regras de classificação](/help/components/classifications/crb/classification-rule-builder.md). Se você renomear uma classificação que tenha regras de classificação, corrija cada regra para que ela aponte para a classificação renomeada.

## Descrições de classificações de conversão

| Elemento | Descrição |
| --- | --- |
| Nome | O nome da classificação |
| Habilitado por data (somente texto) | Indica se a classificação de texto é um intervalo de datas para variáveis de campanha. |
| Opções (somente texto) | Cria uma lista de valores de classificação disponíveis para esta classificação. Use as opções com variáveis de campanha para fornecer aos usuários uma lista dos valores suportados com a classificação no Gerenciador de campanhas. |
| Tipo de número (somente numérico) | Especifica o tipo de número na classificação numérica. As opções incluem Numérico, Porcentagem e Moeda. |

## Adicionar classificações de conversão

Para adicionar classificações de conversão no Admin:

1. Clique em **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Classificações de conversão]**.
1. Na lista suspensa **[!UICONTROL Selecionar tipo de classificação]**, selecione a variável à qual deseja adicionar uma classificação.

   ![Informações da etapa](/help/admin/tools/assets/sub_class_create.png)

1. Passe o mouse sobre o ícone **[!UICONTROL Editar classificação]**, em seguida **[!UICONTROL Adicionar classificação]**.
1. Na caixa de diálogo **[!UICONTROL Classificações de texto]**, configure a classificação como desejado.

1. Adicionar ou remover opções na caixa de diálogo da lista suspensa.

   Adicionar opções cria uma lista de valores de classificação disponíveis para essa classificação. Você pode usar esta opção com variáveis de Campanha para fornecer aos usuários uma lista dos valores suportados para a classificação no Gerenciador de campanhas. Use isso para dimensões de classificação em que você tem um pequeno número de valores permitidos que raramente ou nunca mudam. Por exemplo, você pode executar campanhas diferentes destinadas a diferentes níveis de fidelidade do cliente: prata, ouro e platina. Em seguida, você pode usar a lista suspensa para garantir que os únicos valores aceitos sejam aqueles que correspondem aos seus três níveis. Se alguém tentar usar um valor diferente, ele será descartado.

1. Clique em **[!UICONTROL Salvar]**.

## Excluir uma classificação de conversão

Exclua uma classificação de conversão quando ela não for mais necessária.

1. Abra o Gerenciador de conjunto de relatórios clicando em **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** no cabeçalho do Suite.
1. Selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Classificações de conversão]**.
1. Na lista suspensa **[!UICONTROL Selecionar tipo de classificação]**, selecione a variável da qual deseja excluir uma classificação.
1. Passe o mouse sobre o ícone **[!UICONTROL Editar classificação]**, em seguida selecione **[!UICONTROL Excluir classificação]**.
1. Na caixa de diálogo Excluir classificação, clique em **[!UICONTROL Excluir]**.
