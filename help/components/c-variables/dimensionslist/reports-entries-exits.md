---
description: O relatório de Página de entrada mostra, por porcentagem e por total de visitas, quais páginas no site são as primeiras páginas vistas por um novo visitante.
title: Entradas e Saídas
topic: Reports
uuid: 756de55b-136b-427b-a80c-f822260131b1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Entradas e Saídas

>[!NOTE]
>Para ocorrências com múltiplos valores na variável de produtos, Entradas e Saídas agora aplicam-se a todos os valores de produtos em uma ocorrência, em vez de somente ao primeiro.

O relatório de Página de entrada mostra, por porcentagem e por total de visitas, quais páginas no site são as primeiras páginas vistas por um novo visitante.

Você pode selecionar:

* **Páginas de entrada** (ou seções): mostra, por porcentagem e por total de visitas, quais páginas no site são as primeiras páginas vistas por um novo visitante. Você pode usar este relatório para identificar qual das suas páginas da Web são os pontos mais frequentes de entrada, otimizar os pontos de entrada primária do site e o tráfego de entrada da unidade para suas mensagens-chave.

   Uma maneira útil de usar a métrica Exibição de página é executar um relatório de **[!UICONTROL Caminhos]** > **[!UICONTROL Páginas]** > **[!UICONTROL Entrada de páginas]**, ordenado por ela, e ver quais entradas de pagina direcionam a maioria das exibições de página.

* **Páginas de entrada originais**: mostra a primeira página visualizada pela primeira vez pelos visitantes do site. Cada usuário é contado apenas uma vez, a não ser que ele exclua seus cookies do navegador ou não esteja sendo rastreado por cookies.
* **Visitas únicas à página**: mostra páginas que frequentemente são páginas de entrada e saída para as sessões de navegação do visitante.
* **Páginas de saída**: mostram, por porcentagem e pelo total de visitas, quais locais no site foram os últimos que os visitantes visualizaram antes de sair do site. As páginas de saída possuem um escopo de interrupção de visita, o que significa que elas persistem em todos os hits de uma visita.

**Métricas em um Relatório de páginas de entrada**

* **Entradas**: assim como as instâncias ou ocorrências, é o número de vezes que a página foi a página de entrada para uma visita.
* **Visitas**: para quantas visitas esta página foi a página de entrada (esta métrica deve corresponder às entradas).
* **Saídas**: número de vezes que ocorreu uma saída no local onde a página de entrada havia sido especificada. Se você deseja ver o número de vezes que a página de entrada também funcionou como página de saída, use a métrica Devoluções e não a de saídas.

**Segmentação em um Relatório de páginas de entrada**

A execução de um [!UICONTROL Relatório de páginas de entrada] informa apenas sobre páginas de entrada, mesmo se você aplicar segmentos a uma páginas de não entrada.

Por exemplo, considere um sequência de visita da seguinte forma:

[!DNL Page A] > [!DNL Page B] > [!DNL Page C]

Se Página B e Página C são usados em um segmento, somente a Página A é relatada em um [!UICONTROL Relatório de páginas de entrada], pois a Página A é a página de entrada.
