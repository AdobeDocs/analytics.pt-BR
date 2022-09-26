---
title: Dicas do cliente
description: Saiba mais sobre como as dicas do cliente substituirão gradualmente o Agente do usuário como fonte de informações do dispositivo.
source-git-commit: f2f1e64a62796b58c24e6ff652db93b21f750669
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 5%

---


# Visão geral e perguntas frequentes das dicas do cliente

Dicas de cliente são informações individuais sobre o dispositivo de um usuário. Eles são fornecidos por navegadores Chromium, como Google Chrome e Microsoft Edge. Nesses navegadores, as dicas do cliente substituirão gradualmente o Agente do usuário como fonte de informações do dispositivo. A Adobe Analytics atualizará seu processo de pesquisa de dispositivo para que ele use dicas de cliente além do Agente do usuário para determinar as informações do dispositivo.

O Google divide as dicas do cliente User-Agent em duas categorias: dicas de baixa entropia e alta entropia.

* **Dicas de baixa entropia** contém informações mais genéricas sobre dispositivos. Essas dicas são fornecidas automaticamente pelos navegadores Chromium.

* **Alta entropia** as dicas contêm informações mais detalhadas. Essas dicas estão disponíveis somente por solicitação. AppMeasurement e SDK da Web [pode ser configurado](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) para solicitar dicas de alta entropia. Por padrão, ambas as bibliotecas têm **not** solicite dicas de alta entropia.

>[!NOTE]
>
>A partir de outubro de 2022, novas versões dos navegadores Chromium iniciarão o &#39;congelamento&#39; da versão do sistema operacional representada na string User-Agent. À medida que os usuários atualizam seus dispositivos, o sistema operacional no Agente do usuário não será alterado. Assim, com o tempo, as informações da versão operacional representadas no Agente do usuário se tornarão menos precisas. A versão do sistema operacional é uma dica de alta entropia, portanto, para manter a precisão da versão do sistema operacional em seus relatórios, é necessário configurar a biblioteca de coleta para coletar essas dicas de alta entropia. Com o tempo, outras informações do dispositivo do Agente do Usuário serão congeladas, o que exige que as dicas do cliente mantenham a precisão do relatório do dispositivo.

## Perguntas frequentes

+++**Onde posso obter mais informações sobre dicas de clientes?**

Essa [Publicação do blog do Google](https://web.dev/user-agent-client-hints/) é uma boa referência e um bom ponto de partida.

+++

+++**Como habilitar a coleta de dicas do cliente?**

As dicas de baixa entrelinha são fornecidas automaticamente pelo navegador e incluídas no Adobe para obter informações sobre o dispositivo e o navegador de derivação. As versões mais recentes do AppMeasurement (a partir da versão 2.23.0) e do SDK da Web (a partir da versão 2.12.0) podem ser configuradas para coletar dicas de alta entropia. Para ambas as bibliotecas, a coleção de dicas de alta entropia é **desativado por padrão**.

+++

+++**Como capturo dicas de alta entropia?**

Dicas de alta entropia podem ser configuradas com o SDK da Web e as bibliotecas do AppMeasurement por meio de suas respectivas extensões de Tags ou diretamente com o sinalizador collectHighEntropyUserAgentHint.

+++

+++**Posso escolher quais dicas de alta entropia eu coletar?**

Não neste momento. Você pode optar por coletar todas as dicas de alta entropia ou nenhuma.

+++

+++**Haverá alterações nos relatórios de dispositivos no Analytics?**

Os campos de dispositivo disponíveis para relatório não serão alterados. Os dados capturados para esses campos podem mudar, dependendo de qual campo e como você configurou a coleta para dicas do cliente.

+++

+++**Quais campos de relatórios do Analytics são derivados do Agente do usuário?**

* [Navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Tipo de navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Tipos de sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Dispositivo móvel e tipo de dispositivo móvel](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)
* [Feeds de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR)

+++

+++**Quais campos de relatórios do Analytics são derivados de valores armazenados em dicas de alta entropia?**

A partir de setembro de 2022, a linha do tempo publicada pela Google para dicas de &quot;congelamento&quot; do agente-usuário indica que a versão do sistema operacional deixará de ser atualizada a partir de outubro de 2022. Quando os usuários atualizam o sistema operacional, a versão do sistema operacional no Agente do usuário não será atualizada. Sem dicas de alta entropia, a precisão da versão do sistema operacional, que está incluída na dimensão &quot;Sistema operacional&quot; do Analytics, será gradualmente degradada.

Consulte a [linha do tempo publicada pela Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) para ver o tempo de congelamento de outras partes do Agente do Usuário.

+++

+++**Como o Adobe usará as dicas do cliente para derivar informações do dispositivo?**

O Adobe usa um Atlas de dispositivo de terceiros, que usará as dicas do cliente e o Agente do usuário para derivar informações do dispositivo.

+++

+++**Quais navegadores são afetados pelas dicas do cliente?**

As dicas do cliente se aplicam somente a navegadores Chromium, como Google Chrome e Microsoft Edge. Não há alterações nos dados de outros navegadores ou aplicativos móveis.

+++

++**As dicas do cliente são suportadas em conexões inseguras?

Não. As dicas do cliente só podem ser coletadas por meio de uma conexão HTTP segura, como HTTPS.

+++

+++**As dicas do cliente estarão disponíveis nos dados enviados para o AEP e o CJA por meio do Conector de fonte do Adobe?**

O Adobe planeja incluir dicas do cliente em dados por meio do Adobe Source Connector no primeiro semestre de 2023.

+++

+++**Como as dicas do cliente são representadas no XDM?**

Consulte a [documentação do schema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) no Adobe Experience Platform.

+++

+++**Quais são os vários campos de dica? Quais afetam o relatório do dispositivo?**

A tabela abaixo descreve as dicas do cliente a partir de setembro de 2022.

| Dica | Descrição | Entrofia alta ou baixa | Exemplo |
| --- | --- | --- | --- | 
| Sec-CH-UA | Navegador e versão significativa | Baixo | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | Dispositivo móvel (verdadeiro ou falso) | Baixo | TRUE |
| Sec-CH-UA-Platform | Sistema operacional/plataforma | Baixo | &quot;Android&quot; |
| Sec-CH-UA-Arch | Arquitetura do site | Alto | &quot;braço&quot; |
| Sec-CH-UA-Bitness | Bites de arquitetura | Alto | &quot;64&quot; |
| Sec-CH-UA-Full-Version | Versão completa do navegador | Alto | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | Lista de marcas com sua versão | Alto | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | Modelo do dispositivo | Alto | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | Versão do sistema operacional/plataforma | Alto | &quot;10&quot; |

+++



+++**Que partes do Agente de Usuário estão sendo &quot;congeladas&quot; e quando?**

Consulte a [linha do tempo publicada pela Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Esta situação pode estar sujeita a alterações.

+++
