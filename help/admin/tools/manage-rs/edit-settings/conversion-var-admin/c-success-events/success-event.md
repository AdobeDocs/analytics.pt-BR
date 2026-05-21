---
description: Eventos bem-sucedidos são ações que podem ser rastreadas. Você determina o que é um evento bem-sucedido. Por exemplo, se um visitante comprar um item, o evento de compra pode ser considerado o evento bem-sucedido.
keywords: evento
title: Visão geral dos eventos bem-sucedidos
feature: Metrics
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
TQID: https://experienceleague.adobe.com/wOWG6t9fsrfkd4FE-BNkwIrPW6DEGxBKDc2XItyRaoc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 962
ht-degree: 25%

---

# Eventos bem-sucedidos

Eventos bem-sucedidos (também conhecidos como eventos de conversão ou eventos personalizados) são ações que podem ser rastreadas. Você determina o que é um evento bem-sucedido. Por exemplo, se um visitante comprar um item, o evento de compra pode ser considerado o evento bem-sucedido.

Para obter uma visão geral em vídeo sobre eventos de sucesso, consulte [Introdução a eventos de conversão](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/metrics/introduction-to-conversion-events) no guia de tutoriais do Analytics.

## Exemplos de evento bem-sucedido

Há vários tipos de eventos bem-sucedidos, dependendo do tipo de site. Vários exemplos incluem:

* **Varejo**: exibição de produto, check-out, compra
* **Mídia**: assinatura, inscrição em concurso, exibição de página, exibição de vídeo
* **Finanças**: envio de aplicativo, logon, uso de ferramentas de autoatendimento
* **Viagem**: Reserva (compra), campanha interna (click-through), pesquisa (itinerário de preços)
* **Telecomunicações**: compra, clientes potenciais, uso de ferramentas de autoatendimento
* **Alta tecnologia**: download de white-paper, RFP, preenchimento de formulários, solicitações de suporte
* **Automotivo**: envio de clientes potenciais, solicitação de cotação, download de folheto

A variável [s.events](/help/implement/vars/page-vars/events/event-serialization.md) define um evento bem-sucedido.

## Configurar os eventos bem-sucedidos

Você pode configurar as variáveis de Evento usadas no site. Você pode adicionar até 1.000 eventos de sucesso. Os eventos 81-1.000 funcionam somente se você estiver usando o código H22 ou superior.

Para configurar eventos bem-sucedidos:

