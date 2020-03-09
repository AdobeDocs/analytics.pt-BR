---
description: Essas são algumas armadilhas comuns do uso do Report Builder com o Power BI.
title: Solução de problemas de integração do Power BI
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Solução de problemas de integração do Power BI

Essas são algumas armadilhas comuns do uso do Report Builder com o Power BI.

## Etapa 1. Falha na publicação para o Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

Pastas de trabalho agendadas que exigem publicação no Power BI dependem de serviços do Power BI para funcionar. Duas razões principais para uma falha na publicação são:

* Os serviços do Power BI não estão ativos.
* O usuário que agendou a pasta de trabalho não possui mais credenciais válidas para uma conta da Microsoft.

Cada tarefa agendada do Report Builder tem três tentativas por execução agendada:

* Após a primeira tentativa mal sucedida, aparecerá a mensagem “Não foi possível publicar essa pasta de trabalho agendada no Microsoft Power BI. Tentaremos novamente em breve.”
* Após a segunda tentativa mal sucedida, não aparecerá nenhuma mensagem.
* Após a terceira tentativa mal sucedida, aparecerá a mensagem: “Não foi possível publicar essa pasta de trabalho no Power BI.”

## Etapa 2. Visualizações quebradas no Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Essas são as principais razões pelas quais visualizações quebradas podem ocorrer após a publicação de solicitações do Report Builder no Power BI:

* Você editou uma solicitação no Report Builder, tal como alteração de métricas ou dimensões e depois republicou no Power BI. A edição de solicitações pode quebrar as suas visualizações.
* Você excluiu uma solicitação que foi usada em uma visualização.

