---
title: Configurar análises entre dispositivos
description: Configure um conjunto de relatórios virtual para ativar o CDA.
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 91%

---


# Configurar análises entre dispositivos

Depois que todos os pré-requisitos forem atendidos, use as seguintes etapas para ativar o Cross-Device Analytics. Você deve pertencer a um grupo de Administrador do perfil de produto ou ter privilégios de administrador no Adobe Analytics para seguir essas etapas.

>[!IMPORTANT]
>
>Todos os pré-requisitos devem ser atendidos antes de seguir essas etapas. Se todos os pré-requisitos não forem atendidos, o recurso não estará disponível ou não funcionará. Consulte a página [de](overview.md) visão geral e o método de sutura desejado (costura[baseada em](field-based-stitching.md) campo ou gráfico [](device-graph.md)de dispositivo, respectivamente) para obter os pré-requisitos e as limitações.

## Escolha o conjunto de relatórios entre dispositivos que será ativado para o CDA

Quando sua organização é provisionada para usar o CDA, você escolhe qual conjunto de relatórios usar. Essa opção pode ser comunicada por meio do Gerente de conta da Adobe. A Adobe ativa o conjunto de relatórios escolhido para o processamento do CDA.

## Crie um conjunto de relatórios virtuais entre dispositivos para ver a exibição entre dispositivos

Os administradores com acesso para criar conjuntos de relatórios virtuais podem criar conjuntos de relatórios virtuais do CDA da seguinte maneira:

1. Navegue até [experience.adobe.com](https://experiencecloud.adobe.com) e faça logon usando as credenciais da Adobe ID.
2. Clique no ícone de 9-grid na parte superior e clique em Analytics.
3. Passe o mouse sobre Componentes na parte superior e clique em Conjuntos de relatórios virtuais.
4. Clique em Adicionar.
5. Insira um nome para o conjunto de relatórios virtual e verifique se o conjunto de relatórios habilitado para CDA está selecionado.
6. (Opcional) Aplique um segmento ao conjunto de relatórios virtual. Por exemplo, você pode aplicar um segmento que limita o conjunto de relatórios virtual a datas, depois que o CDA foi ativado e que a compilação começou. Esse segmento permite que os usuários vejam apenas os intervalos de datas compilados no VRS.
7. Clique na caixa de seleção &quot;Ativar processamento de tempo do relatório&quot;, que permite várias outras opções, incluindo o Cross-Device Analytics.
8. Clique na caixa de seleção &quot;Identificar visitas de usuários em todos os dispositivos&quot;.
9. Clique em Continuar, conclua a configuração do conjunto de relatórios virtual e clique em Salvar.

![Caixa de seleção CDA](assets/cda-checkbox.png)

## Adições e alterações em conjuntos de relatórios virtuais entre dispositivos

Quando o Cross-Device Analytics estiver ativado em um conjunto de relatórios virtual, observe as seguintes alterações:

* Um novo ícone entre dispositivos é exibido ao lado do nome do conjunto de relatórios virtual. Esse ícone é exclusivo para conjuntos de relatórios virtuais entre dispositivos.
* Uma nova dimensão chamada &quot;Estado identificado&quot; está disponível. Essa dimensão determina se a Experience Cloud ID dessa ocorrência é conhecida pelo gráfico do dispositivo nesse momento.
* Novas métricas chamadas &quot;Pessoas&quot; e &quot;Dispositivos únicos&quot; estão disponíveis.
* A métrica &quot;Visitantes únicos&quot; não está disponível, pois foi substituída por &quot;Pessoas&quot; e &quot;Dispositivos únicos&quot;.
* Ao criar segmentos, o contêiner de segmento &quot;Visitante&quot; é substituído pelo contêiner &quot;Pessoa&quot;.
