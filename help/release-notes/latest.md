---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: bb2b0f715941135d119d862b64c02f05800b3fdd
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 40%

---

# Notas de versão atuais do Adobe Analytics (fevereiro de 2024)

**Última atualização**: quinta-feira, 21 de fevereiro de 2024

Essas notas de versão abrangem o período de lançamento de 14 de fevereiro de 2024 a 11 de março de 2024. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Documentação da API do Data Warehouse** | Consulte a [API do Adobe Analytics Data Warehouse 2.0](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Warehouse%20APIs#/Data%20Warehouse%20Scheduled%20Requests%20API) para obter mais informações. Ir para [!UICONTROL Selecionar uma definição] e selecione [!UICONTROL APIs do Data Warehouse]. | | terça-feira, 19 de fevereiro de 2024 |
| **Activity Map para o SDK da Web sem custo extra** | Atualmente, os eventos de link de Activity Map são contados como seus próprios eventos e incorrem em custo extra. Esse aprimoramento pega alguns eventos de link e os empacota na próxima ocorrência, de modo semelhante a como os eventos são tratados pelo AppMeasurement. |  | quinta-feira, 6 de março de 2024 |
| **Aumento nos limites padrão de tráfego baixo** | Entrada **meados de abril de 2024**, o Adobe começará a aumentar os limites de tráfego baixo do conjunto de relatórios padrão da seguinte maneira: ![limites de tráfego baixo](assets/thresholds.png) Isso afetará somente as variáveis que estão definidas abaixo dos novos limites. Essas alterações serão feitas de forma incremental, e esperamos que o trabalho seja concluído pela **fim de maio**. À medida que esses aumentos forem implementados, você poderá notar alterações nas variáveis de alta cardinalidade:<ul><li>Mais valores de dimensão podem estar disponíveis para relatórios.</li><li>Segmentos e métricas calculadas podem incluir mais dados.</li><li>Os conjuntos de relatórios virtuais baseados em segmentos podem incluir mais dados.</li><li>As exportações de classificação podem incluir mais dados.</li></ul> | Meados de abril de 2024 | Final de maio de 2024 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção dos seguintes problemas de Classificações: AN-319515; AN-337559; AN-338149; AN-338702; AN-338769; AN-338891; AN-339327; AN-339649; AN-339668; AN-3395 9669; AN-339776; AN-339822; AN-340017; AN-340202; AN-340476;
* Correção dos seguintes problemas do Construtor de regras de classificação: AN-338385; AN-338399; AN-338592; AN-338810; AN-338893; AN-339431; AN-339894; AN-339933; AN-340201; AN-3 40309;
* Correção dos seguintes problemas do A4T: AN-334830; AN-336194; AN-338309; AN-338650;
* Correção do seguinte problema de coleta de dados: AN-339323
* Correção dos seguintes problemas de Data Warehouse: AN-335542; AN-331425; AN-337215; AN-338445; AN-338643; AN-338651; AN-339461; AN-340066; AN-340207; AN-340 0460
* Correção dos seguintes problemas de Feeds de dados: AN-335952; AN-338653; AN-339508; AN-339681; AN-340418
* Correção dos seguintes problemas das Fontes de dados: AN-338648
* Correção dos seguintes problemas do Analysis Workspace: AN-326509; AN-336186; AN-336190; AN-336309; AN-337922; AN-338094; AN-338323; AN-338556; AN-339600; AN-340 445

### Outras correções do Analytics

AN-328239; AN-332908; AN-335449; AN-335517; AN-336075; AN-336100; AN-336128; AN-338088; AN-338270; AN-338393; AN-338494; AN-339326; AN-339742; AN-339883; AN-340419;

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| Adições de membros a objetos da API da Adobe | 17 de janeiro de 2024 | O Adobe pode adicionar membros opcionais de solicitação e resposta (pares de nome/valor) a objetos de API existentes a qualquer momento e sem aviso prévio ou alterações no controle de versão. A Adobe recomenda que você consulte a documentação da API de qualquer ferramenta de terceiros que você integre às nossas APIs para que essas adições sejam ignoradas no processamento, se não forem entendidas. Se implementadas corretamente, essas adições são alterações ininterruptas na implementação. A Adobe não removerá parâmetros nem adicionará parâmetros obrigatórios sem primeiro fornecer uma notificação padrão por meio de notas de versão. |
| `getPageLoadTime` plug-in obsoleto | 10 de janeiro de 2024 | Não há mais suporte para este plugin. Seu código utiliza o método performance.timing, que (de acordo com o MDN) foi [descontinuado](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Foi iniciado o trabalho em um plug-in atualizado. |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.25.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2023](/help/release-notes/2023.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
