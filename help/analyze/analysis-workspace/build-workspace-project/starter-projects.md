---
description: 'null'
title: Modelos
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Modelos

## Modelos {#topic_40932F09E18A467983AFBB29908E1CB8}

Você pode criar um projeto a partir de:

* Um projeto em branco (padrão). Para mais instruções, consulte [Criar um projeto do Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md).
* Um modelo padrão. Esses modelos são criados pela Adobe e enviados para o recurso instantâneo.
* Um modelo personalizado. Esses modelos podem ser criados por usuários com direitos de administrador ou por não administradores, presumindo que tenham a permissão de “Salvar como modelo”. Consulte [Gerenciar permissões do produto](https://helpx.adobe.com/br/enterprise/using/manage-permissions-and-roles.html) na documentação do Admin Console para mais informações.

![](assets/start_modal.png)

* [Criar um modelo personalizado](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)
* [Modelos padrão](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)

## Criar um modelo personalizado {#create-custom-template}

Os usuários com direitos de administrador podem tornar qualquer projeto criado por ele um modelo personalizado. Veja como:

1. Abrir o projeto.
1. Vá para **[!UICONTROL Projeto]** &gt; **[!UICONTROL Salvar como modelo]**.

   ![](assets/save_project_template.png)

   O projeto será salvo com o nome do projeto atual, seguido da palavra (Modelo) entre parênteses. Os administradores podem alterar esse nome ao editar o modelo.

   >[!NOTE]
   >
   >Por padrão, os modelos de projeto estão visíveis para todos em sua organização. Você pode organizá-los aplicando tags. (Para editar as tags e as descrições, vá para **[!UICONTROL Projeto]** &gt; **[!UICONTROL Informações e configurações do projeto]**.)

### Ações executáveis nos modelos personalizados

![](assets/custom_templates.png)

<table id="table_D7C7B0CA1EE64E108484C03426800EBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ação </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Editar  modelo </p> </td> 
   <td colname="col2"> <p>Permite que um administrador edite o modelo ao alterar a fonte de dados, modificar componentes, exibições, intervalos de data etc. </p> <p>Para editar um modelo personalizado, </p> 
    <ul id="ul_2B3A371F83334E14806385753A360903"> 
     <li id="li_EE75E0281B764BA9B56FF1DB1B12D2CC">abra a lista de modelos personalizados do Analysis Workspace, selecione um e clique em <span class="uicontrol">Editar modelo</span>, ou </li> 
     <li id="li_4934DAAA46204990A295E22A97F81EDA">no Analytics, clique em <span class="ignoretag"><span class="uicontrol">Componentes</span> &gt; <span class="uicontrol">Projetos</span></span> e filtre por <span class="uicontrol">Modelos</span>. Clique no nome do modelo que deseja editar. </li> 
    </ul> <p> </p> <p>Observação: após editar um modelo, dependendo da situação, você terá duas opções: <span class="uicontrol">Salvar</span> e <span class="uicontrol">Salvar como</span>. Elas se diferem da seguinte forma: 
     <ul id="ul_87E2842C8AA442399585B1C6189F5E16"> 
      <li id="li_AB7B189729E14E40A0141ECE2A24C113"><b>Salvar</b>: atualiza o modelo personalizado para todos os usuários. Quando outra pessoa cria um projeto a partir deste modelo personalizado, ela verá suas alterações. </li> 
      <li id="li_C85B0B9873A3404D8B443BBD30B37CEB"><b>Salvar como</b>: cria uma cópia do modelo personalizado com suas alterações. </li> 
     </ul> </p> <p>(Você saberá que está no modo de edição quando o item de menu <span class="uicontrol">Compartilhar</span> &gt; <span class="uicontrol">Compartilhar projeto</span> estiver desativado.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pesquisar nos modelos </p> </td> 
   <td colname="col2"> <p>Na caixa de diálogo Modelos personalizados, clique em <span class="uicontrol">Pesquisar modelos</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Classificar modelos </p> </td> 
   <td colname="col2"> <p>É possível classificar modelos por ordem alfabética, relevância e data de criação. </p> <p>Na caixa de diálogo Modelos personalizados, clique em <span class="uicontrol">Classificar:</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aplicar tags ao modelo </p> </td> 
   <td colname="col2"> <p>Abra o modelo e vá até <span class="ignoretag"><span class="uicontrol">Projeto</span> &gt; <span class="uicontrol">Informações e configurações do projeto</span></span>. Clique em <span class="uicontrol">Adicionar tags</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificar descrição do modelo </p> </td> 
   <td colname="col2"> <p>Abra o modelo e vá até <span class="ignoretag"><span class="uicontrol">Projeto</span> &gt; <span class="uicontrol">Informações e configurações do projeto</span></span>. Clique duas vezes na descrição e edite-a. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modelos padrão {#concept_4FE900FEEC894E849CB6C6A0E0ADA524}

Quando você abre um Workspace pela primeira vez, os modelos ficam disponíveis no painel esquerdo. Os modelos do Analysis Workspace abrangem casos usuais. São agrupados pela vertical à qual pertencem e são preenchidos com diferentes dimensões, segmentos, métricas e visualizações, dependendo do conjunto de relatórios selecionado.

Você pode usar esses modelos pré-preenchidos como estão ou adaptá-los às suas necessidades (adicionando ou substituindo métricas ou visualizações, por exemplo) e salvá-los com um novo nome.

[Modelos padrão do Analysis Workspace no YouTube](https://www.youtube.com/watch?v=aRgYwPneVXg&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=6) (2:46)

Estes são os modelos disponíveis e as perguntas que cada modelo ajuda a responder:

### Publicidade

>[!IMPORTANT]
>
>Os modelos de publicidade estão disponíveis somente se o seu conjunto de relatórios estiver habilitado para a Advertising Cloud.

* **Mecanismos de pesquisa**: esse modelo detalha tendências de publicidade, plataformas de publicidade, palavras-chave, contas, campanhas e muito mais.

### Comércio

* **Magento: marketing e comércio**: esse modelo detalha sua conversão de comércio eletrônico por atribuição de canal de marketing, além de fornecer informações por palavra-chave de pesquisa, página de aterrissagem, localização geográfica e muito mais. Para ter uma visão geral, assista ao vídeo &gt;[!VIDEO](https://www.youtube.com/watch?v=AQOViVLEMHw)

### Mídia

* **Consumo de áudio**: que conteúdo está sendo mais consumido pelos usuários, resultando em interações?
* **Recenticidade - Frequência - Fidelidade**: quem são meus leitores fiéis?

### Dispositivos móveis

>[!IMPORTANT]
>
>Os modelos para dispositivos móveis estão disponíveis somente se o seu conjunto de relatórios estiver habilitado para dispositivos móveis.

* **Mensagens:** focaliza o desempenho das mensagens no aplicativo e por push.
* **Localização:** inclui um mapa que exibe os dados de localização.
* **Métricas principais:** permite o controle das métricas principais do seu aplicativo.
* **Uso do aplicativo:** quantos usuários, inicializações e primeiras inicializações o aplicativo teve e qual foi a duração média das sessões?
* **Aquisição:** você pode ver o desempenho dos links de aquisição para dispositivos móveis.
* **Desempenho:** como está o desempenho do aplicativo e que problemas os usuários estão tendo?
* **Retenção:** quem são meus usuários fiéis e o que eles fazem?
* **Jornadas:** quais são os principais padrões de uso do meu aplicativo?

### Varejo

* **Desempenho da campanha:** que campanhas estão gerando mais receita?
* **Produtos:** que produtos estão tendo o melhor desempenho?

### Web

* **Aquisição:** quais são os principais impulsionadores de tráfego do meu site?
* **Consumo de conteúdo:** quais são os lugares mais acessados do meu site?
* **Retenção:** que tipo de usuário tem maior probabilidade de se tornar um usuário fiel do meu site?
* **Tecnologia:** que tecnologia as pessoas estão usando para acessar o meu site?

### Pessoas

> [!NOTE] O modelo Pessoas e sua respectiva métrica Pessoas estão disponíveis para uso somente como parte do [Device Co-op da Adobe Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/mcdc/mcdc-people.html).

Tem como base a métrica Pessoas, que é uma versão deduplicada da métrica Visitantes únicos. A métrica de Pessoas oferece uma medida da frequência que os clientes que usam vários dispositivos interagem com a sua marca. O modelo permite

* Segmentar seus dados por EUA/Canadá vs. o resto do mundo. No momento, o Device Co-op está disponível somente para a América do Norte.
* Comparar as métricas de Pessoas e de Visitantes únicos lado a lado.
* Ver a "taxa de compressão", uma métrica calculada que calcula o quão menor a métrica de Pessoas é como uma porcentagem de Visitantes únicos.
* Comparar os totais de tipos de dispositivos que seus clientes usam
* Ver a média de quantos dispositivos por pessoa são usados.
* Descobrir como usar o empilhamento de segmentos com a métrica de Pessoas.
* Saber mais sobre como usar a Experience Cloud ID em seu ambiente melhora a eficácia da métrica Pessoas.

