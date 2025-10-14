---
description: Entenda como criar relatórios sobre o tráfego de chatbots de IA
title: Analisar tráfego de chatbots de IA
feature: Metrics, Data Configuration and Collection
source-git-commit: d16214865a037efe41b9f95682758daa577a12ed
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

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

A dimensão Tipo de referenciador inclui o [Item de dimensão de ferramentas da IA de conversa](/help/components/dimensions/referrer-type.md#conversational-ai-tools). Esse item de dimensão inclui uma lista predefinida de chatbots de IA.

Para obter mais informações, consulte [Tipo de referenciador](/help/components/dimensions/referrer-type.md).

### Analisar o tráfego de IA usando a detecção de bot

Você pode usar a detecção de bot no Analysis Workspace para analisar o tráfego de IA proveniente do pré-treinamento.

