---
title: Depurar a coleta de dados do Analytics
description: Confirme se o Adobe Analytics recebe os dados esperados do AppMeasurement, da extensão do Analytics, do Web SDK, do Mobile SDK e da API de inserção de dados.
keywords: depuração, validação, analisador de pacotes, monitor de pacotes, /b/ss/, Edge Trace, Assurance, hitdebugger, conjunto de relatórios
feature: Implementation Basics
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 049b9b7447c7f91d67eb58fc781898b685bd9d91
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 2%
---
# Depurar a coleta de dados do Analytics

Este artigo explica o que verificar quando você depura os dados enviados para o Adobe Analytics. Encontre seu método de implementação na tabela a seguir e siga sua seção. Se você estiver investigando dados de relatório inesperados, comece com [Comparar solicitações com relatórios](#reports).

Para obter as etapas e ferramentas que se aplicam a toda a coleta de dados do Adobe, como capturar solicitações de rede, habilitar o log de depuração e investigar solicitações canceladas, consulte [Depuração e solução de problemas da coleta de dados](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/overview).

| Método de implementação | Onde ver os dados que o Analytics recebe | Orientação |
| --- | --- | --- |
| AppMeasurement ou a extensão de tag do Analytics | Solicitações do navegador diretamente para os servidores de coleta de dados do Analytics | [AppMeasurement](#appmeasurement) |
| SDK da web | Edge Trace, depois que o Edge Network converte o evento em uma ocorrência do Analytics | [Web SDK](#web-sdk) |
| SDK móvel | A visualização Eventos do Analytics no Assurance. Se você usa a extensão Edge Network ou Edge Bridge, ative a **[!UICONTROL Exibição do Analytics Edge]**. | [exibição de Eventos do Adobe Analytics no Assurance](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/adobe-analytics) |
| API de inserção de dados | As solicitações de saída do seu servidor e suas respostas | [Solucionar problemas de solicitações da API de inserção de dados](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting) |

## AppMeasurement e a extensão do Analytics {#appmeasurement}

### Localizar a solicitação {#appmeasurement-find}

[Capturar solicitações de rede](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#web) e filtrar por `/b/ss/`. Os depuradores de tag, como o Adobe Experience Platform Debugger, identificam e decodificam essas solicitações para você.

Se nenhuma solicitação `/b/ss/` aparecer:

* Verifique se há erros de JavaScript no console do navegador.
* Se você usar a extensão de tag do Analytics, confirme se o código de inserção de tag está dentro do elemento `<head>` da página e se sua biblioteca foi publicada no ambiente que você está testando. [Modo de depuração da marca](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/logging) mostra se a regra que envia a ocorrência foi acionada.
* Se você hospeda o AppMeasurement, abra o URL da biblioteca diretamente para confirmar se o arquivo é carregado e contém o código.
* Desative as extensões do navegador, como bloqueadores de anúncios, que podem impedir o envio de solicitações.
* O depurador não reconhece solicitações enviadas de um iframe. Em vez disso, use as ferramentas de desenvolvedor do navegador. Consulte [Usar AppMeasurement com iFrames](../use-cases/iframe.md).

### Verificar o que o Analytics recebeu {#appmeasurement-contents}

* **Conjuntos de relatórios**: o segmento de caminho após `/b/ss/` lista as IDs de conjunto de relatórios que recebem a ocorrência. Confirme se eles são os conjuntos de relatórios esperados, como um conjunto de relatórios de desenvolvimento em páginas de desenvolvimento.
* **Variáveis**: solicitações brutas usam nomes de parâmetros de consulta em vez de nomes de variáveis; por exemplo, eVar1 aparece como `v1` e prop1 como `c1`. Consulte a [referência da variável](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference). Quando uma solicitação é muito longa, o AppMeasurement a envia com HTTP `POST`, para que as variáveis apareçam no corpo da solicitação em vez da URL.
* **Tipo de ocorrência**: as solicitações enviadas por [`tl()`](../vars/functions/tl-method.md) incluem o parâmetro `pe` e não incrementam as exibições de página. As solicitações enviadas por [`t()`](../vars/functions/t-method.md) não incluem `pe`.

Se os valores estiverem presentes, mas estiverem errados, consulte [Solução de problemas de implementação do JavaScript](../js/troubleshooting.md) para causas comuns, como aspas, maiúsculas e minúsculas e espaço em branco.

### Verifique a resposta {#appmeasurement-response}

Uma resposta de `2xx` confirma apenas que o servidor de coleta de dados recebeu a solicitação, não que a ocorrência foi registrada. Com o tipo de resposta padrão, uma solicitação pode retornar sucesso mesmo quando a ocorrência é descartada. Espera-se uma resposta de `302` na primeira solicitação de um novo visitante. Consulte [códigos de resposta HTTP](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes).

O AppMeasurement envia solicitações de link de saída e todas as solicitações quando [`useBeacon`](../vars/config-vars/usebeacon.md) está habilitado, com `navigator.sendBeacon()`. As ferramentas do desenvolvedor podem rotular essas solicitações como canceladas mesmo quando enviadas pelo navegador. Consulte [Solicitações canceladas](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#aborted-requests).

## SDK da web {#web-sdk}

### Localizar a solicitação {#web-sdk-find}

Com o Web SDK, o navegador envia eventos para a Edge Network em vez de diretamente para o Analytics, para que você não veja uma solicitação `/b/ss/`. [Inspecione a solicitação do Edge Network](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#edge-network-requests) e confirme o seguinte:

* O parâmetro `configId` corresponde a uma sequência de dados que tem o [serviço Adobe Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure#analytics) habilitado com os conjuntos de relatórios esperados.
* A carga é qualificada como uma exibição de página ou um evento de link. O Analytics ignora cargas que não contêm detalhes de página nem um tipo de interação com a Web. Consulte [tipos de evento do Edge Network no Adobe Analytics](../aep-edge/hit-types.md).

### Verificar o que o Analytics recebeu {#web-sdk-contents}

Inicie um [Edge Trace](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/edge-trace) e reproduza a ação. Localize a linha que começa com **[!UICONTROL Mapeamento Automático do Analytics]** e expanda `mappedQueryParams` e a ID do conjunto de relatórios abaixo dela.

* **Variáveis**: os valores mapeados usam os mesmos nomes de parâmetro de consulta que as solicitações do AppMeasurement, às vezes em forma abreviada, como `gn` para nome de página e `pl` para produtos. Consulte [mapeamento de campo de objeto XDM](../aep-edge/xdm-var-mapping.md) e [mapeamento de campo de objeto de dados](../aep-edge/data-var-mapping.md).
* **Dados de contexto**: os campos XDM que não são mapeados para uma variável do Analytics aparecem como dados de contexto com o prefixo `c.a.x.`. Use [regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) para atribuí-las a variáveis.
* **Conjuntos de relatórios**: se você usar substituições de conjuntos de relatórios, a linha de configuração da sequência de dados no Edge Trace mostrará os conjuntos de relatórios que a Edge Network usou.

### Verificar processamento {#web-sdk-processing}

Na sessão do Assurance aberta pelo Edge Trace, pesquise eventos para `hitdebugger`. Esses eventos usam o fornecedor `com.adobe.analytics.hitdebugger` e suas cargas mostram valores após o processamento do Analytics, como Experience Cloud ID (`mcvisId`) e `pageName`.

Para obter uma apresentação guiada, consulte [Configurar o Adobe Analytics com o Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/pt-br/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics).

## Comparar solicitações com relatórios {#reports}

Uma ocorrência que atinge o Analytics não é exibida nos relatórios imediatamente e os valores relatados podem diferir dos valores na solicitação:

* **Latência**: dados concluídos normalmente aparecem em relatórios cerca de duas horas após a coleta. Alguns dados, como ocorrências com carimbo de data e hora, podem levar mais tempo. Consulte [Disponibilidade e latência de dados](/help/technotes/latency.md).
* **Processando**: regras de processamento, regras VISTA, regras de bot e outras etapas de processamento podem alterar ou excluir valores após a coleção. Consulte [Ordem de processamento dos dados no Adobe Analytics](/help/technotes/processing-order.md). Os dados pós-processados do Assurance mostram o resultado do processamento de uma ocorrência individual.
* **Conjunto de relatórios**: confirme se você está visualizando o mesmo conjunto de relatórios ao qual a solicitação ou a sequência de dados se destina.
* **Valores inesperados**: se uma dimensão mostrar picos ou valores inesperados, consulte [Colisões de hash](hash-collisions.md).

Para alterações de tráfego mais amplas, consulte [Solução de problemas de picos e quedas nos dados](/help/technotes/event/spikes-drops.md).
