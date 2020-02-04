---
description: Eventos bem-sucedidos são ações que podem ser rastreadas. Você determina o que é um evento bem-sucedido. Por exemplo, se um visitante comprar um item, o evento de compra pode ser considerado o evento bem-sucedido.
keywords: event
title: Visão geral dos eventos bem-sucedidos
topic: Admin tools
uuid: 410eee44-8960-462c-a9c3-07b44d0b1df0
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# Visão geral dos eventos bem-sucedidos

Eventos bem-sucedidos são ações que podem ser rastreadas. Você determina o que é um evento bem-sucedido. Por exemplo, se um visitante comprar um item, o evento de compra pode ser considerado o evento bem-sucedido.

Acesse a página Eventos de sucesso nas configurações do conjunto de relatórios:

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your AdobeID credentials.
2. Click the 9-grid button at the top, then click [!UICONTROL Analytics].
3. Navegue até [!UICONTROL Admin] > [!UICONTROL Conjuntos de relatórios]
4. Selecione o conjunto de relatórios desejado e navegue até [!UICONTROL Editar configurações] > [!UICONTROL Conversão] > Eventos [!UICONTROL de]sucesso.
5. Localize o evento desejado e modifique a lista suspensa Gravação [!UICONTROL de evento] único para [!UICONTROL Registrar uma vez por visita] ou [!UICONTROL Usar ID]de evento.

Há muitas formas de eventos de sucesso, dependendo do tipo de site da Web. Vários exemplos incluem:

* **Vendas**: exibição de produto, check-out, compra
* **Mídia**: assinatura, assinatura de concurso, exibição de página, exibição de vídeo
* **Finanças**: envio de aplicativo, logon, uso de ferramentas de autoatendimento
* **Viagem**: reserva (compra), campanha interna (click-through), busca (preços do itinerário)
* **Telecomunicações**: compra, clientes em potencial, uso de ferramentas de autoatendimento
* **Alta tecnologia**: download de white-paper, RFP, preenchimento de formulário, solicitações de suporte
* **Automotivo**: submissão de cliente em potencial, solicitação de cotação, download de panfleto

A variável [s.events](https://marketing.adobe.com/resources/help/en_US/sc/implement/events.html) define um evento bem-sucedido.

## Página Eventos bem-sucedidos - Descrições {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]**>**[!UICONTROL  Administrador]** > **[!UICONTROL Conjuntos de relatórios]**>**[!UICONTROL  Editar configurações]** > **[!UICONTROL Conversão]**>**[!UICONTROL  Eventos bem-sucedidos]**

A página Eventos bem-sucedidos permite configurar as variáveis Evento usadas no site. É possível adicionar até 1000 eventos bem-sucedidos. Os eventos 81-1000 funcionam somente no código H22 ou superior.

| Elemento | Descrição |
|--- |--- |
| Evento | O nome original do evento. |
| Nome | Dê nomes significativos aos eventos bem-sucedidos usados em seu site. Por exemplo, se event1 for usado para controlar registros, altere o nome aqui, de modo que event1 seja representado como a métrica &quot;Registros&quot; em todos os relatórios de Conversão. |
| Tipo | O Tipo selecionado determina se o evento é um evento de contador (padrão), numérico ou de moeda. Eventos numéricos e de moeda permitem incrementar métricas como mais de uma.  Os eventos de contador são usados para registrar um evento no tempo apropriado, enquanto eventos de moeda registram um número decimal, como imposto ou frete. O valor transmitido para eventos de moeda será convertido da moeda da página para a moeda de base do conjunto de relatórios mediante ao recebimento. Para obter mais detalhes sobre o uso de eventos de moeda, entre em contato com um representante da Adobe. Eventos numéricos são usados para relatar números que não são moeda, como o número de cupons usados em um pedido. Eventos de moeda são usados para acompanhar encargos de impostos e remessa. Eventos usados no tipo de Padrão de Fontes de dados devem ser eventos numéricos ou de moeda. |
| Polaridade | A polaridade da métrica permite indicar se o Adobe Analytics deve considerá-la boa ou ruim se um determinado evento personalizado (métrica) aumentar. Isso permitirá que o Adobe Analytics exiba indicadores direcionais (setas) para diversas métricas para adicionar contexto (por exemplo, comparações entre semanas). Exemplos: se &quot;Bugs enviados&quot; aumentar semana após semana, o Adobe Analytics deve considerar isso bom ou ruim? Um aumento nos Registros de email provavelmente é bom. Mas um aumento em Erros no envio do formulário provavelmente é ruim.  Na Analysis Workspace, a polaridade é aplicada: à formatação condicional da tabela de forma livre, às visualizações de alteração de resumo e ao esquema de cor positivo/negativo da visualização de mapa. |
| Descrição | Uma breve descrição do objetivo e utilização do evento. |
| Registro exclusivo de evento | **Registrar uma vez por visita**: Vincula o evento fornecido à sessão do visitante. As contagens subsequentes para um determinado evento na mesma visita são ignoradas. Esse tipo de serialização de eventos não requer alterações de implementação.<br>**Usar ID **de evento: Vincula o evento fornecido a uma ID personalizada. As contagens subsequentes para um determinado evento com a mesma ID de evento são ignoradas. Esse tipo de serialização de eventos requer uma ID personalizada em ocorrências para desduplicar valores. Consulte Serialização[da ID do](../../../implement/vars/page-vars/events/event-serialization.md)evento no guia Implementar usuário. |
| Participação | Consulte [Participação de métricas](/help/components/c-variables/c-metrics/metrics-participation.md). |
| Aviso (evento de moeda) | Ao alterar tipos de evento para ou partir de um evento de moeda, uma mensagem será exibida declarando que os dados históricos não estarão disponíveis no relatório.  Tipos de evento diferentes usam tabelas de dados separadas e não podem ser usados ao mesmo tempo. Alguns dados históricos podem ser restaurados se o usuário reverter o tipo de evento. Contudo, todos os dados coletados após a alteração inicial não estarão disponíveis. Tome cuidado ao alterar um tipo de evento. |

