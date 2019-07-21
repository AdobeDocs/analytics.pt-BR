---
description: Seguindo estas diretrizes, você usará os mesmos domínios de cookies, o que permite aos visitantes serem acompanhados entre vários tipos de implementação.
keywords: Implementação do Analytics
seo-description: Seguindo estas diretrizes, você usará os mesmos domínios de cookies, o que permite aos visitantes serem acompanhados entre vários tipos de implementação.
seo-title: Diretrizes de implementação
solution: Analytics
title: Diretrizes de implementação
topic: Desenvolvedor e implementação
uuid: 2917 f 4 af -19 bd -4666-ae 4 b -056 e 7 e 33 f 642
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Diretrizes de implementação

Seguindo estas diretrizes, você usará os mesmos domínios de cookies, o que permite aos visitantes serem acompanhados entre vários tipos de implementação.

* **RSID:** a [!UICONTROL ID do conjunto de relatórios]
* **VNS (Espaço reservado do visitante):** subdomínio de [!DNL 2o7.net]o ou [!DNL omtrdc.net] usado para armazenar o cookie da [!UICONTROL ID de visitante]
* **COOKIEDOMAIN:** seu VNS + trackingServer. Dependendo do data center e da configuração de RDC, eles podem variar. [Entre em contato com o Atendimento](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) ao cliente se não tiver certeza sobre o domínio de coleta de dados.

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
