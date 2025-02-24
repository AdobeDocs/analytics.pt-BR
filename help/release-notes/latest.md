---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9fcf8871140e010d1c57c3af7004a45bd3a374a5
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 57%

---

# Notas de versão atuais do Adobe Analytics (versão de fevereiro de 2025)

**Última atualização**: 21 de fevereiro de 2024

Essas notas de versão abrangem o período de lançamento de 11 de fevereiro a meados de março de 2025. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Período de retenção da ID da transação** | O período de retenção da ID de transação de 90 dias foi estendido para 25 meses. A variável `transactionID` atribui uma identificação exclusiva a uma transação para que a ocorrência possa se vincular a dados enviados por meio de Fontes de dados. Saiba mais [aqui](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/transactionid) e [aqui](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/transactionid). |  | sexta-feira, 20 de fevereiro de 2025 |
| **Referência da API dos feeds de dados** | A [referência](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs) para a API de feeds de dados agora está disponível. |  | 30 de janeiro de 2025 |
| **API Livestream - Implementação de cliente** | Use a implementação do cliente Livestream para consumir dados Livestream. [Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) |  | quarta-feira, 18 de fevereiro de 2025 |
| **Atualização para a API de classificações** | Agora é possível remover campos de classificação ou chaves individuais do servidor. Isso oferece uma alternativa para excluir um conjunto de dados de classificação inteiro com o método DELETE. [Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/) |  | quarta-feira, 18 de fevereiro de 2025 |
| **Atualização para o campo de dados de contexto do Analytics`a.locale`** | Uma atualização agendada alterará a forma como o campo de dados de contexto do Analytics `a.locale` é definido ao coletar dados por meio do Experience Edge. Quando os dados são enviados para a Adobe Analytics usando a Experience Edge, os campos do Analytics são preenchidos com base em um mapeamento de campos XDM. O mapeamento para `c.a.locale` faz referência a um campo XDM não padrão, `xdm.environment.language`. Este campo será atualizado para fazer referência ao campo correto, `xdm.environment._dc.language`.  O mapeamento continuará fazendo referência a `xdm.environment.language` para compatibilidade com versões anteriores. Para continuidade, se ambos os campos forem definidos, `xdm.environment.language` terá prioridade. Você pode exibir a lista completa de mapeamentos do XDM para campos padrão do Analytics [aqui](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | quinta-feira, 5 de março de 2025 |


## Correções no Adobe Analytics

**Analysis Workspace**: AN-359974; AN-366212; AN-368460
**Classificações**: AN-367186; AN-367328; AN-368548
**Migração de componentes**: AN-364529; AN-366398; AN-367509;
**Feeds de dados**: AN-365685; AN-366745; AN-367256; AN-367349; AN-368363
**Data Warehouse**: AN-368178; AN-368331;
**Aplicativo móvel**: AN-367137
**Plataforma**: AN-351924; AN-365540; AN-365866; AN-366898; AN-367856; AN-367933
**Report Builder**: AN-366456; AN-366655;
**Conjuntos de relatórios virtuais**: AN-367411
**Regras VISTA**: AN-365331

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Clientes de fora do Campaign perderão o acesso aos acionadores** | 16 de outubro de 2023 | Em 30 de janeiro de 2025, os clientes do Adobe Analytics que não têm uma licença do Adobe Campaign perderão o acesso à capacidade de configurar e consumir [Triggers](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/services/triggers). Os clientes precisam comprar o Campaign, planejar o fim do uso dos acionadores ou procurar outras ferramentas da Adobe que ofereçam recursos de acionador. |

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 17 de janeiro de 2025 | Os clientes da API do Adobe Analytics e da transmissão ao vivo que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até **30 de junho de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fim da vida útil da API do Adobe Analytics (versão 1.4)** | 17 de julho de 2024 | Em **12 de agosto de 2026**, os serviços de API legados do Analytics abaixo chegarão ao fim de sua vida útil e serão encerrados, e as integrações atuais criadas com esses serviços deixarão de funcionar:<ul><li>API do Adobe Analytics (versão 1.4)</li><li>Autenticação WSSE do Adobe Analytics</li></ul><p>As integrações que usam a API do Adobe Analytics (versão 1.4) devem migrar para a [API 2.0 do Adobe Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/), enquanto as integrações do WSSE devem migrar para um protocolo de autenticação baseado em OAuth no [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte as [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obter respostas a perguntas comuns e mais orientações.</p> |


## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.26.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/appmeasurement-updates).


## Recursos relacionados

* [Notas de versão anteriores para 2024](/help/release-notes/2024.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recente para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
