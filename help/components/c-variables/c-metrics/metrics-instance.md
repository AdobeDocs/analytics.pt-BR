---
description: O número de vezes que um valor foi definido para uma variável.
keywords: instâncias
seo-description: O número de vezes que um valor foi definido para uma variável.
seo-title: Instâncias
solution: Analytics
title: Instâncias
topic: Métricas
uuid: fec 94 bdd-a 1 dc -4 cb 0-8983-ea 575 b 69589 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Instâncias

O número de vezes que um valor foi definido para uma variável.

As instâncias são contabilizadas por todos os tipos de ocorrência, mas não são contabilizadas quando um valor é gravado para uma variável ou uma ocorrência subsequente por motivos de persistência.

Por exemplo, se um usuário chegar em seu site pelo [!DNL example.com], a primeira solicitação de imagem em seu site conterá o referenciador de [!DNL example.com]. Quando esse valor é estabelecido, uma Instância é atribuída ao [!DNL example.com] mesmo que esse indicador seja gravado em todas as páginas visualizadas durante a visita.

As Instâncias para variáveis de conversão no data warehouse foram adicionadas em meados de 2011, permitindo que as solicitações do data warehouse lidassem com uma instância de variável de conversão específica como uma métrica. Essas métricas não estão disponíveis para relatório antes do tempo em que tiverem sido introduzidas.
