---
description: Mede como vários códigos de rastreamento de anúncio afetam eventos de conversão diferentes do site. Este relatório pode ser usado para medir quais campanhas específicas estão se saindo melhor para eventos bem-sucedidos diferentes ou para ver como as campanhas estão ajudando ou atrasando as iniciativas do site, como quais campanhas geram mais receita.
title: Códigos de rastreamento
topic: Reports
uuid: c893d592-10fd-4b40-84b3-8c8949a67b25
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Códigos de rastreamento

Mede como vários códigos de rastreamento de anúncio afetam eventos de conversão diferentes do site. Este relatório pode ser usado para medir quais campanhas específicas estão se saindo melhor para eventos bem-sucedidos diferentes ou para ver como as campanhas estão ajudando ou atrasando as iniciativas do site, como quais campanhas geram mais receita.

**Propriedades gerais**

* Este relatório faz referência aos dados diretamente do [s.campaign](/help/implement/vars/page-vars/campaign.md)
* A variável deste relatório é baseada em  [variável de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md). Ou seja, pode persistir além da visualização de página e se associar com as métricas dentro de sua expiração especificada.
* A métrica padrão do relatório é a Receita. Você pode alterar esse valor padrão no [!UICONTROL Report Suite Manager] campo em [!UICONTROL Admin Tools]. ( **[!UICONTROL Edit Settings]** > **[!UICONTROL Individual Report Settings]** > **[!UICONTROL Default Metrics]**.)

* Este relatório pode ser visualizado nos formatos de tendência e classificado.
* Este relatório pode usar um filtro de pesquisa para localizar itens de linha específicos.
* The [!UICONTROL Campaigns] and [!UICONTROL Creative Elements] reports are classifications based on this report, and are automatically created with each report suite.

* As Classificações SAINT podem ser usadas neste relatório, permitindo que você renomeie e consolide os itens de linha.
* Você pode dividir este relatório pelos seguintes relatórios (dependendo das configurações da organização e do conjunto de relatórios):

   * Tempo gasto por visita
   * Relatórios de Páginas e Seções do Site, com todas as classificações relacionadas.
   * Profundidade de Página, Páginas de entrada e Páginas de entrada originais
   * Maioria dos relatórios de fontes de tráfego
   * Número de visitas e Fidelidade do cliente
   * Muitos relatórios de Perfil do visitante e de Tecnologia, salvo Segmentação geográfica
   * Todas as variáveis de conversão personalizadas

* As métricas a seguir podem ser utilizadas neste relatório (dependendo das configurações da organização e do conjunto de relatórios):

   * Click-throughs: o número de vezes que a variável *`s.campaign`* é definida
   * Todas as métricas de comércio eletrônico: Receita, Pedidos, Unidades, Carrinhos, Exibição de carrinhos, Adições a carrinhos, Remoções do carrinho.
   * Todos os eventos personalizados: Eventos 1-80 e Eventos 81-100 se em código H22 ou superior
   * Visitas e Visitantes: a disponibilidade depende da organização e do conjunto de relatórios. Entre em contato com seu Gerente de conta para obter mais informações.

**Propriedades do Reports &amp; Analytics**

* Clique em **[!UICONTROL Conversion]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Tracking Code]** para localizar esse relatório, a menos que o menu seja personalizado.

* Este relatório também pode ser detalhado por todas as [Variáveis da lista](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/list-var-admin.html).
* Visualizações de Página, Visitas e Visitantes únicos estão disponíveis como métricas.
* Este relatório pode utilizar segmentos.

**Propriedades da Ad Hoc Analysis**

* Além das variáveis de conversão mais inovadoras, você pode analisar o relatório de código de rastreamento por todos os outros relatórios dentro da interface do relatório.
* Além dos eventos de e-comércio e personalizados, você pode utilizar todas as métricas de conversão e de tráfego, assim como também utilizar alocação diferente para todas as métricas de conversão.
* Este relatório pode utilizar segmentos avançados.

