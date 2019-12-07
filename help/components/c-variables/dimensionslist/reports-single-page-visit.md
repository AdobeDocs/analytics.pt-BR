---
description: Para não ser confundida com a métrica de Visitas únicas à página na Ad Hoc Analysis, o relatório de Visitas únicas à página mostra as páginas em que os visitantes do site entram e saem, sem tomar passos para ver outras páginas.
title: Visita única à página
topic: Reports
uuid: 5ca52be8-c7f5-464a-8a06-55e8271760b4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visita única à página

Para não ser confundida com a métrica de Visitas únicas à página na Ad Hoc Analysis, o relatório de Visitas únicas à página mostra as páginas em que os visitantes do site entram e saem, sem tomar passos para ver outras páginas.

Este relatório é geralmente mais usado no contexto do relatório de [!UICONTROL Páginas], no entanto, pode também ser visualizado em todas as variáveis de tráfego, com [!UICONTROL relatórios de definição de caminho] habilitados. Você pode utilizar este relatório para identificar as páginas de entrada que são menos prováveis de obrigar um visitante a explorar mais site, ou de determinar quantas visitas consistem de uma única página. Estas informações permitem que você otimize o conteúdo para reduzir saídas nessas páginas.

## Propriedades de Relatório {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* Um relatório idêntico pode ser recuperado puxando um relatório de [!UICONTROL Páginas], usando um [!UICONTROL Acesso único] como uma métrica.

* Uma visita única à página é considerada uma visita contendo um único valor, não uma única solicitação de imagem.

   * No contexto de um [relatório de páginas](/help/components/c-variables/dimensionslist/reports-pages.md), somente uma única página pode disparar durante a visita.
   * No contexto de um [relatório de seções do site](/help/components/c-variables/dimensionslist/reports-site-sections.md), uma única seção do site é acionada na visita.
   * No contexto de uma [variável de tráfego](/help/admin/admin/c-traffic-variables/traffic-var.md), uma visita preenche este relatório, se um único valor for acionado.

* As visitas únicas à página podem consistir em várias solicitações de imagem, desde que a variável no contexto do relatório contenha um único valor exclusivo. Assim que um segundo valor exclusivo é preenchido, a visita não é mais considerada como uma visita única à página.
* Isso é considerado um tipo de relatório de definição de caminho. Por padrão, a variável de [!UICONTROL Páginas] possui definição de caminho habilitadas. No entanto, qualquer variável de tráfego possui a mesma capacidade também. Habilitar a definição de caminhos em variáveis de tráfego adicionais depende do seu contrato. Entre em contato com o Gerente de conta da sua organização para obter mais detalhes.
* Este relatório pode usar um filtro de pesquisa para localizar itens de linha específicos.
* Este relatório pode ser visualizado em Formatos [com tendência](/help/components/c-variables/dimensionslist/reports-types.md) e [classificados](/help/components/c-variables/dimensionslist/reports-types.md).

* Não existem detalhamentos disponíveis neste relatório.
* A única métrica disponível neste relatório é [!UICONTROL Visitas].

