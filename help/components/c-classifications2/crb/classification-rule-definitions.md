---
description: Definições de elementos de interface nas páginas no Construtor de regras de classificação.
subtopic: Classifications
title: Regras de classificação - definições
topic: Admin tools
uuid: 77af8669-6e11-435c-9cc3-b03eb627c855
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Regras de classificação - definições

Definições de elementos de interface nas páginas no Construtor de regras de classificação.

## Página Regras {#section_4A5BF384EEEE4994B6DC888339833529}

Essa página exibe as regras em um conjunto de regras.

![](assets/classification_rules_page.png)

**Definições**

<table id="table_2B3A8BB7BDE14836ACA6A1D444B011CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Selecionar Conjuntos de relatórios e variáveis </p> </td> 
   <td colname="col2"> <p><b>Conjunto de relatórios</b> </p> <p>Os conjuntos de relatórios ao quais o conjunto de regras é aplicado. </p> <p><b>Variável</b> </p> <p>É possível aplicar somente uma variável ao criar um conjunto de regras de classificação. Se deseja criar vários conjuntos de regras para uma variável, você deve aplicar cada conjunto de regras a vários conjuntos de relatórios. </p> <p>Observação: você pode usar somente as variáveis que você acessou nos seus conjuntos de relatórios. As variáveis serão exibidas no painel <span class="wintitle">Novo conjunto de regras</span> somente após terem pelo menos uma classificação definida para aquelas variáveis. </p> <p>Por exemplo, para disponibilizar <span class="term"> Páginas</span> como uma variável para o conjunto de regras, verifique se o conjunto de relatórios tem <a href="https://marketing.adobe.com/resources/help/en_US/reference/traffic_classifications.html"  > classificações de tráfego</a> implementadas para a <span class="term"> Página</span>. </p> <p> É possível criar classificações em uma variável em <span class="uicontrol">Admin</span> &gt; <span class="uicontrol">Conjuntos de relatório</span> &gt; <span class="uicontrol">Tráfego</span> &gt; <span class="uicontrol">Classificações de tráfego</span> (ou <span class="uicontrol">Conversão</span> &gt; <span class="uicontrol">Classificações de conversão</span>). Depois, selecione a variável e clique em <span class="uicontrol">Adicionar classificação</span>. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/reference/traffic_classification_admin.html"  >Classificações de tráfego</a> e <a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_classifications.html"  >Classificações de conversão</a> na Ajuda de administração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ativar</span> </p> </td> 
   <td colname="col2"> <p>Valida e ativa uma regra. As regras ativas processam diariamente, examinando os dados de classificação normalmente de um mês. As regras verificam automaticamente novos valores e carregam as classificações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Desativar</span> </p> </td> 
   <td colname="col2"> <p>Desativa as regras para que você possa editá-las e testá-las. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar conjuntos de relatórios e variáveis </p> </td> 
   <td colname="col2"> <p>Exibe a página dos <span class="wintitle">Conjuntos de relatórios disponíveis</span>, onde é possível selecionar um ou mais conjuntos de relatórios disponíveis para serem usados em todos os conjuntos de regras. (Essa página também é exibida quando você executa o <span class="wintitle">Construtor de regras de classificação</span> pela primeira vez). </p> <p>Esse recurso tem o objetivo de ajudar a reduzir o tempo de carregamento do conjunto de relatórios, em um evento que existem centenas de conjuntos de relatórios disponíveis. </p> <p>Os conjuntos de relatórios selecionados aqui ficam disponíveis no nível de regras, quando você clica em <span class="uicontrol">Adicionar conjuntos</span> ao criar uma regra. </p> <p>Observação: um conjunto de relatórios fica disponível <span class="term"> somente</span> quando os conjuntos de relatórios têm pelo menos uma classificação definida para a variável nas <span class="wintitle"> Ferramentas administrativas</span>. <p>(Consulte <span class="term"> Variável</span> em <a href="/help/components/c-classifications2/crb/classification-rule-set.md"  >Conjuntos de regras de classificação</a> para obter uma explicação sobre esse pré-requisito.) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>As regras substituem quaisquer valores existentes </p> </td> 
   <td colname="col2"> <p> (Configuração padrão) Sempre substitua as chaves de classificação existentes, inclusive as classificações carregadas pelo importador (SAINT). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>As regras substituem apenas valores não definidos </p> </td> 
   <td colname="col2"> <p>Preencha apenas as células em branco (não definidas). Classificações existentes não serão alteradas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janela de lookback </p> </td> 
   <td colname="col2"> <p>Quando você ativa e valida regras, pode especificar se as regras devem substituir classificações existentes por teclas afetadas. (Somente as teclas classificadas que tenham passado no <span class="keyword">Adobe Analytics</span> dentro do período especificado por você são afetadas). </p> <p>Se você não especificar uma <span class="term">janela de lookback</span>, as regras visualizam aproximadamente um mês antes (dependendo do dia do mês). As classificações existentes nunca são substituídas, a não se quando você habilita essa opção. </p> <p><b>Dev Center</b>: Os parceiros podem criar regras de classificação no <span class="wintitle">Dev Center</span>. Essas regras são implantadas quando o cliente ativa uma integração. No <span class="wintitle">Dev Center</span>, a opção <span class="uicontrol">Sobrescrever desde</span> permite que o parceiro especifique se o cliente poderá determinar o valor sobrescrito quando ativar ou editar uma integração. </p> <p>Consulte <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  >Como as regras são processadas</a> para mais informações sobre o processamento de regras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  > Adicionar regra </a> </td> 
   <td colname="col2"> <p>Permite adicionar regras ao conjunto de regras. </p> <p>Observação: se um valor corresponder duas ou mais vezes em um conjunto de regras, o sistema usa a última regra para classificar o valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Rascunho</span> </td> 
   <td colname="col2"> Permite especificar que uma regra está no modo de rascunho. O status de rascunho permite testar a regra antes de executá-la. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Duplicar</span> </td> 
   <td colname="col2"> Duplica (copia) um conjunto de regras, de modo que você possa aplicar o conjunto de regras a outra variável, ou à mesma variável em um conjunto de relatório diferente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  > Testar conjunto de regras </a> </p> </td> 
   <td colname="col2"> <p>Permite testar a validade de um conjunto de regras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Condição de correspondência</span> </td> 
   <td colname="col2"> Especifica as condições que deseja para a regra. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ação da classificação</span> </td> 
   <td colname="col2"> <p>Especifica a ação a ser tomada quando a Condição de correspondência ocorrer. </p> <p>Por exemplo, você define um Nome de campanha como $2, que identifica a posição 2 em um código de rastreamento como o Nome da campanha. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>O número da regra. </p> <p>Consulte <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  > Como as regras são processadas</a> para obter mais informações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Selecionar tipo de regra</span> </td> 
   <td colname="col2"> <p>Cada conjunto de regras aplica-se a uma variável específica. As seleções válidas são: </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">Começa com </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">Termina com </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">Contém </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  > Expressão regular </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Inserir os critérios de correspondência</span> </td> 
   <td colname="col2"> O padrão de texto que você está procurando em uma tecla. Esses critérios podem ser termos de pesquisa, caracteres ou expressão regular. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Definir a classificação</span> </td> 
   <td colname="col2"> A coluna de classificação que deseja definir se os critérios de correspondência forem atendidos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Para</span> </td> 
   <td colname="col2"> O valor que deseja especificar para a coluna de classificação selecionada se os critérios de correspondência forem atendidos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> Permite procurar regras. </td> 
  </tr> 
 </tbody> 
</table>

## Página Expressão regular {#section_C932A5469E774841B2229965A154163C}

É possível editar expressões regulares na página [!UICONTROL Expressão regular].

![](assets/regex_tracking_code.png)

**Definições**

| Elemento | Descrição |
|---|---|
| Tecla de amostra | A sequência de teste a ser usada. Por exemplo, você pode criar uma classificação com base em caracteres específicos em um código de rastreamento. Você pode corresponder caracteres, palavras ou padrões de caracteres específicos. |
| Corresponder grupos | Mostra como a expressão regular corresponde aos caracteres de ID da campanha, tornando possível classificar uma posição na ID da campanha. |
| Corresponder resultado | Exibe as partes de uma sequência que corresponde com êxito à expressão regular. |

Consulte [Expressões regulares em regras de classificação](/help/components/c-classifications2/crb/classification-quickstart-rules.md).

## Página de testes {#section_EC926F97901C4E65901413F9683AA70A}

Essa página permite testar as regras em um conjunto.

**Definições**

| Elemento | Descrição |
|---|---|
| Executar teste | Ao testar o conjunto de regras, use as teclas do relatório para ver como serão impactadas pelo conjunto de regras. |
| Filtro | Filtra os valores no painel [!UICONTROL Resultados]. |

