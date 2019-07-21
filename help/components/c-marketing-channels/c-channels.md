---
description: Adicione ou ative os canais de marketing no Gerenciador de canal de marketing. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).
seo-description: Adicione ou ative os canais de marketing no Gerenciador de canal de marketing. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).
seo-title: Gerenciar canais de marketing
solution: Analytics
subtopic: Canais de marketing
title: Gerenciar canais de marketing
topic: Reports and Analytics
uuid: 9 d 367 bb 6-a 17 b -49 b 8-9 cd 5-24 fac 35 ae 982
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Gerenciar canais de marketing

Adicione ou ative os canais de marketing no Gerenciador de canal de marketing. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).

## Manage marketing channels {#topic_45CF1C6A783B4F96ABF6317EAB6A854F}

Add or enable marketing channels in the [!UICONTROL Marketing Channel Manager]. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).

A seguir, as orientações para a criação de canais:

* Planeje com antecedência, fazendo uma lista de todos os canais, para que todas ocorrências de visitantes sejam categorizadas para o canal correto.
* Sempre inclua canais para as categorias de ocorrências [Internas](../../components/c-marketing-channels/c-faq.md#section_179A2BE5C8E24719A9E5C0DC09AF0947) e [Diretas](../../components/c-marketing-channels/c-faq.md#section_D0A1DD9D5EEF4A05A1CC81F9EADC074A).

A inclusão de [!UICONTROL Canais de marketing] é feita de forma independente da criação de regras na página [Regras de Processamento de Canal de marketing](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08). Ao criar regras, associe-as aos canais.

## Adição de canais de marketing {#task_98C9D3F5DBBC4B198E0A9ED4D3891E03}

Adicione canais de marketing ao Administrador dos Canais de marketing.

>[!NOTE]
>
>Não é possível excluir um canal. Se não quiser usar um canal, desative-o ou renomeie-o, e guarde-o para uso posterior.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Na página do [!UICONTROL Gerenciador de conjunto de relatórios], selecione um conjunto de relatórios.

   Se você selecionar múltiplos conjuntos de ferramentas de relatório, será necessário selecionar um modelo que copie as configurações do modelo para os conjuntos de ferramentas de relatório selecionados.

   Consulte [Aplicar configurações do conjunto de relatório de modelo a múltiplos conjuntos de relatório](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC).

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Manager]**.

   If your report suite does not have channels defined, the [Auto Setup](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B) page displays.

1. Na página do [!UICONTROL Gerenciador de canal de marketing]**, clique em[!UICONTROL Adicionar canal]**.

   Essa opção não está disponível quando são definidos 25 canais.

1. Clique em **[!UICONTROL Salvar.]**
1. Para configurar regras para o canal, clique em **[!UICONTROL Regras de processamento de canal de marketing]**.

   See [Create Marketing Channel processing rules](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08).

## Marketing Channel Manager - interface definitions {#reference_01779A2928054BF48339897D4033AFB9}

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
   <td colname="col1"> <p>Tipo de canal </p> </td> 
   <td colname="col2"> <p> Especifica como o usuário chegou ao seu site. É possível selecionar <span class="uicontrol">online </span>ou <span class="uicontrol">offline</span>. É possível usar canais Online para visitantes que chegam por meio de um mecanismo de busca ou campanha por email. Os canais offline são aplicados a visitantes que localizam seu site por meio de cupons em jornais ou anúncios de revistas. Em geral, os canais offline incluem dados importados por meio de Origens de Dados de relatórios. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/" scope="external" format="http">Origens de Dados</a>. </p> <p>See <a href="../../components/c-marketing-channels/t-offline-data.md#task_FC96E6A48F0D4D37A79BD234E90DAA26" type="task" format="dita" scope="local"> Add Offline Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cor do canal </p> </td> 
   <td colname="col2"> <p>A cor associada a este canal de marketing. Essa cor representa o canal no relatório de <span class="wintitle">Canal de marketing</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

