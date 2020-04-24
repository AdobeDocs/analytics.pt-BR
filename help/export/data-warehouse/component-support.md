---
title: Suporte a componentes no Data Warehouse
description: Saiba quais dimensões e métricas adicionais estão disponíveis no Data Warehouse e o que não é suportado.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Suporte a componentes no Data Warehouse

A arquitetura de processamento exclusiva do Data Warehouse permite que alguns componentes normalmente não estejam disponíveis em outros recursos do Adobe Analytics. Devido à sua arquitetura exclusiva, alguns componentes não estão disponíveis para uso em relatórios ou segmentos. Use esta página para entender o que pode ser usado e o que não pode ser usado.

## Componentes exclusivos do Data Warehouse

Algumas dimensões e métricas podem ser usadas no Data Warehouse, enquanto não estão disponíveis usando outros recursos no Adobe Analytics.

### Dimensões suportadas exclusivamente

* Experience Cloud ID: Para implementações que usam o Serviço da Experience Cloud ID (ECID), um número de 128 bits que consiste em dois números concatenados de 64 bits preenchidos com 19 dígitos.
* URL da página: O URL da página em que a ocorrência ocorreu.
* IDs de compra: Identificador exclusivo para uma compra, definido usando a variável purchaseID.
* ID do visitante: Fornece o identificador exclusivo do visitante. Esse valor é igual ao valor concatenado de `visid_high` e `visid_low` colunas em feeds de dados. Consulte Referência [da coluna](../analytics-data-feed/c-df-contents/datafeeds-reference.md) Dados em Feeds de dados para obter mais informações.

### Métricas suportadas exclusivamente

* Visitas: Essa métrica no contexto do Data Warehouse exclui visitas de cookies não persistentes.
* Visitas - Todos os visitantes: Essa métrica no contexto do Data Warehouse tem mais paridade com a métrica de visitas em outras ferramentas do Adobe Analytics.

## Componentes não compatíveis com o Data Warehouse

Algumas dimensões e métricas não são suportadas no Data Warehouse.

>[!NOTE] Se uma dimensão ou métrica não for suportada no Data Warehouse, os segmentos que usam esses componentes também não serão suportados. Sempre verifique a compatibilidade do produto ao criar ou editar um segmento.

### Dimensões não suportadas

* Algumas dimensões baseadas em tempo, incluindo:
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
* Algumas dimensões baseadas em definição de caminho, incluindo:
   * Todas as dimensões de entrada, exceto Página de entrada
   * Todas as dimensões de saída, exceto Página de saída e Link de saída
   * Profundidade de ocorrência
   * Frequência de Retorno
   * Tempo antes do evento
   * Tempo gasto na página - No intervalo
   * Tempo gasto por visita - Em bucket
   * Profundidade da Visita
* Toda a classificação da página de pesquisa
* Variáveis de hierarquia
* Tipo de ocorrência
* Páginas não encontradas (disponível como uma dimensão; não suportado para segmentação)
* Pesquisa paga
* Visitas únicas à página
* Motivo da desativação do rastreamento
* Estados dos Estados Unidos

### Métricas não suportadas

* Algumas métricas baseadas em definição de caminho, incluindo:
   * Devoluções
   * Entradas
   * Saídas
   * Recargas
   * Único Acesso
   * Métricas de ‘tempo gasto’
