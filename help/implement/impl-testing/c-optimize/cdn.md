---
description: Os serviços de entrega de conteúdo ou as redes de distribuição de conteúdo (CDNs), como Akamai e Speedera, enviam o conteúdo Web para mais perto da borda da rede, mantendo documentos solicitados com frequência perto do local em que são acessados.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Redes/serviços de entrega de conteúdo
topic: Developer and implementation
uuid: 6cb57c59-d0f9-4ca5-9f15-0e74e585a4a1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Redes/serviços de entrega de conteúdo

Os serviços de entrega de conteúdo ou as redes de distribuição de conteúdo (CDNs), como Akamai e Speedera, enviam o conteúdo Web para mais perto da borda da rede, mantendo documentos solicitados com frequência perto do local em que são acessados.

Em geral, isso reduz a latência de acesso, o uso da largura de banda e o custo de infraestrutura.

Seu arquivo AppMeasurement para biblioteca JavaScript pode ser entregue via CDN para aprimorar o desempenho e entregar o arquivo no site do visitante. Os clientes da Adobe devem assegurar que tenham configurado seus serviços de CDN corretamente. Os CDNs são um motivo comum para flutuações nos tempos de download e devem ser considerados a causa mais provável de quaisquer alterações nos tempos de download.

O gerenciador de tags armazena todo o JavaScript em um CDN.
