---
description: Para ativar a integração, você deve concluir o assistente de configuração na interface dos Conectores de dados.
seo-description: Para ativar a integração, você deve concluir o assistente de configuração na interface dos Conectores de dados.
seo-title: Conclusão do Assistente de integração da Adobe
title: Conclusão do Assistente de integração da Adobe
uuid: 75260 b 92-a 6 f 5-44 b 6-b 3 ea-d 5945 fdd 1 bce
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Conclusão do Assistente de integração da Adobe{#completing-the-adobe-integration-wizard}

Para ativar a integração, você deve concluir o assistente de configuração na interface dos Conectores de dados.

1. Navegue até a área Conectores de dados (antigo Genesis) na Adobe Marketing Cloud.
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
   <td colname="col2"> (Opcional) Descrição para essa configuração de integração. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chave da API Demandbase </td> 
   <td colname="col2"> Você pode obter isso pelo seu representante Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensão de demandbase personalizada N n </td> 
   <td colname="col2"> Essas são IDs para as 8 dimensões opcionais. Para obter mais informações, consulte Dimensões personalizadas Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enviar para o Adobe Target </td> 
   <td colname="col2">Se «true», as dimensões Demandbase também serão enviadas para o Adobe Target usando uma mbox oculta. <p>Observação: Um arquivo mbox. js configurado deve ser implementado na página da Web para que as dimensões sejam coletadas. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configure os seguintes itens de Mapeamentos de variáveis:

   | Item | Descrição |
   |---|---|
   | Dimensões de demandbase | Escolha uma variável evar disponível de seu conjunto de relatórios. |
   | Dimensões personalizadas demandbase (opcional) | Escolha uma variável evar disponível de seu conjunto de relatórios. |

1. Configure os nomes da Dimensão personalizada (se aplicável).

   1. Se você optou por incluir Dimensões personalizadas na etapa 4 e mapear a evar opcional na etapa 5, então é necessário fornecer nomes amigáveis para essas dimensões. Por exemplo, se você escolher inserir «stock_ ticker» como Dimensão personalizada 1, você deve alterar a caixa que contém «Dimensão 1» para «Stock Ticker».
   1. **NÃO** modifique os nomes das dimensões padrão 8 (ou seja, SID de Demandbase, Nome da empresa, Setor etc.).

1. Marque a caixa para que o painel de Integração Demandbase seja criado automaticamente para você (recomendado).
1. Revise todos os itens de configuração e clique **[!UICONTROL em Ativar agora]**.

