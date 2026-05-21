---
description: Entenda como criar relatórios sobre o tráfego de chatbots de IA
title: Analisar tráfego de chatbots de IA
feature: Metrics, Data Configuration and Collection
exl-id: 0b013b7d-02a2-405d-bdd6-c991f0baac8e
TQID: https://experienceleague.adobe.com/lyzSP-7iZ8Y5XiTG1t7Axsg1f5AJf6BbcZbu7MmkwWU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: b7156124-d291-4de4-ac0c-ed17d8078449
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 643
ht-degree: 2%

---

# Analisar o tráfego de ferramentas de IA conversacional

O Adobe Analytics fornece ferramentas para analisar o tráfego de IA no seu site.

Ao analisar o tráfego de IA, primeiro é necessário compreender os tipos de tráfego de IA que podem ocorrer e quais tipos geram ocorrências. Em seguida, é possível analisar o tráfego no Analysis Workspace.

## Entender o tráfego de IA

### Entender os tipos de tráfego de IA

O tráfego de IA em seu site pode ocorrer em qualquer uma das seguintes circunstâncias:

* **Durante o pré-treinamento**: ocorre com pouca frequência, quando o conteúdo do seu site é raspado e assimilado nos dados de treinamento de IA.

* **Ao responder a solicitações sob demanda**: ocorre no momento em que o usuário solicita uma pergunta à IA e a chatbot de IA responde. O chatbot de IA realiza uma pesquisa na Web e o conteúdo do site é incluído na resposta. (Esse tipo de interações às vezes é chamado de Geração aumentada de recuperação (RAG).)

  Algumas respostas do chatbot de IA incluem links para o material de origem no site e algumas não incluem.

* **Ao executar fluxos de trabalho de agente**: ocorre sempre que um agente de IA visita seu site ao clicar em uma série de páginas da Web em um navegador para responder a uma solicitação do usuário. Nesse caso, a IA está agindo como um agente para o usuário que fez a solicitação.

### Entenda quando as ocorrências são geradas para o tráfego de IA

Uma ocorrência é gerada em uma página da Web quando o JavaScript é executado na página. Dependendo do tipo de tráfego de IA que está ocorrendo no site, o JavaScript pode ou não ser executado.

| Tipo de tráfego de IA | Gera ocorrências | Considerações |
|---------|----------|---------|
| **Pré-treinamento** | Sim | As ocorrências são geradas durante o pré-treinamento quando o conteúdo do site é assimilado na IA. No entanto, o pré-treinamento ocorre com pouca frequência, e o conteúdo incluído no pré-treinamento de uma IA pode ser reutilizado várias vezes em respostas futuras, sem gerar mais acessos no site. <p>Em outras palavras, uma única ocorrência que ocorre durante o pré-treinamento de uma IA pode ser reutilizada várias vezes para várias respostas sob demanda sem gerar ocorrências adicionais em seu site.</p><p>Para obter informações sobre como analisar esse tipo de tráfego de IA no Analysis Workspace, consulte [Analisar o tráfego de IA usando a detecção de bot](#analyze-ai-traffic-using-bot-detection).</p> |
| **Solicitações sob demanda** | Não | A resposta da IA não gera ocorrências porque a resposta usa uma combinação de:<ul><li>Dados pré-treinados <br/>As informações já estão incluídas no conhecimento pré-treinado da IA, portanto, a IA não executa o JavaScript em páginas.</li><li>Pesquisa na Web sob demanda <br/>Busca somente o HTML bruto da página da Web durante a pesquisa na Web, de modo que a IA não execute o JavaScript nas páginas.</li></ul> |
| **links de material do Source em respostas da IA** | Sim | As ocorrências são geradas quando um usuário clica no link para o material de origem que está incluído na resposta da IA. Uma ocorrência não é gerada se um link for incluído na resposta e o link não for clicado pelo usuário. <p>Algumas respostas de chatbot de IA incluem links para o material de origem e algumas não. </p><p>Para obter informações sobre como analisar esse tipo de tráfego de IA no Analysis Workspace, consulte [Analisar tráfego de IA por tipo de Referenciador](#analyze-ai-traffic-by-referrer-type).</p> |
| **Fluxos de trabalho de agente** | Sim | As ocorrências são geradas em cada página à medida que o agente de IA clica no fluxo de trabalho em nome do usuário. <p>Para obter informações sobre como analisar esse tipo de tráfego de IA no Analysis Workspace, consulte [Analisar tráfego de IA por tipo de Referenciador](#analyze-ai-traffic-by-referrer-type).</p> |

## Analisar o tráfego de IA no Analysis Workspace

### Analisar o tráfego da IA por tipo de referenciador

Você pode usar a dimensão Tipo de referenciador no Analysis Workspace para analisar os seguintes tipos de tráfego de IA:

* Links de material do Source em respostas de IA

* Fluxos de trabalho de agente

A dimensão Tipo de referenciador inclui o [Item de dimensão de ferramentas da IA de conversa](/help/components/dimensions/referrer-type.md#conversational-ai-tools). Este item de dimensão inclui uma lista predefinida de chatbots de IA.

Para obter mais informações, consulte [Tipo de referenciador](/help/components/dimensions/referrer-type.md).

### Analisar o tráfego de IA usando a detecção de bot

Você pode usar a detecção de bot no Analysis Workspace para analisar o tráfego de IA proveniente do pré-treinamento.
