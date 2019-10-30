---
description: As tabelas a seguir listam os parâmetros de consulta que contêm o valor para cada variável de análise enviada para a coleção de dados.
keywords: Implementação do Analytics
seo-description: As tabelas a seguir listam os parâmetros de consulta que contêm o valor para cada variável de análise enviada para a coleção de dados.
seo-title: Parâmetros de consulta para coleta de dados
solution: Analytics
title: Parâmetros de consulta para coleta de dados
topic: Desenvolvedor e implementação
uuid: 4d5af486-df27-42fe-bb9c-28938dddf2b2
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Parâmetros de consulta para coleta de dados

As tabelas a seguir listam os parâmetros de consulta que contêm o valor para cada variável de análise enviada para a coleção de dados.

Essas informações podem ser usadas ao depurar usando [Analisadores de pacote](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258), ao criar manualmente as solicitações de imagem ou ao usar [Variáveis dinâmicas](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262).

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> Parâmetro </th> 
   <th class="entry"> Variável do Analytics </th> 
   <th class="entry"> Relatório preenchido </th> 
   <th class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> Nenhum </td> 
   <td colname="col3"> Nenhum </td> 
   <td colname="col4"> Dica de localização do Audience Manager (usada na integração do perfil compartilhado da Experience Cloud) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> Nenhum </td> 
   <td colname="col3"> Nenhum </td> 
   <td colname="col4"> Blob do Audience Manager (usado na integração do perfil compartilhado da Experience Cloud) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> Nenhum </td> 
   <td colname="col3"> Nenhum </td> 
   <td colname="col4"> ID do visitante do Analytics </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> Nenhum </td> 
   <td> Nenhum </td> 
   <td> Indica o início de uma solicitação de imagem. </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> Nenhum </td> 
   <td> Nenhum </td> 
   <td> Indica o fim de uma solicitação de imagem e significa que a solicitação não foi truncada. </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> Nenhum </td> 
   <td> Perfil do visitante | Tecnologia | Altura do navegador </td> 
   <td> Altura da janela do navegador (em pixels) </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> Nenhum </td> 
   <td> Perfil do visitante | Tecnologia | Largura do navegador </td> 
   <td> Largura da janela do navegador (em pixels) </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> Nenhum </td> 
   <td> Perfil do visitante | Tecnologia | Profundidade de cores do monitor </td> 
   <td> Qualidade de cor (em bits) </td> 
  </tr> 
  <tr> 
   <td> </td><td><p></p></td><td><p></p></td><td><p></p><p><code> &lt;my.a&gt;red&lt;/my.a&gt; </code></p><p></p><p><code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code></p><p><code> my.a = red </code></p><p><code> c.&my.a=red </code></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td><code> D </code></td><td></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p><code> t </code></p><code>
      dd/mm/yyyy&amp;nbsp;hh:mm:ss&amp;nbsp;D&amp;nbsp;OFFSET 
    </code><p><code> 0-6 </code><code> OFFSET </code></p><code>
      offset&amp;nbsp;from&amp;nbsp;GMT&amp;nbsp;in&amp;nbsp;hours&amp;nbsp;*&amp;nbsp;60&amp;nbsp;*&amp;nbsp;-&amp;nbsp;1 
    </code><p></p><code>
      23/09/2016&amp;nbsp;14:00:00&amp;nbsp;1&amp;nbsp;420 
    </code></td></tr><tr><td><code> ts </code></td><td><p></p></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td><p></p></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p></p></td></tr></tbody></table>

