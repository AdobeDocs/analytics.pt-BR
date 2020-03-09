---
description: 'null'
title: Limitações e especificações
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Limitações e especificações

## Restrições de publicação do Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

> [!NOTE] Essas restrições se aplicam apenas à opção &quot;Publicar solicitações do Report Builder como tabelas de conjunto de dados do Power BI&quot;.

* Um máximo de 100 solicitações do Report Builder pode ser exportado para o Power BI por pasta de trabalho.
* O processo de agendamento interromperá a exportação das solicitações quando a 101a solicitação for atingida.
* Apenas as primeiras 10.000 linhas de dados do Analytics serão enviadas ao Power BI por solicitação do Report Builder. As linhas restantes serão ignoradas.

## Editar uma solicitação do Report Builder após a publicação no Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

> [!NOTE] Essa especificação se aplica às opções &quot;Publicar todas as solicitações do Report Builder como tabelas de conjunto de dados do Power BI&quot; e &quot;Publicar todas as tabelas formatadas na pasta de trabalho como tabelas de conjuntos de dados do Power BI&quot;.

Editar uma solicitação do Report Builder após a sua publicação no Power BI pode causar problemas.

* **Caso 1**: você publica uma pasta de trabalho no Power BI e cria uma visualização baseada em seus dados. Depois, você faz alterações na pasta de trabalho, o que causa o desaparecimento de uma das colunas do conjunto de dados que a referencia. Depois você republica. Isso quebrará a visualização no Power BI.

   **Este é um exemplo de como a visualização quebrará:**

   1. No Report Builder, crie uma pasta de trabalho com uma solicitação, usando a dimensão da Página e a métrica de Exibições da página.
   1. [Agende essa solicitação](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) para publicação no Power BI.
   1. No Power BI, crie uma visualização para a Página e as Exibições da página.
   1. Agora edite a pasta de trabalho através da remoção das Exibições de página da solicitação.
   1. Edite o agendamento com a pasta de trabalho atualizada e republique a solicitação no Power BI.
   1. Uma vez que a nova pasta de trabalho é enviada para o Power BI

      1. Verifique se ela sobrescreveu o conjunto de dados existente criado quando da primeira publicação.
      1. Verifique se a tabela da página_1 está atualizada de forma apropriada na Página e nas Colunas de visitas.
      1. Verifique se a sua visualização está quebrada, já que ela faz referência à coluna da Exibição de página que não está mais presente na tabela da página_1.
   **Este é um exemplo de como a visualização NÃO se quebrará:**

   1. No Report Builder, crie uma pasta de trabalho com uma solicitação, usando a dimensão da Página e a métrica de Exibições da página.
   1. [Agende essa solicitação](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) para publicação no Power BI.
   1. No Power BI, crie uma visualização para a Página e as Exibições da página.
   1. Agora edite a pasta de trabalho no Report Builder, adicionando a métrica Visita enquanto se mantém Página e Exibições de página.
   1. Edite o agendamento com a pasta de trabalho atualizada e republique a solicitação no Power BI.
   1. Uma vez que a nova pasta de trabalho é enviada para o Power BI

      1. Verifique se ela sobrescreveu o conjunto de dados existente criado quando da primeira publicação.
      1. Verifique se a tabela da página_1 foi devidamente atualizada com as colunas Página, Exibições da página e Visitas.
      1. Verifique se a sua visualização continua a funcionar apropriadamente já que ela faz referência a duas colunas que ainda estão presentes na tabela página_1.


* **Caso 2**: você coloca uma seção da sua pasta de trabalho em um painel do Power BI e depois remove essa seção (tal como um gráfico ou uma tabela) dela. Isso quebrará a visualização.

## Alterar o nome de um relatório do Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Por padrão, o nome será extraído do nome de arquivo da pasta de trabalho (sem a extensão .xlsx), exceto pelo fato de que os espaços são substituídos por underscores

Lembre-se

* O rótulo não pode ser uma combinação de letras e números que possa ser confundida com um endereço de linha e coluna. Por exemplo, A100 não pode ser um rótulo porque é o endereço de uma célula na planilha.
* Os seguintes caracteres não são válidos para rótulos: &#39;#&#39;, &#39;@&#39;, &#39;!&#39;, &#39;$&#39;, &#39;^&#39;, &#39;&amp;&#39;, &#39;*&#39;, &#39;`&#39;, &#39;~&#39;, &#39; &#39; . Eles serão substituídos por um caractere underscore.
* Quando um nome inválido é inserido, uma mensagem de aviso será mostrada que sugerirá um nome autogerado. Se clicar em **[!UICONTROL Sim]**, esse nome será usado. Se clicar em **[!UICONTROL Não]**, a interface do usuário do Assistente avançado permitirá que um novo nome seja inserido.

