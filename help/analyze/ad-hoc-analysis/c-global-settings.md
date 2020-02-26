---
description: Definir configurações de comportamento global. Por exemplo, é possível definir as configurações de Salvamento automático, gráfico e tabela e especificar a fonte e o local.
title: Configurações
uuid: 34444052-479b-4923-b379-a03ca614bf3e
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Configurações

Definir configurações de comportamento global. Por exemplo, é possível definir as configurações de Salvamento automático, gráfico e tabela e especificar a fonte e o local.

## Configurações {#concept_D21E3D6F13EA4F97913F60C243B72173}

Definir configurações de comportamento global. Por exemplo, é possível definir as configurações de Salvamento automático, gráfico e tabela e especificar a fonte e o local.

Clique em **[!UICONTROL Ferramentas]** > **[!UICONTROL Configurações]** para acessar as [!UICONTROL Configurações Globais].

## Guia Configurações Gerais - Definições {#reference_EADAF83466994F89BCC6B0F49A9A53DB}

Define as configurações comportamentais para fontes de dados, salvamento de projeto, gráficos e tabelas.

<!-- 

r_dsc_general_settings.xml

 -->

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Configurações de dados </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Contar instâncias repetidas</span>: especifica se as instâncias são contadas nos relatórios. Ou seja, se você tiver vários valores em sequência para a mesma variável, poderá contá-las como uma ou várias instâncias da variável. </p> <p>Por exemplo, você poderá ver recargas de páginas repetidos, que são o número de vezes que as páginas em seu site são recarregadas ou atualizadas durante uma única visita. Esta opção permite que você especifique várias ocorrências na mesma página que são contadas como apenas uma ou várias visualizações de páginas. </p> <p> <span class="uicontrol"> <span class="keyword"> Ad hoc</span></span>: especifica <span class="keyword">Ad hoc</span> como a única fonte de dados para relatório. Esses dados vêm de solicitações de imagem geradas por páginas da Web. </p> <p> <span class="uicontrol"> <span class="keyword"> Fontes de dados</span></span>: especifica se os dados carregados de fontes da Adobe ou fontes de dados personalizados devem ser usados. Os dados são disponibilizados para produtos na <span class="keyword">Experience Cloud</span>. Veja <a href="https://marketing.adobe.com/resources/help/pt_BR/sc/datasources/index.html"  >Fontes de dados</a> para obter mais informações. </p> <p> <span class="uicontrol"> Ambos</span>: (padrão) usa dados de <span class="keyword">Ad Hoc Analysis</span> e outras fontes de dados. </p> <p>Observação: alterar essa opções pode resultar em discrepâncias de relatório entre os dados da <span class="keyword">Ad Hoc Analysis</span> e os dados de <span class="keyword">relatórios e análises de marketing.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Salvar automaticamente configurações </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Salvamento automático ativado</span>: Permite a funcionalidade do salvamento automático. </p> <p> <span class="uicontrol"> Frequência de projeto do salvamento automático</span>: Permite que você ajuste os incrementos de tempo do recurso de salvamento automático. Um salvamento automático do projeto é criado somente quando ocorrer uma pane no ad hoc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Configurações do gráfico </p> </td> 
   <td colname="col2"> <p><b>Recolher os gráficos por padrão</b>: Clique nesse botão para exibir os relatórios sem gráficos na seção superior. Quando o relatório for exibido com essa opção, você pode estendê-lo manualmente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Configurações da tabela </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Mostrar números de linha</span>: Ativa ou desativa a numeração de linha na tabela de relatório. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Guia Classificado - Definições {#reference_FB9BADD7E3DA42C1BB2A02A6E9D5C1CF}

Configura como os dados são exibidos em colunas e seleciona métricas padrão para relatórios de tráfego e conversão.

<!-- 

r_dsc_ranked_tab.xml

 -->

| Campo | Definição |
|--- |--- |
| Configurações de Coluna | Configura como você deseja exibir os dados da célula em tabelas e os gráficos de barras. |
| Selecionar métricas Padrão | Seleciona métricas padrão para relatórios de Tráfego e Conversão, além das métricas disponíveis para todos os relatórios.    Incluir padrão específico de relatório: Especifica se inclui métricas padrão ao personalizar a visualização. |

## Aba de análise do site - Definições {#reference_9DD37C8EF718409E990E149596282FF8}

Define as métricas e outras configurações gráficas para o relatório do Site Analysis.

<!-- 

r_dsc_site_analysis_tab.xml

 -->

| Campo | Definição |
|--- |--- |
| Métricas | Seleciona a métrica representada pela largura e altura do cilindro. Determina quais métricas serão exibidas usando cores e as cores que representam um valor baixo ou alto para essas métricas. Também é possível estabelecer métricas para os eixos X e Y e adicionar qualquer outra métrica que quiser que apareça no texto pop-up do relatório. Também é possível inverter qualquer uma das métricas selecionadas para a exibição. |
| Geral e alertas | Ativa e desativa alguns elementos gráficos do relatório. Você pode configurar alertas que são exibidos no relatório quando as métricas associadas com as páginas representadas por cilindros passam um valor específico. |

## Guia Fonte e Local - Definições {#reference_5F2129B67CC44E5BA9EA7E30A35BFB49}

Especifica as configurações regionais de idioma, assim como a fonte padrão. É preciso reiniciar o para que as alterações de fonte e local tenham efeito.

<!-- 

r_dsc_font_locale.xml

 -->

| Campo | Definição |
|--- |--- |
| Selecionar uma localidade | Permite que você especifique o idioma para exibir na interface do usuário. |
| Selecionar uma fonte | Permite que você especifique uma fonte para exibir. |
