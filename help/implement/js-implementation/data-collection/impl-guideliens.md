---
description: Seguindo estas diretrizes, você usará os mesmos domínios de cookies, o que permite aos visitantes serem acompanhados entre vários tipos de implementação.
keywords: Analytics Implementation
title: Diretrizes de implementação
topic: Developer and implementation
uuid: 2917f4af-19bd-4666-ae4b-056e7e33f642
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Diretrizes de implementação

Seguindo estas diretrizes, você usará os mesmos domínios de cookies, o que permite aos visitantes serem acompanhados entre vários tipos de implementação.

* **RSID:** a [!UICONTROL ID do conjunto de relatórios]
* **VNS (Espaço reservado do visitante):** subdomínio de [!DNL 2o7.net]o ou [!DNL omtrdc.net] usado para armazenar o cookie da [!UICONTROL ID de visitante]
* **COOKIEDOMAIN:** seu VNS + trackingServer. Dependendo do data center e da configuração de RDC, eles podem variar. [Entre em contato com o Atendimento](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) ao cliente se não tiver certeza sobre seu domínio de coleta de dados.

## JavaScript

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## AppMeasurement

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## Solicitação de imagem codificada

```javascript
<img border="0" alt="" src="https://VNS.COOKIEDOMAIN.net/b/ss/RSID/5?ns=VNS" width="1" height="1" /> 

<!-- Note that the visitor namespace is defined twice in hardcoded image requests; once in the http subdomain, and another using the ns= query string parameter! -->
```

Se você estiver usando uma implementação de cookie primário, `VNS.COOKIEDOMAIN.net` pode ser substituído pelo domínio do cookie primário usado. Por exemplo, se estiver usando cookies primários em `adobe.com`, eles seriam substituídos por algo semelhante a `metrics.adobe.com`.
