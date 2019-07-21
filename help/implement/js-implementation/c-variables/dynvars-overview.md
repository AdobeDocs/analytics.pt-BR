---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
seo-title: Variáveis dinâmicas
solution: Analytics
subtopic: Variáveis
title: Variáveis dinâmicas
topic: Desenvolvedor e implementação
uuid: 1 c 6 db 083-570 e -4 bc 4-858 d -84 cf 46 e 7 bec 8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Variáveis dinâmicas

As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.

As variáveis dinâmicas são usadas ao capturar os mesmos dados (por exemplo, códigos de rastreamento de campanha) em diversas variáveis simultâneas. Essa é uma prática comum em casos nos quais relatórios diferentes oferecem métricas únicas e importantes. Por exemplo, capturar palavras-chave de pesquisa interna em uma variável de [!UICONTROL Conversão personalizada] e em uma variável de [!UICONTROL Tráfego personalizado] permite exibir métricas de [!UICONTROL Receita] e [!UICONTROL Visitantes únicos semanais] associados a essas palavras-chave, respectivamente.

As variáveis dinâmicas também são úteis para exibir dados sob diversas condições de relatório. Um código de rastreamento de campanha pode ser capturado de várias eVars com diversas configurações de alocação e expiração de cookie. Isso permite que os usuário escolha a maneira como desejam atribuir métricas de conversão a essas campanhas.

>[!NOTE]
>
>Variáveis dinâmicas não são compatíveis com cookies (s_ cc, s_ sq, s_ fid, s_ vi e qualquer cookie definido por um plug-in). You can not use `D=<cookie value>`.

Um benefício relevante das variáveis dinâmicas é a capacidade de capturar sequências de caracteres de dados longas sem passar pela sequência longa repetidamente. Alguns navegadores limitam o tamanho máximo de solicitações GET de HTTP (incluindo a solicitação de imagem da Adobe). O uso de variáveis dinâmicas garante que todos os dados serão capturados reduzindo o tamanho das solicitações para os servidores da Adobe nos casos em que os dados são duplicados em diversas variáveis.

Na solicitação de imagem da Adobe que ocorre na exibição de página, se estiver usando variáveis dinâmicas para copiar o valor de [!UICONTROL Tráfego personalizado ] para [!UICONTROL Conversão personalizada ], você veria `v1=D=c1`1=1. Se a eVar1 recebeu um valor anteriormente na solicitação, os servidores da Adobe copiam dinamicamente o valor de [!UICONTROL Tráfego personalizado 1] para [!UICONTROL Conversão personalizada 1] durante o processamento de dados. Como resultado, o valor passado originalmente usando [!UICONTROL Tráfego personalizado 1] também aparece nos relatórios de [!UICONTROL Conversão personalizada 1].

Dynamic variables are passed by setting a variable to the desired value and then setting other variables to `D=[variable abbreviation]`. For abbreviations for each variable, see [Data Collection Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md). As variáveis dinâmicas podem obter dados dos seguintes locais:

* Outras variáveis de cadeia de consulta
* Cabeçalhos HTTP (exceto pelo cabeçalho HTTP de cookie)

Para criar uma variável dinâmica, adicione um prefixo especial ao início do valor. O prefixo padrão é "D=". Há dois métodos de sinalizar variáveis dinâmicas:

* Use um prefixo padrão de D= (Por exemplo: s.prop1="D=User-Agent" )
* Para implementações não JavaScript, você pode definir um prefixo personalizado com o parâmetro de cadeia de consulta "D". For example, if the query-string parameter is `"&D=$"`, you can create a dynamic variable with the following command: `s.prop1="$User-Agent"` .

A abreviação de variável usada deve corresponder ao nome do parâmetro de variável passado na solicitação de imagem. Algumas variáveis têm vários parâmetros aceitados usados em casos diferentes. For example, `pageName=` and `gn=` both pass the page name, but the latter is most often used in mobile and hard-coded implementations. If the image request uses `pageName=` to pass the page name, then `D=pageName` is acceptable but `D=gn` is not. If the image request uses `gn=`, then `D=gn` is acceptable, but `D=pageName` is not.

As seguintes informações se aplicam à variáveis dinâmicas:

* As variáveis dinâmicas funcionam com todas as versões do código do AppMeasurement.
* As variáveis dinâmicas diferenciam letras maiúsculas de minúsculas
* As variáveis dinâmicas suportam cadeiras literais em citações.
* A substituição da variável dinâmica ocorre antes do processamento de regras, VISTA e outros processos.
* O prefixo de variável dinâmica "D=" deve estar no início do valor da variável e não no meio. For example, use `c2='D="test7"+User-Agent'` rather than `c2='"test7"+D=User-Agent'` .

