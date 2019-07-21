---
description: 'null'
seo-description: 'null'
seo-title: Limitações e especificações
title: Limitações e especificações
uuid: 6717 b 6 ea -7 e 01-49 b 8-8 f 6 e-fb 733 a 03 b 687
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Limitações e especificações

## Power BI publishing restrictions {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Essas restrições se aplicam somente à opção "Publicar solicitações do Construtor de relatórios como tabelas de conjuntos de dados do Power BI".

* Um máximo de 100 solicitações pode ser exportado para o Power BI por pasta de trabalho.
* O processo de agendamento interromperá a exportação das solicitações quando a 101a solicitação for atingida.
* Apenas as primeiras 10.000 linhas de dados do Analytics serão enviadas ao Power BI por solicitação do Construtor de relatórios. As linhas restantes serão ignoradas.

## Edit a Report Builder request after publishing to Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Essa especificação se aplica à opção «Publicar todas as solicitações do Construtor de relatórios como tabelas de conjunto de dados do Power BI» e «Publicar todas as tabelas formatadas na pasta de trabalho como tabelas de conjuntos de dados do Power BI».

Editar uma solicitação do Construtor de relatórios após a sua publicação no Power BI pode causar problemas.

* **Caso 1**: você publica uma pasta de trabalho no Power BI e cria uma visualização baseada em seus dados. Depois, você faz alterações na pasta de trabalho, o que causa o desaparecimento de uma das colunas do conjunto de dados que a referencia. Depois você republica. Isso quebrará a visualização no Power BI.

   **Este é um exemplo de como a visualização quebrará:**

   1. No Construtor de relatórios, crie uma pasta de trabalho com uma solicitação, usando a dimensão da Página e a métrica de Exibições da página.
   1. [Agende essa solicitação](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463) para publicação no Power BI.
   1. No Power BI, crie uma visualização para a Página e as Exibições da página.
   1. Agora edite a pasta de trabalho através da remoção das Exibições de página da solicitação.
   1. Edite o agendamento com a pasta de trabalho atualizada e republique a solicitação no Power BI.
   1. Uma vez que a nova pasta de trabalho é enviada para o Power BI

      1. Verifique se ela sobrescreveu o conjunto de dados existente criado quando da primeira publicação.
      1. Verifique se a tabela da página_1 está atualizada de forma apropriada na Página e nas Colunas de visitas.
      1. Verifique se a sua visualização está quebrada, já que ela faz referência à coluna da Exibição de página que não está mais presente na tabela da página_1.
   **Este é um exemplo de como a visualização NÃO se quebrará:**

   1. No Construtor de relatórios, crie uma pasta de trabalho com uma solicitação, usando a dimensão da Página e a métrica de Exibições da página.
   1. [Agende essa solicitação](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463) para publicação no Power BI.
   1. No Power BI, crie uma visualização para a Página e as Exibições da página.
   1. Agora edite a pasta de trabalho no Construtor de relatórios, adicionando a métrica Visita enquanto se mantém Página e Exibições de página.
   1. Edite o agendamento com a pasta de trabalho atualizada e republique a solicitação no Power BI.
   1. Uma vez que a nova pasta de trabalho é enviada para o Power BI

      1. Verifique se ela sobrescreveu o conjunto de dados existente criado quando da primeira publicação.
      1. Verifique se a tabela da página_1 foi devidamente atualizada com as colunas Página, Exibições da página e Visitas.
      1. Verifique se a sua visualização continua a funcionar apropriadamente já que ela faz referência a duas colunas que ainda estão presentes na tabela página_1.


* **Caso 2**: você coloca uma seção da sua pasta de trabalho em um painel do Power BI e depois remove essa seção (tal como um gráfico ou uma tabela) dela. Isso quebrará a visualização.

## Change the name of a Power BI report {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Por padrão, o nome será extraído do nome de arquivo da pasta de trabalho (sem a extensão .xlsx), exceto pelo fato de que os espaços são substituídos por underscores

Lembre-se

* O rótulo não pode ser uma combinação de letras e números que possa ser confundida com um endereço de linha e coluna. Por exemplo, A100 não pode ser um rótulo porque é o endereço de uma célula na planilha.
* Os seguintes caracteres não são válidos para rótulos: '#', '@', '!', '$', '^', '&amp;', '*', '`', '~', ' ' . Eles serão substituídos por um caractere underscore.
* Quando um nome inválido é inserido, uma mensagem de aviso será mostrada que sugerirá um nome autogerado. If you click **[!UICONTROL Yes]**, this name will be used. If you click **[!UICONTROL No]**, the Advanced Wizard UI will let you enter the new name.

