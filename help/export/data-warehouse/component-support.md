---
title: Suporte a componentes no Data Warehouse
description: Saiba quais dimensões e métricas adicionais estão disponíveis no Data Warehouse e o que não é suportado.
translation-type: tm+mt
source-git-commit: 6bae6861586fc2aba33888cadfec3b1399898b90

---


# Suporte a componentes no Data Warehouse

A arquitetura de processamento exclusiva do Data Warehouse permite alguns componentes que normalmente não estão disponíveis em outros recursos do Adobe Analytics. Além disso, devido à sua arquitetura exclusiva, alguns componentes não estão disponíveis para uso em relatórios ou segmentos. Use esta página para entender o que pode ser usado e o que não pode ser usado.

## Componentes exclusivos para o Data Warehouse

Algumas dimensões e métricas podem ser usadas no Data Warehouse, e elas não estão disponíveis usando outros recursos no Adobe Analytics.

### Dimensões suportadas exclusivamente

* ID de visitante da Experience Cloud:
* IP:
* URL da página:
* IDs de Compra:
* ID do visitante: Fornece o identificador exclusivo para o visitante. Esse valor é igual ao valor concatenado de `visid_high``visid_low` colunas em feeds de dados. Consulte [Referência da coluna Dados](../analytics-data-feed/c-df-contents/datafeeds-reference.md) em Feeds de dados para obter mais informações.

### Métricas suportadas exclusivamente

* Visitas: Essa métrica no contexto do Data Warehouse exclui visitas de cookie não persistente.
* Visitas - Todos os visitantes: Essa métrica no contexto do Data Warehouse tem paridade mais próxima com a métrica de visitas em outras ferramentas do Adobe Analytics.

## Componentes não suportados no Data Warehouse

Algumas dimensões e métricas não são suportadas no Data Warehouse.

> [!IMPORTANT] Se uma dimensão ou métrica não for suportada no Data Warehouse, os segmentos que usam esses componentes também não são suportados. Sempre verifique a compatibilidade do produto ao criar ou editar um segmento.

### Dimensões não suportadas

* Algumas dimensões com base em tempo, incluindo:
   * AM/PM
   * Dia do mês
   * Dias da semana
   * Dia do ano
   * Hora do dia
   * Minuto
   * Mês do ano
   * Trimestre do ano
   * Dia da semana/Fim de semana
   * Ano
* Algumas dimensões baseadas em caminho, incluindo:
   * Todas as dimensões de Entrada, exceto Página de entrada
   * Todas as dimensões de Saída, exceto Página de saída e Link de saída
   * Profundidade de ocorrência
   * Frequência de Retorno
   * Tempo antes do evento
   * Tempo gasto na página - No intervalo
   * Tempo gasto por visita - Em bucket
   * Profundidade da Visita
* Toda a classificação da página de pesquisa
* Variáveis de hierarquia
* Tipo de ocorrência
* Páginas não encontradas (somente segmentos)
* Pesquisa paga
* Visitas únicas à página
* Motivo da desativação do rastreamento
* Estados dos Estados Unidos

### Métricas não suportadas

* Algumas métricas com base em caminho, incluindo:
   * Devoluções
   * Entradas
   * Saídas
   * Recargas
   * Único Acesso
   * Métricas de tempo gasto
