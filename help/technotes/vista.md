---
title: Regras VISTA no Adobe Analytics
description: Saiba mais sobre as regras VISTA e seus recursos.
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 81%

---

# Regras VISTA no Adobe Analytics

As regras VISTA são uma forma alternativa de modificação de dados personalizados que podem ser aplicadas entre a coleção e o processamento de dados. Consulte [Ordem de processamento](processing-order.md) para obter mais informações sobre o estágio exato no pipeline de dados ao qual as regras VISTA se aplicam. As regras VISTA afetam apenas os dados atuais à medida em que são coletados; não altera os dados existentes.

Alguns casos de uso comuns de regras VISTA incluem:

* Copie uma ocorrência do Analytics de um conjunto de relatórios para outro, alterando, opcionalmente, os dados para o conjunto de relatórios copiado
* Exclusão de IP personalizado que excede os casos de uso oferecidos por [Excluir por IP](/help/admin/admin/exclude-ip.md)
* Modificar de forma condicional ou global qualquer valor de variável
* Duplicação de valores de variável para outras variáveis
* Faça upload de arquivos para um site Adobe FTP que possa afetar os valores das variáveis

Muitos casos de uso para regras VISTA já são oferecidos por [Regras de processamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md), [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), [Conjuntos de relatórios virtuais](/help/components/vrs/vrs-about.md) ou simplesmente atualizando a implementação do Adobe Analytics. A Adobe recomenda as regras VISTA somente como último recurso.

>[!IMPORTANT]
>
>As regras VISTA exigem um contrato pago entre sua organização e a Adobe Professional Services. Entre em contato com a equipe de conta da Adobe se desejar criar ou atualizar uma regra VISTA.

## Criar uma regra VISTA {#create}

Você deve trabalhar com o Adobe Professional Services para criar uma regra VISTA. Entre em contato com a equipe de conta da Adobe se desejar criar uma regra VISTA.

## Consulte as regras VISTA existentes {#see}

A Adobe não oferece uma interface para visualizar as regras VISTA existentes. Entre em contato com a equipe de conta da Adobe ou com o Atendimento ao cliente com o conjunto de relatórios desejado para recuperar uma lista de regras VISTA existentes.
