---
title: Configuração da Análise entre dispositivos
description: Saiba como configurar o Cross-Device Analytics após atender aos pré-requisitos.
translation-type: ht
source-git-commit: 8c5e8d18ce4e09049d3fea07b8dd75ded6894313

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
7. Clique na caixa de seleção "Ativar processamento de tempo do relatório", que permite várias outras opções, incluindo o Cross-Device Analytics.
8. Clique na caixa de seleção "Compilar dispositivos entre visitas de usuário".
9. Clique em Continuar, conclua a configuração do conjunto de relatórios virtual e clique em Salvar.

![Caixa de seleção CDA](assets/cda-checkbox.png)

## Adições e alterações em conjuntos de relatórios virtuais entre dispositivos

Quando o Cross-Device Analytics estiver ativado em um conjunto de relatórios virtual, observe as seguintes alterações:

* Um novo ícone entre dispositivos é exibido ao lado do nome do conjunto de relatórios virtual. Esse ícone é exclusivo para conjuntos de relatórios virtuais entre dispositivos.
* Novas métricas chamadas "Pessoas" e "Dispositivos únicos" estão disponíveis.
* A métrica "Visitantes únicos" não está disponível, pois foi substituída por Pessoas e Dispositivos únicos.
* Ao criar segmentos, o contêiner de segmento "Visitante" é substituído pelo contêiner "Pessoa".

## A métrica calculada Compactação

A capacidade do Cross-Device Analytics de compilar dispositivos depende de uma grande variedade de fatores. A eficácia da capacidade do recurso de compilar dados pode ser medida com uma métrica calculada chamada Compactação. Os fatores que contribuem para a compactação incluem:

* Usando o gráfico Cooperativo ou Privado: em geral, as organizações que usam a cooperação de dispositivos tendem a ver melhores taxas de compactação, em relação às organizações que usam o gráfico privado.
* Taxa de logon: quanto mais usuários entrarem no site, mais a Adobe poderá identificar e compilar visitantes entre dispositivos. Os sites com uma taxa de logon baixa também têm taxas de compactação baixas.
* Cobertura da Experience Cloud ID: somente os visitantes com uma ECID podem ser compilados. Uma porcentagem menor de visitantes do site que usam uma ECID está correlacionada a taxas de compactação mais baixas.
* Uso de vários dispositivos: se os visitantes do site não usarem vários dispositivos, você poderá ver taxas de compactação mais baixas.
* Granularidade do relatório: a compactação por dia geralmente é menor do que a compactação por mês ou ano. As chances de um indivíduo usar vários dispositivos se tornam menores em um único dia do que em mais de um mês inteiro. A segmentação, a filtragem ou o uso de dimensões de detalhamento também podem mostrar uma taxa de compactação menor.

Para ver a compactação de sua organização para um período específico:

1. Clique em Workspace na parte superior e, em seguida, "Criar novo projeto".
2. Comece com um Projeto em branco e clique em Criar.
3. Arraste a métrica Dispositivos únicos para a área da tela chamada "Soltar uma métrica aqui".
4. Arraste a métrica Pessoas para a tela diretamente à direita do cabeçalho da métrica Dispositivos únicos para que as duas métricas fiquem lado a lado.
5. Clique no símbolo "`+`" ao lado das métricas disponíveis à esquerda para abrir o Criador de métricas calculadas.
6. Atribua a esta métrica calculada as seguintes configurações:
   * Nome: compactação entre dispositivos
   * Formato: porcentagem
   * Casas decimais: 2
   * Definição: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] Clique em "Adicionar" no canto superior direito da área de definição para adicionar um número estático. Arraste Pessoas e Dispositivos únicos da lista de métricas disponíveis à esquerda.
7. Clique em Salvar.
8. Arraste a nova métrica calculada para a tela diretamente à direita do cabeçalho da métrica Pessoas para que todas as três métricas fiquem lado a lado.
9. Opcional: o espaço de trabalho carrega a dimensão Dia por padrão. Arraste uma dimensão de data alternativa, como semana ou mês, na parte superior da dimensão Dia, se desejar uma granularidade de tempo diferente.
