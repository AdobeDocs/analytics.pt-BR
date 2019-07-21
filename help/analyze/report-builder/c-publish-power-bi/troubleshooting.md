---
description: Essas são algumas armadilhas comuns do uso do Construtor de relatórios com o Power BI.
seo-description: Essas são algumas armadilhas comuns do uso do Construtor de relatórios com o Power BI.
seo-title: Solução de problemas de integração do Power BI
title: Solução de problemas de integração do Power BI
uuid: c 1 e 7 e 164-4 bc 6-4513-9332-92 c 53 be 021 cc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Solução de problemas de integração do Power BI

Essas são algumas armadilhas comuns do uso do Construtor de relatórios com o Power BI.

## Etapa 1. Failure to publish to Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

Pastas de trabalho agendadas que exigem publicação no Power BI dependem de serviços do Power BI para funcionar. Duas razões principais para uma falha na publicação são:

* Os serviços do Power BI não estão ativos.
* O usuário que agendou a pasta de trabalho não possui mais credenciais válidas para uma conta da Microsoft.

Cada tarefa agendada do Construtor de relatórios tem três tentativas por execução agendada:

* Após a primeira tentativa mal sucedida, aparecerá a mensagem “Não foi possível publicar essa pasta de trabalho agendada no Microsoft Power BI. Tentaremos novamente em breve.”
* Após a segunda tentativa mal sucedida, não aparecerá nenhuma mensagem.
* Após a terceira tentativa mal sucedida, aparecerá a mensagem: “Não foi possível publicar essa pasta de trabalho no Power BI.”

## Etapa 2: Broken visualizations in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Essas são as principais razões pelas quais visualizações quebradas podem ocorrer após a publicação de solicitações do Construtor de relatórios no Power BI:

* Você editou uma solicitação no Construtor de relatórios, tal como alteração de métricas ou dimensões e depois republicou no Power BI. A edição de solicitações pode quebrar as suas visualizações.
* Você excluiu uma solicitação que foi usada em uma visualização.

