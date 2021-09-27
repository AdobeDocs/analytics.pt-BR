---
description: Use segmentos rápidos no Analysis Workspace.
title: Segmentos rápidos
feature: Workspace Basics
role: User, Admin
source-git-commit: 313b4288774163b681f37da44fe2f3cc99abe28d
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 1%

---


# Segmentos rápidos

Você pode criar segmentos rápidos em um projeto para ignorar a complexidade do [construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) completo. Segmentos rápidos

* Aplicar somente a projetos específicos (você pode alterar isso).
* Permitir até 3 regras
* Não acomode contêineres aninhados ou regras sequenciais.
* Trabalhar em painéis com vários conjuntos de relatórios

Para uma comparação do que os segmentos rápidos podem fazer em relação aos segmentos da lista de componentes completos, acesse [aqui](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Os segmentos rápidos estão atualmente em testes limitados e ainda não estão disponíveis no geral.

## Pré-requisitos

Os usuários precisam da permissão [!UICONTROL Criação de segmentos] no [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools) para poderem criar segmentos rápidos.

## Criar segmentos rápidos

Em uma tabela de Forma livre, clique no ícone filter+ no cabeçalho do painel:

![](assets/quick-seg1.png)

| Configuração | Descrição |
| --- | --- |
| Nome | O nome padrão de um segmento é uma combinação dos nomes das regras no segmento. Você pode renomear o segmento. |
| Incluir/excluir | Você pode incluir ou excluir componentes na definição do seu segmento, mas não ambos. |
| Contêiner de Ocorrência/Visita/Visitante | Os segmentos rápidos incluem um [contêiner de segmento](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=en#section_AF2A28BE92474DB386AE85743C71B2D6) somente que permite incluir uma dimensão/métrica/intervalo de datas no (ou excluí-lo) segmento.  O Visitante contém dados abrangentes específicos para visitantes em visitas e visualizações de página. Um contêiner de [!UICONTROL Visita] permite definir regras para detalhar os dados do visitante com base em visitas e um contêiner de [!UICONTROL Ocorrência] permite detalhar as informações do visitante com base em visualizações de página individuais. O contêiner padrão é [!UICONTROL Hit]. |
| Componentes (Dimension/métrica/intervalo de datas) | Defina até 3 regras adicionando dimensões e/ou métricas de componentes e/ou intervalos de datas e seus valores. Há 3 maneiras de encontrar o componente correto:<ul><li>Comece a digitar e o construtor [!UICONTROL Quick Segment] encontra automaticamente o componente apropriado.</li><li>Use a lista suspensa para localizar o componente.</li><li>Arraste e solte componentes do painel esquerdo.</li></ul> |
| Operador | Use o menu suspenso para encontrar operadores padrão e operadores [!UICONTROL Distinct Count]. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=en) |
| Sinal de mais (+) | Adicionar outra regra |
| Qualificadores E/OU | Você pode adicionar qualificadores &quot;AND&quot; ou &quot;OR&quot; às regras, mas não pode misturar &quot;AND&quot; e &quot;OR&quot; em uma única definição de segmento. |
| Aplicar | Aplique este segmento ao painel. Se o segmento não contiver dados, você será perguntado se deseja continuar. |
| Abrir builder | Abre o Construtor de segmentos. Depois de salvar o segmento no Construtor de segmentos, ele não é mais considerado um &quot;Segmento rápido&quot;. Ele se torna parte da biblioteca de segmentos da lista de componentes. |
| Cancelar | Cancele esse segmento rápido - não o aplique. |
| Intervalo de datas | O validador usa o intervalo de datas do painel para sua pesquisa de dados. Mas qualquer intervalo de datas aplicado em um segmento rápido substitui o intervalo de datas do painel na parte superior do painel. |
| Visualização (canto superior direito) | Permite ver se você tem um segmento válido e a amplitude deste. Representa o detalhamento do conjunto de dados que você pode esperar ver ao aplicar esse segmento. você pode receber um aviso que indica que esse segmento não tem dados. Você pode continuar ou alterar a definição do segmento. |

Este é um exemplo de um segmento que combina dimensões e métricas:

![](assets/quick-seg2.png)

O segmento aparece na parte superior. Observe a barra lateral com listras azuis, em vez da barra lateral azul para segmentos de nível de componente na biblioteca de segmentos à esquerda.

![](assets/quick-seg3.png)

## Editar segmentos rápidos

1. Passe o mouse sobre o segmento rápido e selecione o ícone de lápis.
1. Edite a definição do segmento ou o nome do segmento.

## Salvar segmentos rápidos

Você pode optar por salvar segmentos rápidos no [!UICONTROL Construtor de segmentos rápido] ou no [!UICONTROL Construtor de segmentos].

>[!IMPORTANT]
>Depois de salvar ou aplicar o segmento, não é mais possível editá-lo no Construtor de segmentos rápido, somente no Construtor de segmentos comum.

### Salvar no construtor de Segmentos rápidos

1. Depois de aplicar o segmento rápido, passe o mouse sobre ele e selecione o ícone de informações (&quot;i&quot;).
1. Clique em **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes]**.
1. (Opcional) Renomeie o segmento.
1. Clique em **[!UICONTROL Salvar]**.

Observe como a barra lateral do segmento muda de azul listrado para azul. Agora ele aparece na lista de componentes no painel esquerdo.

### Salvar no Construtor de segmentos

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

Os segmentos somente do projeto são segmentos rápidos ou segmentos de projeto ad-hoc do Workspace. Ao editá-los/abri-los no [!UICONTROL Construtor de segmentos], a caixa somente do projeto será exibida. Se você APLICAR um segmento rápido no construtor, mas não marcar a caixa disponibilizar , ele ainda será um segmento somente do projeto, mas não poderá mais ser aberto no [!UICONTROL Quick Segment Builder]. Se marcar a caixa e clicar em **[!UICONTROL SAVE]**, agora é um segmento da lista de componentes.