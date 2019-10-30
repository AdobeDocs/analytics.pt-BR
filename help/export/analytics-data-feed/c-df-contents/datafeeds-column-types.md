---
description: A coluna anterior contém os dados conforme foram enviados para a coleção de dados. A coluna posterior contém o valor após o processamento.
keywords: Feed de dados;tarefa;pré coluna;pós coluna;distinção entre maiúsculas e minúsculas
seo-description: A coluna anterior contém os dados conforme foram enviados para a coleção de dados. A coluna posterior contém o valor após o processamento.
seo-title: Colunas anterior e posterior
solution: Analytics
title: Colunas anterior e posterior
topic: Reports and Analytics
uuid: a415327b-6151-4d08-b8b9-5aaa2348eb0c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Colunas anterior e posterior

A coluna anterior contém os dados conforme foram enviados para a coleção de dados. A coluna posterior contém o valor após o processamento.

Por exemplo, a persistência da variável, as regras de processamento, as regras VISTA e a conversão de moeda podem alterar o valor final registrado para um variável que consta na coluna posterior. Na maioria dos cálculos, você deseja usar a coluna posterior a menos que esteja aplicando uma lógica comercial personalizada (por exemplo, aplicar uma fórmula personalizada para determinar a atribuição).

Se uma coluna não tiver uma versão anterior ou posterior (por exemplo, `visit_num`), ela pode ser considerada uma coluna posterior. Columns prefixed with " `pre_`" typically contain data that was populated by Adobe and not sent by your implementation. For example, `pre_browser` is populated by Adobe, but `evar1` is populated by your implementation. Both of these columns have a " `post_`" column ( `post_browser`, `post_evar1`), which contains the value used by reporting.

## Diferenciação entre maiúsculas e minúsculas nos valores {#section_F979E099BFAB4AFEBEA2D7E228963CE8}

A maior parte das variáveis do Analytics não diferenciam maiúsculas de minúsculas para fins de registro, o que significa que letras maiúsculas ou minúsculas possuem o mesmo valor ("neve", "Neve", "NEVE" e "nEve" possuem o mesmo valor). No entanto, para fins de exibição, a diferenciação entre maiúsculas e minúsculas é mantida já que a maioria dos clientes prefere submeter caracteres variados para exibição nos relatórios.

Ao processar o feed de dados, é possível colocar os valores em minúsculas para fins de comparação; contudo, recomendamos que você mantenha a capitalização para fins de exibição.

Caso veja variações de maiúsculas e minúsculas para um mesmo valor entre as colunas anterior e posterior (por exemplo, "neve" na coluna anterior e "Neve" na coluna posterior), isso significa que ambas as versões do mesmo valor foram transmitidas para o site. A diferenciação entre maiúsculas e minúsculas na coluna posterior foi transmitida e armazenada no cookie virtual ou processada ao mesmo tempo que o conjunto de relatórios. Por exemplo:

Hit 1: s.list1="Tabby,Persian,Siamese";

Ocorrência 2: s.list1="tabby,persian,siamese";

Quando o hit 2 é relatado no feed de dados, a coluna anterior terá a capitalização exata transmitida (tabby,persian,siamese), mas o valor do hit 1 provavelmente será predominante para aquela visita e será relatado na coluna posterior (na qual será Tabby,Persian,Siamese) já que os hits 1 e 2 possuem o mesmo valor em uma comparação entre maiúsculas e minúsculas.
