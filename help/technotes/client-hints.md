---
title: Dicas do cliente
description: Saiba como as dicas do cliente substituirão gradualmente o usuário-agente como a fonte de informações do dispositivo.
source-git-commit: 1bd34bd2bdbe5ad8abb75be81554837e53c112fb
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 76%

---


# Visão geral e perguntas frequentes sobre dicas do cliente

As dicas do cliente são informações individuais sobre o dispositivo de um usuário. Elas são fornecidas por navegadores Chromium, como o Google Chrome e Microsoft Edge. Nesses navegadores, as dicas do cliente substituirão gradualmente o usuário-agente como a fonte de informações do dispositivo. O Adobe Analytics atualizará seu processo de pesquisa de dispositivo para usar dicas do cliente além do usuário-agente para determinar as informações do dispositivo.

O Google divide as dicas do cliente de usuário-agente em duas categorias: dicas de baixa entropia e alta entropia.

* **Dicas de baixa entropia** contém informações mais genéricas sobre dispositivos. Essas dicas são fornecidas automaticamente pelos navegadores Chromium.

* As dicas de **alta entropia** contêm informações mais detalhadas. Essas dicas estão disponíveis somente mediante solicitação. O AppMeasurement e o SDK da Web [podem ser configurados](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) para solicitar dicas de alta entropia. Por padrão, ambas as bibliotecas **não** solicitam dicas de alta entropia.

>[!NOTE]
>
>A partir de outubro de 2022, novas versões dos navegadores Chromium iniciarão o “congelamento” da versão do sistema operacional representada na string do usuário-agente. A versão do sistema operacional é uma dica de alta entropia, portanto, para manter a precisão da versão do sistema operacional em seus relatórios, é necessário configurar a biblioteca de coleção para coletar essas dicas de alta entropia. Com o tempo, outras informações do dispositivo do usuário-agente serão congeladas, o que exigirá que as dicas do cliente mantenham a precisão do relatório do dispositivo.

>[!NOTE]
>
>AAM requer que dicas de alta entropia sejam coletadas para preservar a funcionalidade completa. Se estiver usando [encaminhamento pelo lado do servidor para o AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=pt-BR) em seguida, talvez você queira ativar a coleta de dicas de alta entropia.

## Perguntas frequentes

+++**Onde posso obter mais informações sobre dicas do cliente?**

Esta [publicação do blog do Google](https://web.dev/user-agent-client-hints/) é uma boa referência e um bom ponto de partida.

+++

+++**Como habilitar a coleção de dicas do cliente?**

As dicas de baixa entropia são fornecidas automaticamente pelo navegador e incluídas no processo da Adobe para obtenção de informações do dispositivo e do navegador. As versões mais recentes do AppMeasurement (a partir da versão 2.23.0) e do SDK da Web (a partir da versão 2.12.0) podem ser configuradas para coletar dicas de alta entropia. Para ambas as bibliotecas, a coleção de dicas de alta entropia é **desativada por padrão**.

+++

+++**Como capturar dicas de alta entropia?**

As dicas de alta entropia podem ser configuradas com o SDK da Web e as bibliotecas do AppMeasurement por meio de suas respectivas extensões de tags ou diretamente com o sinalizador “collectHighEntropyUserAgentHints”.

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

Esses campos são diretamente derivados do Agente do usuário, mas o Agente do usuário pode ser usado para ajudar a derivar valores para outros campos relacionados ao dispositivo, dependendo dos detalhes do dispositivo.

* [Navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=pt-BR)
* [Tipo de navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=pt-BR)
* [Sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=pt-BR)
* [Tipos de sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=pt-BR)
* [Dispositivo móvel e tipo de dispositivo móvel](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=pt-BR)

+++

+++**Quais campos de relatórios do Analytics são obtidos de valores armazenados em dicas de alta entropia?**

Isso será alterado com o tempo, à medida que o Google &quot;congela&quot; mais partes do Agente do usuário. O primeiro campo a ser diretamente afetado é &quot;Sistema operacional&quot;, que inclui a versão do sistema operacional De acordo com a linha do tempo publicada pela Google para dicas de &quot;congelamento&quot; do agente-usuário, a versão do sistema operacional será congelada a partir do final de outubro de 2022 com o Chromium versão 107. Nesse momento, a versão do sistema operacional no Agente do usuário estará imprecisa em alguns casos.

Consulte a [linha do tempo publicada pelo Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) para ver o tempo de congelamento de outras partes do usuário-agente.

+++

+++**Como a Adobe usará as dicas do cliente para obter informações do dispositivo?**

O Adobe usa um Atlas de dispositivo de terceiros, que usará as dicas do cliente e o Agente do usuário para derivar informações do dispositivo.

+++

+++**Quais navegadores são afetados pelas dicas do cliente?**

As dicas do cliente se aplicam apenas a navegadores Chromium, como Google Chrome e Microsoft Edge. Não há alterações nos dados de outros navegadores ou aplicativos móveis.

+++

+++**As dicas do cliente são permitidas em conexões inseguras?**

Não. As dicas do cliente só podem ser coletadas por meio de uma conexão HTTP segura, como HTTPS.

+++

+++**As dicas do cliente estarão disponíveis nos dados enviados para o AEP e o CJA por meio do Conector de origem da Adobe?**

A Adobe planeja incluir dicas do cliente em dados por meio do Conector de origem da Adobe no primeiro semestre de 2023.

+++

+++**Como as dicas do cliente são representadas no XDM?**

Consulte a [documentação do esquema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) na Adobe Experience Platform.

+++

+++**Que partes do usuário-agente estão sendo “congeladas” e quando?**

Consulte a [linha do tempo publicada pelo Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Esta situação pode estar sujeita a alterações.

+++

+++**O encaminhamento pelo lado do servidor AAM dará suporte a dicas do cliente?**

Sim. As dicas do cliente serão incluídas nos dados encaminhados ao AAM. Observe que AAM requer que dicas de alta entropia sejam coletadas para preservar a funcionalidade completa. Se estiver usando [encaminhamento pelo lado do servidor para o AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) em seguida, talvez você queira ativar a coleta de dicas de alta entropia.

+++

