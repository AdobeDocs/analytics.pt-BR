---
description: Use segmentos rápidos no Analysis Workspace.
title: Segmentos rápidos
feature: Workspace Basics
role: User, Admin
source-git-commit: f3185f1ee341348fb7bdbaab8b68d421e7c79076
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---


# Segmentos rápidos

Você pode criar segmentos rápidos em um projeto para ignorar a complexidade do [construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) completo. Para uma comparação do que os segmentos rápidos podem fazer em relação aos segmentos da lista de componentes completos, acesse [aqui](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Os segmentos rápidos estão atualmente em testes limitados e ainda não estão disponíveis no geral.

## Criar segmentos rápidos

1. Em uma tabela de Forma livre, clique no ícone filter+ no cabeçalho do painel:

   ![](assets/quick-seg1.png)

   Observe que:

   - Há apenas um contêiner de segmento que permite incluir uma dimensão/métrica/intervalo de datas no segmento (ou excluí-lo dele).
   - É possível definir o contêiner como nível de Ocorrência, Visita ou Visitante. O padrão é Ocorrência.

1. Adicione uma dimensão/métrica/intervalo de datas de uma das três formas a seguir:

   - Comece a digitar e o [!UICONTROL Construtor de segmento rápido] encontra automaticamente o componente apropriado.
   - Use a lista suspensa para localizar o componente.
   - Arraste e solte componentes do painel esquerdo.

1. Especifique a primeira regra, como `Page equals workspace`. É possível ter até três regras em uma definição de segmento. Basta clicar no sinal &quot;+&quot; para adicionar outra regra. Você pode adicionar qualificadores &quot;AND&quot; ou &quot;OR&quot; às regras, mas não pode misturar &quot;AND&quot; e &quot;OR&quot; em uma única definição de segmento.

   Este é um exemplo de um segmento que combina dimensões e métricas:

   ![](assets/quick-seg2.png)

1. Clique em **[!UICONTROL Aplicar]** para aplicar este segmento ao painel.
O segmento aparece na parte superior. Observe sua barra lateral cinza, em oposição à barra lateral azul para segmentos de nível de componente na biblioteca de segmentos à esquerda.

   ![](assets/quick-seg3.png)

## Editar segmentos rápidos

1. Passe o mouse sobre o segmento rápido e selecione o ícone de lápis.
1. Edite a definição do segmento ou o nome do segmento.

## Salvar segmentos rápidos

Você pode optar por salvar segmentos rápidos seguindo essas etapas.

>[!IMPORTANT]
>Depois de salvar ou aplicar o segmento, não é mais possível editá-lo no Construtor de segmentos rápido, somente no Construtor de segmentos comum.

1. Passe o mouse sobre o segmento rápido e selecione o ícone de informações (&quot;i&quot;).
1. Selecione **[!UICONTROL Salvar segmento]**

   ![](assets/save-quick-seg.png)

1. Deixe o nome como está ou renomeie o segmento.

   Retorne ao Workspace e observe como o segmento agora tem uma barra lateral azul. Isso indica que ele não pode mais ser editado/aberto no Construtor de segmento rápido. E ao salvá-lo, ele se torna parte da lista de componentes.

   ![](assets/quick-seg4.png)

Depois de aplicar o segmento, você pode optar por adicioná-lo à lista de componentes do segmento e disponibilizá-lo para todos os seus projetos.

1. Passe o mouse sobre o segmento salvo e selecione o ícone de lápis.

1. Na parte superior do Construtor de segmentos, observe esta caixa de diálogo:

   ![](assets/project-only.png)

1. Marque a caixa de seleção ao lado de **[!UICONTROL Disponibilize este segmento para todos os projetos e adicione-o à lista de componentes.]**
1. Clique em **[!UICONTROL Salvar]**.
1. O segmento agora aparece na lista de componentes do segmento para todos os seus projetos.
1. Você também pode [compartilhar o segmento](/help/components/segmentation/segmentation-workflow/t-seg-share.md) com outras pessoas em sua organização.

## O que são segmentos somente de projeto?

Os segmentos somente do projeto são segmentos rápidos ou segmentos de projeto ad-hoc do Workspace. Ao editá-los/abri-los no construtor de segmentos, a caixa somente do projeto será exibida. Se eles APLICAREM um segmento rápido no construtor, mas não marcarem a caixa disponibilizar , ele ainda será um segmento somente de projeto, mas não poderá mais ser aberto no construtor de QS. Se eles marcarem a caixa e SALVAR, agora é um segmento da lista de componentes.