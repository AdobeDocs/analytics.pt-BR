---
title: Fontes de dados de ID de transação
description: Saiba mais sobre o fluxo de trabalho geral do uso de fontes de dados de ID de transação.
translation-type: tm+mt
source-git-commit: a5c3d9b2cd02dc7e89abb469e2e0e44985a17638

---


# Fontes de dados de ID de transação

As fontes de dados da ID de transação permitem que você visualize dados online e offline lado a lado, mas vincule os dados juntos. Ela requer o uso da [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variável na implementação do Analytics.

Quando você envia uma ocorrência on-line que contém um `transactionID` valor, a Adobe captura um &quot;instantâneo&quot; de todas as variáveis definidas ou persistentes no momento. Se uma ID de transação correspondente carregada por meio das Fontes de Dados for encontrada, os dados offline e online serão vinculados. Não importa qual fonte de dados é vista primeiro.

## Fluxo de trabalho geral das fontes de dados da ID de transação

Use o fluxo de trabalho genérico a seguir para começar a usar fontes de dados da ID de transação:

1. Crie uma fonte de dados (categoria &quot;Genérica&quot; e tipo &quot;Fonte de Dados Genérica (ID de Transação)&quot;).
1. Siga o assistente de configuração do feed de dados para obter um local FTP para carregar dados e baixar um arquivo de modelo de fontes de dados.
1. Atualize sua implementação para incluir a `transactionID` variável.
1. Carregue um arquivo de fontes de dados no site FTP com um `.fin` arquivo.
