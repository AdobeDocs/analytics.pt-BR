---
description: 'Quando um usuário visita seu site, um cookie persistente é configurado pelo servidor da Web da Adobe, que o inclui na resposta HTTP enviada ao navegador. Esse cookie é definido no domínio especificado da coleta de dados. '
keywords: Implementação do Analytics
seo-description: 'Quando um usuário visita seu site, um cookie persistente é configurado pelo servidor da Web da Adobe, que o inclui na resposta HTTP enviada ao navegador. Esse cookie é definido no domínio especificado da coleta de dados. '
seo-title: ID do visitante do Analytics
solution: Analytics
title: ID de visitante do Analytics
topic: Desenvolvedor e implementação
uuid: fa 7737 cc -0190-4 d 27-af 1 b -87301 a 715 df 2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID do visitante do Analytics

Quando um usuário visita seu site, um cookie persistente é configurado pelo servidor da Web da Adobe, que o inclui na resposta HTTP enviada ao navegador. Esse cookie é definido no domínio especificado da coleta de dados. 

Quando uma solicitação é enviada para o servidor de coleção de dados da Adobe, o cabeçalho é verificado para procurar um cookie da ID do visitante (`s_vi`.) Se este cookie estiver na solicitação, ele é usado para identificar o visitante. Se o cookie não está na solicitação, o servidor gera uma ID de visitante exclusiva, a configura como um cookie no cabeçalho de resposta HTTP e a envia com a solicitação. O cookie é armazenado no navegador e é enviado para o servidor de coleção de dados durante visitas subsequentes ao site, o que permite a identificação do visitante em visitas.

## Cookies de terceiros e registros CNAME {#section_61BA46E131004BB2B75929C1E1C93139}

Alguns navegadores, como o Apple Safari, não armazenam cookies configurados no cabeçalho HTTP provenientes de domínios que não correspondem ao domínio do site (como um cookie utilizado em um contexto de terceiro, ou um cookie de terceiro). Por exemplo, se você está em `mysite.com` e o servidor de coleta de dados for `mysite.omtrdc.net`, o cookie retornado no cabeçalho HTTP de `mysite.omtrdc.net` pode ser rejeitado pelo navegador.

Para evitar isso, vários clientes implementaram registros de CNAME para seus servidores de coleção de dados como parte de uma [implementação de cookie primária](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/). Se um registro CNAME é configurado para mapear um nome de host no domínio do cliente para o servidor de coleção de dados (por exemplo, mapear `metrics.mysite.com` para `mysite.omtrdc.net`), o cookie da ID de visitante é armazenado, pois o domínio de coleção de dados agora corresponde ao domínio do site. Isso aumenta a probabilidade do cookie da ID de visitante ser armazenado, mas apresenta uma sobrecarga, pois é necessário configurar registros de CNAME e manter certificados SSL para servidores de coleção de dados.

## Cookies em dispositivos móveis {#section_7D05AE259E024F73A95C48BD1E419851}

Quando os dispositivos móveis são rastreados com cookies, há algumas configurações que você pode usar para modificar como a medição ocorre. O tempo de vida padrão do cookie é de 5 anos, mas você pode usar a variável de parâmetro de consulta de CL (`s.cookieLifetime`) para alterar esse padrão. Para definir o local do cookie para implementações cname, use a string de consulta CDP `s.cookieDomainPeriods`. O padrão é 2 se nenhum valor for especificado. e o local padrão é domínio.com. Para implementações que não usam CNAME, a localidade do cookie da ID de visitante é o domínio 207.net.
