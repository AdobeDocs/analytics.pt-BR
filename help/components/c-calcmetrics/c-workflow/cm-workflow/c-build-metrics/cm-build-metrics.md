---
description: O Criador de métricas calculadas oferece uma tela para arrastar e soltar dimensões, métricas, segmentos e funções a fim de criar métricas personalizadas com base em lógicas de hierarquia de contêiner, regras e operadores. Essa ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples ou avançadas e mais complexas.
title: Criar métricas
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: d9f95b12a43305cecff1190e6544334f3b48835d
workflow-type: ht
source-wordcount: '1112'
ht-degree: 100%

---

# Criar métricas {#build-metrics}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="ID externa"
>abstract="Alterar o ID externo pode afetar como a métrica calculada aparece em fontes externas, como em ferramentas de business intelligence"


O Adobe Analytics fornece uma tela para arrastar e soltar dimensões, métricas, segmentos e funções para criar métricas personalizadas com base na lógica de hierarquia de containers, regras e operadores. Esta ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples e complexas.

## Comece criando uma métrica calculada

É possível usar o construtor de métricas calculadas para criar ou editar métricas calculadas. Quando criadas dessa forma, as métricas calculadas ficam disponíveis na lista de componentes e podem ser usadas em projetos por toda a organização. Como alternativa, é possível criar rapidamente uma métrica calculada que esteja disponível somente para o projeto em que foi criada, conforme descrito na seção [Criar métricas calculadas para um único projeto](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) em [Métricas](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

Acesse o construtor de métricas calculadas para começar a criar uma métrica calculada que esteja disponível na lista de componentes.

1. Acesse o construtor de métricas calculadas de qualquer uma das seguintes maneiras:

   * No Analysis Workspace, abra um projeto e selecione **[!UICONTROL Componentes]** > **[!UICONTROL Criar métrica]**.
   * No Analysis Workspace, abra um projeto e selecione o ícone de **adição** ao lado da seção [!UICONTROL **Métricas**] no painel esquerdo.
   * No [!DNL Adobe Analytics], acesse **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]** e selecione **[!UICONTROL + Adicionar]** na parte superior da página Métricas calculadas.

