---
description: 'null'
seo-description: 'null'
seo-title: Solução de problemas de segmentação
title: Solução de problemas de segmentação
uuid: 8476 d 617-4 b 44-4 ff 2-9 b 3 a -02685 f 666 afc
translation-type: tm+mt
source-git-commit: 50069fe860d58f04df7ffe63714afeef9d3d7a28

---


# Solução de problemas de segmentação

## Error: "Incompatible elements in this segment" {#section_B167EE10A0844E649DD7E14D0BAEDA17}

Esse erro ocorre quando você tenta salvar um segmento na pasta Data warehouse, na qual o segmento contém elementos incompatíveis com o Data warehouse. Para solucionar este erro, execute uma destas duas ações:

* Salve o segmento em uma pasta diferente.
* Remova ou altere as porções incompatíveis do segmento.

## Por que o meu segmento não retorna dados? {#section_999749CBBE984142AEA49A6E68E6730A}

Possíveis motivos:

* Aninhamento reverso: por exemplo, o aninhamento de um contêiner de Visitante em um contêiner de Visitante.
* O relatório não oferece suporte para a segmentação.
* Nenhum dado corresponde ao critério de segmentação.

## Por que não consigo ver o segmento que criei no Gerenciador de segmentos? {#section_BE0A0930A2694A23BB32DA71696D52CE}

Possíveis motivos:

* Algumas dimensões estão disponíveis somente no Data warehouse, e não no Gerenciador de segmentos.
* O segmento não é compatível com o Relatórios e análises.
* O segmento é marcado somente para um conjunto de relatórios específico.
* Um segmento compartilhado pode ter sido excluído por outro usuário.
* Os segmentos não puderam ser carregados devido a um problema no datacenter ou no cache do navegador.
* O segmento não foi salvo.
* O endereço IP pode estar bloqueado na extremidade do usuário.

## Por que os dados de página exibidos depois da aplicação de um segmento parecem incorretos? {#section_B226AF69FE06463A8BC5337FDA8D4949}

Possíveis motivos:

* As regras/operadores estão incorretos para o resultado exigido.
* Aplicação incorreta dos contêineres ao segmento.
* As variáveis de tráfego usadas para segmentar não estão definidas corretamente ou expiraram.

