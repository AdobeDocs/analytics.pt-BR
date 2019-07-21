---
description: Os serviços de entrega de conteúdo ou as redes de distribuição de conteúdo (CDNs), como Akamai e Speedera, enviam o conteúdo Web para mais perto da borda da rede, mantendo documentos solicitados com frequência perto do local em que são acessados.
keywords: Implementação do Analytics
seo-description: Os serviços de entrega de conteúdo ou as redes de distribuição de conteúdo (CDNs), como Akamai e Speedera, enviam o conteúdo Web para mais perto da borda da rede, mantendo documentos solicitados com frequência perto do local em que são acessados.
seo-title: Redes/serviços de entrega de conteúdo
solution: Analytics
subtopic: Solução de problemas
title: Redes/serviços de entrega de conteúdo
topic: Desenvolvedor e implementação
uuid: 6 cb 57 c 59-d 0 f 9-4 ca 5-9 f 15-0 e 74 e 585 a 4 a 1
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Redes/serviços de entrega de conteúdo

Os serviços de entrega de conteúdo ou as redes de distribuição de conteúdo (CDNs), como Akamai e Speedera, enviam o conteúdo Web para mais perto da borda da rede, mantendo documentos solicitados com frequência perto do local em que são acessados.

Em geral, isso reduz a latência de acesso, o uso da largura de banda e o custo de infraestrutura.

Seu arquivo AppMeasurement para biblioteca JavaScript pode ser entregue via CDN para aprimorar o desempenho e entregar o arquivo no site do visitante. Os clientes da Adobe devem assegurar que tenham configurado seus serviços de CDN corretamente. Os CDNs são um motivo comum para flutuações nos tempos de download e devem ser considerados a causa mais provável de quaisquer alterações nos tempos de download.

O gerenciador de tags armazena todo o JavaScript em um CDN.
