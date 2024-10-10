---
description: Etapas que descrevem como criar uma solicitação do data warehouse.
title: Configurações gerais da solicitação de Data Warehouse
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: 1e1a26b8595ca026fb049322125a6f91d9d5513c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 32%

---

# Configurações gerais da solicitação de Data Warehouse

Há várias opções de configuração disponíveis ao criar uma solicitação do data warehouse. As informações a seguir descrevem como definir configurações gerais para a solicitação.

Para obter informações sobre como começar a criar uma solicitação, bem como links para outras opções de configuração importantes, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para definir as configurações gerais de uma solicitação Data Warehouse:

1. Comece a criar uma solicitação de Data Warehouse no Adobe Analytics selecionando **[!UICONTROL Ferramentas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Adicionar**].

   Para obter detalhes adicionais, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Na página Nova solicitação de Data Warehouse, selecione a guia [!UICONTROL **Configurações gerais**].

   ![Guia Destino do relatório](assets/dw-general-settings.png)

1. Preencha os campos a seguir:

   | Opção | Função |
   |---------|----------|
   | Nome da solicitação | Esse nome aparece na página principal da Data Warehouse ao gerenciar solicitações. |
   | Intervalos de datas | Selecione o intervalo de datas a ser incluído no relatório. <p>Você pode escolher datas personalizadas ou um intervalo de datas predefinido. Os intervalos predefinidos são relativos à data em que o relatório é enviado.</p><p>As seguintes opções predefinidas estão disponíveis:</p><ul><li>Hoje</li><li>Ontem</li><li>Últimos 7 dias</li><li>Últimos 30 dias</li><li>Nesta semana</li><li>Semana passada</li><li>Últimas 2 semanas</li><li>Últimas 3 semanas</li><li>Últimas 4 semanas</li><li>Este mês</li><li>Último mês</li><li>Última hora</li></ul> |
   | Granularidade | A granularidade de tempo. Os valores válidos são Nenhum, Hora, Dia, Semana, Mês, Trimestre e Ano.<p>Relatar a granularidade requer tempo de processamento adicional. Se você estiver relatando a granularidade mensal de um ano inteiro, seus relatórios serão processados com muito mais rapidez se você enviar uma solicitação de relatório para cada mês.</p><p>**Observação:** ao ser aplicada a granularidade em uma solicitação de Data Warehouse, a coluna &#39;Data&#39; é adicionada ao relatório. Dependendo da granularidade selecionada, o formato de data muda, da seguinte maneira:</p><ul><li>**Granularidade horária**:<ul> <li>**Formato**: `mmmm d, yyyy` Hora `H`</li><li>**Exemplo**: 1º de janeiro, 20XX, Hora 0 </li></ul><li>**Granularidade diária**:<ul> <li>**Formato**: `mmmm d, yyyy`</li><li>**Exemplo**: 1º de janeiro, 20XX</li></ul><li>**Granularidade semanal**:<ul> <li>**Formato**: Semana `w, yyyy`</li><li>**Exemplo**: Semana 1, 20XX </li></ul><li>**Granularidade mensal**:<ul> <li>**Formato**: `mmmm yyyy`</li><li>**Exemplo**: 20XX de janeiro </li></ul><li>**Granularidade trimestral**:<ul> <li>**Formato**: `q` Trimestre `yyyy`</li><li>**Exemplo**: 1º trimestre de 20XX </li></ul><li>**Granularidade anual**:<ul> <li>**Formato**: `yyyy`</li><li>**Exemplo**: 20XX</li></ul> |
   | Disponibilize para usuários em sua organização | Todas as solicitações do data warehouse estão visíveis somente para você e qualquer administrador do sistema. Ative essa opção se desejar que a solicitação fique visível para todos em sua organização. <p>Habilitar essa opção é útil se você quiser que outros usuários em sua organização ajudem a criar ou atualizar a solicitação.</p> |

   {style="table-layout:auto"}

1. Continue configurando sua solicitação do Data Warehouse na guia [!UICONTROL **Criar relatório**]. Para obter mais informações, consulte [Criar um relatório para uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/dw-request-build-report.md).
