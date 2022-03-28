---
title: Algoritmos de criptografia HTTPS suportados
description: Em 23 de junho de 2022, removeremos o suporte para cifras TLS 1.2 que utilizam SHA1 ou CBC para clientes com nível de segurança de cifras definido como "Alto".
feature: Regional Data Collection
source-git-commit: ce607610516a94e4d0fbbc53a1f8f53f5977a777
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Algoritmos de criptografia HTTPS suportados

O Adobe oferece dois níveis de segurança de criptografia para atender às diversas necessidades de segurança do cliente na coleta de dados primários. Esses níveis determinam quais algoritmos de criptografia são compatíveis com conexões HTTPS com nossos servidores. Os clientes assumem o padrão de &quot;Padrão&quot;, que suporta apenas algoritmos de criptografia modernos. &quot;Alto&quot; suporta uma lista menor de algoritmos de criptografia para clientes que estão mais preocupados com essas conexões. Para ambos os níveis de segurança, o Adobe atualiza regularmente o conjunto de algoritmos suportados com base nas práticas de segurança atuais. Se você quiser alterar as configurações de segurança da criptografia, entre em contato com o Atendimento ao cliente.

Em 23 de junho de 2022, removeremos o suporte para cifras TLS 1.2 que utilizam SHA1 ou CBC para clientes com nível de segurança de cifras definido como &quot;Alto&quot;.  Essa alteração afetará a coleta segura de dados para usuários finais em sistemas operacionais mais antigos.

As seguintes cifras TLS 1.2 não serão mais suportadas:

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

Os seguintes clientes são conhecidos por serem afetados por essa alteração porque não têm suporte para os padrões de criptografia atuais:

* Windows 8.1 e anterior (última atualização em 2018)
* Windows Phone 8.1 e anterior (última atualização em 2016)
* OS X 10.10 e anterior (última atualização em 2017)
* iOS 8.4 e anterior (última atualização em 2015)

Os dispositivos Android não são afetados por essa alteração.

Clientes com nível de segurança de cifra definido como &quot;Padrão&quot; não são afetados por essa alteração.

