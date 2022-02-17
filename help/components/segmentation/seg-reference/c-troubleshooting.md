---
description: Solucione e corrija problemas relacionados a segmentos.
title: Solução de problemas de segmentação
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 100%

---

# Solução de problemas de segmentação

## Erro: “Elementos incompatíveis neste segmento”  {#incompatible}

Esse erro ocorre quando você tenta salvar um segmento na pasta Data Warehouse, na qual o segmento contém elementos incompatíveis com o Data Warehouse. Para solucionar este erro, execute uma destas duas ações:

* Salve o segmento em uma pasta diferente.
* Remova ou altere as porções incompatíveis do segmento.

## Por que o meu segmento não retorna dados? {#no-data}

Possíveis motivos:

* Aninhamento reverso: por exemplo, o aninhamento de um contêiner de Visitante em um contêiner de Visitante.
* O relatório não oferece suporte para a segmentação.
* Nenhum dado corresponde ao critério de segmentação.

## Por que não consigo ver o segmento que criei no Gerenciador de segmentos? {#invisible}

Possíveis motivos:

* Algumas dimensões estão disponíveis somente no Data Warehouse, e não no Gerenciador de segmentos.
* O segmento não é compatível com o Reports &amp; Analytics.
* O segmento é marcado somente para um conjunto de relatórios específico.
* Um segmento compartilhado pode ter sido excluído por outro usuário.
* Os segmentos não puderam ser carregados devido a um problema no datacenter ou no cache do navegador.
* O segmento não foi salvo.
* O endereço IP pode estar bloqueado na extremidade do usuário.

## Por que os dados de página exibidos depois da aplicação de um segmento parecem incorretos? {#page-data}

Possíveis motivos:

* As regras/operadores estão incorretos para o resultado exigido.
* Aplicação incorreta dos contêineres ao segmento.
* As variáveis de tráfego usadas para segmentar não estão definidas corretamente ou expiraram.
