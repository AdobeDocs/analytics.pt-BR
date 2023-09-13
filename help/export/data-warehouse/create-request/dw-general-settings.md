---
description: Etapas que descrevem como criar uma solicitação do Data Warehouse.
title: Configurações gerais da solicitação de Data Warehouse
feature: Data Warehouse
source-git-commit: c63e5d5f1065aabdbbd5471d6a2e702f9f099396
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 27%

---

# Configurações gerais da solicitação de Data Warehouse

{{release-limited-testing}}

Há várias opções de configuração disponíveis ao criar uma solicitação do Data Warehouse. As informações a seguir descrevem como definir configurações gerais para a solicitação.

Para obter informações sobre como começar a criar uma solicitação, bem como links para outras opções de configuração importantes, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para definir as configurações gerais de uma solicitação Data Warehouse:

1. Comece a criar uma solicitação do Data Warehouse no Adobe Analytics selecionando **[!UICONTROL Ferramentas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Adicionar**].

   Para obter detalhes adicionais, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Na página Nova solicitação de Data Warehouse, selecione a variável [!UICONTROL **Configurações gerais**] guia.

   ![Guia Destino do relatório](assets/dw-general-settings.png)

1. Preencha os campos a seguir:

   | Opção | Função |
   |---------|----------|
   | Nome da solicitação | Esse nome aparece na página principal da Data Warehouse ao gerenciar solicitações. |
   | Intervalos de datas | Selecione o intervalo de datas a ser incluído no relatório. <p>Você pode escolher datas personalizadas ou um intervalo de datas predefinido. Os intervalos predefinidos são relativos à data em que o relatório é enviado.</p><p>As seguintes opções predefinidas estão disponíveis:</p><ul><li>Hoje</li><li>Ontem</li><li>Últimos 7 dias</li><li>Últimos 30 dias</li><li>Nesta semana</li><li>Semana passada</li><li>Últimas 2 semanas</li><li>Últimas 3 semanas</li><li>Últimas 4 semanas</li><li>Este mês</li><li>Último mês</li><li>Última hora</li><li>Hoje</li><li>Hoje</li></ul> |
   | Granularidade | <!--what does this setting do? It's not the schedule/frequency... --> A granularidade de tempo. Os valores válidos são Nenhum, Hora, Dia, Semana, Mês, Trimestre e Ano.<p>Relatar a granularidade requer tempo de processamento adicional. Se você estiver relatando a granularidade mensal de um ano inteiro, seus relatórios serão processados com muito mais rapidez se você enviar uma solicitação de relatório para cada mês.</p> |

   {style="table-layout:auto"}

1. Continue configurando sua solicitação do Data Warehouse no [!UICONTROL **Crie seu relatório**] guia. Para obter mais informações, consulte [Criar um relatório para uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/dw-request-build-report.md).