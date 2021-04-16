---
description: Antes de começar a criar conjuntos de relatórios virtuais, lembre-se das informações a seguir.
keywords: Conjunto de relatórios virtuais
title: Criar conjuntos de relatórios virtuais
feature: Noções básicas do Reports & Analytics
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 99%

---

# Criar conjuntos de relatórios virtuais

Antes de começar a criar conjuntos de relatórios virtuais, lembre-se das informações a seguir.

* Usuários não administradores não podem visualizar o Gerenciador de conjunto de relatórios virtuais.
* Os conjuntos de relatórios virtuais não podem ser compartilhados. O “Compartilhamento” é efetuado por grupos/permissões.
* No Gerenciador de conjunto de relatórios virtuais, você pode exibir apenas seus próprios conjuntos de relatórios virtuais. É necessário clicar em &quot;mostrar tudo&quot; para exibir o restante.

1. Navegue até **[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de relatórios virtuais]**.
1. Clique em **[!UICONTROL Adicionar +]**.

   ![](assets/new_vrs.png)

1. Preencha os campos:

<table id="table_0F85B56480BB46CBA5BE236BBD70156D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> <p>O nome do conjunto de relatórios virtual não é herdado do conjunto de relatórios pai e não deve ser distinto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descrição </td> 
   <td colname="col2"> <p>Adicione uma boa descrição para beneficiar seus usuários comerciais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tags </td> 
   <td colname="col2"> <p>É possível adicionar tags para organizar seus conjuntos de relatórios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupos </td> 
   <td colname="col2"> <p>Selecione os grupos de permissões que você deseja que acessem essa VRS. (Você também pode gerenciar permissões de grupo em <span class="ignoretag"><span class="uicontrol"> Administrador</span> &gt; <span class="uicontrol">Gerenciamento de usuários</span> &gt; <span class="uicontrol">Grupos</span></span>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conjunto de relatórios pai </td> 
   <td colname="col2"> <p>O conjunto de relatórios do qual este conjunto de relatórios virtual herda as seguintes configurações. A maioria dos níveis e recursos do serviço (por exemplo, configurações de eVar, Regras de processamento, Classificações e assim por diante) são herdados. Para alterar essas configurações herdadas em um VRS, é necessário editar o conjunto de relatórios pai (<span class="ignoretag"><span class="uicontrol">Administrador</span> &gt; <span class="uicontrol">Conjuntos de relatórios</span></span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fuso horário </td> 
   <td colname="col2"> <p>A escolha de um fuso horário é opcional. </p> <p>Se você escolher um fuso horário, ele será salvo com o VRS. Se não escolher um, o fuso horário do conjunto de relatórios principal é usado. </p> <p>Ao editar um VRS, o seletor suspenso exibe o fuso horário salvo com o VRS. Se o VRS tiver sido criado antes da adição do suporte a fuso horário, o seletor suspenso mostrará o fuso do conjunto de relatórios pai. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segmentos </td> 
   <td colname="col2"> <p>Você pode adicionar um segmento ou <a href="https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/segmentation-workflow/seg-build.html"  >empilhá-los</a>. </p> <p> <p>Observação: ao empilhar dois segmentos, eles são unidos por padrão por uma instrução AND. Isso não pode ser alterado para uma instrução OR. </p> </p> <p>Ao tentar excluir ou modificar um segmento usado em um conjunto de relatórios virtuais, você receberá um aviso. </p> </td> 
  </tr> 
 </tbody> 
</table>
