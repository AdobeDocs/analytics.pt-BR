---
title: Dicas do cliente
description: Saiba como as dicas do cliente substituirão gradualmente o usuário-agente como a fonte de informações do dispositivo.
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
source-git-commit: e7260f745f40dd89bd0aeb476b70b2d77813af96
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 83%

---

# Visão geral e perguntas frequentes sobre dicas do cliente

As dicas do cliente são informações individuais sobre o dispositivo de um usuário. Elas são fornecidas por navegadores Chromium, como o Google Chrome e Microsoft Edge. Nesses navegadores, as dicas do cliente substituirão gradualmente o usuário-agente como a fonte de informações do dispositivo. O Adobe Analytics atualizará seu processo de pesquisa de dispositivo para usar dicas do cliente além do usuário-agente para determinar as informações do dispositivo.

O Google divide as dicas do cliente de usuário-agente em duas categorias: dicas de baixa entropia e alta entropia.

* **Dicas de baixa entropia** contém informações mais genéricas sobre dispositivos. Essas dicas são fornecidas automaticamente pelos navegadores Chromium.

* As dicas de **alta entropia** contêm informações mais detalhadas. Essas dicas estão disponíveis somente mediante solicitação. O AppMeasurement e o SDK da Web podem ser configurados para solicitar dicas de alta entropia. Por padrão, ambas as bibliotecas **não** solicitam dicas de alta entropia.

>[!NOTE]
>
>As dicas do cliente serão incorporadas ao processo de pesquisa de dispositivo do Analytics a partir de 25 de janeiro de 2023. Atualmente, o AppMeasurement e o SDK da Web são compatíveis com a coleção de dados de dicas, mas esta não será usada na pesquisa de dispositivo até meados de janeiro. Isso é para evitar uma potencial interrupção dos relatórios durante o período crítico de fim de ano. Conforme observado abaixo, a versão do sistema operacional será congelada a partir de outubro, mas devido a uma implantação gradual e ao fato de a maioria dos agentes de usuário ser congelada para a versão correta do sistema operacional, estimamos que isso afetará menos de 3% dos visitantes que utilizam o Chrome.

>[!NOTE]
>
>A partir de outubro de 2022, novas versões dos navegadores Chromium iniciarão o “congelamento” da versão do sistema operacional representada na string do usuário-agente. A versão do sistema operacional é uma dica de alta entropia, portanto, para manter a precisão da versão do sistema operacional em seus relatórios, é necessário configurar a biblioteca de coleção para coletar essas dicas de alta entropia. Com o tempo, outras informações do dispositivo do usuário-agente serão congeladas, o que exigirá que as dicas do cliente mantenham a precisão do relatório do dispositivo.

>[!NOTE]
>
> Desde janeiro de 2023, algumas versões dos sistemas operacionais Mac e Windows são representadas incorretamente no Agente do usuário, mas corretamente representadas em dicas de cliente de alta entropia. Consulte [Sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=pt-BR) para obter mais informações.

>[!NOTE]
>
>O AAM requer que dicas de alta entropia sejam coletadas para preservar a funcionalidade completa. Se estiver usando o [encaminhamento pelo lado do servidor para o AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=pt-BR), talvez você queira ativar a coleção de dicas de alta entropia.

## Perguntas frequentes

+++**Onde posso obter mais informações sobre dicas do cliente?**

