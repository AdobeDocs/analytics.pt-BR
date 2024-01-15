---
description: Rotular os dados do conjunto de relatórios significa que você atribui os rótulos de identidade, sensibilidade e governança de dados a cada variável em um determinado conjunto de relatórios.
title: Rotular dados do conjunto de relatórios
feature: Data Governance
role: Admin
exl-id: d1bd833c-3fd4-4572-a5dc-d7bab8a79cb8
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 100%

---

# Rotular dados do conjunto de relatórios

Rotular os dados do conjunto de relatórios significa que você atribui os rótulos de identidade, sensibilidade e governança de dados a cada variável em um determinado conjunto de relatórios. Primeiro, familiarize-se com os [rótulos e suas definições](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md).

>[!NOTE]
>
>Lembre-se de que a Rotulagem precisa ser analisada sempre que um novo conjunto de relatórios for criado ou quando uma nova variável for ativada em um conjunto de relatórios existente. Você também pode analisar a rotulagem quando novas integrações da solução forem ativadas, pois elas podem expor novas variáveis que podem exigir rótulos. A reimplementação de aplicativos ou sites móveis pode alterar como as variáveis existentes são usadas, o que também pode exigir atualizações nos rótulos.

## Atribuir ou editar rótulos de privacidade do conjunto de relatórios {#assign-edit}

**Exemplo**: você, como controlador de dados, planeja coletar endereços de email e IDs de cookies de titulares de dados para processar suas solicitações de Privacidade de dados. Essas IDs de cookies são armazenadas em um conjunto de relatórios no Adobe Analytics.

1. No Adobe Analytics, navegue até **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Configuração e coleção de dados]** > **[!UICONTROL Governança de dados]**.

   ![Rotulagem de privacidade](assets/privacy_rs_settings.png)

1. Selecione um conjunto de relatórios no **[!UICONTROL Conjuntos de relatórios]** na parte superior.

1. Na seção de filtro à esquerda, selecione quais grupos de variáveis você deseja rotular. Você pode rotular somente um grupo de variáveis por vez.

   * **Componentes padrão**: os componentes padrão são dimensões e métricas do Analytics prontas para uso que são coletadas por padrão em uma implementação do Analytics.
   * **Variáveis de conversão**: a variável de conversão do Insight personalizado (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados. Uma eVar pode ter por base visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.
   * **Variáveis de lista**: as variáveis de lista são variáveis personalizadas que podem ser usadas da maneira que você desejar. Elas funcionam de forma semelhante às eVars, mas podem conter vários valores na mesma ocorrência. As variáveis de lista não têm limite de caracteres.
   * **Variáveis de tráfego**: as variáveis de tráfego de Insight personalizado (ou props) permitem que você correlacione dados personalizados com eventos relacionados a tráfego. As variáveis de prop estão incluídas no código de implementação de cada página do site.
   * **Eventos bem-sucedidos**: (também conhecidos como eventos de conversão ou eventos personalizados) são ações que podem ser rastreadas. Você determina o que é um evento bem-sucedido. Por exemplo, se um visitante comprar um item, o evento de compra pode ser considerado o evento bem-sucedido.
   * **Classificações**: detalhamentos de classificação são usados para mapear dados de relatórios para propriedades relacionadas. Classificações podem ser usadas para uma variedade de finalidades, mas são usadas com mais frequência para classificar códigos de controle de campanha (tanto internos quanto externos) e IDs de produtos.

1. Selecione uma variável clicando na caixa de seleção e, em seguida, clique em **[!UICONTROL Editar rótulos de privacidade]** na barra azul que aparece na parte inferior da tela.

   ![Editar](assets/edit-label.png)

   Esta tela mostra os rótulos aplicados no momento e permite que você aplique rótulos adicionais. Não será possível aplicar ou modificar todos os rótulos dependendo do componente.

   ![Rótulos aplicados](assets/edit-labels2.png)

1. Clique em **[!UICONTROL Aplicar]** após concluir toda a rotulagem.

