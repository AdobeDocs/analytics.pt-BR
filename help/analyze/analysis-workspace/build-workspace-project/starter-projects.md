---
description: Crie projetos do Espaço de trabalho com base em modelos padrão ou personalizados.
title: Modelos
feature: Workspace Basics
role: User, Admin
exl-id: 751399fe-6d4f-47cc-8827-82c992079b52
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 100%

---

# Modelos

Você pode criar um projeto a partir de:

* **Projeto em branco (padrão)**: para obter instruções, consulte [Criar um projeto no Analysis Workspace](/help/analyze/analysis-workspace/home.md).
* **Modelo padrão**: esses modelos são criados pela Adobe e fornecidos com o produto.
* **Modelo personalizado**: esses modelos podem ser criados, compartilhados ou excluídos por usuários com direitos de administrador ou por não administradores, desde que tenham recebido a permissão [!UICONTROL Analysis Workspace: salvar como modelo] no Admin Console. [Saiba mais...](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=pt-BR)

![](assets/start_modal.png)

## Criar modelos personalizados {#create-custom-template}

Os usuários com direitos de administrador podem tornar qualquer projeto criado por ele um modelo personalizado. Veja como:

1. Abrir o projeto.
1. Vá até **[!UICONTROL Projeto]** > **[!UICONTROL Salvar como modelo]**.

   ![](assets/save_project_template.png)

   O projeto será salvo com o nome do projeto atual, seguido da palavra (Modelo) entre parênteses. Os administradores podem alterar esse nome ao editar o modelo.

   >[!NOTE]
   >
   >Por padrão, os modelos de projeto estão visíveis para todos em sua organização. Você pode organizá-los aplicando tags. (Vá até **[!UICONTROL Projeto]** > **[!UICONTROL Informações e configurações do projeto]** para editar tags e descrições.)

Veja um vídeo sobre como criar e gerenciar modelos personalizados:

