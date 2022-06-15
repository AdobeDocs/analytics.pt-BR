---
title: Configurações do conjunto de classificações
description: Crie ou edite um Conjunto de classificações.
source-git-commit: c9465ea0524225494aa5067d00ca5e7aba4bca92
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---


# Configurações do conjunto de classificações

Configure um conjunto de classificações, faça upload de dados ou baixe dados.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]** > Clique no nome do Conjunto de classificações desejado

Ao editar um Conjunto de classificações, duas guias estão disponíveis; **[!UICONTROL Esquema]** e **[!UICONTROL Configurações]**.

## Configurações 

Os seguintes campos estão disponíveis na variável [!UICONTROL Configurações] e pode ser editado:

* **[!UICONTROL Nome]**: O nome do Conjunto de classificações.
* **[!UICONTROL Descrição]**: A descrição do Conjunto de classificações.
* **[!UICONTROL Nome do proprietário]**: O nome do proprietário.
* **[!UICONTROL Email do proprietário]**: O endereço de email do proprietário.
* **[!UICONTROL Notificação de problemas]**: Uma lista delimitada por vírgulas de endereços de email que são notificados sobre problemas com este Conjunto de classificações.
* **[!UICONTROL Tags]**: Adicione uma ou mais tags ao(s) conjunto(s) de classificação selecionado(s), o que permite organizar ou agrupar conjuntos de classificação para facilitar a localização no futuro.

Campos adicionais estão disponíveis para fins informativos e não podem ser editados:

* **[!UICONTROL Tipo]**: O tipo de classificação entre [!UICONTROL Primário] e [!UICONTROL Pesquisa]. As classificações primárias são normalmente usadas.
* **[!UICONTROL Subscrições]**: O Conjunto de relatórios e a variável à qual o Conjunto de classificações se aplica. Atualmente, apenas um conjunto de relatórios é compatível com um determinado conjunto de classificações; o suporte para vários conjuntos de relatórios está planejado.

## Esquema

Exibir dimensões de classificação atualmente configuradas para esta assinatura. Os seguintes botões estão disponíveis:

* **[!UICONTROL Upload]**: Faça upload manual dos dados de classificação de uma ou mais dimensões de classificação. Arquivos JSON, CSV, TSV e TAB são compatíveis. O upload de um arquivo válido mostra uma pré-visualização de tabela de dados a serem classificados.
   * **[!UICONTROL Codificação de arquivo]**: Selecione a codificação de arquivo correta usando essa lista suspensa. As opções válidas incluem [!UICONTROL UTF-8] e [!UICONTROL Latim1].
   * **[!UICONTROL Delimitador de lista]**: Selecione o delimitador de lista correto. Se estiver usando um arquivo baixado ou um arquivo de modelo, verifique se [!UICONTROL Delimitador de lista] corresponde ao [!UICONTROL Delimitador de lista] quando o arquivo foi baixado.
   * **[!UICONTROL Aplicar]**: Salve os dados de classificação carregados no Conjunto de classificações.
