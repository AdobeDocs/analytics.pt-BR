---
title: Hierarquia
description: Uma dimensão personalizada que pode ser usada nos relatórios.
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 22%

---

# Hierarquia

>[!IMPORTANT]
>
>Essa dimensão foi removida e não é uma dimensão disponível no Analysis Workspace. A Adobe recomenda usar [eVars](evar.md) e classificações.

As hierarquias são variáveis personalizadas que podem ser usadas da maneira que você desejar. Elas não persistem além da ocorrência definida. Até 5 hierarquias estarão disponíveis se seu contrato com o Adobe permitir.

## Preencher hierarquias com dados

Cada hierarquia coleta dados da variável [`h1` - `h5` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. Por exemplo, a variável `h1` o parâmetro da sequência de consulta coleta dados para a Hierarquia 1, enquanto a variável `h4` o parâmetro da sequência de consulta coleta dados para a Hierarquia 4.

O AppMeasurement, que compila variáveis JavaScript em uma solicitação de imagem para coleta de dados, usa as variáveis `hier1` - `hier5`. Consulte [hier](/help/implement/vars/page-vars/hier.md) no guia Implementar usuário para obter diretrizes de implementação.

## Itens de dimensão

Como as hierarquias contêm strings personalizadas na implementação, sua organização determina quais itens de dimensão são para cada hierarquia. Registre a finalidade de cada hierarquia e os itens de dimensão típicos em uma [documento de design da solução](/help/implement/prepare/solution-design.md).
