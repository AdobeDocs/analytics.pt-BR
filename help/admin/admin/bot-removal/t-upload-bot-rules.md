---
description: Para as regras de bot de importação em massa, é possível fazer upload do arquivo CSV que define as regras.
seo-description: Para as regras do robô de importação em massa, é possível carregar o arquivo CSV que define as regras.
seo-title: Fazer upload de regras de bot
solution: Analytics
subtopic: Regras de bot
title: Fazer upload de regras de bot
topic: Ferramentas administrativas
uuid: bd 70 c 199-5817-437 e -980 d -6 d 8 f 95 d 82 f 2 c
translation-type: tm+mt
source-git-commit: d0bd48684764a60b488d1e39c968ad70c743f1db

---


# Fazer upload de regras de bot

Para as regras de bot de importação em massa, é possível fazer upload do arquivo CSV que define as regras.

Crie um arquivo CSV com as seguintes colunas, na ordem apresentada:

| Coluna 1 | Coluna 2 | Coluna 3 | Coluna 4 | Coluna 5 |
|--- |--- |---|---|---|
|  Nome do bot |  IP Início  |  IP Fim  | Agent Match Rule<br>(contains or starts with)</br> | Excluir agente<br>(limite de 255 caracteres)</br> |

É possível definir três tipos de regras de bot:

* O agente do usuário contém ou começa com
* Endereço IP único ou correspondência curinga
* Correspondência de intervalo de IP

Cada linha no arquivo de importação pode conter apenas uma das seguintes definições:

* **O agente do usuário contém ou começa com**: Forneça uma única sequência de agente do usuário para corresponder na coluna Incluir agente. Especifique o tipo de correspondência que deseja fazer colocando *contém* ou *começa com* no campo Regra de correspondência do agente. An optional value can be included in the Agent Exclude column that defines one or more pipe-delimited ( `|` ) strings that the Agent does not contain. As correspondências de string não distinguem maiúsculas de minúsculas. As colunas IP início e IP fim devem estar vazias.

* **Endereço IP único ou correspondência curinga**: Para corresponder a um único endereço IP ( `10.10.10.1`) ou endereço IP curinga ( `10.10.*.*`), coloque o mesmo valor nas colunas IP início e IP fim. Regra de correspondência, Incluir agente e Excluir agente devem estar vazios.

* **Correspondência de intervalo de IP**: Defina um intervalo de endereços IP usando as colunas IP início e IP fim. Wildcards can be used to match IP ranges, for example `10.10.10.*` to `10.10.20.*`. Regra de correspondência, Incluir agente e Excluir agente devem estar vazios.

## Vária regras combinadas com OU

Para encontrar um bot usando uma combinação de regras juntas a um OU (por exemplo, agente do usuário ou endereço IP), forneça um nome idêntico para todas as regras que deseja combinar no campo de nome do bot. Correspondências E não são suportadas.

## Substituir todas as regras com um arquivo de upload

Marque a caixa de seleção **[!UICONTROL Substituir todas as regras]para excluir todas as regras existentes e substituí-las pelas regras definidas no arquivo de upload.**

## Exportar regras

O botão **[!UICONTROL Exportar o arquivo de bot carregado]exporta todas as regras definidas na interface do usuário em um formato CSV.**
