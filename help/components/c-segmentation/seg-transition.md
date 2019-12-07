---
description: 'null'
keywords: segmentation;segments
title: Perguntas frequentes
topic: Segments
uuid: f49dc829-1d53-4183-9add-1aeaa5219d89
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Perguntas frequentes

Responde perguntas frequentes sobre recursos de segmentação, acesso, permissões, práticas recomendadas e gerenciamento de segmentos herdados.

## Recursos {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* Segmentação na Analysis Workspace:

   * Você pode [comparar segmentos](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segment-comparison.html).
   * Use [segmentos como dimensões](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segments_as_dimensions.html) em uma comparação.
   * Use segmentos na [análise de fallout](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/graphics/compare-segments-fallout.html).

* É possível [aplicar vários segmentos a um relatório ou projeto](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md).
* Os segmentos são universais para todos os conjuntos de relatórios.
* O [Construtor de segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) simplifica a criação de segmentos.
* O [Gerenciador de segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) permite que você configure [fluxos de trabalho](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) com verificação, marcação, compartilhamento de segmentos e recursos de aprovação.

* Você pode [adicionar tags a segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) para organizar e pesquisar depois, em vez de usar pastas. Anteriormente, as pastas eram usadas (na [!DNL Ad Hoc Analysis]) para organizar os segmentos.

* Você pode criar [Segmentos sequenciais](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md) fora da Ad Hoc Analysis.
* O contêiner de Visualização de página foi renomeado para contêiner de Ocorrência para indicar que esse contêiner segmenta todos os tipos de dados e não apenas visualizações de página. Por exemplo, chamadas de rastreamento de link e chamadas trackAction de SDKs móveis são todas incluídas ou excluídas pelo contêiner de ocorrências. Observe que não houve uma alteração no funcionamento deste contêiner; ele foi apenas renomeado.

