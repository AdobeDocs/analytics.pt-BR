---
title: Dicas do cliente
description: Saiba mais sobre
source-git-commit: b99852f4b8e0a3034ea8965e5646b1ab2f1a8c4c
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 4%

---


# Visão geral e perguntas frequentes das dicas do cliente

Dicas de cliente são informações individuais sobre o dispositivo de um usuário. Eles são fornecidos por navegadores Chromium, como Google Chrome e Microsoft Edge. Nesses navegadores, as dicas do cliente substituirão gradualmente o Agente do usuário como fonte de informações do dispositivo. A Adobe Analytics atualizará seu processo de pesquisa de dispositivo para que ele use dicas de cliente além do Agente do usuário para determinar as informações do dispositivo.

O Google divide as dicas do cliente Agente do usuário em duas categorias: dicas de baixa entropia e alta entropia.

* As dicas de baixa entropia têm informações mais genéricas sobre dispositivos. Essas dicas são fornecidas automaticamente pelos navegadores Chromium.

* As dicas de alta entropia têm informações mais detalhadas. Essas dicas estão disponíveis somente por solicitação. O AppMeasurement e o SDK da Web podem ser configurados para solicitar dicas de alta entropia. Por padrão, ambas as bibliotecas têm **not** solicite dicas de alta entropia.

>[!NOTE]
>
>A partir de outubro de 2022, novas versões dos navegadores Chromium iniciarão o &#39;congelamento&#39; da versão do sistema operacional representada na string User Agent. Isso significa que, com o tempo, as informações da versão operacional representadas no Agente do usuário se tornarão menos precisas. A versão do sistema operacional é uma dica de alta entropia, portanto, para manter a precisão da versão do sistema operacional em seus relatórios, é necessário configurar a biblioteca de coleta para coletar essas dicas de alta entropia. Com o tempo, outras informações do dispositivo do Agente do usuário serão congeladas, o que exige que as dicas do cliente mantenham a precisão do relatório do dispositivo.

## Perguntas frequentes

+++**Como habilitar a coleta de dicas do cliente?**

As dicas de baixa entrelinha são fornecidas automaticamente pelo navegador e incluídas no Adobe para obter informações sobre o dispositivo. As versões mais recentes do AppMeasurement (iniciando a TBD) e do SDK da Web (iniciando a TBD) podem ser configuradas para coletar dicas de alta entropia. Para ambas as bibliotecas, a coleção de dicas de alta entropia é **desativado por padrão**. Consulte aqui para obter detalhes sobre como implementar isso.

+++**Posso escolher quais dicas de alta entropia eu coletar?**

Não neste momento. Você pode optar por coletar todas as dicas de alta entropia ou nenhuma.

+++**Haverá alterações nos relatórios de dispositivos no Analytics?**

Os campos de dispositivo disponíveis para relatório não serão alterados. Os dados capturados para esses campos podem mudar, dependendo de qual campo e como você configurou a coleta para dicas do cliente.

+++**Quais campos de relatórios do Analytics são derivados do Agente do usuário?**

* [Navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Tipo de navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Tipos de sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Dispositivo móvel e tipo de dispositivo móvel](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)??
* Feeds de dados (observe que os usuários devem atualizar para capturar esses campos. Além disso, há uma dependência em que não podemos expor a ID do dispositivo móvel juntamente com as informações do dispositivo.)
* Conector de origem do Analytics (não pronto)

+++**Quais campos de relatórios do Analytics são derivados de valores armazenados em dicas de alta entropia?**

A partir de setembro de 2022, a linha do tempo publicada pela Google para congelar dicas do agente-usuário indica que a versão do sistema operacional deixará de ser atualizada a partir de outubro de 2022. Sem dicas de alta entropia, a precisão da versão do sistema operacional, incluída na dimensão &quot;Sistema operacional&quot; do Analytics, será gradualmente degradada.

Consulte a [linha do tempo publicada pela Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) para ver o tempo de congelamento do agente do usuário.

+++**Quais navegadores são afetados pelas dicas do cliente?**

As dicas do cliente se aplicam somente a navegadores Chromium, como Google Chrome e Microsoft Edge. Não há alterações nos dados de outros navegadores ou aplicativos móveis.

+++**Como o Adobe usará as dicas do cliente para derivar informações do dispositivo?**

O Adobe usa um Atlas de dispositivo de terceiros, que usará as dicas do cliente e o agente do usuário para derivar informações do dispositivo.

+++**As dicas do cliente estarão disponíveis nos feeds de dados?**

Sim. Consulte a documentação (para seguir).

+++**As dicas do cliente estarão disponíveis nos dados enviados para o AEP e o CJA por meio do Conector de fonte do Adobe?**

Planejamos incluir dicas do cliente em dados por meio do Conector de fonte do Adobe no primeiro semestre de 2023.

+++**Como as dicas do cliente são representadas no XDM?**

Consulte a [documentação do schema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) no Adobe Experience Platform.

+++**Onde posso obter mais informações sobre dicas de clientes?**

Essa [Publicação do blog do Google](https://web.dev/user-agent-client-hints/) é uma boa referência e um bom ponto de partida.

+++**Quais são os vários campos de dica? Quais afetam o relatório do dispositivo?**

A tabela abaixo descreve as dicas do cliente a partir de setembro de 2022.

| Dica (cabeçalho) | Dica | Entrofia alta ou baixa | Exemplo | Campos de relatórios do Analytics |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | Navegador e versão significativa | Baixo | Google Chrome 84 | [Navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) e [Tipo de navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en) |
| Sec-CH-UA-Mobile | Dispositivo móvel (verdadeiro ou falso) | Baixo | TRUE | [Dispositivo móvel e tipo de dispositivo móvel](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)?? |
| Sec-CH-UA-Platform | Sistema operacional/plataforma | Baixo | Android | [Sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |
| Sec-CH-UA-Arch | Arquitetura do site | Alto | &quot;braço&quot; | Nenhum? |
| Sec-CH-UA-Bitness | Sec-CH-UA-Bitness | Alto |  | Nenhum? |
| Sec-CH-UA-Full-Version | Versão completa do navegador | Alto | &quot;84.0.4143.2&quot; | Nenhum? |
| Sec-CH-UA-Full-Version-List | ??? | Alto | ???? | Nenhum? |
| Sec-CH-UA-Model | Modelo do dispositivo | Alto | &quot;Pixel 3&quot; | Nenhum? |
| Sec-CH-UA-Platform-Version | Versão do sistema operacional/plataforma | Alto | &quot;10&quot; | [Sistema operacional](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |

+++**Como capturo dicas de alta entropia?**

Dicas de alta entropia podem ser configuradas

* Para AppMeasurement diretamente [link para a entrada do sinalizador no Guia de Implementação]
* Na extensão Tags do Analytics
* No SDK da Web.

+++**Quais dados estão sendo removidos do Agente do usuário e quando?**

Consulte a [linha do tempo publicada pela Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Esta situação pode estar sujeita a alterações.

+++