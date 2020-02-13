---
title: Configuração da Análise entre dispositivos
description: Saiba como configurar o Cross-Device Analytics após atender aos pré-requisitos.
translation-type: tm+mt
source-git-commit: 2faec7513624be207a6cf01545702a977a84d5fc

---


# Configuração da Análise entre dispositivos

> [!NOTE] A documentação do Cross-Device Analytics está sujeita a alterações à medida que o recurso for sendo desenvolvido. Verifique regularmente se há atualizações.

Depois que todos os pré-requisitos forem atendidos, use as seguintes etapas para ativar o Cross-Device Analytics. Você deve pertencer a um grupo de Administrador do perfil de produto ou ter privilégios de administrador no Adobe Analytics para seguir essas etapas.

> [!IMPORTANT] Todos os pré-requisitos devem ser atendidos antes de seguir essas etapas. Se todos os pré-requisitos não forem atendidos, o recurso não estará disponível ou não funcionará. Consulte [Cross-Device Analytics](cda-home.md) para obter os pré-requisitos e as limitações.

## Escolha o conjunto de relatórios entre dispositivos que será ativado para o CDA

Quando sua organização é provisionada para usar o CDA, você escolhe qual conjunto de relatórios usar. Essa opção pode ser comunicada por meio do Gerente de conta da Adobe. A Adobe ativa o conjunto de relatórios escolhido para o processamento do CDA.

## Crie um conjunto de relatórios virtuais entre dispositivos para ver a exibição entre dispositivos

Os administradores com acesso para criar conjuntos de relatórios virtuais podem criar conjuntos de relatórios virtuais do CDA da seguinte maneira:

1. Navegue até [experience.adobe.com](https://experiencecloud.adobe.com) e faça logon usando as credenciais da AdobeID.
2. Clique no ícone de 9-grid na parte superior e clique em Analytics.
3. Passe o mouse sobre Componentes na parte superior e clique em Conjuntos de relatórios virtuais.
4. Clique em Adicionar.
5. Insira um nome para o conjunto de relatórios virtual e verifique se o conjunto de relatórios habilitado para CDA está selecionado.
6. (Opcional) Aplique um segmento ao conjunto de relatórios virtual. Por exemplo, você pode aplicar um segmento que limita o conjunto de relatórios virtual a datas, depois que o CDA foi ativado e que a compilação começou. Esse segmento permite que os usuários vejam apenas os intervalos de datas compilados no VRS.
7. Clique na caixa de seleção &quot;Ativar processamento de tempo do relatório&quot;, que permite várias outras opções, incluindo o Cross-Device Analytics.
8. Clique na caixa de seleção &quot;Compilar dispositivos entre visitas de usuário&quot;.
9. Clique em Continuar, conclua a configuração do conjunto de relatórios virtual e clique em Salvar.

![Caixa de seleção CDA](assets/cda-checkbox.png)

## Adições e alterações em conjuntos de relatórios virtuais entre dispositivos

Quando o Cross-Device Analytics estiver ativado em um conjunto de relatórios virtual, observe as seguintes alterações:

* Um novo ícone entre dispositivos é exibido ao lado do nome do conjunto de relatórios virtual. Esse ícone é exclusivo para conjuntos de relatórios virtuais entre dispositivos.
* Uma nova dimensão chamada &quot;Estado identificado&quot; está disponível. Essa dimensão determina se a Experience Cloud ID dessa ocorrência é conhecida pelo gráfico do dispositivo nesse momento.
* Novas métricas chamadas &quot;Pessoas&quot; e &quot;Dispositivos únicos&quot; estão disponíveis.
* A métrica &quot;Visitantes únicos&quot; não está disponível, pois é substituída por &quot;Pessoas&quot; e &quot;Dispositivos exclusivos&quot;.
* Ao criar segmentos, o contêiner de segmento &quot;Visitante&quot; é substituído pelo contêiner &quot;Pessoa&quot;.

## Modelo do CDA Workspace

A Adobe oferece um modelo para ver dados vitais de desempenho entre dispositivos.

1. Navegue até [experience.adobe.com](https://experiencecloud.adobe.com) e faça logon usando as credenciais da AdobeID.
1. Clique no ícone de 9-grid na parte superior e clique em Analytics.
1. Clique [!UICONTROL Workspace] na parte superior e clique em [!UICONTROL Create New Project].
1. Localize o &quot;IQ da jornada: &quot;Análise entre dispositivos&quot; e, em seguida, clique em [!UICONTROL Create].
1. Se solicitado, altere o conjunto de relatórios para um que suporte CDA.

Um projeto da Analysis Workspace é criado com vários painéis. Na parte superior, um índice e uma introdução são mostrados, permitindo o contexto do relatório e a navegação para relatórios individuais. Clique em um link dentro do sumário ou expanda a tabela de um painel para exibir esses relatórios.

<!-->The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md<-->

* **Nota especial para os membros do Gráfico** de Cooperação: Mostra qual parte do conjunto de relatórios contém visitantes em regiões nas quais o gráfico cooperativo é suportado e em regiões nas quais ele não é suportado.
* **Identificação de usuários**: Mostra a frequência com que os visitantes do site são identificados usando métodos baseados no Cross-Device Analytics.
* **Medir o tamanho** do público-alvo: Mostra uma comparação entre &quot;Dispositivos únicos&quot; e &quot;Pessoas&quot;. A proporção desses dois números é conhecida como &quot;compactação entre dispositivos&quot;, uma métrica calculada visível neste painel. Essa métrica de compactação depende de uma ampla variedade de fatores:
   * Usando o gráfico Cooperativo ou Privado: em geral, as organizações que usam a cooperação de dispositivos tendem a ver melhores taxas de compactação, em relação às organizações que usam o gráfico privado.
   * Taxa de logon: quanto mais usuários entrarem no site, mais a Adobe poderá identificar e compilar visitantes entre dispositivos. Os sites com uma taxa de logon baixa também têm taxas de compactação baixas.
   * Cobertura da Experience Cloud ID: somente os visitantes com uma ECID podem ser compilados. Uma porcentagem menor de visitantes do site que usam uma ECID está correlacionada a taxas de compactação mais baixas.
   * Uso de vários dispositivos: se os visitantes do site não usarem vários dispositivos, você poderá ver taxas de compactação mais baixas.
   * Granularidade do relatório: a compactação por dia geralmente é menor do que a compactação por mês ou ano. As chances de um indivíduo usar vários dispositivos se tornam menores em um único dia do que em mais de um mês inteiro. A segmentação, a filtragem ou o uso de dimensões de detalhamento também podem mostrar uma taxa de compactação menor.
* **Segmentos** baseados em pessoas: Contém uma lista suspensa de segmentos que permite exibir dados específicos do dispositivo. Esse painel incentiva a experimentação com segmentos para ver como incluir ou excluir tipos de dispositivos afetam os relatórios.
* **Analisando a jornada** entre dispositivos: Fornece relatórios de fluxo e fallout com base no tipo de dispositivo.
* **Atribuição** entre dispositivos: Combine os recursos de QI de viagem e QI de atribuição.
* **Outras dicas e truques**: Tópicos úteis sobre o CDA que permitem que você aproveite ao máximo o uso.
