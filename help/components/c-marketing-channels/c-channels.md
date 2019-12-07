---
description: Adicionar ou ativar canais de marketing ao Administrador dos Canais de marketing. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).
subtopic: Marketing channels
title: Gerenciar canais de marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gerenciar canais de marketing

Adicionar ou ativar canais de marketing ao Administrador dos Canais de marketing. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).

A seguir, as orientações para a criação de canais:

* Planeje com antecedência, fazendo uma lista de todos os canais, para que todas ocorrências de visitantes sejam categorizadas para o canal correto.
* Sempre inclua canais para as categorias de ocorrências [Internas](/help/components/c-marketing-channels/c-faq.md) e [Diretas](/help/components/c-marketing-channels/c-faq.md).

A inclusão de [!UICONTROL Canais de marketing] é feita de forma independente da criação de regras na página [Regras de Processamento de Canal de marketing](/help/components/c-marketing-channels/t-rules.md). Ao criar regras, associe-as aos canais.

## Adição de canais de marketing {#add-mktg-channels}

Adicione canais de marketing ao Administrador dos Canais de marketing.

> [!NOTE] Não é possível excluir um canal. Se não quiser usar um canal, desative-o ou renomeie-o, e guarde-o para uso posterior.

1. Clique em **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Conjuntos de relatórios]**.
1. Na página do [!UICONTROL Gerenciador de conjunto de relatórios], selecione um conjunto de relatórios.

   Se você selecionar múltiplos conjuntos de ferramentas de relatório, será necessário selecionar um modelo que copie as configurações do modelo para os conjuntos de ferramentas de relatório selecionados.

   Consulte [Aplicar configurações do conjunto de relatório de modelo a múltiplos conjuntos de relatório](/help/components/c-marketing-channels/t-template.md).

1. Clique em **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Canais de marketing]** &gt; **[!UICONTROL Gerenciador de canal de marketing]**.

   Se seu conjunto de relatórios não tem canais definidos, a página [Configuração automática](/help/components/c-marketing-channels/c-channel-autosetup.md) é exibida.

1. Na página do [!UICONTROL Gerenciador de canal de marketing]**, clique em[!UICONTROL Adicionar canal]**.

   Essa opção não está disponível quando são definidos 25 canais.

1. Clique em **[!UICONTROL Salvar.]**
1. Para configurar regras para o canal, clique em **[!UICONTROL Regras de processamento de canal de marketing]**.

   Consulte [Criar regras de processamento de canal de marketing](/help/components/c-marketing-channels/t-rules.md).

## Gerenciador de canal de marketing - definições de interface {#mktg-channel-mgr}

Definições de campo para a página do [!UICONTROL Gerenciador de canal de marketing].

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ativado </p> </td> 
   <td colname="col2"> <p> Ativa ou desativa este canal de marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de canal </p> </td> 
   <td colname="col2"> <p>O nome amigável do canal de marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Substituir canal de último toque </p> </td> 
   <td colname="col2"> <p> É possível escolher substituir um canal existente e persistente de último toque pelo canal selecionado. Se você marcar esta caixa de seleção, qualquer canal (incluindo canal Direto e Interno) substituirá um canal de último contato existente. O resultado é uma conversão atribuída a um canal que pode não merecer o crédito. Por exemplo, esta opção pode garantir que o Canal direto não receba crédito pela conversão se o usuário for avisado por meio do canal de Pesquisa Natural. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Análise de canal </p> </td> 
   <td colname="col2"> <p>Permite analisar um canal de acordo com este valor. É possível adicionar análises de canal (subcanais) ao criar classificações de canais de marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo </p> </td> 
   <td colname="col2"> <p> Especifica como o usuário chegou ao seu site. É possível selecionar <span class="uicontrol">online </span>ou <span class="uicontrol">offline</span>. É possível usar canais Online para visitantes que chegam por meio de um mecanismo de busca ou campanha por email. Os canais offline são aplicados a visitantes que localizam seu site por meio de cupons em jornais ou anúncios de revistas. Em geral, os canais offline incluem dados importados por meio de Origens de Dados de relatórios. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/"  >Origens de Dados</a>. </p> <p>Consulte <a href="/help/components/c-marketing-channels/t-offline-data.md"   >Adicionar dados offline</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cor do canal </p> </td> 
   <td colname="col2"> <p>A cor associada a este canal de marketing. Essa cor representa o canal no relatório de <span class="wintitle">Canal de marketing</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

