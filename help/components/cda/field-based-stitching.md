---
title: Arranque em campo
description: Entenda os pré-requisitos e as limitações da sutura de dados usando a sutura baseada em campo.
translation-type: tm+mt
source-git-commit: 2e7ec3b2e4401b02005b3099dae2bb34c64a6846
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 23%

---


# Arranque em campo

O Analytics entre dispositivos fornece dois métodos distintos para unir dados. Esse método depende de uma variável do Analytics, como uma [prop](/help/implement/vars/page-vars/prop.md) ou [eVar](/help/implement/vars/page-vars/evar.md), para conter um identificador de pessoa. Ela usa essa variável como base para vincular dispositivos.

## Pré-requisitos específicos da costura baseada em campo

Se você pretende implementar o Analytics entre dispositivos usando a identificação baseada em campo, as seguintes opções são obrigatórias. Trabalhe com as equipes em sua organização e com seu Gerente de conta da Adobe para atender a todos os itens a seguir.

>[!IMPORTANT] O não cumprimento de todos os pré-requisitos pode gerar a incapacidade de ativar o Cross-Device Analytics ou resultados inadequados ao compilar os dados.

* Todos os pré-requisitos listados na página [de](overview.md)visão geral.
* Sua implementação deve definir uma prop ou eVar que identifique exclusivamente um indivíduo sempre que possível, como quando um usuário faz logon ou abre um email. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Comunique a variável de identificação desejada ao seu Gerente de conta quando provisionado para a identificação baseada em campo.

## Limitações específicas à costura em campo

* A costura baseada em campo funciona melhor em conjuntos de relatórios que têm uma alta taxa de identificação do usuário. Se o conjunto de relatórios tiver uma baixa taxa de identificação ou login, considere usar o gráfico [](device-graph.md)Co-op.

## Próximas etapas

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).