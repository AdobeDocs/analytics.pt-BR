---
title: Configuração da Análise entre dispositivos
description: Saiba como configurar o Cross-Device Analytics após atender aos pré-requisitos.
translation-type: tm+mt
source-git-commit: 8c5e8d18ce4e09049d3fea07b8dd75ded6894313

---


# Configuração da Análise entre dispositivos

> [!NOTE] A documentação do Cross-Device Analytics está sujeita a alterações à medida que o recurso for sendo desenvolvido. Verifique regularmente se há atualizações.

Depois que todos os pré-requisitos forem atendidos, use as seguintes etapas para ativar o Cross-Device Analytics. Você deve pertencer a um grupo Administrador do perfil do produto ou ter privilégios de administrador no Adobe Analytics para seguir essas etapas.

> [!IMPORTANT] Todos os pré-requisitos devem ser atendidos antes de seguir essas etapas. Se todos os pré-requisitos não forem atendidos, o recurso não estará disponível ou não funcionará. Consulte Análises [](cda-home.md) entre dispositivos para obter os pré-requisitos e as limitações.

## Escolha o conjunto de relatórios entre dispositivos que será ativado para CDA

Quando sua organização está provisionada para usar o CDA, você escolhe qual conjunto de relatórios usar. Essa opção pode ser comunicada por meio do seu Gerente de contas da Adobe. A Adobe então ativa seu conjunto de relatórios escolhido para processamento CDA.

## Criar um conjunto de relatórios virtuais entre dispositivos para ver a exibição entre dispositivos

Os administradores com acesso para criar conjuntos de relatórios virtuais podem criar conjuntos de relatórios virtuais CDA da seguinte maneira:

1. Navegue até [experience.adobe.com](https://experiencecloud.adobe.com) e faça logon usando suas credenciais da AdobeID.
2. Clique no ícone de grade de 9 na parte superior e clique em Analytics.
3. Passe o mouse sobre Componentes na parte superior e clique em Conjuntos de relatórios virtuais.
4. Clique em Adicionar.
5. Insira um nome para o conjunto de relatórios virtual e verifique se o conjunto de relatórios habilitado para CDA está selecionado.
6. (Opcional) Aplique um segmento ao conjunto de relatórios virtual. Por exemplo, você pode aplicar um segmento que limita o conjunto de relatórios virtual a datas depois que o CDA foi ativado e a sutura começou. Esse segmento permite que os usuários vejam apenas intervalos de datas marcados no VRS.
7. Clique na caixa de seleção 'Ativar processamento de tempo do relatório', que permite várias outras opções, incluindo a Análise entre dispositivos.
8. Clique na caixa de seleção 'Stitch User Visits Across Devices'.
9. Clique em Continuar, conclua a configuração do conjunto de relatórios virtual e clique em Salvar.

![Caixa de seleção CDA](assets/cda-checkbox.png)

## Adições e alterações em conjuntos de relatórios virtuais entre dispositivos

Quando a Análise entre dispositivos estiver ativada em um conjunto de relatórios virtual, observe as seguintes alterações:

* Um novo ícone entre dispositivos é exibido ao lado do nome do conjunto de relatórios virtual. Esse ícone é exclusivo para conjuntos de relatórios virtuais entre dispositivos.
* Novas métricas chamadas "Pessoas" e "Dispositivos exclusivos" estão disponíveis.
* A métrica "Visitantes únicos" não está disponível, pois é substituída por Pessoas e Dispositivos únicos.
* Ao criar segmentos, o contêiner de segmento "Visitante" é substituído por um contêiner "Pessoa".

## A métrica calculada Compactação

A capacidade do Cross-Device Analytics de unir dispositivos depende de uma grande variedade de fatores. A eficácia da capacidade do recurso de unir dados pode ser medida com uma métrica calculada chamada compactação. Os fatores que contribuem para a compressão incluem:

* Usando o gráfico de cooperativa ou privado: Geralmente, as organizações que usam a cooperativa de dispositivos tendem a ver taxas de compactação melhores do que as organizações que usam o gráfico privado.
* Taxa de logon: Quanto mais usuários fizerem logon em seu site, mais a Adobe poderá identificar e unir visitantes em dispositivos. Os sites com baixa taxa de logon também têm taxas de compactação baixas.
* Cobertura da Experience Cloud ID: Somente os visitantes com uma ECID podem ser agrupados. Uma porcentagem menor de visitantes do site usando um ECID correlaciona-se a taxas de compactação mais baixas.
* Uso de vários dispositivos: Se os visitantes do seu site não usarem vários dispositivos, você poderá ver taxas de compactação mais baixas.
* Granularidade do relatório: A compactação por dia geralmente é menor do que a compactação por mês ou ano. As chances de um indivíduo usar vários dispositivos se tornam menores em um único dia do que em mais de um mês inteiro. A segmentação, filtragem ou uso de dimensões de detalhamento também pode mostrar uma taxa de compactação menor.

Para ver a compactação de sua organização para um determinado período:

1. Clique em Espaço de trabalho na parte superior e em 'Criar novo projeto'.
2. Comece com um projeto em branco e clique em Criar.
3. Arraste a métrica Dispositivos únicos para a área de tela chamada 'Solte uma métrica aqui'.
4. Arraste a métrica de Pessoas para a tela diretamente à direita do cabeçalho da métrica de Dispositivos únicos, para que as duas métricas fiquem lado a lado.
5. Clique no símbolo '`+`' ao lado das métricas disponíveis à esquerda para abrir o Criador de métricas calculadas.
6. Atribua a esta métrica calculada as seguintes configurações:
   * Nome: Compactação entre dispositivos
   * Formato: Porcentagem
   * Casas decimais: 2
   * Definição: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] Clique em "Adicionar" no canto superior direito da área de definição para adicionar um número estático. Arraste Pessoas e Dispositivos únicos da lista de métricas disponíveis à esquerda.
7. Clique em Salvar.
8. Arraste a nova métrica calculada para a tela diretamente à direita do cabeçalho da métrica de Pessoas, de modo que todas as três métricas fiquem lado a lado.
9. Opcional: O espaço de trabalho carrega a dimensão Dia por padrão. Arraste uma dimensão de data alternativa, como semana ou mês, sobre a dimensão Dia se desejar uma granularidade de tempo diferente.
