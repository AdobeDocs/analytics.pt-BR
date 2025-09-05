---
title: Suporte a componentes no Data Warehouse
description: Saiba quais dimensões e métricas adicionais estão disponíveis no Data Warehouse e o que não é suportado.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 45%

---

# Suporte a componentes no Data Warehouse

O processamento exclusivo na arquitetura do Data Warehouse permite que alguns componentes normalmente não estejam disponíveis em outros recursos do Adobe Analytics. Devido à sua arquitetura exclusiva, alguns componentes não estão disponíveis para uso em relatórios ou segmentos. Use esta página para entender o que pode ser usado e o que não pode ser usado.

## Componentes exclusivos do Data Warehouse

Algumas dimensões e métricas que podem ser usadas no Data Warehouse não estão disponíveis ao usar outros recursos no Adobe Analytics.

### Dimensões suportadas exclusivamente

* **Experience Cloud ID**: para implementações que usam o Experience Cloud ID Service (ECID), um número de 128 bits que consiste em dois números concatenados de 64 bits preenchidos com 19 dígitos.
* **URL da página**: a URL da página em que a ocorrência ocorreu.
* **IDs de compra**: identificador exclusivo para uma compra, definido usando a variável purchaseID.
* **ID do Visitante**: fornece o identificador exclusivo do visitante. Esse valor é igual ao valor concatenado de `visid_high` e `visid_low` colunas em feeds de dados. Consulte Referência [da coluna](../analytics-data-feed/c-df-contents/datafeeds-reference.md) Dados em Feeds de dados para obter mais informações.

### Métricas suportadas exclusivamente

* **Visitas**: essa métrica no contexto do Data Warehouse exclui visitas de cookies não persistentes.
* **Visitas - Todos os visitantes**: essa métrica no contexto do Data Warehouse tem mais paridade com a métrica de visitas em outras ferramentas do Adobe Analytics.

## Componentes não compatíveis com o Data Warehouse

Algumas dimensões e métricas não são suportadas no Data Warehouse.

>[!NOTE]
>
>Se uma dimensão ou métrica não for aceita no Data Warehouse, os segmentos que usam esses componentes também não serão aceitos. Sempre verifique a compatibilidade do produto ao criar ou editar um segmento.

### Dimensões não suportadas

* AM/PM
* Algumas dimensões baseadas em definição de caminho, incluindo:
   * Todas as dimensões de entrada, exceto Página de entrada
   * Todas as dimensões de saída, exceto Página de saída e Link de saída
   * Profundidade da ocorrência
   * Frequência de Retorno
   * Tempo antes do evento
   * Tempo gasto na página - Classificado
   * Tempo gasto por visita - Classificado
* Toda a classificação da página de pesquisa
* Variáveis de hierarquia
* Tipo de ocorrência
* Páginas não encontradas (disponível como uma dimensão; não suportado para segmentação)
* Pesquisa paga
* Visitas em única página
* Motivo da desativação do rastreamento
* Estados dos Estados Unidos

### Métricas não suportadas

* Algumas métricas baseadas em definição de caminho, incluindo:
   * Rejeições
   * Entradas
   * Saídas
   * Recargas
   * Acesso único
   * Métricas de ‘tempo gasto’
* Métricas de participação (conforme descrito em [Criar uma métrica de &quot;Participação&quot;](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md))

### Dimensões compatíveis de uma maneira diferente (formatação de data não padrão)

As seguintes dimensões baseadas em tempo são compatíveis:

* Ano
* Trimestre
* Mês
* Semana
* Dia
* Hora
* Minuto

No entanto, a saída de datas não é padrão ao usar essas dimensões.

Considere o seguinte ao calcular a saída de datas no Data Warehouse:

* As dimensões de data são mostradas no seguinte formato: `1YYMMDDHHMM`

* O ano (AA) é compensado por 1900. Isso significa que você adiciona `1900` aos três primeiros valores do campo de data.

  Por exemplo, se o valor do campo Semana do intervalo de datas no Data Warehouse for `1250901`, você adicionaria de 1900 a 125, o que resultará no ano de 2025.

* Todos os meses são baseados em zero, com janeiro sendo representado por 00, fevereiro por 01 e assim por diante, da seguinte forma:

   * 00: janeiro
   * 01: fevereiro
   * 02: março
   * 03: abril
   * 04: maio
   * 05: junho
   * 06: julho
   * 07: agosto
   * 08: setembro
   * 09: outubro
   * 10: novembro
   * 11: dezembro

  Por exemplo, se o valor do campo Semana do intervalo de datas no Data Warehouse for `1250901`, o mês será representado como 09, o que indica outubro.




## Segmentos como dimensões no Data Warehouse

Quando você usa um segmento como uma dimensão no Data Warehouse, o relatório retorna uma coluna que contém `"0"` ou `"1"`:

* **`"0"`**: o item de dimensão não atendeu aos critérios do segmento.
* **`"1"`**: o item de dimensão atendeu aos critérios do segmento.
