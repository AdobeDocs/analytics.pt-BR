---
title: Excluir dados no Adobe Analytics
description: Saiba mais sobre vários métodos de exclusão de dados antes e depois da coleta de dados.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Excluir dados no Adobe Analytics

A exclusão de dados é geralmente usada para impedir que os esforços de teste de sua organização preencham dados de produção, ou para impedir que dados indesejados aumentem falsamente os relatórios. Use qualquer um dos métodos a seguir para excluir dados da Adobe Analytics, dependendo do caso de uso.

## Excluir a coleta de dados pós-dados

Os métodos a seguir são maneiras de excluir dados no relatórios do Analytics depois que os servidores de coleta de dados do Adobe recebem solicitações de imagem. Os dados excluídos por meio desses métodos ainda contam para chamadas de servidor faturáveis.

* **Excluir por IP**: A Adobe Analytics oferece a funcionalidade básica para excluir dados de endereços IP ou intervalos em um conjunto de relatórios. Consulte [Excluir por IP](/help/admin/admin/exclude-ip.md) no guia do usuário administrativo.
* **Regras** do robô: As regras do robô recebem tráfego de sequências conhecidas do agente do usuário do robô e as excluem dos relatórios do Analytics. Os dados excluídos pelas regras do robô são colocados no relatório Bots. As regras do robô personalizadas podem ser criadas para excluir dados adicionais. See [Bot Rules](/help/admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
* **Regras** VISTA: Dependendo das necessidades de sua organização, as ocorrências que correspondem aos seus requisitos são enviadas para outro conjunto de relatórios dedicado ao recebimento de dados excluídos. Normalmente, as regras VISTA são usadas em relação aos endereços IP, mas não se limitam a eles. É possível usar qualquer dimensão para incluir ou excluir dados em conjuntos de relatórios. As regras VISTA estão sujeitas a custos adicionais; entre em contato com o gerente de conta de sua organização para obter detalhes.
* **Cookies** de não participação: Todos os visitantes do site podem opt out voluntariamente de ser rastreados no Adobe Analytics visitando uma página específica do servidor de rastreamento. Consulte [Implementar links](/help/implement/js/opt-out.md) de opção no guia do usuário Implementar.

>[!TIP]
>
>As regras de processamento não podem excluir dados ou enviar dados para outro conjunto de relatórios. No entanto, determinadas variáveis podem ser definidas condicionalmente e um segmento pode ser usado para excluir esses dados do relatórios.

## Excluir a coleta de dados pré-dados

Se desejar impedir que certas ocorrências cheguem aos servidores de coleta de dados do Analytics, use a [`abort`](/help/implement/vars/config-vars/abort.md) variável. Esse sinalizador impede que a solicitação de imagem seja enviada. As chamadas de servidor faturáveis não são aumentadas para solicitações de imagem abortadas, pois não chegam aos servidores de coleta de dados do Adobe.
