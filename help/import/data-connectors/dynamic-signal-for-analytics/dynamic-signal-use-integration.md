---
description: 'null'
title: Uso da integração
uuid: c902a868-20a7-42df-8a79-8e154608f299
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Uso da integração{#using-the-integration}

Após a implantação, você pode começar a usar os recursos adicionais que essa integração oferece.

**Observação**: Pode levar de 24 a 48 horas para começar a ver alguns dos dados de Sinal dinâmico nos relatórios do Adobe Analytics.

As ações a seguir resultam em valor agregado dessa integração no Adobe Analytics.

## Exibindo métricas de tráfego e conversão por dimensões dinâmicas de sinal{#viewing-traffic-and-conversion-metrics-by-dynamic-signal-dimensions}

Exemplo de um relatório no Adobe Analytics.

Essa integração fornece novas dimensões que se tornam disponíveis como relatórios do Adobe Analytics. O relatório abaixo é um exemplo de análise de Visitas e uma métrica de conversão (Registros) que foram divididas por Título do artigo.

![](assets/examplereport.png)

## Segmentação por dimensões dinâmicas de sinal{#segmenting-by-dynamic-signal-dimensions}

Exemplos de segmentos com base nas dimensões do Sinal dinâmico.

Um recurso principal dessa integração é a capacidade de criar segmentos do Adobe Analytics com base nas dimensões de relatório integradas. Por exemplo, você pode criar um segmento que inclui somente Visitas originárias de uma Comunidade do VoiceStorm específica. Você pode chamar isso de "Visitas acionadas por SuperFãs". Essa definição de segmento pode parecer com o seguinte.

![](assets/segment1.png)

![](assets/segment2.png)

## Dimensões de relatório integradas{#integrated-reporting-dimensions}

Lista as dimensões de relatório de Sinal dinâmico incluídas nesta integração.

| Dimensão | Descrição |
|---|---|
| Tipo de Canal | A rede social (ou plataforma de blogagem) onde o usuário compartilhou uma postagem da comunidade. Os usuários podem compartilhar uma publicação em vários canais. Os cliques e outras atividades são segmentados por canal. Este campo exibe Facebook, Twitter etc. para que você possa ver qual Tipo de canal está direcionando a atividade. |
| ID do artigo | A ID do artigo identifica exclusivamente cada parte do conteúdo na comunidade de Sinal dinâmico. |
| Tipo de origem | Este campo indica se a publicação foi criada por um "Membro" ou "Marca". Observe que, em ambos os casos, o conteúdo pode ser criado manualmente no aplicativo ou importado de um feed externo. |
| Nome do Usuário | O usuário que compartilhou uma publicação em sua rede social, gerando click-throughs para o site. |
| ID de origem | A ID de origem identifica exclusivamente o criador (ou autor) da publicação compartilhada. Este é mais frequentemente um membro específico ou um feed externo. |
| ID de usuário | A ID de usuário identifica exclusivamente um usuário (ou seja, um membro) na comunidade de Sinal dinâmico. Nesse caso, o usuário é o compartilhador que compartilhou a publicação em sua rede social. |
| Nome da fonte | A fonte é o criador (ou autor) da publicação compartilhada. Na maioria dos casos, este é um membro da comunidade ou um feed externo. |
| Título do artigo | O título da postagem compartilhada que gerou os cliques de volta ao seu site. |
| Nome da comunidade | O nome da sua comunidade de Sinal dinâmico. |

