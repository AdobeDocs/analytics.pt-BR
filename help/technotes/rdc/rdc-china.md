---
title: Coleta de dados regional da China
seo-title: Adobe Analytics China RDC
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Coleta de dados regional da China

A Coleta de dados regional (RDC) na China continental permite que os usuários da China enviem dados para um Centro de coleta de dados (DCC) dentro da China, em vez de outros locais do mundo. Isso melhora os tempos de carregamento de página e a precisão dos dados em comparação ao envio de dados para Centros de coleta de dados (DCC) fora da China.

> [!IMPORTANT] Há um custo adicional associado à utilização do nó RDC da China. Antes de implementar a coleta de dados na China usando o nó RDC descrito neste documento, entre em contato com o gerente de conta de sua organização para garantir que você tenha direito a essa funcionalidade.

## Configuração do servidor de rastreamento para a China

O rastreamento pode ser trazido para a RDC da China no momento mais conveniente para o seu serviço. Para qualquer propriedade digital (como um aplicativo móvel ou página da Web) que você deseja rotear para a RDC da China, altere o servidor de rastreamento para:

`<namespace>.sc.adobedc.cn`

Certifique-se de inserir o namespace adequado. Ele normalmente é encontrado no início do servidor de rastreamento existente. For example: `<namespace>.sc.adobedc.cn` - although any namespace value will work. Além disso, é possível apontar um registro primário não SSL [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) para este novo local.

Não defina o valor do trackingServer globalmente, para todas as propriedades e regiões geográficas, para a RDC da China se uma parte substancial da sua base de clientes estiver fora da China. O trackingServer deve ser definido para o valor de RDC da China somente para clientes que estiverem na China. Caso contrário, ele afetará negativamente a velocidade dos usuários fora da China, pois força a coleta de dados a ir para China e voltar para uma resposta.

## Identificação de usuários na China

Independentemente de onde sua propriedade digital estiver hospedada ou de qual idioma ela usa, seus usuários na China vão experienciar melhoras se você estiver usando o nó da RDC na China. Sendo assim, a prática recomendada é determinar quais usuários estão localizados na China e usar a RDC para esses usuários. Os métodos que podem ajudar a identificar esses usuários incluem:

* Usando uma solução GeoIP confiável.  Você pode optar por usar uma solução do lado do servidor para se integrar facilmente ao Adobe Experience Platform Launch (ou ao Gerenciamento de tags de dados). Nesse caso, o local pode ser determinado incluindo um elemento de dados padrão no objeto Experience Platform Launch ou DTM. Ou você pode usar uma solução GeoIP do lado do cliente. Nesse caso, o Experience Platform Launch pode ser conectado ao código do cliente. Observe que essas soluções podem envolver solicitar que o usuário acesse o site localizado. Isso apresenta um risco de que a primeira página seja contada pelo servidor de rastreamento global e a segunda página pela página na China, o que pode resultar em uma visita contada duas vezes. Siga as práticas recomendadas para as soluções GeoIP. A Adobe não é responsável pela precisão da solução GeoIP usada.

* Using site structure or the browser language (the `navigator.language / accept-language` header). A vantagem desse método é o baixo custo e a possibilidade de um melhor desempenho. A desvantagem é que os visitantes falantes de chinês que localizam-se fora da China são sujeitos a velocidades de navegação que foram afetadas negativamente.
* Usar uma solução de hospedagem com base na China e configurar o trackingServer para a RDC da China com base no seu host. Isso também aumentará substancialmente a velocidade.

## Limitações atuais

As limitações atuais da RDC da China:

1. A RDC da China não é compatível com SSL primário ([s.trackingServerSecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) em seu JavaScript) ou com o encaminhamento [pelo lado do](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) servidor para o Adobe Audience Manager.
2. Embora o [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) e o [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/) sejam compatíveis, os domínios do Target e do Demdex não estão na China Continental atualmente e não terão os mesmos benefícios de velocidade ou confiabilidade que aqueles na RDC da China.

## Compromisso da Adobe com a China

A Adobe planeja manter permanentemente o progresso da RDC da China e, eventualmente, adicionará suporte a recursos como o SSL primário e o encaminhamento ao lado do servidor. Além disso, a Adobe planeja fornecer um domínio demdex (ou equivalente) na China para oferecer suporte completo à coleta do ECID e do Audience Manager de dentro da China. Os clientes que começam a usar a RDC da China da Adobe são bem-vindos a continuar usando este endpoint de coleta de dados indefinidamente.
