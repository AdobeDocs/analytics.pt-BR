---
title: Hierarquia
description: Uma dimensão personalizada que você pode usar nos relatórios.
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# Hierarquia

>[!IMPORTANT]
>
>Essa dimensão foi removida e não está disponível no Analysis Workspace. Em vez disso, a Adobe recomenda usar [eVars](evar.md) e classificações.

As hierarquias são variáveis personalizadas que podem ser usadas da maneira que você desejar. Elas não persistem além da ocorrência definida. Até 5 hierarquias estarão disponíveis se seu contrato com a Adobe permitir.

## Preencher hierarquias com dados

Cada hierarquia coleta dados da [`h1` - `h5` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. Por exemplo, o parâmetro da sequência de consulta `h1` coleta dados para Hierarquia 1, enquanto o parâmetro da sequência de consulta `h4` coleta dados para Hierarquia 4.

O AppMeasurement, que compila variáveis JavaScript em uma solicitação de imagem para coleta de dados, usa as variáveis `hier1` - `hier5`. Consulte [hier](/help/implement/vars/page-vars/hier.md) no guia de usuário Implementar para obter diretrizes de implementação.

## Itens de dimensão

Como as hierarquias contêm strings personalizadas na implementação, sua organização determina quais itens de dimensão são para cada hierarquia. Registre a finalidade de cada hierarquia e os itens de dimensão típicos em um [documento de design de solução](/help/implement/prepare/solution-design.md).