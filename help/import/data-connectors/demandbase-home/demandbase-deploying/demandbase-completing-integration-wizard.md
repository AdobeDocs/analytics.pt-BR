---
description: Para ativar a integração, você deve concluir o assistente de configuração na interface dos Conectores de dados.
seo-description: Para ativar a integração, você deve concluir o assistente de configuração na interface dos Conectores de dados.
seo-title: Concluindo o Assistente de integração da Adobe
title: Concluindo o Assistente de integração da Adobe
uuid: 75260b92-a6f5-44b6-b3ea-d5945fdd1ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Concluindo o Assistente de integração da Adobe{#completing-the-adobe-integration-wizard}

Para ativar a integração, você deve concluir o assistente de configuração na interface dos Conectores de dados.

1. Navegue até a área Conectores de dados (anteriormente Genesis) na Adobe Experience Cloud.
1. Inicie o assistente de integração Demandbase 2.0.
1. Escolha o Conjunto de relatórios desejado e forneça um nome para a integração.
1. Configure os seguintes itens:

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Endereço de email </td> 
   <td colname="col2"> O endereço de email do contato principal. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descrição </td> 
   <td colname="col2"> (Opcional) Descrição para esta configuração de integração. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chave da API Demandbase </td> 
   <td colname="col2"> Você pode obter isso do representante do Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensão Demandbase Personalizada #N </td> 
   <td colname="col2"> Essas são as IDs das 8 dimensões opcionais. Para obter mais informações, consulte Dimensões personalizadas da Base de Demanda. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enviar para o Adobe Target </td> 
   <td colname="col2">Se "true", as dimensões Demandbase também serão enviadas para o Adobe Target usando uma mbox oculta. <p>Observação:  Um arquivo mbox.js configurado deve ser implementado na página da Web para que as dimensões sejam coletadas. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configure os seguintes itens de Mapeamentos de variável:

   | Item | Descrição |
   |---|---|
   | Dimensões Demandbase | Escolha uma variável eVar disponível no conjunto de relatórios. |
   | Dimensões personalizadas Demandbase (opcional) | Escolha uma variável eVar disponível no conjunto de relatórios. |

1. Configure os nomes para a Dimensão personalizada (se aplicável).

   1. Se você optou por incluir Dimensões personalizadas na etapa 4 e mapeou a eVar opcional na etapa 5, é necessário fornecer nomes amigáveis para essas dimensões. Por exemplo, se você optar por inserir "stock_ticker" como Dimensão personalizada 1, você deverá alterar a caixa que contém "Dimensão 1" para "Contador de ações".
   1. Não **** modifique os nomes das dimensões padrão 8 (ou seja, SID demandbase, Nome da empresa, Indústria etc.).

1. Marque a caixa para que o painel Integração Demandbase seja criado automaticamente para você (recomendado).
1. Revise todos os itens de configuração e clique em **[!UICONTROL Ativar agora]**.

