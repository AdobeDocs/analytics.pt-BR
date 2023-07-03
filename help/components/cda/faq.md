---
title: Perguntas frequentes sobre a Análise entre dispositivos
description: Perguntas frequentes sobre o Análise entre dispositivos
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
feature: CDA
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '1927'
ht-degree: 100%

---

# Perguntas frequentes

## Como posso usar o CDA para ver como as pessoas mudam de um tipo de dispositivo para outro?

Você pode usar uma visualização de [!UICONTROL Fluxo] com a dimensão Tipo de dispositivo móvel.

1. Faça logon no Adobe Analytics e crie um novo projeto em branco da Workspace.
2. Clique na guia Visualizações à esquerda e arraste uma visualização de Fluxo para a tela à direita.
3. Clique na guia Componentes à esquerda e arraste a dimensão “Tipo de dispositivo móvel” para o local central chamado “Dimensão ou item”.
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

## Posso ver como as pessoas se movem entre diferentes experiências de usuário (por exemplo, navegador de desktop vs. navegador móvel vs. aplicativo móvel)?

O exemplo Tipo de dispositivo móvel ilustrado acima permite ver como as pessoas se movem entre tipos de dispositivos móveis e tipos de dispositivos de desktop. No entanto, isso não permite distinguir navegadores de desktop de navegadores móveis. Se você quiser esse insight, poderá criar uma variável personalizada (como uma prop ou eVar) que registra se a experiência aconteceu em um navegador de desktop, navegador móvel ou aplicativo móvel. Em seguida, você pode criar um diagrama de fluxo conforme descrito acima, usando a variável personalizada em vez da dimensão Tipo de dispositivo móvel. Isso fornece uma visão um pouco diferente sobre o comportamento entre dispositivos.

## Até que ponto o CDA compila os visitantes?

A compilação entre dispositivos do CDA ocorre em dois processos simultâneos.

* O primeiro processo é chamado de “compilação em tempo real”, que ocorre à medida que os dados fluem para o Adobe Analytics. Durante a compilação em tempo real, o CDA faz o melhor que pode para reafirmar os dados no nível da pessoa. No entanto, se a pessoa for desconhecida no momento da compilação em tempo real, o CDA voltará para a ID de visitante para representar a pessoa.

* O segundo processo é chamado de “repetição”. Durante a repetição, o CDA recua no tempo e reafirma os dados históricos, quando possível, em uma janela de pesquisa especificada. Essa janela de pesquisa é de 1 dia ou 7 dias, dependendo de como você solicitou a configuração do CDA. Durante a repetição, o CDA tenta reafirmar as ocorrências em que a pessoa era anteriormente desconhecida.

* **Se estiver usando um gráfico de dispositivos**, a Adobe mantém os mapeamentos do gráfico de dispositivos por aproximadamente seis meses. Uma ECID que não tenha atividade por mais de seis meses é removida do gráfico. Os dados já compilados no CDA não são afetados, mas as ocorrências subsequentes dessa ECID serão tratadas como uma nova pessoa.

## Como o CDA trata as ocorrências com carimbos de data e hora?

A Adobe trata as ocorrências com carimbos de data e hora como se fossem recebidas no momento do carimbo de data e hora, e não quando a Adobe recebeu a ocorrência. As ocorrências com carimbo de data e hora com mais de 1 mês nunca são compiladas pois estão fora do intervalo que a Adobe usa para compilar.

## Como o CDA se compara às IDs de visitante personalizadas?

O uso da ID de visitante personalizada é um método herdado para [conectar os usuários aos dispositivos](/help/implement/js/xdevice-visid/xdevice-connecting.md). Com uma ID de visitante personalizada, você usa a variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md) para definir explicitamente a ID usada para a lógica do visitante. A variável `visitorID` substitui todas as IDs baseadas em cookies presentes.

As IDs de visitante personalizadas têm vários efeitos colaterais indesejados que o CDA supera ou minimiza. Por exemplo, a metodologia de ID de visitante personalizada não tem recursos de [repetição](replay.md). Se um usuário for autenticado no meio de uma visita, a primeira parte da visita será associada a uma ID de visitante diferente da última parte da visita. As IDs de visitante separadas resultam no aumento de visitas e visitantes. O CDA reafirma os dados históricos para que ocorrências não autenticadas pertençam à pessoa correta.

## É possível atualizar da ID de visitante personalizada para o CDA?

Os clientes que já usam a ID de visitante personalizada podem atualizar para o CDA sem nenhuma alteração de implementação. A variável `visitorID` ainda é usada no conjunto de relatórios de origem. No entanto, o CDA ignora a variável `visitorID` no conjunto de relatórios virtual se um usuário se autenticar.