Consulte a publicação [Melhorias na segmentação do Adobe Analytics](https://blogs.adobe.com/digitalmarketing/analytics/improving-segmentation-adobe-analytics/) no Blog de marketing digital para obter mais detalhes.

## Acesse as Ferramentas de segmentação {#section_088AD0E4E21943DFA8CF7206AEC485DD}

**Como obtenho o Construtor de segmentos?**

Para acessar o Construtor de segmentos, basta:

* Exiba um relatório existente e clicar no ícone Segmentos ![](assets/segment_icon.png) na navegação à esquerda. No painel de segmentos exibido, clique em **[!UICONTROL Adicionar]** ou

* Clique em **[!UICONTROL Adicionar mais, na parte superior do Gerenciador de segmentos]**.  ![](assets/add_button.png)

   or

* Clique em um título de segmento existente no Gerenciador de segmentos para editar o segmento no Construtor de segmentos.

**Como obtenho o Gerenciador de Segmentos?**

Para acessar o Gerenciador de segmentos:

* Vá para **[!UICONTROL Analytics]** &gt; **[!UICONTROL Componentes]** na navegação superior. Em seguida, clique em **[!UICONTROL Segmentos]** ou

* Exiba um relatório existente e clicar no ícone Segmentos ![](assets/segment_icon.png) na navegação à esquerda. Em seguida, clique em **[!UICONTROL Gerenciar]** ou

* Pressione a tecla “/” em qualquer lugar na interface e pesquisando pelo gerenciador de segmentos.

**Para onde foi o menu suspenso de segmentos herdados?**

O menu suspenso de segmentos em Relatórios e análises foi substituído por uma interface do  [Construtor de segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) mais avançada, que permite criar segmentos “universais” utilizáveis em conjuntos de relatórios e soluções do Adobe Analytics. Para exibir uma lista de segmentos existentes, clique no ícone de Segmentos ![](assets/segment_icon.png)

no painel de navegação esquerdo e no painel de segmentos.

**Para onde foi o menu suspenso de conjunto de relatórios herdados?**

O menu suspenso do conjunto de relatórios foi movido para o lado do seletor de datas, no canto superior direito de cada relatório ou painel.

![](assets/report_suite_selector.png)

## Permissões {#section_648DFA3A882146C485A84ED014EEC707}

**Que direitos e privilégios eu preciso para usar, criar e gerenciar segmentos?**

Por padrão, todos os usuários podem criar e editar segmentos pessoais. Contudo, os administradores podem escolher quem deve ter [permissões para criar segmentos](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) e quem pode atribuí-los a grupos específicos. Esses segmentos podem ser compartilhados diretamente com qualquer outro usuário do Analytics.

Os administradores podem editar qualquer segmento e compartilhar segmentos com grupos e todos na organização. [Mais...](/help/components/c-segmentation/seg-reference/seg-rights.md)

**É possível exibir todos os segmentos na empresa?**

Sim, administradores podem visualizar todos os segmentos nas interfaces do usuário do [!DNL Analysis Workspace] e do [!DNL Reports & Analytics].

O Construtor de relatórios e a Análise ad hoc exibem os segmentos que você possui e os segmentos que foram compartilhados com você.

**É possível gerenciar todos os segmentos do Analytics no Gerenciador de segmentos?**

Sim, todos os segmentos podem ser gerenciados no Gerenciador de segmentos do Analysis Workspace, do Relatórios e análises e da Análise ad hoc. O Gerenciador de segmentos exibe segmentos que são visíveis para o proprietário (usuário que criou o segmento), usuários compartilhados e usuários administradores. O seletor de segmentos exibe segmentos de propriedade e compartilhados com o usuário.

Administradores podem visualizar todos os segmentos nas interfaces do usuário da Analysis Workspace e do [!DNL Reports & Analytics].

O Construtor de relatórios e a Análise ad hoc exibem somente os segmentos criados por você ou os segmentos que foram compartilhados especificamente com você.

**Por que não posso excluir esse segmento?**

Se o segmento foi [publicado na Experience Cloud](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md), você não pode excluí-lo ou editá-lo. Entretanto, é possível copiá-lo e editar a versão copiada.

## Práticas recomendadas {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

**O que devo fazer com segmentos duplicados que possuem o mesmo nome, mas podem ter definições diferentes?**
Agora que os segmentos funcionam em vários conjuntos de relatórios, você pode acabar descobrindo que possui vários segmentos com o mesmo nome. Recomendamos que você

* Renomeie os segmentos com o mesmo nome, mas com diferentes definições, ou
* Exclua os segmentos que não são mais necessários.

**O que a Adobe recomenda com relação à limpeza de segmentos?**

* Marque todos os segmentos com uma tag legada.
* Analise todos os seus segmentos.
* Quando apropriado, adicione-os à biblioteca de segmentos.
* Aprovar segmentos canônicos.
* Marcar segmentos de acordo com as  [práticas recomendadas](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md).

## Gerenciamento de segmentos herdados {#section_76CF47142D1A4FB6A0718AD9073049FE}

**O que aconteceu com meus segmentos existentes?**

Seus segmentos existentes continuarão a funcionar como anteriormente. Quaisquer relatórios com esses segmentos aplicados continuarão a funcionar corretamente. [Mais...](/help/components/c-segmentation/seg-transition.md)

A maioria dos segmentos pré-definidos e de conjunto serão migrados como  modelos de segmento no Construtor de segmentos. Os modelos de segmentos são usados para criar rapidamente segmentos personalizados com públicos comuns. Os modelos de segmento não podem ser aplicados diretamente a um relatório, mas podem ser salvos facilmente em um segmento personalizado.

Os modelos de segmento são marcados com um ícone especial no Construtor de segmentos:

![](assets/seg_templates.png)

**O que aconteceu com as pastas de segmento existentes?**

Em vez de pastas (análise ad hoc), o Gerenciador de segmentos usa  específicos. Os nomes das pastas são convertidos automaticamente em tags e estas são aplicadas aos respectivos segmentos.

**O que aconteceu com os relatórios programados com segmentos aplicados?**

Os relatórios agendados continuar a funcionar apropriadamente com os segmentos definidos.

Ao excluir um segmento, os relatórios e painéis agendados com esse segmento aplicado continuam a funcionar normalmente, ou seja, o segmento ou painel continua a usar o segmento excluído.

Os relatórios agendados não são atualizados quando você edita um segmento com o mesmo nome. Exemplo: imagine que você tem 2 segmentos com o mesmo nome em conjuntos de relatórios diferentes:

![](assets/duplicate_seg_names.png)

Você tem um marcador que faz referência ao segmento para o conjunto de relatórios da produção principal. Em seguida, você exclui esse segmento, pois é uma duplicata. O marcador continuará a funcionar, com referência à definição do segmento excluído. Se você alterar a definição de segmento para o segmento de desenvolvimento principal a fim de incluir a Ilha de Catalina e Tijuana no México, o segmento aplicado ao marcador não mudará. Usará a definição antiga. Para corrigir isso, atualize o marcador para fazer referência à nova definição. Se você não tiver certeza se um marcador, painel ou relatório agendado está usando um segmento excluído, é possível alterar o nome do segmento restante para que fique mais clara se o marcador usa o segmento restante.

**O que acontece com os segmentos de Data Warehouse?**

Todos os segmentos existentes no Data Warehouse ainda funcionam nele. A maioria dos segmentos do Data Warehouse também funcionarão em outros componentes, como a Analysis Workspace, a Ad Hoc Analysis e o Reports &amp; Analytics.

Você pode criar ou editar novos segmentos de Data Warehouse no gerenciador/construtor de segmentos. O mecanismo de Compatibilidade do produto no Construtor de segmentos determina automaticamente se um segmento é compatível com o Data Warehouse.

**O que acontece com os segmentos favoritos (análise ad hoc)?**

Esses segmentos da análise ad hoc são exibidos como segmentos regulares no Adobe Analytics.

Eles não devem ser confundidos com o recurso Favoritos no Gerenciador de segmentos, que permite que você marque os segmentos como favoritos.

**O que acontece com os segmentos pré-configurados?**

* **Visitas únicas à página**
* **Visitas de dispositivos móveis**
* **Visitas da pesquisa natural**
* **Visitantes da pesquisa paga**
* **Visitantes com cookie de ID do visitante**

Esses segmentos serão transferidos como  modelos de segmento no Construtor de segmentos.

Os relatórios com esses segmentos aplicados continuarão funcionando da forma correta.

**O que acontece com os segmentos da Experience Cloud (Suite):**

* Não compradores
* Compradores
* Novas visitas
* Visitas de sites sociais
* Visitas de mais de 10 minutos*
* Visitas com mais de cinco visitas anteriores*
* Visitas do Facebook*

A maioria desses segmentos (exceto os marcados com um asterisco *) serão transferidos como  modelos de segmento no construtor de segmentos. Além disso, vários novos modelos de segmento foram adicionados.

Os relatórios com esses segmentos aplicados continuarão funcionando da forma correta.

**O que acontece com os segmentos Admin (também conhecidos como segmentos “Globais”)?**

Os segmentos do **administrador** serão migrados na nova interface de segmentos e serão exibidos como segmentos compartilhados com todos.

O proprietário desses segmentos está definido como o administrador com a conta mais antiga na lista de usuários administradores da empresa de logon, no entanto, todos os Administradores podem excluir, editar e compartilhar esses segmentos.

A interface de gerenciamento de segmento no Admin Console, onde os administradores criaram e gerenciaram esses segmentos globais, não está mais disponível. Os administradores agora devem usar o novo construtor de segmentos para criar segmentos e compartilhá-los com os grupos ou indivíduos apropriados, ou com todos.

<!-- 

seg_definition.xml

 -->

Os segmentos existentes que usam lógica que foi alterada como descrito nesse documento continuam a funcionar corretamente, embora precisem ser atualizados antes de serem salvos novamente. Por exemplo, se você tem um segmento existente, onde Estados dos EUA contém "Nova York", ele continua a funcionar corretamente, embora na próxima vez que você editar o segmento será necessário atualizá-lo para usar o tipo enumerado com uma condição de igual.

**Dicas de migração**

As seguintes dicas ajudarão você a migrar dimensões comuns:

* Cidade/regiões/país geográfico - pesquise e selecione cidades, regiões ou países específicos em vez de usar uma correspondência parcial.
* Navegadores - use a dimensão de Tipos de navegador para obter todos os navegadores em um tipo, por exemplo, Google Chrome
* Sistemas operacionais - use as dimensões de Tipos de sistema operacional para obter todos os sistemas operacionais em um tipo, por exemplo, Microsoft Windows.

* [Dimensões novas e renomeadas](/help/components/c-segmentation/seg-transition.md#section_73CF121B64A24DEF8E6499F3167BF742)
* [Alterações em Contém](/help/components/c-segmentation/seg-transition.md#section_1A9EDEE5CBC44B5AA6262560052ABE77)
* [Alterações em Menor que e Maior que](/help/components/c-segmentation/seg-transition.md#section_84A8AAD0344148AD9F9211D3EB271903)

## Dimensões novas e renomeadas {#section_73CF121B64A24DEF8E6499F3167BF742}

A tabela a seguir contém uma lista de dimensões que foram renomeadas no Construtor de segmentos.

<table id="table_1A8C1940FD0446FA8414C6A7DE66E44C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome da nova dimensão </th> 
   <th colname="col2" class="entry"> Nome anterior </th> 
   <th colname="col3" class="entry"> Notas </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tipos de sistema operacional </td> 
   <td colname="col2"> Novo </td> 
   <td colname="col3"> Adicionado no segundo trimestre de 2015. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largura do navegador - Classificado </td> 
   <td colname="col2"> Largura da janela do navegador </td> 
   <td colname="col3"> Essa dimensão é compatível com todas as interfaces e é dividida em uma lista enumerada de intervalos em vez dos valores inteiros específicos. Se for necessário segmentar valores específicos, use a versão granular dessa dimensão no segmento de data warehouse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Altura do navegador - Classificado </td> 
   <td colname="col2"> Altura da janela do navegador </td> 
   <td colname="col3"> Essa dimensão é compatível com todas as interfaces e é dividida em uma lista enumerada de intervalos em vez dos valores inteiros específicos. Se for necessário segmentar valores específicos, use a versão granular dessa dimensão no segmento de data warehouse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largura do navegador - Granular </td> 
   <td colname="col2"> Largura da janela do navegador </td> 
   <td colname="col3"> <p>Isso foi renomeado e agora é compatível somente com data warehouse. Ao definir segmentos compatíveis com todas as interfaces, use o tipo enumerado, Largura de navegador - Classificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Altura do navegador - Granular </td> 
   <td colname="col2"> Altura da janela do navegador </td> 
   <td colname="col3"> <p>Isso foi renomeado e agora é compatível somente com data warehouse. Ao definir segmentos compatíveis com todas as interfaces, use o tipo enumerado, Altura do navegador - Classificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suporte a cookies </td> 
   <td colname="col2"> Cookies </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intensidade de cor </td> 
   <td colname="col2"> Intensidade de cor do monitor </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> "Aplicativo - *" </td> 
   <td colname="col3"> Os prefixos "Aplicativo - " foram removidos de vários tipos de dimensão. Como os dados de aplicativo móvel são normalmente capturados em um conjunto de relatórios que não contém dados da Web, esses prefixos não são necessários. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página de entrada original </td> 
   <td colname="col2"> Página de entrada original </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Java ativado </td> 
   <td colname="col2"> Java </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Extensão máx. do URL do navegador móvel </td> 
   <td colname="col2"> Extensão do URL do navegador remoto </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Decoração de correio móvel </td> 
   <td colname="col2"> Suporte a email de decoração remoto </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dispositivo móvel </td> 
   <td colname="col2"> Nome do dispositivo móvel </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Extensão Max do Marcador Remoto </td> 
   <td colname="col2"> Extensão Max do URL do Marcador Remoto </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Extensão máx. de email móvel </td> 
   <td colname="col2"> Extensão Max do URL do Email Remoto </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sistema operacional móvel (obsoleto) </td> 
   <td colname="col2"> Sistema operacional móvel </td> 
   <td colname="col3"> Use a dimensão do Sistema operacional e, em vez disso, aplique a visitas de segmentos de dispositivos móveis. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Push móvel para falar </td> 
   <td colname="col2"> PTT Remoto </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizações da Pesquisa de Opinião </td> 
   <td colname="col2"> Total de visualizações da pesquisa </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Respostas da Pesquisa de Opinião </td> 
   <td colname="col2"> Total de respostas da pesquisa </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profundidade da Visita </td> 
   <td colname="col2"> Comprimento do caminho </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Código Postal </td> 
   <td colname="col2"> CEP/Código postal </td> 
   <td colname="col3"> - </td> 
  </tr> 
 </tbody> 
</table>

## Alterações nas dimensões com base em sequência de caracteres com valores conhecidos {#section_1A9EDEE5CBC44B5AA6262560052ABE77}

Dimensões com base em sequência de caracteres com conjunto de valores conhecidos foram alteradas para tipos enumerados. Ao criar um segmento com essas dimensões, a lista é pré-preenchida com todos os valores conhecidos e o único operador suportado é igual. Isso permite que você segmente rapidamente os valores exatos que você estava procurando sem selecionar valores não intencionais ao usar correspondências menos restritivas.

As seguintes dimensões foram alteradas para listas enumeradas:

| fabricante remoto | comprimento de email remoto | intensidade de cor |
|---|---|---|
| tamanho da tela remota | número do dispositivo remoto | resolução do monitor |
| altura da tela remota | push móvel para falar | plugin |
| Suporte a cookie em dispositivo móvel | decoração de correio móvel | sistema operacional |
| Suporte a imagem em dispositivo móvel | serviços de informações Remotos | tipo de referenciador |
| intensidade de cor remota | tipo de dispositivo móvel | mecanismo de pesquisa |
| suporte a áudio remoto | tipo de navegador | state |
| suporte a vídeo remoto | navegador | país geográfico |
| drm remoto | tipo de conexão | região geográfica |
| protocolos de rede remota | operadora de celular | cidade geográfica |
| sistema operacional móvel | cookie | dma geográfico |
| java vm móvel | fidelidade do cliente | cookie persistente |
| tamanho do marcador remoto | java ativado | pesquisa paga |
| extensão do URL remoto | idioma |  |

## Alterações nas dimensões com base em inteiro com valores conhecidos {#section_84A8AAD0344148AD9F9211D3EB271903}

Dimensões com base em inteiros (como a largura do navegador) com um conjunto conhecido de valores foram divididas em intervalos enumerados para que você possa definir rapidamente segmentos para um intervalo específico. Essas listas enumeradas são anexadas com " - Classificado" após o nome da dimensão. A seguinte tela demonstra como essas dimensões são segmentadas usando as interfaces do construtor de segmento anterior e novo:

![](assets/seg_browser_dimension.png)

Os operadores menor que, maior que e semelhante agora são compatíveis somente com os segmentos do Data Warehouse. Os segmentos que devem ser compatíveis com todas as interfaces de relatório devem usar a versão “Classificada” da métrica com o operador igual.