* Assim como em todas as técnicas de implementação, a Adobe recomenda testar amplamente implementações de variável dinâmica em um ambiente de desenvolvimento antes de implantar na produção. Como as strings completas não estão visíveis nas ferramentas de depuração do lado do cliente, analise os relatórios afetados do Analytics para confirmar a implementação.
* Ao copiar valores entre variáveis com tamanhos máximos diferentes, observe que copiar um valor que excede o comprimento máximo da variável de destino resulta em truncamento. Por exemplo, as variáveis de [!UICONTROL Tráfego personalizado] têm limites de 100 caracteres e as variáveis [!UICONTROL Conversão personalizada] têm limites de 255 caracteres. Quando você copia um valor de 150 caracteres de s.eVar1 para s.prop1 usando variáveis dinâmicas, esse valor é truncado no relatório [!UICONTROL Tráfego personalizado] em 100 caracteres. 

## Exemplos de variável dinâmica {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

Exemplos de variáveis dinâmicas que podem ser usadas no Analytics.

Na solicitação de imagem da Adobe que ocorre na exibição de página, se estiver usando variáveis dinâmicas para copiar o valor de [!UICONTROL Tráfego personalizado ] para [!UICONTROL Conversão personalizada ], você veria `v1=D=c1`1=1. Se a eVar1 recebeu um valor anteriormente na solicitação, os servidores da Adobe copiam dinamicamente o valor de [!UICONTROL Tráfego personalizado 1] para [!UICONTROL Conversão personalizada 1] durante o processamento de dados. Como resultado, o valor passado originalmente usando [!UICONTROL Tráfego personalizado 1] também aparece nos relatórios de [!UICONTROL Conversão personalizada 1].

Note that the `D=[variable]` value should be in quotes. O código do Analytics trata isso como uma string. A sequência de caracteres será o URL codificado ao ser passado para o Analytics (como você verá se estiver exibindo a solicitação no DigitalPulse Debugger ou em um utilitário semelhante). Isso é normal. Adobe's servers recognize the `D=[variable]` construction and will copy the appropriate value when they encounter this string.

>[!NOTE]
>
>Ao usar a solicitação de imagem para rastrear links, o tipo de link (download = lnk_ d, exit = lnk_ e ou custom link = lnk_ o) deve ser definido, assim como o Link URL/Name (pev 2). Links require manual implementation by inserting code within the `<a href>` tag.

>[!NOTE]
>
>Variáveis dinâmicas não são compatíveis com cookies (s_ cc, s_ sq, s_ fid, s_ vi e qualquer cookie definido por um plug-in). You can not use `D=<cookie value>`.

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemplo de JavaScript </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. evar 1 = "D = pagename" </code>
  </td> 
   <td colname="col2"> <p>Captura o valor pageName na eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop 1 =' D = v 2 + ": " + c 2 ' &amp; amp; nbsp; </code>
  </td> 
   <td colname="col2"> <p>Concatena eVar2:prop2 em prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop 1 = s. evar 1 = "D = g" &amp; amp; nbsp; </code>
  </td> 
   <td colname="col2"> <p>Transfere o URL da página para prop1 e eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. evar 1 = "D = v 0" </code>
  </td> 
   <td colname="col2"> <p>Captura a campanha em eVar 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop 1 =' D = User-Agent + "; - " + Accept-Language" </code>
  </td> 
   <td colname="col2"> <p>Concatena o agente do usuário e aceita cabeçalhos de linguagem em prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>s. prop 1 = "D = User-Agent" </code>
  </td> 
   <td colname="col2"> <p>Captura o agente do usuário em prop1, </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_DD0B7F0648054E01A5F98CDF18D745E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemplo de solicitação de imagem </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">/b/ss/rsid/? gn = Home &amp; D = ~ ~ &amp; c 1 = ~ ~ v 0 /b/ss/rsid/? gn = Home &amp; D = ~ ~ &amp; c 1 = ~ ~ campaign /b/ss/rsid/? gn = Home &amp; c 1 = D % 3 dv 0% 3 d é /b/ss/rsid/? gn = Home &amp; c 1 = % 5 b % 5 bv 0% 5 d % 5 d % 5 b </code>
  </td> 
   <td colname="col2"> <p>Quatro maneiras de definir prop1 para uma campanha </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>/b/ss/rsid/? gn = Home &amp; D = ~ ~ &amp; c 2 = ~ ~ x-up-subno </code>
  </td> 
   <td colname="col2"> <p> Puxa o cabeçalho x-up-subno para prop2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>c 1 = D % 3 duser-Agent </code>
  </td> 
   <td colname="col2"> <p> Transforma prop1 em uma variável dinâmica preenchida com o Agente do usuário do cabeçalho HTTP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c 1 = D % 3 D % 22 test % 22 </code>
  </td> 
   <td colname="col2"> <p> Transforma prop1 em uma variável dinâmica preenchida com a string “teste”. Isso é útil quando usado com a concatenação que utiliza o operador +. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c 1 = D % 3 D % 22 US % 3 A % 20% 22% 2 buser-Agent </code>
  </td> 
   <td colname="col2"> <p> Transforma prop1 em uma variável dinâmica preenchida com User-Agent com o prefixo "UA:" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; vid = D % 3 DX-TM-ANTID </code>
  </td> 
   <td colname="col2"> <p> Este exemplo procura por um cabeçalho exclusivo, que neste caso é X-TM-ANTID. </p> </td> 
  </tr> 
 </tbody> 
</table>
