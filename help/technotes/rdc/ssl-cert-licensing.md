---
title: Licença do certificado SSL
description: Procedimentos de certificado para certificados gerenciados pelo cliente
exl-id: 7d1373c8-6f7b-4ce7-a555-d3d506e08d17
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '256'
ht-degree: 100%

---

# Licenciamento de certificado SSL/TLS

A Adobe recomenda que você gerencie seu certificado sem custo adicional por meio do [Programa de certificados gerenciados da Adobe](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=pt-BR). O programa de certificados gerenciados da Adobe é totalmente automatizado e garante que os certificados sejam renovados em tempo hábil para que não haja impacto por causa aos certificados expirados.

Se optar por não usar o [Programa de certificados gerenciados da Adobe](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=pt-BR), você será responsável por fornecer um certificado SSL/TLS a ser usado para cookies próprios.

Se você fornece seus próprios certificados, é sua responsabilidade adquirir e mantê-los.  Seu certificado SSL/TLS deve incluir uma licença de servidor ilimitada.

Para garantir a segurança do certificado, obtenha da Adobe uma solicitação de assinatura do certificado [CSR] e organize com a autoridade de certificação desejada para que o certificado seja assinado.  Forneça à Adobe o certificado assinado para implementação.  Ao seguir esse processo, a segurança da chave do certificado é mantida.  O Atendimento ao cliente da Adobe ajudará neste processo.

Como parte da manutenção de certificados, pelo menos um mês antes da expiração do certificado, organize com a autoridade de certificação desejada para obter um certificado renovado e fornecê-lo à Adobe.  Este certificado deve usar o mesmo CSR usado anteriormente.  Entre em contato com a Adobe se precisar de uma cópia do CSR ou se quiser que um novo CSR seja gerado com uma nova chave.

O Atendimento ao cliente pode ser contatado via customercare@adobe.com ou ligando para 1-800-497-0335.

As autoridades de certificação normalmente usadas incluem DigiCert, Comodo e GeoTrust.
