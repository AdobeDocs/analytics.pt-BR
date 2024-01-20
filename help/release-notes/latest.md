---
title: Notas de versão atuais do Adobe Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 29%

---

# Notas de versão atuais do Adobe Analytics (janeiro de 2024)

**Última atualização:** quinta-feira, 10 de janeiro de 2024

Essas notas de versão abrangem o período de lançamento de janeiro de 2024 a 13 de fevereiro de 2024. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data Warehouse atualizações** | As seguintes melhorias na Data Warehouse estão disponíveis:<ul><li>Ao criar uma solicitação do Data Warehouse, os usuários agora podem disponibilizar solicitações para todos os usuários na organização, ativando o novo botão chamado [!UICONTROL **Disponibilizar para usuários em sua organização**].<p>Para obter mais informações, consulte [Configurações gerais da solicitação de Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md).</p></li><li>Ao criar ou gerenciar destinos de relatórios do Data Warehouse, os administradores do sistema agora podem mostrar contas e locais que foram criados por usuários na organização, ativando a opção chamada [!UICONTROL **Mostrar todos os destinos**].<p>Para obter mais informações, consulte [Configurar um destino de relatório para uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).</p></li> | N/D | quinta-feira, 10 de janeiro de 2024 |
| **Atualizações na visualização do Resumo das métricas principais** | Ao usar a visualização Resumo da métrica principal, o Intervalo de datas de comparação agora pode ser atualizado automaticamente, dependendo se a opção Intervalo de datas de comparação escolhida é relativa ao intervalo de datas principal ou fixa. [Saiba mais](/help/analyze/analysis-workspace/visualizations/key-metric.md). | N/D | quinta-feira, 17 de janeiro de 2024 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção dos seguintes problemas de Classificações: AN-314821; AN-326839; AN-332079; AN-332704; AN-332812; AN-332902; AN-332975; AN-333300; AN-333023; AN-333 3033; AN-333174; AN-333910; AN-334097; AN-334208; AN-334373; AN-334439; AN-334698; AN-334838; AN-334848; AN-333 4987; AN-335046; AN-335082; AN-335202; AN-335203; AN-335254; AN-335322; AN-335552; AN-335591; AN-335603; AN-335 5610; AN-335617; AN-335699; AN-335891; AN-335901; AN-336063; AN-336072; AN-336193; AN-336479; AN-336684; AN-333 6801; AN-337370; AN-337398
* Correção dos seguintes problemas do Construtor de regras de classificações: AN-332390; AN-332573; AN-332718; AN-332927; AN-333248; AN-333953; AN-334647; AN-334736; AN-334910; AN-33490 35642; AN-335683; AN-335811; AN-336033; AN-336569; AN-336852; AN-336875; AN-336902; AN-337190;
* Correção dos seguintes problemas do A4T: AN-334564; AN-336178;
* Correção dos seguintes problemas de Uso de chamadas do servidor: AN-332568; AN-333105; AN-333167; AN-333983; AN-334209; AN-334278
* Correção dos seguintes problemas de Data Warehouse: AN-333010; AN-333076; AN-330227; AN-331580; AN-333350; AN-334291; AN-334283; AN-334287; AN-334301; AN-333 4385; AN-334453; AN-334977; AN-335079; AN-335171; AN-335245; AN-335426; AN-335680; AN-335818; AN-336087; AN-333 7308;
* Correção dos seguintes problemas de Feeds de dados: AN-332241; AN-332366; AN-332617; AN-332654; AN-332702; AN-332723; AN-333014; AN-333166; AN-334037; AN-333 AN-334211; AN-334216; AN-334235; AN-334976; AN-335158; AN-335368; AN-335408; AN-335468; AN-335468; AN-335471; AN-333 AN-335596; AN-335662; AN-335733; AN-335883; AN-335894; AN-335968; AN-336098; AN-336192; AN-336243; AN-336243; AN-336977; AN-337117; AN-337219; AN-337262; AN-337393; AN-337462; AN-337854
* Correção dos seguintes problemas de Report Builder: AN-335246; AN-336311;
* Correção dos seguintes problemas do Analysis Workspace: AN-323760; AN-324191; AN-324913; AN-330126; AN-332808; AN-333168; AN-333382; AN-334839; AN-336040; AN-3337 043;

### Outras correções

AN-323975; AN-325383; AN-325809; AN-326787; AN-331611; AN-331818; AN-332124; AN-332272; AN-332911; AN-333070; AN-333302; AN-333377; AN-333904; AN-333928; AN-333968; AN-334056; AN-334099; AN-334191; AN-334207; AN-334776; AN-335206; AN-335294; AN-335320; AN-335394; AN-335443; AN-335967; AN-336099; AN-337452; AN-337463

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| Adições de membros de objetos da API Adobe | quinta-feira, 17 de janeiro de 2024 | O Adobe pode adicionar membros opcionais de solicitação e resposta (pares de nome/valor) a objetos de API existentes sem aviso prévio ou alterações no controle de versão. Essas adições devem ser alterações imperceptíveis para a implementação do. A Adobe recomenda que você consulte a documentação da API de qualquer ferramenta de terceiros que você integre às nossas APIs para que essas adições sejam ignoradas no processamento, se não forem entendidas. O Adobe não removerá parâmetros ou adicionará parâmetros necessários sem primeiro fornecer uma notificação padrão por meio das notas de versão. |
| `getPageLoadTime` plug-in obsoleto | quinta-feira, 10 de janeiro de 2024 | Este plug-in não é mais suportado. Seu código utiliza o método performance.timing, que (de acordo com o MDN) foi [obsoleto](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). O trabalho em um plug-in atualizado foi iniciado. |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Fim da vida útil do [!DNL Reports & Analytics]** | quinta-feira, 10 de janeiro de 2024 | Efetivo **17 de janeiro de 2024**, Adobe descontinuado [!DNL Reports & Analytics] e os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam [!DNL Reports & Analytics] não atende mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil.<p>Em 17 de janeiro de 2024, encerramos muitos dos recursos associados do Reports &amp; Analytics, incluindo, entre outros: Relatórios agendados, Extrações de dados e Relatórios DL. Após 17 de janeiro de 2024, os relatórios agendados não serão mais enviados. Além disso, não será mais possível agendar relatórios futuros a partir de 17 de janeiro de 2024. |
| **Fim da vida útil do recurso de [!UICONTROL Listas de publicação]** | quinta-feira, 10 de janeiro de 2024 | Como parte do fim da vida útil do Reports &amp; Analytics, [!UICONTROL Listas de publicação] chegou ao fim da vida útil em **17 de janeiro de 2024**. Não é mais possível criar novos ou acessar existentes [!UICONTROL Listas de publicação] para enviar ou agendar [!UICONTROL Analysis Workspace] projetos. |
| **Fim da vida útil do Data Workbench** | quarta-feira, 2 de janeiro de 2024 | Data Workbench Adobe em vigor até o fim da vida útil **31 de dezembro de 2023**. Consulte [Anúncio do fim da vida útil do Data Workbench](https://express.adobe.com/page/GSu6oKOD88GAj/) para obter detalhes. Entre em contato com o Gerente de conta da Adobe da sua organização se tiver dúvidas. |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.25.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2023](/help/release-notes/2023.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