>[!VIDEO](https://video.tv.adobe.com/v/23231/?quality=12)

### Gerenciar modelos personalizados {#manage-custom-template}

| Ação | Descrição |
|--- |--- |
| Editar modelo | Permite que um administrador edite o modelo ao alterar a fonte de dados, modificar componentes, exibições, intervalos de data etc.  Para editar um modelo personalizado,<ul><li>abra a lista de modelos personalizados do Analysis Workspace, selecione um e clique em Editar modelo, ou</li><li>no Analytics, clique em Componentes > Projetos e filtre por Modelos. Clique no nome do modelo que deseja editar.</li></ul>**Observação:** após editar um modelo, dependendo da situação, você terá duas opções: Salvar, Salvar como. Elas se diferem da seguinte forma:<ul><li>**Salvar:** atualiza o modelo personalizado para todos os usuários. Quando outra pessoa cria um projeto a partir deste modelo personalizado, ela verá suas alterações.</li><li>**Salvar como:** cria uma cópia do modelo personalizado com suas alterações. (Você saberá que está no modo de edição quando o item de menu Compartilhar > Compartilhar projeto estiver desativado.)</li></ul> |
| Pesquisar nos modelos | Na caixa de diálogo Modelos personalizados, clique em Pesquisar modelos. |
| Classificar modelos | É possível classificar modelos por ordem alfabética, relevância e data de criação.  Na caixa de diálogo Modelos personalizados, clique em Classificar. |
| Aplicar tags ao modelo | Abra o modelo e vá até Projeto > Informações e configurações do projeto. Clique em Adicionar tags. |
| Modificar descrição do modelo | Abra o modelo e vá até Projeto > Informações e configurações do projeto. Clique duas vezes na descrição e edite-a. |


## Modelos padrão

Quando você abre um Espaço de trabalho pela primeira vez, os modelos ficam disponíveis no painel esquerdo. Os modelos do Analysis Workspace abrangem casos usuais. São agrupados pela vertical à qual pertencem e são preenchidos com diferentes dimensões, segmentos, métricas e visualizações, dependendo do conjunto de relatórios selecionado.

Você pode usar esses modelos pré-preenchidos como estão ou adaptá-los às suas necessidades (adicionando ou substituindo métricas ou visualizações, por exemplo) e salvá-los com um novo nome.

Tutorial em vídeo sobre [Modelos padrão no Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/standard-templates-in-analysis-workspace.html?lang=pt-BR) (2:46)

Estes são os modelos disponíveis e as perguntas que cada modelo ajuda a responder.

### Treinamento

Esse novo modelo padrão o orientará sobre a terminologia comum e as etapas para criar sua primeira análise no Workspace. Está disponível como modelo padrão no modal Novo projeto e substitui o projeto de amostra atual para novos usuários que não têm outros projetos na lista.

Veja um vídeo sobre o modelo de [!UICONTROL Tutorial de treinamento]:

>[!VIDEO](https://video.tv.adobe.com/v/33773/?quality=12)

### Publicidade

>[!IMPORTANT]
>
>Os modelos de publicidade estão disponíveis somente se o conjunto de relatórios estiver habilitado para o [Advertising Analytics](https://experienceleague.adobe.com/docs/analytics/integration/advertising-analytics/overview.html?lang=pt-BR).

* **Mecanismos de pesquisa paga**: esse modelo detalha tendências de publicidade, plataformas de publicidade, palavras-chave, contas, campanhas e muito mais.

### Comércio

* **Magento: Marketing e Comércio**: esse modelo detalha sua conversão de comércio eletrônico por atribuição de canal de marketing, além de fornecer informações por palavra-chave de pesquisa, página de aterrissagem, localização geográfica e muito mais. Veja um tutorial em vídeo sobre o [Magento: Modelos de marketing e comércio](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/magento/magento-analysis-workspace-template.html?lang=pt-BR).

### Coleta de dados

* **Impacto do ITP**: entenda como o ITP da Apple afeta seus dados e como ajustar os relatórios adequadamente.

### Mídia

* **Consumo de conteúdo**: quem são meus leitores fiéis
* **Recenticidade - Frequência - Fidelidade**: qual conteúdo está sendo mais consumido e está envolvendo os usuários?
* **Consumo de streaming de mídia**: fornece tendências e principais métricas de consumo de mídia em todos os dispositivos digitais. Veja um vídeo sobre o modelo de consumo de streaming de mídia:

   >[!VIDEO](https://video.tv.adobe.com/v/23901/?quality=12)

### Publicação de conteúdo para dispositivos móveis

>[!IMPORTANT]
>
>Os modelos para publicação de conteúdo para dispositivos móveis estão disponíveis somente se o conjunto de relatórios estiver habilitado para análise de aplicativos para dispositivos móveis.

* **Aquisição:** verifique o desempenho dos links de aquisição para publicação de conteúdo para dispositivos móveis.
* **Uso do aplicativo:** quantos usuários, inicializações e primeiras inicializações o aplicativo teve e qual foi a duração média das sessões?
* **Jornadas**: quais são os principais padrões de uso do meu aplicativo?
* **Métricas principais**: permite o controle das métricas principais do seu aplicativo.
* **Localização**: inclui um mapa que exibe os dados de localização.
* **Mensagens**: focaliza o desempenho das mensagens no aplicativo e por push.
* **Desempenho:** como está o desempenho do aplicativo e que problemas os usuários estão tendo?
* **Retenção:** quem são meus usuários fiéis e o que eles fazem?

### Varejo

* **Desempenho da campanha:** que campanhas estão gerando mais receita?
* **Produtos:** que produtos estão tendo o melhor desempenho?

### Web

* **Aquisição:** quais são os principais impulsionadores de tráfego do meu site?
* **Visão geral do desempenho do site AEM**: como está o desempenho do meu site Adobe Experience Manager?
* **Consumo de conteúdo:** quais são os lugares mais acessados do meu site?
* **Retenção:** que tipo de usuário tem maior probabilidade de se tornar um usuário fiel do meu site?
* **Tecnologia:** que tecnologia as pessoas estão usando para acessar o meu site?

### Pessoas

O modelo é baseado na métrica de Pessoas, que é uma versão deduplicada da métrica Visitantes únicos. A métrica de Pessoas oferece uma medida da frequência que os clientes que usam vários dispositivos interagem com a sua marca. O modelo permite: 

* Segmentar seus dados por EUA/Canadá vs. o resto do mundo
* Comparar as métricas de Pessoas e de Visitantes únicos lado a lado
* Ver a &quot;taxa de compressão&quot;, uma métrica calculada que calcula o quão menor a métrica de Pessoas é como uma porcentagem de Visitantes únicos
* Comparar os totais de tipos de dispositivos que seus clientes usam.
* Ver a média de quantos dispositivos por pessoa são usados
* Descobrir como usar o empilhamento de segmentos com a métrica de Pessoas
* Saber mais sobre como usar a Experience Cloud ID em seu ambiente melhora a eficácia da métrica Pessoas

### Journey IQ: modelo do Analytics entre dispositivos

<!--This content is mirrored in the CDA doc.-->

Esse modelo permite que você veja dados essenciais de desempenho entre dispositivos. Ele está disponível somente para clientes que têm acesso ao [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR) (CDA).

* **Identificação de usuários**: mostra a frequência com que os visitantes do site são identificados usando métodos com base na Análise entre dispositivos.
* **Medição do tamanho do público-alvo**: mostra uma comparação entre &quot;Dispositivos únicos&quot; e &quot;Pessoas&quot;. A proporção desses dois números é conhecida como &quot;compactação entre dispositivos&quot;, uma métrica calculada visível neste painel. Essa métrica de compactação depende de vários fatores:
   * **Taxa de logon**: quanto mais usuários entrarem no site, mais a Adobe poderá identificar e compilar visitantes entre dispositivos. Os sites com uma taxa de logon baixa também têm taxas de compactação baixas.
   * **Cobertura da Experience Cloud ID**: somente os visitantes com uma ECID podem ser compilados. Uma porcentagem menor de visitantes do site que usam uma ECID está correlacionada a taxas de compactação mais baixas.
   * **Uso de vários dispositivos**: se os visitantes do site não usarem vários dispositivos, você poderá ver taxas de compactação mais baixas.
   * **Granularidade do relatório**: a compactação por dia geralmente é menor do que a compactação por mês ou ano. As chances de um indivíduo usar vários dispositivos se tornam menores em um único dia do que em mais de um mês inteiro. A segmentação, a filtragem ou o uso de dimensões de detalhamento também podem mostrar uma taxa de compactação menor.
* **Segmentos com base em pessoas**: contêm uma lista suspensa de segmentos que permitem visualizar dados específicos do dispositivo. Esse painel incentiva a experimentação com segmentos para ver como a inclusão ou exclusão de tipos de dispositivos afetam os relatórios.
* **Análise da jornada entre dispositivos**: fornece relatórios de fluxo e fallout de acordo com o tipo de dispositivo.
* **Atribuição entre dispositivos**: combine os recursos de Journey IQ e Attribution IQ.
* **Outras dicas e truques**: tópicos úteis sobre o CDA que permitem que você o aproveite ao máximo.
