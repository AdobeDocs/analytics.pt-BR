---
description: Entenda a experiência de projetos somente leitura no Analysis Workspace.
keywords: Projetos somente de leitura
title: Projetos somente leitura
feature: Curate and Share
role: User, Admin
exl-id: 53372247-6902-4c7f-9132-38a1d453186c
TQID: https://experienceleague.adobe.com/8PyU15pb5sDqq-qZE-T8ceuDJdXDUXyxPQvJYJGUfwg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: dcae653e-62c6-4cc8-84e6-ee110b848296id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 52%

---

# Projetos somente de leitura

Você pode compartilhar projetos como somente leitura com os destinatários por meio da [funcionalidade de compartilhamento](share-projects.md). Os destinatários colocados na função **[!UICONTROL Somente leitura]** receberão uma experiência de projeto mais limitada.

Essa opção pode ser útil se você estiver compartilhando um projeto com usuários menos familiarizados com a estrutura de dados da sua organização, com o Analysis Workspace ou o Adobe Analytics em geral, mas ainda assim quiser que eles vejam os dados e insights em um ambiente seguro.

![Compartilhar como somente leitura](assets/read-only-project-sender.png)

As interações para os recipients somente leitura são limitadas.

![Compartilhamento como somente leitura recebido](assets/read-only-project-receiver.png)

## Interações desativadas

As interações desativadas em um projeto somente visualização incluem:

* Painel esquerdo oculto
* Intervalo de datas do calendário do painel. Observação: se quiser conceder o controle do calendário aos destinatários, adicione um [segmento suspenso com intervalos de datas](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=pt-BR).
* Segmentação de forma livre
* Número de formas livres de linhas visíveis
* Configurações de linha, coluna ou visualização de forma livre
* Segmentos do painel
* Menus Editar, Inserir e Componente
* Dicas do Espaço de trabalho

## Interações habilitadas

Algumas das interações habilitadas mais importantes em um projeto somente visualização incluem:

| Área | Interações habilitadas |
| --- | --- |
| **Tabelas de forma livre** | <li>Paginação e classificação</li><li>Passagem</li><li>Seleções de células que atualizam visualizações vinculadas</li><li>No menu de contexto > Obter link de visualização</li><li>No menu de contexto > Copiar para a área de transferência</li> |
| **Visualizações** | <li>Clicar para ativar/desativar legenda</li><li>Passagem</li><li>No menu de contexto > Obter link de visualização</li><li>Recolher/expandir</li><li>Fluxo - expandir nós de fluxo</li><li>Mapa - zoom</li></ul> |
| **Painéis** | <li>Segmentos suspensos interativos</li><li>No menu de contexto > Obter link do painel</li><li>Recolher/expandir</li> |
| **Projeto** | <li>Como inspecionar todos os ícones de informações</li><li>Menu Projeto - Novo, Abrir, Definir como página de destino, Atualizar, Baixar CSV/PDF, Informações e configurações limitadas do projeto</li><li>Menu Compartilhar - Obter link do projeto, Enviar arquivo agora</li><li>Menu Ajuda - Todas as ações, exceto as opções de Dicas e Depurador</li> |


## Compartilhe com qualquer pessoa

Se você selecionou um projeto usando [Compartilhar com qualquer pessoa](share-projects.md#share-a-project-with-anyone-no-login-required), o destinatário do link só poderá visualizar o projeto e não interagir com ele.

![Compartilhar com qualquer pessoa](assets/share-with-anyone-receiver.png)
