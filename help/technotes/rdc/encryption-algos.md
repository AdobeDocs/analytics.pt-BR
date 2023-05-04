---
title: Algoritmos de criptografia HTTPS aceitos
description: Configurações de segurança de criptografia TLS e tipos de certificado.
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: 299de03c05f6a8af4f6c5d98c76bae54eec4c088
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 30%

---

# Algoritmos de criptografia HTTPS aceitos

## Níveis de segurança da cifra

A Adobe oferece dois níveis de segurança de criptografia para atender às diversas necessidades de segurança do cliente na coleta de dados primários. Esses níveis determinam quais algoritmos de criptografia são compatíveis com conexões HTTPS com nossos servidores. O Adobe analisa e atualiza regularmente o conjunto de algoritmos suportados com base nas práticas de segurança atuais. Se você quiser alterar as configurações de segurança da criptografia, entre em contato com o Atendimento ao cliente.

&#39;Padrão&#39; requer TLS 1.2 ou mais recente e pelo menos criptografia de 128 bits. Ele foi projetado para fornecer a maior compatibilidade de dispositivos, mantendo a criptografia segura.

O nível de segurança de cifras &quot;alto&quot; requer TLS 1.2 ou mais recente e remove o suporte a cifras mais fracas. Ele foi projetado para clientes que desejam a criptografia mais forte e não estão preocupados com o suporte a dispositivos mais antigos.

Os seguintes clientes são conhecidos por não conseguirem se conectar com a segurança de cifras definida como &quot;Alto&quot;.

* Windows 8.1 e anterior (última atualização em 2018)
* Windows Phone 8.1 e anterior (última atualização em 2016)
* OS X 10.10 e anterior (última atualização em 2017)
* iOS 8.4 e anterior (última atualização em 2015)

## Tipos de certificado HTTPS suportados

O Adobe é compatível com os tipos de certificado RSA e ECC para atender às diversas necessidades dos clientes. Os certificados RSA são mais amplamente aceitos para clientes, mas os certificados ECC usam menos processamento tanto no servidor quanto no cliente. Para certificados Adobe Managed, RSA e ECC são fornecidos. Para certificados gerenciados pelo cliente, são recomendados RSA e ECC. Clientes modernos são compatíveis com RSA e ECC. Os seguintes clientes são conhecidos por oferecer suporte somente a certificados RSA:

* Windows Vista e anterior (última atualização em 2012)
* Windows Phone 8.0 e anterior (última atualização em 2014)
* OS X 10.8 e anterior (última atualização em 2013)
* iOS 5.1 e anterior (última atualização em 2012)
* Android 4.3 e anterior (última atualização em 2013)
