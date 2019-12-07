---
description: Como os dispositivos móveis são rastreados por um beacon, como os outros visitantes, a maioria dos relatórios está disponível e correta.
keywords: Analytics Implementation;reports;mobile protocols;search engines;search keywords;referring domains;referrers;geosegmentation;domains;connection type;time zone;cookies;java;javascript;monitor colors;monitor resolution;browser width;height;netscape plug-in
title: Relatórios para dispositivos com protocolos móveis
topic: Developer and implementation
uuid: 4aab125d-c131-4402-9bc8-1c7fd1bb2bee
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Relatórios para dispositivos com protocolos móveis

Como os dispositivos móveis são rastreados por um beacon, como os outros visitantes, a maioria dos relatórios está disponível e correta.

É possível usar o[!DNL VISTA] para alterar dados coletados dos métodos móvel e padrão. Todos os relatórios [!UICONTROL Personalizados] [!UICONTROL de Insight] ([!UICONTROL prop] e [!UICONTROL eVar]), [!UICONTROL de Evento], [!UICONTROL de Tráfego de site] e de [!UICONTROL Definição de caminho] são suportados.

## Mecanismos de pesquisa, palavras-chaves de pesquisa, domínios de referência e referenciador {#section_184D2EF9D906443FBDED04A09CDC50E9}

Esses relatórios só têm dados se o referenciador for preenchido na solicitação de imagem enviada da página remota. O referenciador é preenchido com o parâmetro da string de consulta "r", como mostrado no documento Implementação sem JavaScript. Você também deve transmitir manualmente as informações do referenciador na solicitação de imagem. 

O parâmetro da string de consulta 'r' deve incluir o protocolo do referenciador. Se o protocolo é deixado de fora, o relatório do referenciador não é preenchido. Por exemplo, use `r=https://msn.com` e não `r=msn.com`.

## Segmentação geográfica e domínios {#section_2B4E9443AAFE4ECA961F9E993592E628}

Os relatórios de Segmentação geográfica são baseados no endereço IP do dispositivo que envia a solicitação. Como os dispositivos móveis dependem de um gateway para solicitar imagens dos servidores Adobe, o endereço IP do gateway é usado para determinar a localização geográfica do usuário. Como os gateways e seus endereços IP são registrados para redes grandes, a localização geográfica associada é com frequência menos precisa.

Os domínios também se baseiam no endereço IP do gateway, o que significa que o relatório dos domínios com frequência contém o nome da operadora que detém o gateway. Devido aos Operadores de Rede Virtual Móvel (MVNOs), talvez isso não seja preciso.

## Tipos de conexão {#section_0E7FA18178B848AEBB839B1694B4D691}

A Adobe mantém um intervalo conhecido de endereços de IP pertencentes a operadoras de celular. Quando uma ocorrência de um intervalo de IP pertencente a uma operadora de celular conhecida é recebida, ela aparece como "Operadora móvel" no Relatório do tipo de conexão. Caso contrário, o tráfego móvel é listado em "LAN/Wi-Fi".

## Fusos horários, cookies, Java, JavaScript, cores e resolução do monitor, largura e altura da janela do navegador e plug-ins do Netscape {#section_158C848273AE4691B4413767E849E846}

Esses relatórios são coletados com o uso do JavaScript para detectar configurações específicas do navegador. Como o JavaScript não é usado para criar o beacon da imagem nos dispositivos móveis, os dados coletados de usuários móveis não são incluídos nesses relatórios.
