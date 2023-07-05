---
title: Dicas do cliente
description: Saiba como as dicas do cliente substituirão gradualmente o usuário-agente como a fonte de informações do dispositivo.
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
feature: Data Configuration and Collection
source-git-commit: c697530103ea7cd279cc3560c1daec796759e7a1
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 87%

---

# Visão geral e perguntas frequentes sobre dicas do cliente

As dicas do cliente são informações individuais sobre o dispositivo de um usuário. Elas são fornecidas por navegadores Chromium, como o Google Chrome e Microsoft Edge. Nesses navegadores, as dicas do cliente substituirão gradualmente o usuário-agente como a fonte de informações do dispositivo. O Adobe Analytics atualizará seu processo de pesquisa de dispositivo para usar dicas do cliente além do usuário-agente para determinar as informações do dispositivo.

## Dicas de cliente de baixa entropia e alta entropia

O Google divide as dicas do cliente de usuário-agente em duas categorias: dicas de baixa entropia e alta entropia.

* **Dicas de baixa entropia** contém informações mais genéricas sobre dispositivos. Essas dicas são fornecidas automaticamente pelos navegadores Chromium.

* As dicas de **alta entropia** contêm informações mais detalhadas. Essas dicas estão disponíveis somente mediante solicitação. O AppMeasurement e o SDK da Web podem ser configurados para solicitar dicas de alta entropia. Por padrão, ambas as bibliotecas **não** solicitam dicas de alta entropia.

A partir de outubro de 2022, novas versões dos navegadores Chromium iniciaram o “congelamento” da versão do sistema operacional representada na string do usuário-agente. A versão do sistema operacional é uma dica de alta entropia, portanto, para manter a precisão da versão do sistema operacional em seus relatórios, é necessário configurar a biblioteca de coleção para coletar essas dicas de alta entropia. Com o tempo, outras informações do dispositivo do usuário-agente serão congeladas, o que exigirá que as dicas do cliente mantenham a precisão do relatório do dispositivo.

As dicas do cliente serão incorporadas ao processo de pesquisa de dispositivo do Analytics a partir de 27 de fevereiro de 2023 e concluídas em 2 de março de 2023. Atualmente, o AppMeasurement e o SDK da Web são compatíveis com a coleção de dados de dicas, mas esta não será usada na pesquisa de dispositivo até meados de fevereiro. Conforme observado abaixo, a versão do sistema operacional foi congelada a partir de outubro, mas devido a um lançamento gradual e ao fato de muitos agentes de usuário já fornecerem uma versão do sistema operacional congelada (veja mais [aqui](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=pt-BR)), estimamos que isso afetará &lt;3% dos visitantes do Chrome.

>[!NOTE]
>
> Desde janeiro de 2023, algumas versões dos sistemas operacionais Mac e Windows são representadas incorretamente no agente do usuário, mas corretamente representadas em dicas de cliente de alta entropia. Consulte [Sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=pt-BR) para obter mais informações.

O Adobe Audience Manager requer que dicas de alta entropia sejam coletadas para preservar a funcionalidade completa. Se você estiver usando [encaminhamento pelo lado do servidor para o Adobe Audience Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=pt-BR) em seguida, talvez você queira ativar a coleção de dicas de alta entropia.

## Perguntas frequentes

+++**Onde posso obter mais informações sobre dicas do cliente?**

