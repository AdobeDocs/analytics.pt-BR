---
description: Etapas que descrevem como criar uma solicitação do Data Warehouse.
title: Configurar um destino de relatório para uma solicitação Data Warehouse
feature: Data Warehouse
source-git-commit: 0abf0c76f38b481c0b72d113fe49e0da03ddd8cd
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 15%

---

# Configurar opções de agendamento para uma solicitação Data Warehouse

>[!AVAILABILITY]
>
>Alguns dos recursos do Data Warehouse descritos neste artigo (e outros artigos do Data Warehouse nesta seção) estão disponíveis somente na fase de Teste limitado da versão e podem não estar disponíveis ainda em seu ambiente.
>
>Para obter informações sobre quais recursos ainda não estão disponíveis para todos os clientes, bem como informações sobre a linha do tempo de lançamento desses recursos, consulte o [notas de versão](/help/release-notes/latest.md).
>
>Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Adobe Analytics](/help/release-notes/releases.md).

Há várias opções de configuração disponíveis ao criar uma solicitação do Data Warehouse. As informações a seguir descrevem como configurar opções de programação para a solicitação.

Para obter informações sobre como começar a criar uma solicitação, bem como links para outras opções de configuração importantes, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para configurar opções de programação para uma solicitação Data Warehouse:

1. Comece a criar uma solicitação no Adobe Analytics selecionando **[!UICONTROL Ferramentas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Adicionar**].

   Para obter detalhes adicionais, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Na página Nova solicitação de Data Warehouse, selecione a variável [!UICONTROL **Opções de agendamento**] guia.

   ![Guia Destino do relatório](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Preencha os campos a seguir:

   | Opção | Função |
   |---------|----------|
   | Enviar relatório agora | Envia o relatório como um relatório único. Quando essa opção é selecionada, todas as opções de agendamento são ocultas. |
   | Agendar para mais tarde | Fornece opções para o agendamento da entrega de relatórios. Todas as opções são descritas abaixo. |
   | Frequência do relatório | A frequência com que os relatórios são entregues. <p>As opções disponíveis são as seguintes:</p><ul><li>Por hora</li><p>[!UICONTROL **Por hora**] está disponível somente quando a variável [!UICONTROL **Intervalos de datas**] opção no [!UICONTROL **Configurações gerais**] está definida como [!UICONTROL **Última hora**].</p><li>Diariamente</li><li>Semanalmente</li><li>Mensalmente</li><li>Anualmente</li></ul>  <!-- Is this valid? Was in the old docs: "To schedule Data Warehouse requests for Daily, Weekly, Monthly, or Yearly, make sure *Preset* is correctly selected" --> |
   | Recorrência mensal | O intervalo entre meses quando o relatório é enviado. |
   | Dia do mês | A data de cada mês em que o relatório é enviado.<p>Quando essa opção estiver disponível, a variável [!UICONTROL **Semana do mês**] e [!UICONTROL **Dia da semana**] opções não são. Selecione o [!UICONTROL **Formato alternativo**] botão para alternar entre um e outro. </p> |
   | Semana do mês | A semana de cada mês em que o relatório deve ser enviado. <p>As opções disponíveis são as seguintes:</p><ul><li>Primeiro</li><li>Segundo</li><li>Terceiro</li><li>Quarto</li><p>Envie o relatório na 4ª semana, mesmo em meses com 5 semanas. Escolher [!UICONTROL **Último**] se quiser que o relatório seja enviado na última semana de cada mês.</p><li>Último</li></ul><p>Quando essa opção estiver disponível, a variável [!UICONTROL **Dia do mês**] opção não é. Selecione o [!UICONTROL **Formato alternativo**] botão para alternar entre um e outro. </p> |
   | Dia da semana | O dia da semana em que o relatório deve ser enviado. <p>Quando essa opção estiver disponível, a variável [!UICONTROL **Dia do mês**] opção não é. Selecione o [!UICONTROL **Formato alternativo**] botão para alternar entre um e outro. </p> |
   | Começando em | A data em que o novo cronograma deve começar. |
   | Hora do dia | A hora em que o relatório deve ser enviado. |
   | Opções de entrega final | Escolha quando finalizar os deliveries agendados. Você pode optar por nunca terminar, terminar após um número específico de ocorrências ou terminar em uma data específica. |

   {style="table-layout:auto"}

1. Continue configurando sua solicitação do Data Warehouse no [!UICONTROL **Email de notificação**] guia. Para obter mais informações, consulte [Configurar um email de notificação para uma solicitação de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).

