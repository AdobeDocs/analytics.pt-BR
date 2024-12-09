---
description: Saiba mais sobre o Data Warehouse e como filtrar os dados, permitindo criar e executar relatórios personalizados.
title: Visão geral do Data Warehouse
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 79%

---

# Visão geral do Data Warehouse

O data warehouse permite copiar dados do Adobe Analytics para armazenamento e criação de relatórios personalizados, que podem ser executados filtrando os dados.

## Visão geral dos relatórios

Os relatórios do data warehouse podem exibir relações avançadas de dados provenientes de dados brutos com base em suas perguntas exclusivas. Eles podem incluir um número ilimitado de linhas em uma única solicitação (para relatórios individuais, programados e baixados).

>[!NOTE]
>
>O Data Warehouse informa o primeiro valor encontrado no período do relatório.

>[!IMPORTANT]
>
>Ao segmentar em valores classificados, a Analysis Workspace e o Data Warehouse tratam valores “não especificados” de maneira diferente. “Não especificado” na Analysis Workspace refere-se a valores que não estão classificados, enquanto “Não especificado” no Data Warehouse refere-se a valores que você classificou como “Não especificado”.

## Visão geral da entrega

Os relatórios do data warehouse são enviados por email ou para um provedor de armazenamento na nuvem e podem levar até 72 horas para serem processados. O tempo de processamento depende da complexidade da consulta e da quantidade de dados solicitada.

O Data Warehouse compacta automaticamente todos os arquivos com mais de 1 MB. O tamanho máximo para o anexo de email é de 10 MB.

## Acesso

A Adobe habilita o data warehouse somente para usuários com nível de admin e para conjuntos de relatórios específicos. (Pode ser ativado para conjuntos de relatórios globais e secundários, mas não para conjuntos de relatórios de rollup.) O administrador pode criar um grupo que tenha acesso ao Data Warehouse e, em seguida, associar usuários de nível não administrador a esse grupo.

Consulte [Gerenciar permissões do data warehouse](/help/export/data-warehouse/t-dw-group.md).

## Criar uma solicitação do data warehouse

Para obter informações sobre como criar uma solicitação do data warehouse, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

## Gerenciar solicitações do data warehouse

Para obter informações sobre como gerenciar solicitações do data warehouse, consulte [Gerenciar solicitações do data warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