Esta [publicação do blog do Google](https://web.dev/user-agent-client-hints/) é uma boa referência e um bom ponto de partida.

+++

+++**Como habilitar a coleção de dicas do cliente?**

As dicas de baixa entropia são fornecidas automaticamente pelo navegador e assimiladas para a obtenção de informações do dispositivo e do navegador. As versões mais recentes do SDK da Web (começando com a 2.12.0) e do AppMeasurement (começando com a 2.23.0) podem ser configuradas para coletar dicas de alta entropia por meio de suas respectivas extensões de Tags ou diretamente por meio de uma opção de configuração. Consulte as instruções para o [SDK da Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=pt-BR#enabling-high-entropy-client-hints) e o [AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html?lang=pt-BR).

Para ambas as bibliotecas, a coleção de dicas de alta entropia é **desativada por padrão**.

Para dados enviados por API, como a [API de inserção de dados](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) ou a [API de inserção de dados em massa](https://experienceleague.adobe.com/docs/analytics/import/bulk-data-insert.html?lang=pt-BR), as dicas devem ser incluídas explicitamente na carga. Consulte a documentação respectiva para obter mais detalhes.

+++

+++**Posso escolher quais dicas de alta entropia quero coletar?**

Não neste momento. Você pode optar por coletar todas as dicas de alta entropia ou nenhuma.

Observe que fullVersionList não está coletado no momento porque a versão principal do navegador é capturada como uma dica de baixa entropia.

+++

+++**Quais são os vários valores de dicas do cliente?**

A tabela abaixo descreve as dicas do cliente a partir de outubro de 2022.

| Dica | Descrição | Alta ou baixa entropia | Exemplo |
| --- | --- | --- | --- | 
| Sec-CH-UA | Navegador e versão significativa | Baixa | `"Google Chrome 84"` |
| Sec-CH-UA-Mobile | Dispositivo móvel (verdadeiro ou falso) | Baixa | `true` |
| Sec-CH-UA-Platform | Sistema operacional/plataforma | Baixa | `"Android"` |
| arquitetura | Arquitetura do site | Alta | `"arm"` |
| bitness | Bitness da arquitetura | Alta | `"64"` |
| fullVersionList | Lista de marcas com suas versões | Alta | `"Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"` |
| model | Modelo do dispositivo | Alta | `"Pixel 3"` |
| platformVersion | Versão do sistema operacional/plataforma | Alta | `"10"` |

* As dicas de baixa entropia são coletadas por meio do cabeçalho da solicitação.
* As dicas de alta entropia são coletadas por meio de JavaScript e transmitidas pelos valores de parâmetro da string de consulta. Os parâmetros da string de consulta usam `h.` como um prefixo na solicitação de imagem. Observe que fullVersionList não está coletado no momento porque a versão principal do navegador é capturada como uma dica de baixa entropia.

Dicas de alta entropia são coletadas por meio da chamada do JavaScript e transmitidas pelo parâmetro de consulta

+++

+++**Haverá alterações nos relatórios de dispositivos no Analytics?**

Os campos de dispositivo disponíveis para relatório não serão alterados. Os dados capturados para esses campos podem mudar, dependendo de qual campo e como você configurou a coleção de dicas do cliente.

+++

+++**Quais campos de relatórios do Analytics são obtidos do usuário-agente?**

Esses campos são obtidos diretamente do usuário-agente, mas o usuário-agente pode ser usado para ajudar a obter valores para outros campos relacionados ao dispositivo, dependendo dos detalhes do dispositivo.

* [Navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=pt-BR)
* [Tipo de navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=pt-BR)
* [Sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=pt-BR)
* [Tipos de sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=pt-BR)
* [Dispositivo móvel e tipo de dispositivo móvel](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=pt-BR)

+++

+++**Que partes do usuário-agente estão sendo “congeladas” e quando?**

Consulte a [linha do tempo publicada pelo Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Esta situação pode estar sujeita a alterações.

+++

+++**De que maneiras o Analytics depende do Agente do usuário?**

As informações do dispositivo no relatório são derivadas do Agente do usuário. Atualizamos nossos processos para usar o Agente do usuário e as dicas do cliente, quando disponíveis.

A ID de fallback ([s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=pt-BR)) é derivada do Agente do usuário e do Endereço IP. Essa ID é usada somente se não for possível definir um cookie, portanto, não é amplamente usada

+++

+++**Quais campos de relatórios do Analytics são obtidos de valores armazenados em dicas de alta entropia?**

Isso será alterado com o tempo, à medida que o Google “congela” mais partes do usuário-agente. O primeiro campo a ser diretamente afetado é o “Sistema operacional”, que inclui a versão do sistema operacional. De acordo com a linha do tempo de “congelamento” de dicas do usuário-agente publicada pelo Google, a versão do sistema operacional será congelada a partir do final de outubro de 2022 com a versão 107 do Chromium. Nesse momento, a versão do sistema operacional no usuário-agente será imprecisa em alguns casos.

Consulte a [linha do tempo publicada pelo Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) para ver o tempo de congelamento de outras partes do usuário-agente.

+++

+++**Como a Adobe usará as dicas do cliente para obter informações do dispositivo?**

A Adobe utiliza um terceiro, o Device Atlas, que usará as dicas do cliente e o usuário-agente para obter informações do dispositivo.

+++

+++**Quais navegadores são afetados pelas dicas do cliente?**

As dicas do cliente se aplicam somente aos navegadores Chromium, como Google Chrome e Microsoft Edge. Não há alterações nos dados de outros navegadores ou aplicativos móveis.

+++

+++**As dicas do cliente são permitidas em conexões inseguras?**

Não. As dicas do cliente só podem ser coletadas por meio de uma conexão HTTP segura, como HTTPS.

+++

+++**Como faço para incluir dados de dicas do cliente ao usar o envio da API?**

Consulte a documentação para incluí-los por meio da [API de inserção de dados em massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/).

+++

+++**As dicas do cliente estarão disponíveis nos dados enviados para o Adobe Experience Platform e o Customer Journey Analytics por meio do Conector de origem do Adobe?**

A Adobe planeja incluir dicas do cliente em dados por meio do Conector de origem da Adobe no primeiro semestre de 2023.

+++

+++**Como as dicas do cliente são representadas no XDM?**

Consulte a [documentação do esquema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) na Adobe Experience Platform.

+++

+++**O encaminhamento pelo lado do servidor do Adobe Audience Manager será compatível com as dicas do cliente?**

Sim. As dicas do cliente serão incluídas nos dados encaminhados ao Adobe Audience Manager. Observe que o Adobe Audience Manager requer que dicas de alta entropia sejam coletadas para preservar a funcionalidade completa. Se você estiver usando [encaminhamento pelo lado do servidor para o Adobe Audience Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=pt-BR) em seguida, talvez você queira ativar a coleção de dicas de alta entropia.

+++
