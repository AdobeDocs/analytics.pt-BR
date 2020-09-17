---
description: A Ad Hoc Analysis é integrada ao ambiente de Segmentação de análise, de modo que você possa compartilhar, gerenciar e aplicar os segmentos de visitantes nos produtos da Adobe. A Ad Hoc Analysis oferece uma interface de usuário baseada em Java para o Construtor de segmentos e para o Gerenciador de segmentos que é idêntica às ferramentas baseadas na Web usadas por outras ferramentas do Analytics, adaptando-se às chamadas do servidor e fornecendo os mesmos recursos e funcionalidades de um console baseado em Java.
title: Construir segmentos
topic: Ad hoc analysis
uuid: e14fb777-900a-4700-8dc7-56a45c678d29
translation-type: tm+mt
source-git-commit: 42782779a9b9d5f4795b2663ec78678cd3aada02
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 93%

---


# Construir segmentos

>[!IMPORTANT]
>
>A Adobe está mudando o Ad Hoc Analysis para o fim da sua vida útil em 1º de março de 2021. [Saiba mais](https://adobe.ly/discoverworkspace)

A Ad Hoc Analysis é integrada ao ambiente de Segmentação de análise, de modo que você possa compartilhar, gerenciar e aplicar os segmentos de visitantes nos produtos da Adobe. A Ad Hoc Analysis oferece uma interface de usuário baseada em Java para o Construtor de segmentos e para o Gerenciador de segmentos que é idêntica às ferramentas baseadas na Web usadas por outras ferramentas do Analytics, adaptando-se às chamadas do servidor e fornecendo os mesmos recursos e funcionalidades de um console baseado em Java.

A Ad Hoc Analysis inclui recursos já conhecidos para a criação de segmentos e novas atualizações de recursos, como o [Gerenciador de segmentos](https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/segmentation-workflow/seg-manage.html), usado para configurar um [fluxo de trabalho](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) do gerenciamento de segmentos. Como sempre, você pode criar e salvar segmentos no [Construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) ou [gerar segmentos a partir de um relatório de Fallout](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.html) do console de Ad Hoc Analysis e depois salvar os segmentos novos ou estendidos na biblioteca de público-alvo para aplicativos e acessos gerais.  ![](assets/seg__overview_ad_hoc.png)

## Segmentação Unificada na Ad Hoc Analysis {#section_5FA03A06DE054448AD519CE30C39E294}

Para obter informações e instruções sobre como criar e gerenciar segmentos no ambiente de Segmentação Unificada, incluindo recursos da análise ad hoc, consulte a documentação da [Segmentação Unificada](/help/components/segmentation/segmentation-workflow/seg-build.md).

* [Novos recursos](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_BD58629D1A9346BF879E229FA6BEC7A2)
* [O que aconteceu com meus segmentos existentes?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_76CF47142D1A4FB6A0718AD9073049FE)
* [O que aconteceu com minhas pastas de segmento existentes? ](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_FB04DCF775694E69B761DCA53F301C30)
* [Posso gerenciar todos os segmentos do Analytics no Gerenciador de segmentos?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_AF5EDD72C74A4739BD40C4AF125CE489)
* [O que é um Contêiner de ocorrência? Ele é diferente de um Contêiner de exibições da página?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_65BBE60A836C4001938830DDA15DC256)
* [Quais direitos e privilégios são necessários para que eu possa usar, criar e gerenciar segmentos? ](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_648DFA3A882146C485A84ED014EEC707)
* [O que devo fazer com segmentos duplicados que têm o...](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_E2C3A1B4B4274D1B86CAA9C0359D049C)
* [Como a Adobe recomenda que eu limpe os segmentos? ](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_3AC2D265F9084557A24C6FB39DC6EE49)
* [Por que não posso excluir esse segmento?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_0FEB6711031A4ABCA915CDA745ECF38D)
* [Mais informações sobre o que acontece com os segmentos existentes ](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_83ACAB256F394DCD8B424D8920BDD853)

## Recursos {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* Os [segmentos](https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/seg-home.html) são universais para todos os conjuntos de relatórios. Anteriormente, os segmentos eram específicos ao conjunto de relatórios.
* O [Gerenciador de segmentos](https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/segmentation-workflow/seg-manage.html) permite que você configure [fluxos de trabalho](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) com verificação, marcação, compartilhamento de segmentos e recursos de aprovação.
* O [Construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) foi atualizado para simplificar a criação de segmentos.
* Você pode [adicionar tags a segmentos](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-tag.html) para organizar e pesquisar depois, em vez de usar pastas. Anteriormente, as pastas eram usadas (na [!DNL ad hoc analysis]) para organizar os segmentos.
* Você pode criar [Segmentos sequenciais](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-sequential-build.html) fora da Ad Hoc Analysis.

   >[!NOTE]
   >
   >Na Ad Hoc Analysis, não é possível adicionar intervalos de datas a segmentos. Esse recurso está disponível na Analysis Workspace. Além disso, não é possível usar a sequência Somente Antes/Somente depois na Ad Hoc Analysis.

## O que aconteceu com meus segmentos existentes? {#section_76CF47142D1A4FB6A0718AD9073049FE}

Seus segmentos existentes continuarão a funcionar da mesma maneira que faziam antes da introdução da Segmentação do Analytics. Quaisquer relatórios com esses segmentos aplicados continuarão a funcionar corretamente.

A maioria dos segmentos de conjunto e pré-definidos mais antigos serão migrados como modelos de segmentos no construtor de segmentos. Os modelos de segmentos são usados para criar rapidamente segmentos personalizados com públicos comuns. Os modelos de segmento não podem ser aplicados diretamente a um relatório, mas podem ser salvos facilmente em um segmento personalizado.

## O que aconteceu com minhas pastas de segmento existentes?   {#section_FB04DCF775694E69B761DCA53F301C30}

Em vez de pastas (Ad Hoc Analysis), o Gerenciador de segmentos usa [tags](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-tag.html). Os nomes das pastas são convertidos automaticamente em tags e estas são aplicadas aos respectivos segmentos.

## É possível gerenciar todos os segmentos do Analytics no Gerenciador de segmentos?   {#section_AF5EDD72C74A4739BD40C4AF125CE489}

No Gerenciador de segmentos da Ad Hoc Analysis, é possível visualizar somente os seus segmentos (ou seja, aqueles criados por você) e os segmentos que foram compartilhados especificamente com você.

## O que é um Contêiner de ocorrência? Ele é diferente de um Contêiner de exibições da página?   {#section_65BBE60A836C4001938830DDA15DC256}

O contêiner de Visualização de página foi renomeado para contêiner de Ocorrência para indicar que esse contêiner segmenta todos os tipos de dados e não apenas visualizações de página. Por exemplo, chamadas de rastreamento de links e chamadas [!DNL trackAction] de SDKs móveis são todas incluídas ou excluídas pelo contêiner de ocorrências.

Observe que não ocorreu uma alteração na forma como esse contêiner funciona; ele foi apenas renomeado.

## Quais direitos e privilégios são necessários para que eu possa usar, criar e gerenciar segmentos?   {#section_648DFA3A882146C485A84ED014EEC707}

Todos os usuários podem criar e editar segmentos pessoais. Esses segmentos podem ser compartilhados diretamente com qualquer outro usuário do Analytics.

Os administradores podem editar e [compartilhar segmentos](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/t-seg-share.html) com grupos e [definir os direitos](https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/segment-reference/seg-rights.html) de acesso da organização aos segmentos.

## O que devo fazer com segmentos duplicados que possuem o mesmo nome, mas podem ter definições diferentes? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Uma vez que os segmentos funcionam em vários conjuntos de relatórios, você pode acabar descobrindo que possui vários segmentos com o mesmo nome. Recomendamos que você

* Renomeie os segmentos com o mesmo nome, mas com diferentes definições, ou
* Exclua os segmentos que não são mais necessários.

## Como a Adobe recomenda que eu limpe os segmentos?   {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Marque todos os segmentos com uma tag legada.
* Analise todos os seus segmentos.
* Quando apropriado, adicione-os à biblioteca de segmentos.
* Aprove os segmentos canônicos.
* Marcar segmentos de acordo com as  práticas recomendadas.

## Por que não posso excluir esse segmento? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Se o segmento foi [publicado na Experience Cloud](https://docs.adobe.com/content/help/pt-BR/core-services/interface/audiences/t-publish-audience-segment.html), você não pode excluí-lo ou editá-lo. Entretanto, é possível copiá-lo e editar a versão copiada.

## Mais informações sobre o que acontece com os segmentos existentes   {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Categoria de segmentos </th> 
   <th colname="col2" class="entry"> O que acontece com esses segmentos? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Segmentos favoritos (Ad Hoc Analysis) </td> 
   <td colname="col2">Esses segmentos da Ad Hoc Analysis são exibidos como segmentos regulares no Adobe Analytics. <p>Eles não devem ser confundidos com o recurso Favoritos no Gerenciador de segmentos, que permite que você marque os segmentos como favoritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmentos pré-configurados: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Visitas únicas à página </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Visitas de dispositivos móveis </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Visitas da pesquisa natural </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Visitantes da pesquisa paga </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Visitantes com cookie de ID do visitante </li> 
    </ul> </td> 
   <td colname="col2"> <p>Esses segmentos serão transferidos como modelos de segmento no construtor de segmentos. </p> <p>Os relatórios com esses segmentos aplicados continuarão funcionando da forma correta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmentos da Experience Cloud (Suite): 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Não compradores </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Compradores </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Novas visitas </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Visitas de sites sociais </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Visitas de mais de 10 minutos* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Visitas com mais de cinco visitas anteriores* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Visitas do Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> A maioria desses segmentos (exceto os marcados com um asterisco *) serão transferidos como modelos de segmento no construtor de segmentos. Além disso, vários novos modelos de segmento foram adicionados. </p> <p>Os relatórios com esses segmentos aplicados continuarão funcionando da forma correta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmentos do administrador <p>(também conhecidos como segmentos "Globais") </p> </td> 
   <td colname="col2"> <p> Os segmentos do <b>administrador</b> serão migrados na nova interface de segmentos e serão exibidos como segmentos compartilhados com todos. </p> <p>O proprietário desses segmentos está definido como o administrador com a conta mais antiga na lista de usuários administradores da empresa de logon, no entanto, todos os Administradores podem excluir, editar e compartilhar esses segmentos. </p> <p>A interface de gerenciamento de segmento no Admin Console, onde os administradores criaram e gerenciaram esses segmentos globais, não está mais disponível. Agora, os administradores devem usar o novo construtor de segmentos para criar segmentos e compartilhá-los com os indivíduos ou grupos apropriados ou com todo mundo. </p> </td> 
  </tr> 
 </tbody> 
</table>

