---
description: Perguntas frequentes sobre a configuração automática da implantação do Adobe Analytics. O método de configuração automática gerencia o código do AppMeasurement para você.
keywords: Dynamic Tag Management;plugins;staging;effect on current settings;revision history;potential pitfalls;report suite id;currency code;tracking server;ssl tracking server;custom code;library management
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Perguntas frequentes sobre a ferramenta Adobe Analytics
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Perguntas frequentes sobre a ferramenta Adobe Analytics

Perguntas frequentes sobre a configuração automática da implantação do Adobe Analytics. O método de configuração automática gerencia o código do [!DNL AppMeasurement] para você.

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
   <td colname="col2"> <p> Caso esteja utilizando o DTM para hospedar manualmente o <code> s_code</code>, é possível adicionar plug-ins no mesmo editor como <code> s_code</code> hospedado, de forma semelhante à implementação padrão do Adobe Analytics. </p> <p>No entanto, também é uma opção colocar os plug-ins no editor na seção <span class="term"> Personalizar código de página</span> das configurações da ferramenta. Os dois métodos de implementação devem ser igualmente eficazes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se eu realizar alterações na configuração da nova versão da ferramenta, é possível testá-la durante o armazenamento temporário antes de publicar para produção? </p> </td> 
   <td colname="col2"> <p>Sim. </p> <p>Todas as alterações pode ser testadas durante armazenamento temporário, da maneira que você normalmente faria antes de implantá-la em um ambiente de produção. Se você optar por não publicar pois notou problemas durante o armazenamento temporário, o código de produção continuará a funcionar como antes do lançamento da nova integração. </p> </td> 
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

Consulte [Adicionar ferramenta Adobe Analytics](/help/implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md) para obter informações sobre configuração.

## Possíveis armadilhas {#section_201BF9E0EB7D4BC2B72A617543C2030B}

Há uma pequena chance de a integração causar problemas na coleção de dados se você estiver usando o [!DNL Adobe Analytics] atualmente. Esses problemas podem surgir somente se você publicar sua biblioteca na produção depois do lançamento. (O código de produção permanece intacto até a publicação).

Para evitar esses problemas, verifique se:

* As IDs do conjunto de relatório foram inseridas corretamente na ferramenta.
* As IDs dos conjuntos de relatórios na ferramenta correspondem às IDs no código do [!DNL AppMeasurement].
* Os campos código da moeda, conjunto de caracteres, servidor de rastreamento e configuração do servidor de rastreamento do SSL estão configurados corretamente com valores suportados.
* O código personalizado é definido em [!DNL Library Management].

