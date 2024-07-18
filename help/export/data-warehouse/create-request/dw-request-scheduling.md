---
description: Etapas que descrevem como criar uma solicitação do data warehouse.
title: Configurar um destino de relatório para uma solicitação do data warehouse
feature: Data Warehouse
exl-id: e5f8acaa-156f-41fb-a0fc-bc5475f1f3b7
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 33%

---

# Configurar opções de agendamento para uma solicitação Data Warehouse

Há várias opções de configuração disponíveis ao criar uma solicitação do data warehouse. As informações a seguir descrevem como configurar opções de programação para a solicitação.

Para obter informações sobre como começar a criar uma solicitação, bem como links para outras opções de configuração importantes, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para configurar opções de programação para uma solicitação Data Warehouse:

1. Caso ainda não o tenha feito, crie uma solicitação no Adobe Analytics selecionando **[!UICONTROL Ferramentas]** > **[!UICONTROL Data warehouse]** > [!UICONTROL **Adicionar**].

   Para obter detalhes adicionais, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Na página Nova solicitação de Data Warehouse, selecione a guia [!UICONTROL **Opções de agendamento**].

   ![Guia de destino do relatório](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. Preencha os campos a seguir:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Enviar relatório agora**] | Envia o relatório como um relatório único. Quando essa opção é selecionada, todas as opções de agendamento são ocultas. |
   | [!UICONTROL **Agendar para mais tarde**] | Fornece opções para o agendamento da entrega de relatórios. Todas as opções são descritas abaixo. |
   | [!UICONTROL **Frequência de relatório**] | A frequência com que os relatórios são entregues. <p>As opções disponíveis são as seguintes:</p><ul><li>Por hora</li><p>[!UICONTROL **Por hora**] está disponível somente quando a opção [!UICONTROL **Intervalos de datas**] na guia [!UICONTROL **Configurações gerais**] está definida como [!UICONTROL **Última hora**].</p><li>Diariamente</li><li>Semanalmente</li><li>Mensalmente</li><li>Anualmente</li></ul><p>As opções adicionais são exibidas dependendo da frequência selecionada.</p> |
   | [!UICONTROL **Começando em**] | A data em que o novo cronograma deve começar. |
   | [!UICONTROL **Hora do dia**] | A hora em que o relatório deve ser enviado. |
   | [!UICONTROL **Finalizar opções de entrega**] | Escolha quando finalizar os deliveries agendados. Você pode optar por nunca terminar, terminar após um número específico de ocorrências ou terminar em uma data específica. |

   {style="table-layout:auto"}

1. Continue configurando sua solicitação do Data Warehouse na guia [!UICONTROL **Email de notificação**]. Para obter mais informações, consulte [Configurar um email de notificação para uma solicitação de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).