Esta [publicação do blog do Google](https://web.dev/user-agent-client-hints/) é uma boa referência e um bom ponto de partida.

+++

+++**Como habilitar a coleção de dicas do cliente?**

As dicas de baixa entropia são fornecidas automaticamente pelo navegador e assimiladas para a obtenção de informações do dispositivo e do navegador. As versões mais recentes do SDK da Web (começando com a 2.12.0) e do AppMeasurement (começando com a 2.23.0) podem ser configuradas para coletar dicas de alta entropia por meio de suas respectivas extensões de Tags ou diretamente por meio de uma opção de configuração. Consulte as instruções para o [SDK da Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html#enabling-high-entropy-client-hints) e o [AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html).

Para ambas as bibliotecas, a coleção de dicas de alta entropia é **desativada por padrão**.

+++

+++**Posso escolher quais dicas de alta entropia quero coletar?**

Não neste momento. Você pode optar por coletar todas as dicas de alta entropia ou nenhuma.

+++

+++**Quais são os vários valores de dicas do cliente?**

A tabela abaixo descreve as dicas do cliente a partir de outubro de 2022.

| Dica | Descrição | Alta ou baixa entropia | Exemplo |
| --- | --- | --- | --- | 
| Sec-CH-UA | Navegador e versão significativa | Baixa | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | Dispositivo móvel (verdadeiro ou falso) | Baixa | TRUE |
| Sec-CH-UA-Platform | Sistema operacional/plataforma | Baixa | &quot;Android&quot; |
| Sec-CH-UA-Arch | Arquitetura do site | Alta | &quot;arm&quot; |
| Sec-CH-UA-Bitness | Arquitetura de bits | Alta | &quot;64&quot; |
| Sec-CH-UA-Full-Version | Versão completa do navegador | Alta | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | Lista de marcas com suas versões | Alta | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | Modelo do dispositivo | Alta | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | Versão do sistema operacional/plataforma | Alta | &quot;10&quot; |

+++

+++**Haverá alterações nos relatórios de dispositivos no Analytics?**

Os campos de dispositivo disponíveis para relatório não serão alterados. Os dados capturados para esses campos podem mudar, dependendo de qual campo e como você configurou a coleção de dicas do cliente.

+++

+++**Quais campos de relatórios do Analytics são obtidos do usuário-agente?**

Esses campos são obtidos diretamente do usuário-agente, mas o usuário-agente pode ser usado para ajudar a obter valores para outros campos relacionados ao dispositivo, dependendo dos detalhes do dispositivo.

* [Navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html)
* [Tipo de navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html)
* [Sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html)
* [Tipos de sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html)
* [Dispositivo móvel e tipo de dispositivo móvel](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html)

+++

+++**Que partes do usuário-agente estão sendo “congeladas” e quando?**

Consulte a [linha do tempo publicada pelo Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Esta situação pode estar sujeita a alterações.

+++

+++**De que maneiras o Analytics depende do Agente do usuário?**

As informações do dispositivo no relatório são derivadas do Agente do usuário. Atualizamos nossos processos para usar o Agente do usuário e as dicas do cliente, quando disponíveis.

A ID de fallback ([s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=en)) é derivado do Agente do usuário e do Endereço IP. Essa ID é usada somente se não for possível definir um cookie, portanto, não é amplamente usada

+++

+++**Quais campos de relatórios do Analytics são obtidos de valores armazenados em dicas de alta entropia?**

Isso será alterado com o tempo, à medida que o Google “congela” mais partes do usuário-agente. O primeiro campo a ser diretamente afetado é o “Sistema operacional”, que inclui a versão do sistema operacional. De acordo com a linha do tempo de “congelamento” de dicas do usuário-agente publicada pelo Google, a versão do sistema operacional será congelada a partir do final de outubro de 2022 com a versão 107 do Chromium. Nesse momento, a versão do sistema operacional no usuário-agente será imprecisa em alguns casos.

Consulte a [linha do tempo publicada pelo Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) para ver o tempo de congelamento de outras partes do usuário-agente.

+++

+++**Como a Adobe usará as dicas do cliente para obter informações do dispositivo?**

O Adobe usa um Atlas de dispositivo de terceiros, que usará as dicas do cliente e o Agente do usuário para obter informações do dispositivo.

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

+++**As dicas do cliente estarão disponíveis nos dados enviados para o AEP e o CJA por meio do Conector de origem da Adobe?**

A Adobe planeja incluir dicas do cliente em dados por meio do Conector de origem da Adobe no primeiro semestre de 2023.

+++

+++**Como as dicas do cliente são representadas no XDM?**

Consulte a [documentação do esquema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) na Adobe Experience Platform.

+++

+++**O encaminhamento pelo lado do servidor do AAM será compatível com as dicas do cliente?**

Sim. As dicas do cliente serão incluídas nos dados encaminhados ao AAM. Observe que o AAM requer que dicas de alta entropia sejam coletadas para preservar a funcionalidade completa. Se estiver usando o [encaminhamento pelo lado do servidor para o AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=pt-BR), talvez você queira ativar a coleção de dicas de alta entropia.

+++