## Como o gráfico de dispositivos trata os dispositivos compartilhados?

Em algumas situações, é possível que várias pessoas façam logon no mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou um quiosque em uma loja de varejo.

* **Se estiver usando um gráfico de dispositivos**, a capacidade de lidar com dispositivos compartilhados é limitada. O gráfico de dispositivos usa um algoritmo para determinar a propriedade de um “cluster” e pode ser alterado sempre que o cluster for publicado. Os usuários do dispositivo compartilhado estão sujeitos ao cluster ao qual pertencem.
* **Se estiver usando a compilação em campo**, a prop ou eVar escolhida para ajudar a identificar usuários conectados substituirá outros identificadores. Os dispositivos compartilhados são considerados pessoas separadas, mesmo se forem originários do mesmo dispositivo.

## Como o CDA lida com situações em que uma única pessoa tem MUITOS dispositivos/ECIDs?

Em algumas situações, um usuário individual pode ser associado a um grande número de ECIDs. Isso pode ocorrer se o indivíduo usar muitos navegadores ou aplicativos e pode ser exacerbado se ele limpar os cookies com frequência ou usar o modo de navegação privado ou incognitivo do navegador.

* **Se estiver usando um gráfico de dispositivos**, o CDA limita o número de ECIDs vinculadas a determinada ID de usuário a 50. Se uma ID de usuário estiver associada a muitas ECIDs, o gráfico de dispositivos presumirá que a ID de usuário é inválida e removerá o cluster associado a essa ID de usuário. A ID de usuário é adicionada a uma lista de bloqueios para evitar que ela seja adicionada a algum cluster no futuro. O resultado no relatório é que a ID do usuário não é compilada entre os dispositivos.
* **Se estiver usando a compilação em campo**, o número de dispositivos é irrelevante em favor da prop/eVar que você escolher para ajudar a identificar os usuários conectados. Um único usuário pode pertencer a qualquer número de dispositivos sem afetar a capacidade do CDA de compilar entre os dispositivos.

## Qual é a diferença entre a métrica Pessoas no CDA e a métrica “Visitantes únicos” fora do CDA?

As métricas [Pessoas](/help/components/metrics/people.md) e [Visitantes únicos](/help/components/metrics/unique-visitors.md) têm como objetivo contar visitantes distintos (individuais). No entanto, considere a possibilidade de dois dispositivos diferentes pertencerem à mesma pessoa. O CDA mapeia os dois dispositivos para a mesma pessoa, enquanto os dois dispositivos são registrados como 2 “Visitantes únicos” separados fora do CDA.

## Qual é a diferença entre a métrica “Dispositivos únicos” no CDA e a métrica “Visitantes únicos” fora do CDA?

Essas duas métricas são aproximadamente equivalentes umas às outras. As diferenças entre as duas métricas ocorrem quando:

* Um dispositivo compartilhado mapeia várias pessoas. Nesse cenário, 1 visitante único é contado enquanto vários dispositivos exclusivos são contados.
* Um dispositivo tem tráfego não corrigido e compilado do mesmo visitante. Por exemplo, um navegador gerado identificou tráfego compilado + tráfego anônimo histórico que não foi compilado. Nesse caso, 1 visitante único é contado, enquanto 2 dispositivos únicos são contados.

Consulte [Dispositivos exclusivos](/help/components/metrics/unique-devices.md) para obter mais exemplos e detalhes sobre como funciona.

## É possível incluir métricas do CDA usando a API 2.0?

Sim. O Analysis Workspace usa a API 2.0 para solicitar dados dos servidores da Adobe e você pode visualizar chamadas de API usadas pela Adobe para criar seus próprios relatórios:

1. Enquanto estiver conectado no Analysis Workspace, acesse [!UICONTROL Ajuda] > [!UICONTROL Ativar depurador].
2. Clique no ícone de depuração no painel desejado e selecione a visualização e a hora da solicitação.
3. Localize a solicitação JSON, que você pode usar na chamada de API para a Adobe.

## O Análise entre dispositivos pode unir visitantes únicos. É possível compilar visitas?

Sim. Se um indivíduo enviar ocorrências de dois dispositivos separados dentro do tempo limite de visita do conjunto de relatórios virtual (30 minutos por padrão), eles serão agrupados na mesma visita.

## Qual é a ID de visitante mais avançada que o CDA usa? Posso exportá-la para fora do Adobe Analytics?

* **Se estiver usando um gráfico de dispositivos**, uma ID personalizada com base em seu cluster será o identificador principal.
* **Se estiver usando a compilação em campo**, uma ID personalizada com base na prop/eVar escolhida é o identificador principal.

