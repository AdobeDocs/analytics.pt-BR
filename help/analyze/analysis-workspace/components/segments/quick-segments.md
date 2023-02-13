---
description: Use segmentos rápidos no Analysis Workspace.
title: Segmentos rápidos
feature: Segmentation
role: User, Admin
exl-id: 680e7772-10d3-4448-b5bf-def3bc3429d2
source-git-commit: 86fc28375d62d9f1d71d0b239ea0e2038fae47e4
workflow-type: ht
source-wordcount: '943'
ht-degree: 100%

---

# Segmentos rápidos

Você pode criar segmentos rápidos em um projeto para ignorar a complexidade do [Criador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) completo. Segmentos rápidos

* Aplicar como [segmentos somente de projeto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=pt-BR#what-are-project-only-segments).
* Permita até 3 regras.
* Não acomode containers aninhados ou regras sequenciais.

Para ver o que os segmentos rápidos podem fazer em comparação aos segmentos completos da lista de componentes, clique [aqui](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

Aqui está uma visão geral em vídeo dos segmentos rápidos:

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Pré-requisitos

Qualquer pessoa pode criar um [!UICONTROL Segmento rápido]. No entanto, é necessário ter a permissão [!UICONTROL Criação de segmentos] no [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=pt-BR#analytics-tools) para salvar segmentos rápidos ou abri-los no [!UICONTROL Construtor de segmentos].

## Criar segmentos rápidos

Em uma tabela de Forma livre, clique no ícone filter+ no cabeçalho do painel:

![](assets/quick-seg1.png)

Configure o segmento rápido nesta folha em branco:

![segmento rápido em branco](assets/qs-blank-slate.png)

| Configuração | Descrição |
| --- | --- |
| Nome | O nome padrão de um segmento é uma combinação dos nomes das regras no segmento. Você pode renomear o segmento. |
| Incluir/excluir | Você pode incluir ou excluir componentes na definição do segmento, mas não ambos. |
| Contêiner de ocorrência/visita/visitante | Os segmentos rápidos incluem apenas um [contêiner de segmento](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=pt-BR#section_AF2A28BE92474DB386AE85743C71B2D6) que permite incluir (ou excluir) uma dimensão/métrica/intervalo de datas no segmento. [!UICONTROL O Visitante] contém dados abrangentes específicos para visitantes em visitas e visualizações de página. Um container de [!UICONTROL Visita] permite definir regras para detalhar os dados do visitante com base em visitas, e um container de [!UICONTROL Ocorrência] permite detalhar as informações do visitante com base em visualizações de página individuais. O container padrão é o de [!UICONTROL Ocorrência]. |
| Componentes (dimensão/métrica/intervalo de datas) | Defina até três regras adicionando componentes (dimensões e/ou métricas e/ou intervalos de datas) e seus valores. Há 3 maneiras de encontrar o componente correto:<ul><li>Comece a digitar e o construtor de [!UICONTROL Segmento rápido] encontra automaticamente o componente correto.</li><li>Use a lista suspensa para localizar o componente.</li><li>Arraste os componentes do painel esquerdo e solte-os.</li></ul> |
| Operador | Use o menu suspenso para encontrar operadores padrão e operadores de [!UICONTROL Contagem distinta]. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=pt-BR) |
| Sinal de mais (+) | Adicionar outra regra |
| Qualificadores AND/OR | Você pode adicionar qualificadores &quot;AND&quot; ou &quot;OR&quot; às regras, mas não pode misturar &quot;AND&quot; e &quot;OR&quot; em uma única definição de segmento. |
| Aplicar | Aplique este segmento ao painel. Se o segmento não contiver dados, você será perguntado se deseja continuar. |
| Abrir builder | Abre o Construtor de segmentos. Depois de salvar ou aplicar o segmento no Construtor de segmentos, ele não é mais considerado um “Segmento rápido”. Ele se torna parte da biblioteca de segmentos da lista de componentes. |
| Cancelar | Cancele esse segmento rápido - não o aplique. |
| Intervalo de datas | O validador usa o intervalo de datas do painel para sua pesquisa de dados. Mas qualquer intervalo de datas aplicado em um segmento rápido substitui o intervalo de datas do painel na parte superior do painel. |
| Pré-visualização (canto superior direito) | Permite visualizar se você tem um segmento válido e quão amplo é o segmento. Representa o detalhamento do conjunto de dados que você pode esperar ao aplicar esse segmento. Você poderá receber um aviso indicando que esse segmento não tem dados. Nesse caso, você pode continuar ou alterar a definição do segmento. |

Este é um exemplo de um segmento que combina dimensões e métricas:

![](assets/quick-seg2.png)

O segmento aparece na parte superior. Observe a barra lateral com listras azuis, em vez da barra lateral azul para segmentos de nível de componente na biblioteca de segmentos à esquerda.

![](assets/quick-seg5.png)

## Editar segmentos rápidos

1. Passe o mouse sobre o segmento rápido e selecione o ícone de lápis.
1. Edite a definição do segmento e/ou o nome do segmento.
1. Clique em [!UICONTROL Aplicar].

## Salvar segmentos rápidos

>[!IMPORTANT]
>Depois de salvar ou aplicar o segmento, não é mais possível editá-lo no Construtor de segmentos rápido, somente no Construtor de segmentos comum. Somente os administradores de produtos do Adobe Analytics e o criador do segmento rápido podem salvar as alterações em um segmento rápido existente.

1. Depois de aplicar o segmento rápido, passe o mouse sobre ele e selecione o ícone de informações (&quot;i&quot;).

   ![](assets/quick-seg6.png)

1. Clique em **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes]**.
1. (Opcional) Renomeie o segmento.
1. Clique em **[!UICONTROL Salvar]**.

Observe como a barra lateral do segmento muda de azul listrado para azul-claro. Ela agora também aparece na lista de componentes do painel esquerdo.

## O que são segmentos somente de projeto?

Os segmentos somente do projeto são segmentos que se aplicam somente ao projeto atual em que foram criados. Eles não serão disponibilizados em outros projetos e não poderão ser compartilhados com outros usuários. Eles são destinados à exploração rápida de seus dados sem precisar criar e salvar um segmento no painel esquerdo. Segmentos somente de projeto podem ser criados na área de soltar do painel com filtros rápidos ou [filtros ad hoc](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/ad-hoc-segments.html?lang=pt-BR).

Se um segmento somente de projeto for aberto no [!UICONTROL Construtor de segmentos], uma notificação somente de projeto é exibida. Se você não marcar a opção “Disponibilizar este segmento...” e clicar em **[!UICONTROL APLICAR]**, o segmento permanece um segmento somente de projeto. Nota: se você aplicar um segmento rápido no Construtor de segmentos, ele não poderá mais ser aberto no [!UICONTROL Construtor de segmentos rápidos].

![Somente do projeto desmarcado](assets/project-only-unchecked.png)

Se você marcar a opção “Disponibilizar este segmento...” e clicar em **[!UICONTROL SALVAR]**, o segmento fica disponível na lista de componentes do painel à esquerda para uso em outros projetos. Ele também pode ser compartilhado com outros usuários no Gerenciador de segmentos.

![Somente do projeto marcado](assets/project-only-checked.png)

## Problema conhecido

1. Crie um segmento rápido com 2 entradas e **[!UICONTROL Salve]** como Test1.
1. Clique em **[!UICONTROL Salvar como]** e salve este segmento rápido como Test2.
1. Edite o segmento rápido Test2 e salve-o novamente como Test2.
Observe que o segmento rápido Test1 é modificado pelo Test2.