1. No Adobe Analytics, selecione **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Selecione o conjunto de relatórios no qual você deseja configurar eventos bem-sucedidos.
1. Selecione **[!UICONTROL Editar Configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Eventos Bem-sucedidos]**.

   ![Resultado da etapa](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. Na coluna [!UICONTROL **Evento**], identifique o nome do evento que deseja usar como um evento bem-sucedido.

1. Na coluna **[!UICONTROL Nome]**, marque a caixa de seleção ao lado do item para habilitar a edição e, em seguida, especifique o nome desejado.

   Dê nomes significativos para os eventos de sucesso usados em seu site. Por exemplo, se event1 for usado para rastrear registros, altere o nome aqui para que event1 seja representado como a métrica &quot;Registros&quot; em todos os relatórios de Conversão.

1. Na coluna **[!UICONTROL Tipo]**, marque a caixa de seleção ao lado do item para habilitar a lista suspensa e, em seguida, selecione o tipo desejado.

   >[!IMPORTANT]
   >
   >Considere o seguinte ao alterar o tipo de evento:<ul><li>Você pode alterar o tipo de evento entre contador e numérico sem perder acesso aos dados capturados anteriormente.</li><li>Ao alterar tipos de evento para ou partir de um evento de moeda, uma mensagem é exibida declarando que os dados históricos não estão disponíveis no relatório. Tipos de evento diferentes usam tabelas de dados separadas e não podem ser usados simultaneamente. Alguns dados históricos podem ser restaurados se o usuário reverter o tipo de evento. No entanto, os dados coletados após a alteração inicial não estarão disponíveis.</li></ul>

   O tipo selecionado determina se o evento é um evento de contador (padrão), numérico ou de moeda. <p>Os eventos contadores são usados para registrar um evento a tempo.</p><p>Eventos numéricos são usados para relatar números não relacionados a moeda, como o número de cupons usados em um pedido.</p> <p>Os eventos de moeda registram um número decimal, como imposto ou remessa. O valor transmitido para eventos de moeda é convertido da moeda da página para a moeda base do conjunto de relatórios no recebimento. Os eventos de moeda são usados para rastrear impostos e encargos de remessa. Para obter detalhes sobre o uso de eventos de moeda, entre em contato com um representante da Adobe.<p>Eventos numéricos e de moeda permitem incrementar métricas como mais de uma.</p><p>Os eventos usados no tipo Padrão das Fontes de Dados devem ser numéricos ou de moeda.</p>

1. Na coluna **[!UICONTROL Polaridade]**, marque a caixa de seleção e, no menu suspenso, escolha se uma tendência acima para essa métrica é boa ou ruim.

   isso permite indicar se o Adobe Analytics deve considerá-lo bom ou ruim se um determinado evento personalizado (métrica) aumentar. Ela ativa indicadores direcionais (setas) para diversas métricas para adicionar contexto (por exemplo, comparações entre semanas).  Exemplos: se &quot;Bugs enviados&quot; aumentar semana após semana, a Adobe Analytics deve considerar isso bom ou ruim? Um aumento nos Registros de email provavelmente é bom. Mas um aumento em Erros no envio do formulário provavelmente é ruim.  No Analysis Workspace, a polaridade é aplicada a: formatação condicional da Tabela de forma livre, visualizações de Alteração de resumo e o esquema de cores Positivo/Negativo da visualização do Mapa.

1. Na coluna **[!UICONTROL Visibilidade]**, marque a caixa de seleção e, no menu suspenso, escolha ocultar métricas padrão (incorporadas), eventos personalizados e eventos incorporados no Menu, Seletores de métricas, Construtor de métricas calculadas e o Construtor de segmentos.

   Essa configuração não afeta a coleção de dados da métrica ou do evento, afeta somente a visibilidade na interface do usuário, como mostrado a seguir:

   As seguintes configurações estão disponíveis:

   | Configuração | Visível em | Não visível no |
   |---------|----------|---------|
   | [!UICONTROL **Visível em qualquer lugar**] | <ul><li>Analysis Workspace</li><li>Construtor de segmentos</li><li>Criador de métricas calculada</li></ul> | N/D |
   | [!UICONTROL **Construtores**] | <ul><li>Construtor de segmentos</li><li>Criador de métricas calculada</li><li>Analysis Workspace</li></ul> |  |
   | [!UICONTROL **Oculto em qualquer lugar**] | N/D | <ul><li>Analysis Workspace</li><li>Construtor de segmentos</li><li>Criador de métricas calculada</li></ul> |

1. Na coluna [!UICONTROL **Descrição**], marque a caixa de seleção e forneça uma descrição.
1. Na coluna [!UICONTROL **Gravação de evento único**], marque a caixa de seleção e escolha no menu suspenso se deseja sempre gravar o evento.

   As seguintes opções estão disponíveis:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Gravar Uma Vez Por Visita**] | Vincula o evento fornecido à sessão do visitante. As contagens subsequentes para um determinado evento na mesma visita são ignoradas. Esse tipo de serialização de eventos não requer alterações de implementação. |
   | [!UICONTROL **Usar ID de Evento**] | Vincula o evento fornecido a uma ID personalizada. As contagens subsequentes de um determinado evento com a mesma ID de evento são ignoradas. Esse tipo de serialização de eventos requer uma ID personalizada em ocorrências para desduplicar valores. Consulte [Serialização de ID de evento](/help/implement/vars/page-vars/events/event-serialization.md) no guia de usuário Implementar. |

1. Na coluna [!UICONTROL **Participação**], marque a caixa de seleção e escolha se deseja habilitar ou desabilitar a participação. Quando ativado, oferece crédito de atribuição total a todos os itens de dimensão na visita.

   >[!NOTE]
   >
   >Você pode habilitar a participação de até 100 eventos personalizados. Além disso, você pode criar métricas de participação no construtor de [Métricas calculadas](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md).

1. Selecione **[!UICONTROL Salvar]**.
