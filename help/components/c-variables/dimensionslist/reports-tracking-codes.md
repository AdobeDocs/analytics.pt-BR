---
description: Mede como vários códigos de rastreamento de anúncio afetam eventos de conversão diferentes do site. Este relatório pode ser usado para medir quais campanhas específicas estão se saindo melhor para eventos bem-sucedidos diferentes ou para ver como as campanhas estão ajudando ou atrasando as iniciativas do site, como quais campanhas geram mais receita.
seo-description: Mede como vários códigos de rastreamento de anúncio afetam eventos de conversão diferentes do site. Este relatório pode ser usado para medir quais campanhas específicas estão se saindo melhor para eventos bem-sucedidos diferentes ou para ver como as campanhas estão ajudando ou atrasando as iniciativas do site, como quais campanhas geram mais receita.
seo-title: Códigos de rastreamento
solution: Analytics
title: Códigos de rastreamento
topic: Relatórios
uuid: c893d592-10fd-4b40-84b3-8c8949a67b25
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Códigos de rastreamento

Mede como vários códigos de rastreamento de anúncio afetam eventos de conversão diferentes do site. Este relatório pode ser usado para medir quais campanhas específicas estão se saindo melhor para eventos bem-sucedidos diferentes ou para ver como as campanhas estão ajudando ou atrasando as iniciativas do site, como quais campanhas geram mais receita.

**Propriedades Gerais**

* Este relatório faz referência aos dados diretamente da variável [s.campanha](/help/implement/js-implementation/c-variables/page-variables.md) implementada no site.
* A variável deste relatório é baseada em [variável de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md). Ou seja, pode persistir além da visualização de página e se associar com as métricas dentro de sua expiração especificada.
* A métrica padrão do relatório é a Receita. Você pode alterar esse valor padrão no [!UICONTROL Gerenciador de conjunto de relatórios] nas [!UICONTROL Ferramentas administrativas]. ( **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Individual Report Settings]** &gt; **[!UICONTROL Default Metrics]**.)

* Este relatório pode ser visualizado nos formatos de tendência e classificado.
* Este relatório pode usar um filtro de pesquisa para localizar itens de linha específicos.
* Os relatórios de [!UICONTROL Campanhas] e [!UICONTROL Elementos Criativos] são classificações baseadas neste relatório e são automaticamente criados com cada conjunto de relatórios.

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

   * Click-throughs: o número de vezes em que a variável *`s.campaign`* é definida
   * Todas as métricas de comércio eletrônico: Receita, Pedidos, Unidades, Carrinhos, Exibição de carrinhos, Adições a carrinhos, Remoções do carrinho.
   * Todos os eventos personalizados: Eventos 1-80 e Eventos 81-100 se em código H22 ou superior
   * Visitas e Visitantes: a disponibilidade depende da organização e do conjunto de relatórios. Entre em contato com seu Gerente de conta para obter mais informações.

**Propriedades do Reports &amp; Analytics**

* Click **[!UICONTROL Conversion]** &gt; **[!UICONTROL Campaigns]** &gt; **[!UICONTROL Tracking Code]** to locate this report, unless the menu is customized.

* Este relatório também pode ser detalhado por todas as [Variáveis da lista](https://marketing.adobe.com/resources/help/en_US/sc/implement/list_var.html).
* Visualizações de Página, Visitas e Visitantes únicos estão disponíveis como métricas.
* Este relatório pode utilizar segmentos.

**Propriedades da Ad Hoc Analysis**

* Além das variáveis de conversão mais inovadoras, você pode analisar o relatório de código de rastreamento por todos os outros relatórios dentro da interface do relatório.
* Além dos eventos de e-comércio e personalizados, você pode utilizar todas as métricas de conversão e de tráfego, assim como também utilizar alocação diferente para todas as métricas de conversão.
* Este relatório pode utilizar segmentos avançados.

