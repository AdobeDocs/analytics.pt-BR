---
description: Para não ser confundida com a métrica de Visitas únicas à página na Ad Hoc Analysis, o relatório de Visitas únicas à página mostra as páginas em que os visitantes do site entram e saem, sem tomar passos para ver outras páginas.
seo-description: Para não ser confundida com a métrica de Visitas únicas à página na Ad Hoc Analysis, o relatório de Visitas únicas à página mostra as páginas em que os visitantes do site entram e saem, sem tomar passos para ver outras páginas.
seo-title: Visita única à página
solution: Analytics
title: Visita única à página
topic: 'Relatórios  '
uuid: 5 ca 52 be 8-c 7 f 5-464 a -8 a 06-55 e 8271760 b 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visita única à página

Para não ser confundida com a métrica de Visitas únicas à página na Ad Hoc Analysis, o relatório de Visitas únicas à página mostra as páginas em que os visitantes do site entram e saem, sem tomar passos para ver outras páginas.

Este relatório é geralmente mais usado no contexto do relatório de [!UICONTROL Páginas], no entanto, pode também ser visualizado em todas as variáveis de tráfego, com [!UICONTROL relatórios de definição de caminho] habilitados. Você pode utilizar este relatório para identificar as páginas de entrada que são menos prováveis de obrigar um visitante a explorar mais site, ou de determinar quantas visitas consistem de uma única página. Estas informações permitem que você otimize o conteúdo para reduzir saídas nessas páginas.

## Propriedades de Relatório {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* Um relatório idêntico pode ser recuperado puxando um relatório de [!UICONTROL Páginas], usando um [!UICONTROL Acesso único] como uma métrica.

* Uma visita única à página é considerada uma visita contendo um único valor, não uma única solicitação de imagem.

   * No contexto de um [relatório de páginas](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5), somente uma única página pode disparar durante a visita.
   * In the context of a [site sections report](../../../components/c-variables/dimensionslist/reports-site-sections.md#concept_39E550D7A9E34C9580E81F5F9E12BDDD), a single unique site section fires within the visit.
   * In the context of a [traffic variable](/help/admin/admin/c-traffic-variables/traffic-var.md), a visit populates this report if a single unique value is fired.

* As visitas únicas à página podem consistir em várias solicitações de imagem, desde que a variável no contexto do relatório contenha um único valor exclusivo. Assim que um segundo valor exclusivo é preenchido, a visita não é mais considerada como uma visita única à página.
* Isso é considerado um tipo de relatório de definição de caminho. Por padrão, a variável de [!UICONTROL Páginas] possui definição de caminho habilitadas. No entanto, qualquer variável de tráfego possui a mesma capacidade também. Habilitar a definição de caminhos em variáveis de tráfego adicionais depende do seu contrato. Entre em contato com o Gerente de conta da sua organização para obter mais detalhes.
* Este relatório pode usar um filtro de pesquisa para localizar itens de linha específicos.
* Este relatório pode ser visualizado em [formatos de tendência](/help/components/c-variables/dimensionslist/reports-types.md) e [classificados](/help/components/c-variables/dimensionslist/reports-types.md) .

* Não existem detalhamentos disponíveis neste relatório.
* A única métrica disponível neste relatório é [!UICONTROL Visitas].