1. Prossiga para as [Áreas do construtor de métricas calculadas](#areas-of-the-calculated-metrics-builder).

## Áreas do construtor de métricas calculadas

A imagem a seguir e a tabela que a acompanha explicam algumas das principais áreas e recursos do Construtor de métricas calculadas.

![](assets/cm_builder_ui.png)

| Localização na imagem | Nome e função |
|---|---|
| 1 | **Título:** é obrigatório fornecer um nome para a métrica. Não é possível salvar a métrica sem um nome. |
| 2 | **Descrição:** forneça uma descrição simples para mostrar a utilidade da métrica e distingui-la de outras semelhantes. <p>A descrição também será exibida em um relatório. É melhor NÃO colocar a fórmula na descrição; em vez disso, descreva quando ela deve ou não ser utilizada. (A fórmula é gerada conforme você cria a métrica, abaixo do cabeçalho Resumo. Como resultado, não é necessário adicionar a fórmula à descrição.) </p> |
| 3 | **Formato:** as opções incluem Decimal, Hora, Porcentagem e Moeda. |
| 4 | **Casas decimais:** mostra quantas casas decimais serão exibidas no relatório. O número máximo de casas decimais que você pode especificar é 10. |
| 5 | **Exibir tendência ascendente como:** esta configuração de polaridade da métrica mostra se o Analytics deve considerar uma tendência ascendente como boa (verde) ou ruim (vermelha). Como resultado, o gráfico do relatório será exibido em verde ou vermelho ao subir. |
| 6 | **Tags:** adicionar tags é uma boa maneira de organizar métricas. Todos os usuários podem criar tags e aplicar uma ou mais tags a uma métrica. No entanto, você pode visualizar tags somente para seus segmentos ou os compartilhados com você. Que tipos de tags você deve criar? Estas são algumas sugestões para tags úteis:<ul><li>**Nomes de equipe**, como Marketing social e Marketing para dispositivos móveis.</li><li>**Projetos** (tags de análise), como Análise de página de entrada.</li><li>**Categorias**, como Mulheres e Geografia.</li><li>**Fluxos de trabalho**, como Para aprovação, Preparado por (uma unidade de negócios específica)</li></ul> |
| 7 | **Resumo:** <p>a fórmula de Resumo é atualizada sempre que a definição da métrica é alterada. Esta fórmula também é exibida no painel de métricas à esquerda, ao passar o mouse sobre uma métrica e clicar no  ícone <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />. </p> |
| 8 | **Definição:** arraste para cá métricas, métricas calculadas, segmentos e/ou funções para criar a métrica calculada. <ul><li>Se você arrastar uma métrica calculada, ela expandirá automaticamente sua definição de métrica. </li> <li>Você pode aninhar definições em contêineres. Contudo, diferentemente dos contêineres de segmentos, esses contêineres funcionam como uma expressão matemática e determinam a ordem das operações. </li> </ul> |
| 9 | **Operador:** dividido por ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) é o operador padrão, além dos operadores +, - e x. |
| 10 | **Visualização:** fornece uma leitura rápida sobre possíveis erros. A visualização abrange os últimos 90 dias. Esta é uma maneira de medir, ao menos de maneira inicial, se você selecionou os componentes certos para a sua métrica. Um resultado inesperado significa que você precisa analisar a definição da métrica novamente. |
| 11 | **Compatibilidade do produto:**: mostra se a métrica é compatível com os <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=pt-BR"  >dados atuais</a>, com os dados totalmente processados ou somente com os relatórios do canal de marketing (alocação de primeiro contato). <p>Observação: os dados atuais não suportam todas as métricas. Métricas que contêm segmentos ou funções não são compatíveis com os dados atuais. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Mais... </a> </p> </p> |
| 12 | **Adicionar:** em todos os tipos de métricas calculadas, é possível adicionar containers e números estáticos à definição. Para métricas calculadas avançadas, também é possível adicionar funções e segmentos. <ul><li>Os contêineres funcionam como uma expressão matemática e determinam a ordem das operações. Todo o conteúdo do contêiner será processado antes da próxima operação.</li><li>Arrastar um segmento para um contêiner segmenta todo o conteúdo do mesmo. (Somente métricas calculadas avançadas)</li><li>É possível empilhar vários segmentos em um contêiner.</li></ul> |
| 13 | **Ícone de engrenagem (tipo de métrica e atribuição):** selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  >tipo de métrica e os modelos de atribuição</a>. |
| 14 | **Novo:** permite criar um novo componente, como um novo segmento (que leva você ao <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  >Construtor de segmentos</a>.) |
| 15 | **Componentes de pesquisa:** esta barra de pesquisa permite procurar dimensões, métricas, segmentos (somente métricas calculadas avançadas) e funções (somente métricas calculadas avançadas). |
| 16 | **Lista de dimensões:** em vez de sair do Construtor de métricas calculadas para criar um segmento simples (no Construtor de segmentos), como “Página = Página inicial”, é possível arrastar a Página e selecionar Página inicial diretamente no Construtor de métricas calculadas.<p>Isso resulta em um fluxo de trabalho mais simplificado para a criação de métricas calculadas segmentadas.</p> |
| 17 | **Lista de métricas:** as métricas têm três categorias: <ul> <li>Métricas padrão (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Métricas calculadas ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Modelos de métricas ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />): na parte inferior da lista. </li> </ul> <p>Ao passar o mouse sobre uma métrica, é possível ver o ícone de informações à direita.  <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Clicar neste ícone fornece as seguintes informações: </p><ul> <li>A fórmula de como é calculado. </li><li>Uma tendência prevista da métrica. </li><li>Um ícone de edição (lápis) <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> na parte superior direita que leva ao Construtor de métricas calculadas, onde é possível editar a métrica calculada. </li></ul> |
| 18 | **Lista de segmentos** (apenas métricas calculadas avançadas): como admin, esta lista mostra todos os segmentos criados na sua empresa de logon. Caso você seja um usuário não administrativo, esta lista mostra os segmentos possuídos por você e compartilhados com você. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html?lang=pt-BR"  > Mais... </a> |
| 19 | **Lista de funções** (apenas métricas calculadas avançadas): as funções estão divididas em duas listas: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  >Básicas </a> (usadas com mais frequência) e <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  >Avançadas </a>. |
| 20 | **Seletor do conjunto de relatórios:** permite alternar para um conjunto de relatórios diferente. |

{style="table-layout:auto"}
