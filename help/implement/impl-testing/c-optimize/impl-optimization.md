---
description: A implantação do Analytics é organizada em três etapas principais.
keywords: Implementação do Analytics
seo-description: A implantação do Analytics é organizada em três etapas principais.
seo-title: Visão geral da otimização
solution: Analytics
subtopic: Solução de problemas
title: Visão geral da otimização
topic: Desenvolvedor e implementação
uuid: 8 e 8 ecc 5 b-d 4 b 1-4 d 13-8525-39 e 4924 df 247
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Visão geral da otimização

A implantação do Analytics é organizada em três etapas principais.

1. Isso envolve colar um snippet do código HTML em cada página (ou modelo de página) de um site. O snippet do código HTML é muito pequeno (400 a 1.000 bytes) e contém variáveis JavaScript e outros identificadores que facilitam o processo de coleta de dados.
1. O snippet de código chama um arquivo da biblioteca de JavaScript, que contém funções JavaScript específicas para o Analytics e usadas durante a coleta de métricas. Se o código do Analytics for implementado corretamente, o tempo necessário para o navegador executar o arquivo da biblioteca do JavaScript geralmente será insignificante.

1. O arquivo da biblioteca faz uma solicitação de imagem para uma servidor de coleta de dados da Adobe. O servidor coleta os dados que estão sendo enviados e retorna uma imagem transparente de 1 x 1 para o navegador do visitante. Essa terceira etapa adiciona um incremento insignificante ao tempo total de download da página.

>[!NOTE]
>
>Os clientes podem adotar etapas adicionais para minimizar a sobrecarga do Analytics.

