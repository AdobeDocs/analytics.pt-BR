---
description: 'null'
title: Limitações e especificações
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Limitações e especificações

## Restrições de publicação do Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE] Essas restrições se aplicam apenas à opção &quot;Publicar solicitações do Report Builder como tabelas de conjunto de dados do Power BI&quot;.

* Um máximo de 100 solicitações do Report Builder pode ser exportado para o Power BI por pasta de trabalho.
* O processo de programação interromperá a exportação de solicitações quando a 101ª solicitação for atingida.
* Apenas as primeiras 10.000 linhas de dados do Analytics serão enviadas ao Power BI por solicitação do Report Builder. As linhas restantes serão ignoradas.

## Editar uma solicitação do Report Builder após a publicação no Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE] Essa especificação se aplica às opções &quot;Publicar todas as solicitações do Report Builder como tabelas de conjunto de dados do Power BI&quot; e &quot;Publicar todas as tabelas formatadas na pasta de trabalho como tabelas de conjuntos de dados do Power BI&quot;.

Editar uma solicitação do Report Builder após a sua publicação no Power BI pode causar problemas.

* **Caso 1**: Você publica uma pasta de trabalho no Power BI e cria uma visualização com base em seus dados. Depois, você faz alterações na pasta de trabalho, o que causa o desaparecimento de uma das colunas do conjunto de dados que a referencia. Em seguida, você republica. Isso quebrará a visualização no Power BI.

   **Este é um exemplo de como a visualização quebrará:**

   1. No Report Builder, crie uma pasta de trabalho com uma solicitação, usando a dimensão da Página e a métrica de Exibições da página.
   1. [Agende essa solicitação](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) para ser publicada no Power BI.
   1. No Power BI, crie uma visualização para Visualizações de página e página.
   1. Agora edite a pasta de trabalho removendo Visualizações de página da solicitação.
   1. Edite o agendamento com a pasta de trabalho atualizada e republique a solicitação no Power BI.
   1. Quando a nova pasta de trabalho for enviada para o Power BI

      1. Verifique se ele sobrescreveu o conjunto de dados existente que foi criado quando você publicou pela primeira vez.
      1. Verifique se a tabela page_1 está atualizada corretamente com as colunas Página e Visitas.
      1. Verifique se sua visualização está quebrada, pois ela faz referência à coluna Visualizações de página que não está mais presente na tabela page_1.
   **Este é um exemplo de como a visualização NÃO quebrará:**

   1. No Report Builder, crie uma pasta de trabalho com uma solicitação, usando a dimensão da Página e a métrica de Exibições da página.
   1. [Agende essa solicitação](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) para ser publicada no Power BI.
   1. No Power BI, crie uma visualização para Visualizações de página e página.
   1. Agora edite a pasta de trabalho no Report Builder, adicionando a métrica Visita enquanto se mantém Página e Exibições de página.
   1. Edite o agendamento com a pasta de trabalho atualizada e republique a solicitação no Power BI.
   1. Quando a nova pasta de trabalho for enviada para o Power BI

      1. Verifique se ele sobrescreveu o conjunto de dados existente que foi criado quando você publicou pela primeira vez.
      1. Verifique se a tabela page_1 está atualizada corretamente com as colunas Página, Visualizações de página e Visitas.
      1. Verifique se a visualização continua a funcionar corretamente, já que ela faz referência a duas colunas que ainda estão presentes na tabela page_1.


* **Caso 2**: Você prende uma seção da sua pasta de trabalho a um painel no Power BI e depois remove essa seção (como um gráfico ou uma tabela) da pasta de trabalho. Isso quebrará a visualização.

## Alterar o nome de um relatório do Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Por padrão, o nome será preenchido a partir do nome de arquivo da pasta de trabalho (sem a extensão .xlsx), exceto que os espaços são substituídos por caracteres sublinhados.

Lembre-se

* O rótulo não pode ser uma combinação de letras e números que podem ser confundidos com um endereço de linha e coluna. Por exemplo, A100 não pode ser um rótulo porque é o endereço de uma célula em uma planilha.
* Os seguintes caracteres não são caracteres de rótulo válidos: &#39;#&#39;, &#39;@&#39;, &#39;!&#39;, &#39;$&#39;, &#39;^&#39;, &#39;&amp;&#39;, &#39;*&#39;, &#39;`&#39;, &#39;~&#39;, &#39; &#39; &#39; . Eles serão substituídos por um caractere sublinhado.
* Quando você digita um nome inválido, uma mensagem de aviso será exibida sugerindo um nome gerado automaticamente. Se você clicar **[!UICONTROL Yes]**, esse nome será usado. Se você clicar **[!UICONTROL No]**, a interface do usuário do Assistente avançado permitirá que você insira o novo nome.

