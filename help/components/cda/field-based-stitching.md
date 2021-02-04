---
title: Compilação em campo
description: Entenda os pré-requisitos e as limitações da compilação de dados usando a compilação em campo.
translation-type: ht
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: ht
source-wordcount: '226'
ht-degree: 100%

---


# Compilação em campo

O Cross-Device Analytics fornece dois métodos distintos para compilar dados. Esse método depende de uma variável do Analytics, como uma [prop](/help/implement/vars/page-vars/prop.md) ou [eVar](/help/implement/vars/page-vars/evar.md), para conter um identificador de pessoa. Ele usa essa variável como base para vincular dispositivos.

## Pré-requisitos específicos da compilação em campo

Se você pretende implementar o Cross-Device Analytics usando a compilação em campo, as seguintes etapas são obrigatórias. Trabalhe com as equipes em sua organização e com seu Gerente de conta da Adobe para atender a todos os itens a seguir.

>[!IMPORTANT]
>
>O não cumprimento de todos os pré-requisitos pode gerar a incapacidade de ativar o Cross-Device Analytics ou resultados inadequados ao compilar os dados.

* Todos os pré-requisitos estão listados na [página de visão geral](overview.md).
* Sua implementação deve definir uma prop ou eVar que identifique exclusivamente um indivíduo sempre que possível, como quando um usuário faz logon ou abre um email. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Comunique a variável de identificação desejada ao seu Gerente de conta quando provisionado para a compilação em campo.

## Limitações específicas da compilação em campo

* A compilação em campo funciona melhor em conjuntos de relatórios que têm uma alta taxa de identificação do usuário. Se o conjunto de relatórios tiver uma baixa taxa de identificação ou logon, considere usar o [Gráfico cooperativo](device-graph.md).

## Próximas etapas

Assim que sua organização atender a todos os requisitos e entender as limitações, você poderá iniciar a [Configuração do Cross-Device Analytics](setup.md).