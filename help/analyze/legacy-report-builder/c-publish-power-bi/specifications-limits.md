---
description: Limitações ao usar o Report Builder e o Microsoft Power BI.
title: Limitações e especificações
feature: Report Builder
role: User, Admin
exl-id: 4bbeec5b-64bc-4285-9f13-33b223b88834
TQID: https://experienceleague.adobe.com/L3R3ufcclrTpw-fKoFLD8Y-v56rTm4tXlXqjaTdmdoQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 631
ht-degree: 38%

---

# Limitações e especificações

{{legacy-arb}}

## Restrições de publicação do Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Essas restrições se aplicam apenas à opção &quot;Publicar solicitações do Report Builder como tabelas de conjunto de dados do Power BI&quot;.

* Um máximo de 100 solicitações do Report Builder pode ser exportado para o Power BI por pasta de trabalho.
* O processo de agendamento parará de exportar solicitações quando a 101ª solicitação for atingida.
* Apenas as primeiras 10.000 linhas de dados do Analytics serão enviadas ao Power BI por solicitação do Report Builder. As linhas restantes serão ignoradas.

## Editar uma solicitação do Report Builder após a publicação no Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Essa especificação se aplica às opções &quot;Publicar todas as solicitações do Report Builder como tabelas de conjunto de dados do Power BI&quot; e &quot;Publicar todas as tabelas formatadas na pasta de trabalho como tabelas de conjuntos de dados do Power BI&quot;.

Editar uma solicitação do Report Builder após a sua publicação no Power BI pode causar problemas.

* **Caso 1**: publique uma pasta de trabalho no Power BI e crie uma visualização com base em seus dados. Depois, você faz alterações na pasta de trabalho, o que causa o desaparecimento de uma das colunas do conjunto de dados que a referencia. Em seguida, você republica. Isso quebrará a visualização no Power BI.

  **Este é um exemplo de como a visualização SERÁ interrompida:**

   1. No Report Builder, crie uma pasta de trabalho com uma solicitação, usando a dimensão da Página e a métrica de Exibições da página.
   2. Programe essa solicitação para publicação no Power BI.
   3. No Power BI, crie uma visualização para Página e Exibições de página.
   4. Agora edite a pasta de trabalho removendo Exibições de página da solicitação.
   5. Edite o agendamento com a pasta de trabalho atualizada e publique novamente a solicitação no Power BI.
   6. Quando a nova pasta de trabalho for enviada para o Power BI

      1. Verifique se ele substituiu o conjunto de dados existente criado quando você publicou pela primeira vez.
      2. Verifique se a tabela page_1 foi atualizada corretamente com as colunas Página e Visitas.
      3. Verifique se a visualização está quebrada, pois faz referência à coluna Exibições de página que não está mais presente na tabela page_1.

  **Este é um exemplo de como a visualização NÃO será interrompida:**

   1. No Report Builder, crie uma pasta de trabalho com uma solicitação, usando a dimensão da Página e a métrica de Exibições da página.
   2. Programe essa solicitação para publicação no Power BI.
   3. No Power BI, crie uma visualização para Página e Exibições de página.
   4. Agora edite a pasta de trabalho no Report Builder, adicionando a métrica Visita enquanto se mantém Página e Exibições de página.
   5. Edite o agendamento com a pasta de trabalho atualizada e publique novamente a solicitação no Power BI.
   6. Quando a nova pasta de trabalho for enviada para o Power BI

      1. Verifique se ele substituiu o conjunto de dados existente criado quando você publicou pela primeira vez.
      2. Verifique se a tabela page_1 foi atualizada corretamente com as colunas Página, Exibições de página e Visitas.
      3. Verifique se a visualização continua a funcionar corretamente, pois faz referência a duas colunas que ainda estão presentes na tabela page_1.

* **Caso 2**: você prende uma seção da sua pasta de trabalho a um painel no Power BI e depois remove essa seção marcada (como um gráfico ou uma tabela) da pasta de trabalho. Isso quebrará a visualização.

## Alterar o nome de um relatório do Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Por padrão, o nome será preenchido com base no nome do arquivo da pasta de trabalho (sem a extensão .xlsx), exceto que os espaços são substituídos por caracteres de sublinhado.

Lembre-se

* O rótulo não pode ser uma combinação de letras e números que podem ser confundidos com um endereço de linha e coluna. Por exemplo, A100 não pode ser um rótulo porque é o endereço de uma célula em uma planilha.
* Os seguintes caracteres não são válidos para rótulos: `'#', '@', '!', '$', '^', '&', '&#42;', '`&#39; e `'~', ' '` . Eles serão substituídos por um caractere de sublinhado.
* Quando você inserir um nome inválido, será exibida uma mensagem de aviso que sugerirá um nome gerado automaticamente. Se você clicar em **[!UICONTROL Sim]**, esse nome será usado. Se você clicar em **[!UICONTROL Não]**, a interface do Assistente Avançado permitirá que você insira um novo nome.
