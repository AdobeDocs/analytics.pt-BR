---
description: Eventos bem-sucedidos são ações que podem ser rastreadas. Você determina o que é um evento bem-sucedido. Por exemplo, se um visitante comprar um item, o evento de compra pode ser considerado o evento bem-sucedido.
keywords: evento
title: Visão geral dos eventos bem-sucedidos
feature: Metrics
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 54%

---

# Eventos bem-sucedidos

Eventos bem-sucedidos (também conhecidos como eventos de conversão ou eventos personalizados) são ações que podem ser rastreadas. Você determina o que é um evento bem-sucedido. Por exemplo, se um visitante comprar um item, o evento de compra pode ser considerado o evento bem-sucedido.

Para obter uma visão geral em vídeo sobre eventos de sucesso, consulte [Introdução a eventos de conversão](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/metrics/introduction-to-conversion-events) no guia de tutoriais do Analytics.

## Exemplos de evento bem-sucedido

Há muitas formas de eventos de sucesso, dependendo do tipo de site da Web. Vários exemplos incluem:

* **Vendas**: exibição de produto, check-out, compra
* **Mídia**: assinatura, assinatura de concurso, exibição de página, exibição de vídeo
* **Finanças**: envio de aplicativo, logon, uso de ferramentas de autoatendimento
* **Viagem**: reserva (compra), campanha interna (click-through), busca (preços do itinerário)
* **Telecomunicações**: compra, clientes em potencial, uso de ferramentas de autoatendimento
* **Alta tecnologia**: download de white-paper, RFP, preenchimento de formulário, solicitações de suporte
* **Automotivo**: submissão de cliente em potencial, solicitação de cotação, download de panfleto

A variável [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=pt-BR) define um evento bem-sucedido.

## Configurar os eventos bem-sucedidos

Você pode configurar as variáveis de Evento usadas no site. É possível adicionar até 1000 eventos bem-sucedidos. Os eventos 81-1.000 funcionam somente se você estiver usando o código H22 ou superior.

Para configurar eventos bem-sucedidos:

1. No Adobe Analytics, selecione **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Selecione o conjunto de relatórios no qual você deseja configurar eventos bem-sucedidos.
1. Selecione **[!UICONTROL Editar Configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Eventos Bem-sucedidos]**.

   ![Resultado da etapa](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. Na coluna [!UICONTROL **Evento**], identifique o nome do evento que deseja usar como um evento bem-sucedido.

1. Na coluna **[!UICONTROL Nome]**, marque a caixa de seleção ao lado do item para habilitar a edição e, em seguida, especifique o nome desejado.

   Dê nomes significativos aos eventos bem-sucedidos usados em seu site. Por exemplo, se event1 for usado para controlar registros, altere o nome aqui, de modo que event1 seja representado como a métrica &quot;Registros&quot; em todos os relatórios de Conversão.

1. Na coluna **[!UICONTROL Tipo]**, marque a caixa de seleção ao lado do item para habilitar a lista suspensa e, em seguida, selecione o tipo desejado.

   >[!IMPORTANT]
   >
   >Considere o seguinte ao alterar o tipo de evento:<ul><li>Você pode alterar o tipo de evento entre contador e numérico sem perder acesso aos dados capturados anteriormente.</li><li>Ao alterar tipos de evento para ou partir de um evento de moeda, uma mensagem é exibida declarando que os dados históricos não estão disponíveis no relatório. Tipos de evento diferentes usam tabelas de dados separadas e não podem ser usados ao mesmo tempo. Alguns dados históricos podem ser restaurados se o usuário reverter o tipo de evento. No entanto, os dados coletados após a alteração inicial não estarão disponíveis.</li></ul>

   O tipo selecionado determina se o evento é um evento de contador (padrão), numérico ou de moeda. <p>Os eventos contadores são usados para registrar um evento a tempo.</p><p>Eventos numéricos são usados para relatar números não relacionados a moeda, como o número de cupons usados em um pedido.</p> <p>Os eventos de moeda registram um número decimal, como imposto ou remessa. O valor transmitido para eventos de moeda será convertido da moeda da página para a moeda de base do conjunto de relatórios mediante ao recebimento. Eventos de moeda são usados para acompanhar encargos de impostos e remessa. Para obter mais detalhes sobre o uso de eventos de moeda, entre em contato com um representante da Adobe.<p>Eventos numéricos e de moeda permitem incrementar métricas como mais de uma.</p><p>Eventos usados no tipo de Padrão de Fontes de dados devem ser eventos numéricos ou de moeda.</p>

1. Na coluna **[!UICONTROL Polaridade]**, marque a caixa de seleção e, no menu suspenso, escolha se uma tendência acima para essa métrica é boa ou ruim.

   isso permite indicar se o Adobe Analytics deve considerá-lo bom ou ruim se um determinado evento personalizado (métrica) aumentar. Ela ativa indicadores direcionais (setas) para diversas métricas para adicionar contexto (por exemplo, comparações entre semanas).  Exemplos: se &quot;Bugs enviados&quot; aumentar semana após semana, o Adobe Analytics deve considerar isso bom ou ruim? Um aumento nos Registros de email provavelmente é bom. Mas um aumento em Erros no envio do formulário provavelmente é ruim.  Na Analysis Workspace, a polaridade é aplicada: à formatação condicional da tabela de forma livre, às visualizações de alteração de resumo e ao esquema de cor positivo/negativo da visualização de mapa.

1. Na coluna **[!UICONTROL Visibilidade]**, marque a caixa de seleção e, no menu suspenso, escolha ocultar métricas padrão (incorporadas), eventos personalizados e eventos incorporados no Menu, Seletores de métricas, Construtor de métricas calculadas e o Construtor de segmentos.

   Essa configuração não afeta a coleção de dados da métrica ou do evento, afeta somente a visibilidade na interface do usuário, como mostrado a seguir:

   As seguintes configurações estão disponíveis:

   | Configuração | Visível em | Não visível em |
   |---------|----------|---------|
   | [!UICONTROL **Visível em qualquer lugar**] | <ul><li>Analysis Workspace</li><li>Construtor de segmentos</li><li>Criador de métricas calculada</li></ul> | N/D |
   | [!UICONTROL **Construtores**] | <ul><li>Construtor de segmentos</li><li>Criador de métricas calculada</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **Oculto em qualquer lugar**] | N/A | <ul><li>Analysis Workspace</li><li>Construtor de segmentos</li><li>Criador de métricas calculada</li></ul> |

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
   >Você pode ativar a participação de até 100 eventos personalizados. Além disso, você pode criar métricas de participação no construtor de [Métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md).

1. Selecione **[!UICONTROL Salvar]**.
