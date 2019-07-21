---
description: As opções de calendário diferentes do modelo gregoriano. As opções incluem os modelos de calendário 4-4-5, 4-5-4 e 5-4-4, que são usados como padrões para o setor de varejo. Além disso, o relatório oferece uma opção de calendário totalmente personalizável que você mesmo pode configurar.
seo-description: As opções de calendário diferentes do modelo gregoriano. As opções incluem os modelos de calendário 4-4-5, 4-5-4 e 5-4-4, que são usados como padrões para o setor de varejo. Além disso, o relatório oferece uma opção de calendário totalmente personalizável que você mesmo pode configurar.
seo-title: Personalizar calendário
solution: Analytics
title: Personalizar calendário
topic: Ferramentas administrativas
uuid: 4 e 5 e 538 b -54 c 9-4 c 2 f -8 b 6 c -9 f 91 b 6 c 7 bcc 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Personalizar calendário

As opções de calendário diferentes do modelo gregoriano. As opções incluem os modelos de calendário 4-4-5, 4-5-4 e 5-4-4, que são usados como padrões para o setor de varejo. Além disso, o relatório oferece uma opção de calendário totalmente personalizável que você mesmo pode configurar.

**[!UICONTROL Administração]** &gt; **[!UICONTROL Conjuntos de relatórios]** &gt; **[! UICONTROL[select report suite]]** &gt; **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Geral]** &gt; **[!UICONTROL Personalizar calendário]**

>[!CAUTION]
>
>Alterar o calendário muda a maneira como os dados são processados (isto é, a definição de visitantes únicos semanal e mensal). Quando a definição do calendário de semanas e meses muda, os dados históricos não são alterados.

Você pode usar o calendário para definir o primeiro dia da semana e ano, ou usar um estilo de calendário de varejo diferente. Os formatos de calendário são usados para várias finalidades, inclusive comparações de vendas e padronização de previsões, análise de custos com folha de pagamento ou regulamento de contagem de inventário físico. Por exemplo, o setor de varejo usa o calendário contábil 4-5-4 em suporte à temporada de vendas característica do setor de varejo. Cada um dos formatos de calendário é descrito abaixo.

## Personalizar descrições de calendário {#section_B0D224DACB914A378902A4E0E1234889}

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calendário </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Calendário Gregoriano </p> </td> 
   <td colname="col2"> <p> Use o formato de calendário tradicional (janeiro a dezembro com 30 ou 31 dias e um número variável de semanas em cada mês). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendário Gregoriano Modificado </p> </td> 
   <td colname="col2"> <p> Usa o calendário gregoriano tradicional, mas permite que você selecione o primeiro mês do ano e o primeiro dia da semana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendário de varejo 4-5-4 </p> </td> 
   <td colname="col2"> <p> Desmembra cada mês pelo número de semanas no mês. Isto é, janeiro tem quatro semanas, e assim por diante. A Federação Nacional do Varejo nos Estados Unidos usa o formato de calendário 4-5-4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendário personalizado </p> </td> 
   <td colname="col2"> <p> Oferece três formatos baseados no número de semanas em cada mês. O número de semanas em cada mês depende do primeiro dia do ano selecionado. </p> <p>Um ano possui 52 semanas. Divida esse valor por 4 trimestres e você terá 13 semanas por trimestre. Mas há 3 meses em um trimestre. O número 13 não é divisível por três, dessa forma você acaba colocando uma semana extra em um dos meses, de forma que seja sempre consistente. 5-4-4 significa que o primeiro mês do trimestre recebe a semana extra. 4-5-4 significa que o segundo mês do trimestre recebe a semana extra, etc. No calendário 5-4-4, a 53ª semana é adicionada ao último trimestre do ano. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>: janeiro possui quatro semanas, fevereiro cinco, março quatro e assim por diante. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: janeiro possui quatro semanas, fevereiro quatro, março cinco e assim por diante. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-4-4</b>: janeiro tem cinco semanas, fevereiro tem quatro, março tem quatro, e assim em diante. </li> 
    </ul> <p>Observação: essa opção de calendário é suportada em todas as ferramentas do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, Report Builder, Activity Map, Ad Hoc Analysis) exceto para Data Warehouse, que não tem suporte a calendários personalizados. </p> </td> 
  </tr> 
 </tbody> 
</table>

