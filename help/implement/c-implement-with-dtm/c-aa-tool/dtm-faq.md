---
description: Perguntas frequentes sobre a configuração automática da implantação do Adobe Analytics. O método de configuração automática gerencia o código do AppMeasurement para você.
keywords: Gerenciamento dinâmico de tags; plug-plugins; armazenamento temporário; efeito nas configurações atuais; histórico de revisão; armadilhas potenciais; id do conjunto de relatórios; código de moeda; servidor de rastreamento; servidor de rastreamento de ssl; código personalizado; gerenciamento de biblioteca
seo-description: Perguntas frequentes sobre a configuração automática da implantação do Adobe Analytics. O método de configuração automática gerencia o código do AppMeasurement para você.
seo-title: Perguntas frequentes sobre a ferramenta Adobe Analytics
solution: Marketing Cloud, Analytics, Target, Gerenciamento dinâmico de tags
title: Perguntas frequentes sobre a ferramenta Adobe Analytics
uuid: 8 fcef 893-e 305-4 a 95-a 033-9066 a 56 b 09
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Perguntas frequentes sobre a ferramenta Adobe Analytics

Perguntas frequentes sobre a configuração automática da implantação do Adobe Analytics. The automatic configuration method manages the [!DNL AppMeasurement] code for you.

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Onde coloco meus plug-ins durante a implementação do Adobe Analytics por meio do DTM? </p> </td> 
   <td colname="col2"> <p> Caso esteja utilizando o DTM para hospedar manualmente o <code>s_code</code>, é possível adicionar plug-ins no mesmo editor como <code>s_code</code> hospedado, de forma semelhante à implementação padrão do Adobe Analytics. </p> <p>However, it is also an option to place the plugins in the editor within the <span class="term"> Customize Page Code</span> section of the tool settings. Os dois métodos de implementação devem ser igualmente eficazes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se eu realizar alterações na configuração da nova versão da ferramenta, é possível testá-la durante o armazenamento temporário antes de publicar para produção? </p> </td> 
   <td colname="col2"> <p>Sim.  </p> <p>Todas as alterações pode ser testadas durante armazenamento temporário, da maneira que você normalmente faria antes de implantá-la em um ambiente de produção. Se você optar por não publicar pois notou problemas durante o armazenamento temporário, o código de produção continuará a funcionar como antes do lançamento da nova integração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se eu alternar da configuração manual (a configuração padrão para ferramentas existentes) para a configuração automática, as minhas configurações atuais serão afetadas? </p> </td> 
   <td colname="col2"> <p>Não. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se eu alternar do gerenciamento manual da biblioteca para Administrado pela Adobe, minhas configurações atuais ou o código serão afetados? </p> </td> 
   <td colname="col2"> <p>Qualquer código de usuário especificado é substituído pela biblioteca base do <span class="keyword">AppMeasurement</span>. Você deve mover este código para a nova seção <span class="wintitle">Código personalizado da página</span> no fim da configuração da ferramenta, para que o código continue a ser executado. Este método permite que a biblioteca do <span class="keyword">AppMeasurement</span> seja gerenciada (e atualizada) separadamente do código personalizado do usuário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O histórico de revisão da ferramenta <span class="keyword">Adobe Analytics</span> será retido quando a nova integração for lançada? </p> </td> 
   <td colname="col2"> <p>Sim. </p> </td> 
  </tr> 
 </tbody> 
</table>

See [Add Adobe Analytics Tool](../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8) for configuration information.

## Possíveis armadilhas {#section_201BF9E0EB7D4BC2B72A617543C2030B}

Há uma pequena chance de a integração causar problemas na coleção de dados se você estiver usando o [!DNL Adobe Analytics] atualmente. Esses problemas podem surgir somente se você publicar sua biblioteca na produção depois do lançamento. (O código de produção permanece intacto até a publicação).

Para evitar esses problemas, verifique se:

* As IDs do conjunto de relatório foram inseridas corretamente na ferramenta.
* As IDs dos conjuntos de relatórios na ferramenta correspondem às IDs no código do [!DNL AppMeasurement].
* Os campos código da moeda, conjunto de caracteres, servidor de rastreamento e configuração do servidor de rastreamento do SSL estão configurados corretamente com valores suportados.
* Custom code is defined in [!DNL Library Management].