Ambos os identificadores são calculados pela Adobe no momento em que o relatório é executado, também conhecido como [Processamento no momento do relatório](../vrs/vrs-report-time-processing.md). A natureza do processamento no momento do relatório indica que ele não é compatível com o Data Warehouse, feeds de dados ou outros recursos de exportação que a Adobe oferece.

## Como posso migrar do gráfico de dispositivos para a compilação em campo, ou vice-versa?

A mudança do gráfico de dispositivos para a compilação em campo ou vice-versa pode ser solicitada por meio do Atendimento ao cliente. No entanto, essa alteração pode levar algumas semanas ou mais para ser concluída e *dados históricos compilados do método anterior são perdidos.*

## Como a Adobe lida com limites exclusivos para uma prop ou eVar usados na compilação em campo?

O CDA extrai itens de dimensão variável do identificador antes que eles sejam otimizados para relatórios. Você não precisa se preocupar com limites únicos para fins de CDA. No entanto, se você tentou usar essa prop ou eVar em um projeto do Workspace, ainda é possível ver o item de dimensão [(tráfego baixo)](/help/technotes/low-traffic.md).

## Quantos conjuntos de relatórios da minha empresa podem ser habilitados para o CDA?

A partir de 1 de maio de 2022, qualquer nova implementação do CDA será limitada a no máximo três IDs de conjunto de relatórios (RSIDs) por cliente. O CDA não mescla conjuntos de relatórios. Cada conjunto de relatórios habilitado para o CDA precisa ser de natureza entre dispositivos (contendo dados de várias superfícies, como Web para desktop, Web móvel, aplicativo móvel etc.).

## Se a minha ID de organização tiver várias empresas em diferentes regiões, é possível habilitar o CDA para todas elas?

Não. Para a mesma ID de organização, somente uma região pode ter o CDA ativado.

## Quais são as vantagens e desvantagens de uma repetição de 7 dias em relação a uma repetição de 1 dia?

A vantagem da janela de lookback de reprodução de 7 dias é que o CDA pode voltar mais a tempo para tentar associar eventos anônimos anteriores a uma pessoa que fez logon posteriormente nesses 7 dias. As desvantagens da janela de lookback de sete dias são 1) a repetição é executada somente uma vez por semana e 2) os sete dias mais recentes estão sujeitos a alterações.

As vantagens de usar a janela de lookback de reprodução de um dia são 1) as execuções de repetição acontecem todos os dias e 2) somente o dia de ontem está sujeito a alterações. A desvantagem da janela de lookback de 1 dia é que o CDA só pode voltar 1 dia para tentar associar eventos anônimos anteriores a uma pessoa que fez logon ontem.

## O que acontecerá com os dados compilados em meus conjuntos de relatórios virtuais do CDA se minha empresa decidir fazer downgrade do Analytics Ultimate?

Se um cliente fizer o downgrade do Ultimate, ele não terá mais acesso aos dados compilados. Todos os dados compilados anteriormente serão removidos. Isso significa que os conjuntos de relatórios virtuais do CDA agora não refletirão compilações entre dispositivos. Os dados serão semelhantes ao conjunto de relatórios não compilado original.

## Por que o número total de hits no conjunto de relatórios de origem é diferente do conjunto de relatórios virtual do CDA?

O CDA usa um pipeline de processamento paralelo complexo, com vários componentes dependentes. É esperada uma incompatibilidade de dados de aproximadamente 1% entre o número total de ocorrências do conjunto de relatórios original e o do conjunto de relatórios virtual do CDA.

## Por que a métrica “Pessoas identificadas” está inflada?

O número da métrica “Pessoas identificadas” pode ser um pouco maior se o valor da prop ou do eVar do identificador for executado em uma [colisão de hash](/help/implement/validate/hash-collisions.md).

Para a compilação em campo, a variável personalizada do identificador diferencia maiúsculas e minúsculas. O número da métrica “Pessoas identificadas” pode ser significativamente maior se os valores do identificador não corresponderem letras maiúsculas e minúsculas. Por exemplo, se `bob` e `Bob` forem enviadas e esperadas como a mesma pessoa, o CDA interpreta esses dois valores como distintos.

## Ao visualizar o identificador prop/eVar, por que vejo valores diferentes de zero para a métrica “Pessoas não identificadas”?

Essa situação geralmente ocorre quando um visitante gera ocorrências autenticadas e não autenticadas na janela de relatórios. O visitante pertence a “Não identificado” e “Identificado” na dimensão [Estado identificado](/help/components/dimensions/identified-state.md), causando uma atribuição de ocorrências não identificadas a um identificador. Esse cenário pode mudar após a execução de [Reproduzir](replay.md), dependendo da frequência de repetição e da taxa de sucesso.