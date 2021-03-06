---
description: Solucione problemas e corrija problemas relacionados a segmentos.
title: Solução de problemas de segmentação
uuid: 8476d617-4b44-4ff2-9b3a-02685f666afc
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 96%

---


# Solução de problemas de segmentação

## Erro: “Elementos incompatíveis neste segmento” {#section_B167EE10A0844E649DD7E14D0BAEDA17}

Esse erro ocorre quando você tenta salvar um segmento na pasta Data Warehouse, na qual o segmento contém elementos incompatíveis com o Data Warehouse. Para solucionar este erro, execute uma destas duas ações:

* Salve o segmento em uma pasta diferente.
* Remova ou altere as porções incompatíveis do segmento.

## Por que o meu segmento não retorna dados? {#section_999749CBBE984142AEA49A6E68E6730A}

Possíveis motivos:

* Aninhamento reverso: por exemplo, o aninhamento de um contêiner de Visitante em um contêiner de Visitante.
* O relatório não oferece suporte para a segmentação.
* Nenhum dado corresponde ao critério de segmentação.

## Por que não consigo ver o segmento que criei no Gerenciador de segmentos?  {#section_BE0A0930A2694A23BB32DA71696D52CE}

Possíveis motivos:

* Algumas dimensões estão disponíveis somente no Data Warehouse, e não no Gerenciador de segmentos.
* O segmento não é compatível com o Reports &amp; Analytics.
* O segmento é marcado somente para um conjunto de relatórios específico.
* Um segmento compartilhado pode ter sido excluído por outro usuário.
* Os segmentos não puderam ser carregados devido a um problema no datacenter ou no cache do navegador.
* O segmento não foi salvo.
* O endereço IP pode estar bloqueado na extremidade do usuário.

## Por que os dados de página exibidos depois da aplicação de um segmento parecem incorretos?  {#section_B226AF69FE06463A8BC5337FDA8D4949}

Possíveis motivos:

* As regras/operadores estão incorretos para o resultado exigido.
* Aplicação incorreta dos contêineres ao segmento.
* As variáveis de tráfego usadas para segmentar não estão definidas corretamente ou expiraram.

