---
title: Configurar o Cross-Device Analytics
description: Configure um conjunto de relatórios virtual para ativar o CDA.
exl-id: e6d4e0c2-6b85-4f89-b51f-c0eed7a4e3da
source-git-commit: 005cb590f4f7d31d3de801437a0ba6fa25b2ea64
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 89%

---

# Configurar o Cross-Device Analytics

Depois que todos os pré-requisitos forem atendidos, use as seguintes etapas para ativar o Cross-Device Analytics. Você deve pertencer a um grupo de Administrador do perfil de produto ou ter privilégios de administrador no Adobe Analytics para seguir essas etapas.

>[!IMPORTANT]
>
>Todos os pré-requisitos devem ser atendidos antes de seguir essas etapas. Se todos os pré-requisitos não forem atendidos, o recurso não estará disponível ou não funcionará. Consulte a [página de visão geral](overview.md) e o método de união desejado ([União com base em arquivo](field-based-stitching.md) ou [gráfico de dispositivos](device-graph.md), respectivamente) para ver os pré-requisitos e as limitações.

## Abra um ticket no Atendimento ao cliente para provisionar o CDA em seu conjunto de relatórios entre dispositivos

O CDA é provisionado em seu conjunto de relatórios entre dispositivos pela engenharia da Adobe. Para iniciar esse processo, entre em contato com o Atendimento ao cliente e esteja preparado para fornecer as seguintes informações:

* Sua ID organizacional da Adobe Experience Cloud (uma sequência alfanumérica terminando em @AdobeOrg)
* A ID de conjunto de relatórios para o conjunto de relatórios entre dispositivos que você deseja ativar com o CDA
* Qual método de CDA você deseja usar (costura baseada em campo, gráfico privado da Adobe ou gráfico cooperativo da Adobe)
* Se você pretende usar a costura baseada em campo, a propriedade ou eVar que contém a ID do usuário
* Sua preferência por frequência de repetição e duração da retrospectiva. As opções incluem uma repetição uma vez por semana com uma janela de retrospectiva de sete dias ou uma repetição todos os dias com uma janela de retrospectiva de um dia.

Após fornecer essas informações ao Atendimento ao cliente, ele trabalhará com a engenharia de Adobe para ativar o conjunto de relatórios escolhido para o processamento do CDA.

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
* Uma nova dimensão chamada [Estado identificado](../dimensions/identified-state.md) está disponível. Essa dimensão determina se a Experience Cloud ID dessa ocorrência é conhecida pelo gráfico do dispositivo nesse momento.
* Novas métricas chamadas [Pessoas](../metrics/people.md) e [Dispositivos únicos](../metrics/unique-devices.md) estão disponíveis.
* A métrica [Visitantes únicos](../metrics/unique-visitors.md) não está disponível, pois foi substituída por Pessoas e Dispositivos únicos.
* Ao criar segmentos, o contêiner de segmento &quot;Visitante&quot; é substituído pelo contêiner &quot;Pessoa&quot;.
