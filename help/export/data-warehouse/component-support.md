---
title: Suporte a componentes no Data Warehouse
description: Saiba quais dimensões e métricas adicionais estão disponíveis no Data Warehouse e o que não é suportado.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: ecd02a087e7ab344ccfbad1d5e1c30260577002c
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 59%

---

# Suporte a componentes no Data Warehouse

O processamento exclusivo na arquitetura do Data Warehouse permite que alguns componentes normalmente não estejam disponíveis em outros recursos do Adobe Analytics. Devido à sua arquitetura exclusiva, alguns componentes não estão disponíveis para uso em relatórios ou segmentos. Use esta página para entender o que pode ser usado e o que não pode ser usado.

## Componentes exclusivos do Data Warehouse

Algumas dimensões e métricas que podem ser usadas no Data Warehouse não estão disponíveis ao usar outros recursos no Adobe Analytics.

### Dimensões suportadas exclusivamente

* **ID de Experience Cloud**: para implementações que usam o Serviço de ID de Experience Cloud (ECID), um número de 128 bits que consiste em dois números concatenados de 64 bits preenchidos com 19 dígitos.
* **URL da página**: a URL da página em que a ocorrência ocorreu.
* **IDs de compra**: identificador exclusivo para uma compra, definido usando a variável purchaseID.
* **ID do Visitante**: fornece o identificador exclusivo do visitante. Esse valor é igual ao valor concatenado de `visid_high` e `visid_low` colunas em feeds de dados. Consulte Referência [da coluna](../analytics-data-feed/c-df-contents/datafeeds-reference.md) Dados em Feeds de dados para obter mais informações.

### Métricas suportadas exclusivamente

* **Visitas**: essa métrica no contexto da Data Warehouse exclui visitas de cookies não persistentes.
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
* Métricas de participação (conforme descrito em [Criar uma métrica de &quot;Participação&quot;](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md))

### Suporte a Dimension de uma maneira diferente

As seguintes dimensões baseadas em tempo são compatíveis. No entanto, a saída de datas não utiliza valores padrão ao usar essas dimensões. Especificamente, o ano é compensado por 1900, e os meses são baseados em zero.

* Ano
* Trimestre
* Mês
* Semana
* Dia
* Hora
* Minuto
