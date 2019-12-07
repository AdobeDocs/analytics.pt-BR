---
description: Uma utilização comum de hierarquias de conteúdo é mostrar os caminhos diferentes que os visitantes adotaram em determinada página, nível e assim por diante.
keywords: Analytics Implementation;content hierachies;hier
title: Contagem de hierarquias de conteúdo
topic: Developer and implementation
uuid: d41df92d-65fb-44de-bf46-8fac24303dad
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Contagem de hierarquias de conteúdo

Uma utilização comum de hierarquias de conteúdo é mostrar os caminhos diferentes que os visitantes adotaram em determinada página, nível e assim por diante.

**Como rastrear minha[!UICONTROL hierarquia de conteúdo]?**

Você deve compreender os requisitos de geração de relatório para rastrear [!UICONTROL hierarquias de conteúdo]. Se os requisitos para rastrear a hierarquia forem muito detalhados, geralmente, a variável de hierarquia ( *`hier`*) é recomendada. As hierarquias geralmente exigem uma taxonomia rigorosa predefinida em que o mesmo nó filho raramente fica sob vários nós pais. Considere o exemplo a seguir:

[!UICONTROL Hierarquia global]

Todos os sites &gt; Regiões &gt; Países &gt; Idioma &gt; Categoria

Neste exemplo, a hierarquia pode começar a ser dividida no nível do idioma. Se um requisito for gerar relatórios sobre o tráfego geral em inglês, você poderá se deparar com o problema de que inglês é exibido nos EUA, na Inglaterra, na Austrália e assim por diante. As hierarquias só permitem a busca detalhada. Para cortar horizontalmente várias hierarquias, a prática recomendada é usar uma[!UICONTROL  variável de tráfego personalizado] (prop).

Se você quiser oferecer aos usuários a capacidade de busca detalhada por meio do site (semelhante à forma como usuários navegariam no site) e gerar relatórios sobre [!UICONTROL Visitantes exclusivos] em cada nível da hierarquia, a variável da hierarquia será recomendada.

Há ocasiões em que o uso de props e das variáveis *`hier`* faz sentido. A seguir, há uma prop com suporte para cada tipo de variável:

<table id="table_E960D100DA0F433A94A4B246D6EF0D0A"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> Props </th> 
   <th class="entry"> Hierarquia </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Correlações </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2A70A61A78024204B6CEE4FFF9A0851E" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Definição de caminho </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_EE5ED36AC75F4D648F54858D796F82BD" /> </p> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Exibição da Página </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_5BB82776D41642E78C2ECFD71DD33164" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_18F34EE8957946AF9D6C2C9B492CEDB7" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Visitantes únicos </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_A475267547B94DB4A1EEFD903B2CA1EB" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_1E9E302D999146128CDBCE13E52BC38C" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Classificações </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_FC5FEFE7BA8C4475BA4F31D57302BE6B" /> </p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

