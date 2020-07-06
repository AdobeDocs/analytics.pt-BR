---
title: Configuração da Análise entre dispositivos
description: Saiba como configurar o Cross-Device Analytics após atender aos pré-requisitos.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 100%

---


# Configuração da Análise entre dispositivos

Depois que todos os pré-requisitos forem atendidos, use as seguintes etapas para ativar o Cross-Device Analytics. Você deve pertencer a um grupo de Administrador do perfil de produto ou ter privilégios de administrador no Adobe Analytics para seguir essas etapas.

>[!IMPORTANT]
>
>Todos os pré-requisitos devem ser atendidos antes de seguir essas etapas. Se todos os pré-requisitos não forem atendidos, o recurso não estará disponível ou não funcionará. Consulte [Cross-Device Analytics](cda-home.md) para obter os pré-requisitos e as limitações.

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

## Modelo do CDA Workspace

A Adobe oferece um modelo para ver dados essenciais de desempenho entre dispositivos.

1. Navegue até [experience.adobe.com](https://experiencecloud.adobe.com) e faça logon usando as credenciais da Adobe ID.
1. Clique no ícone de 9-grid na parte superior e clique em Analytics.
1. Clique em [!UICONTROL Workspace] na parte superior e em seguida em [!UICONTROL Criar novo projeto].
1. Localize o &quot;IQ da jornada: Análise entre dispositivos&quot; e, em seguida, clique em [!UICONTROL Criar].
1. Se solicitado, altere o conjunto de relatórios para um compatível com CDA.

É criado um projeto do Analysis Workspace com vários painéis. Na parte superior, um índice e uma introdução são mostrados, permitindo o contexto do relatório e a navegação para relatórios individuais. Clique em um link dentro do índice ou expanda a tabela de um painel para visualizar esses relatórios.

<!-->The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md<-->

* **Nota especial para os membros do Gráfico de cooperação**: mostra qual parte do conjunto de relatórios contém visitantes em regiões onde o gráfico cooperativo é aceito e em regiões onde ele não é aceito.
* **Identificação de usuários**: mostra a frequência com que os visitantes do site são identificados usando métodos com base na Análise entre dispositivos.
* **Medição do tamanho do público-alvo**: mostra uma comparação entre &quot;Dispositivos únicos&quot; e &quot;Pessoas&quot;. A proporção desses dois números é conhecida como &quot;compactação entre dispositivos&quot;, uma métrica calculada visível neste painel. Essa métrica de compactação depende de uma ampla variedade de fatores:
   * Usando o gráfico Cooperativo ou Privado: em geral, as organizações que usam a cooperação de dispositivos tendem a ver melhores taxas de compactação, em relação às organizações que usam o gráfico privado.
   * Taxa de logon: quanto mais usuários entrarem no site, mais a Adobe poderá identificar e compilar visitantes entre dispositivos. Os sites com uma taxa de logon baixa também têm taxas de compactação baixas.
   * Cobertura da Experience Cloud ID: somente os visitantes com uma ECID podem ser compilados. Uma porcentagem menor de visitantes do site que usam uma ECID está correlacionada a taxas de compactação mais baixas.
   * Uso de vários dispositivos: se os visitantes do site não usarem vários dispositivos, você poderá ver taxas de compactação mais baixas.
   * Granularidade do relatório: a compactação por dia geralmente é menor do que a compactação por mês ou ano. As chances de um indivíduo usar vários dispositivos se tornam menores em um único dia do que em mais de um mês inteiro. A segmentação, a filtragem ou o uso de dimensões de detalhamento também podem mostrar uma taxa de compactação menor.
* **Segmentos com base em pessoas**: contêm uma lista suspensa de segmentos que permitem visualizar dados específicos do dispositivo. Esse painel incentiva a experimentação com segmentos para ver como a inclusão ou exclusão de tipos de dispositivos afetam os relatórios.
* **Análise da jornada entre dispositivos**: fornece relatórios de fluxo e fallout de acordo com o tipo de dispositivo.
* **Atribuição entre dispositivos**: combine os recursos de Journey IQ e Attribution IQ.
* **Outras dicas e truques**: tópicos úteis sobre o CDA que permitem que você o aproveite ao máximo.
