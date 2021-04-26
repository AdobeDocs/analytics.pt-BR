---
title: Perguntas frequentes sobre a Análise entre dispositivos
description: Perguntas frequentes sobre o Cross-Device Analytics
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
translation-type: tm+mt
source-git-commit: 60856c2c410d7b45ba54d1ae7bdd659d181965ff
workflow-type: tm+mt
source-wordcount: '1672'
ht-degree: 81%

---

# Perguntas frequentes

## Como posso usar o CDA para ver como as pessoas mudam de um tipo de dispositivo para outro?

Você pode usar uma visualização [!UICONTROL Fluxo] com a dimensão Tipo de dispositivo móvel.

1. Faça logon no Adobe Analytics e crie um novo projeto em branco da Workspace.
2. Clique na guia Visualizações à esquerda e arraste uma visualização de Fluxo para a tela à direita.
3. Clique na guia Componentes à esquerda e arraste a dimensão &quot;Tipo de dispositivo móvel&quot; para o local central chamado &quot;Dimensão ou item&quot;.
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

## Posso ver como as pessoas se movem entre diferentes experiências de usuário (por exemplo, navegador de desktop vs. navegador móvel vs. aplicativo móvel)?

Usar o Tipo de dispositivo móvel como ilustrado acima permite ver como as pessoas se movem entre tipos de dispositivo móvel e tipos de dispositivo de desktop. Entretanto, talvez você queira distinguir os navegadores de desktop dos navegadores móveis. Uma maneira de fazer isso é criar uma eVar que registre se a experiência ocorreu em um navegador de desktop, navegador móvel ou aplicativo móvel. Em seguida, crie um Fluxograma conforme descrito acima, usando sua eVar &quot;experiência&quot;, em vez da dimensão Tipo de dispositivo móvel. Isso fornece uma visão um pouco diferente sobre o comportamento entre dispositivos.

## Até que ponto o CDA compila os visitantes?

A compilação entre dispositivos do CDA ocorre em dois processos simultâneos.

* O primeiro processo é chamado de &quot;compilação em tempo real&quot;, que ocorre à medida que os dados fluem para o Adobe Analytics. Durante a compilação em tempo real, o CDA faz o melhor que pode para reafirmar os dados no nível da pessoa. No entanto, se a pessoa for desconhecida no momento da compilação em tempo real, o CDA voltará para a ID de visitante para representar a pessoa.

* O segundo processo é chamado de &quot;repetição&quot;. Durante a repetição, o CDA recua no tempo e reafirma os dados históricos, quando possível, em uma janela de pesquisa especificada. Essa janela de pesquisa é de 1 dia ou 7 dias, dependendo de como você solicitou a configuração do CDA. Durante a repetição, o CDA tenta reafirmar as ocorrências em que a pessoa era anteriormente desconhecida.

* **Se estiver usando um gráfico de dispositivos**, a Adobe mantém os mapeamentos de dispositivo no Gráfico cooperativo e no Gráfico privado por aproximadamente 6 meses. Uma ECID que não tem atividade por mais de seis meses é removida do gráfico. Os dados já compilados no CDA não são afetados, mas as ocorrências subsequentes dessa ECID são tratadas como uma nova pessoa.

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

A métrica [Pessoas](/help/components/metrics/people.md) é semelhante à métrica [Visitantes únicos](/help/components/metrics/unique-visitors.md) na medida em que ela relata o número de indivíduos únicos. No entanto, ao usar o Cross-Device Analytics, visitantes únicos são combinados quando, de outra forma, são registrados como dois visitantes únicos separados fora do CDA. A métrica &quot;Pessoas&quot; substitui a métrica &quot;Visitantes únicos&quot; quando o Cross-Device Analytics está ativado. Uma nova métrica, [Dispositivos únicos](/help/components/metrics/unique-devices.md), está disponível e é aproximadamente igual aos Visitantes únicos fora do Cross-Device Analytics.

## Qual é a diferença entre a métrica “Dispositivos únicos” no CDA e a métrica “Visitantes únicos” fora do CDA?

Essas duas métricas são aproximadamente equivalentes umas às outras.

## É possível incluir métricas do CDA usando a API 2.0?

Sim. O Analysis Workspace usa a API 2.0 para solicitar dados dos servidores da Adobe e você pode visualizar chamadas de API usadas pela Adobe para criar seus próprios relatórios:

1. Enquanto estiver conectado no Analysis Workspace, acesse [!UICONTROL Ajuda] > [!UICONTROL Ativar depurador].
2. Clique no ícone de depuração no painel desejado e selecione a visualização e a hora da solicitação.
3. Localize a solicitação JSON, que você pode usar na chamada de API para a Adobe.

## O Cross-Device Analytics pode unir visitantes únicos. É possível compilar visitas?

Sim. Se um indivíduo enviar ocorrências de dois dispositivos separados dentro do tempo limite de visita do conjunto de relatórios virtual (30 minutos por padrão), eles serão agrupados na mesma visita.

## Qual é a ID de visitante mais avançada que o CDA usa? Posso exportá-la para fora do Adobe Analytics?

* **Se estiver usando um gráfico de dispositivos**, uma ID personalizada com base em seu cluster será o identificador principal.
* **Se estiver usando a compilação em campo**, uma ID personalizada com base na prop/eVar escolhida é o identificador principal.

Ambos os identificadores são calculados pela Adobe no momento em que o relatório é executado, também conhecido como [Processamento no momento do relatório](../vrs/vrs-report-time-processing.md). A natureza do processamento no momento do relatório indica que ele não é compatível com o Data Warehouse, feeds de dados ou outros recursos de exportação que a Adobe oferece.

## Como posso migrar do gráfico de dispositivos para a compilação em campo, ou vice-versa?

Se você quiser trocar os métodos de identificação do CDA, entre em contato com o Gerente de conta da sua organização. O Gerente de conta pode provisionar seu conjunto de relatórios para o método desejado para identificar pessoas. *Os dados históricos compilados do método anterior são perdidos.*

## Como a Adobe manipula limites exclusivos para uma eVar usada na compilação em campo?

O CDA extrai itens de dimensão de eVar antes de serem otimizados para o relatórios. Você não precisa se preocupar com limites únicos para fins de CDA. No entanto, se você tentou usar essa prop/eVar em um projeto do Workspace, ainda é possível ver o item de dimensão [(tráfego baixo)](/help/technotes/low-traffic.md).

## Quantos conjuntos de relatórios da minha empresa podem ser habilitados para o CDA?

Vários conjuntos de relatórios podem estar ativados, no entanto, cada conjunto de relatórios adicional aumentará o tempo de provisionamento geral se vários conjuntos de relatórios forem solicitados ao mesmo tempo. O CDA não mescla conjuntos de relatórios. Cada conjunto de relatórios habilitado para o CDA precisa ser de natureza entre dispositivos (contendo dados de várias superfícies, como Web para desktop, Web móvel, aplicativo móvel etc.)

## Se minha organização de Experience Cloud (também conhecida como organização IMS) tem várias empresas em diferentes regiões, posso habilitar o CDA para todas elas?

Não. Para a mesma organização, somente uma região pode ter o CDA ativado.

## Quais são as vantagens e desvantagens de uma repetição de 7 dias versus uma repetição de 1 dia?

A vantagem da janela de lookback de reprodução de 7 dias é que o CDA pode voltar mais a tempo para tentar associar eventos anônimos anteriores a uma pessoa que fez logon posteriormente nesses 7 dias. As desvantagens da janela de lookback de 7 dias são 1) a repetição é executada somente uma vez por semana e 2) os 7 dias mais recentes estão sujeitos a alterações.

As vantagens de usar a janela de lookback de reprodução de 1 dia são 1) as execuções de repetição todos os dias e 2) somente ontem estão sujeitas a alterações. A desvantagem da janela de lookback de 1 dia é que o CDA só pode voltar 1 dia para tentar associar eventos anônimos anteriores a uma pessoa que fez logon ontem.

## O que acontece com os dados compilados em meus conjuntos de relatórios virtuais do CDA se minha empresa decidir fazer o download do Analytics Ultimate?

Se um cliente fizer o download do Ultimate, ele não terá mais acesso aos dados compilados. Todos os dados compilados anteriormente serão removidos. Isso significa que os conjuntos de relatórios virtuais do CDA agora não refletirão compilações entre dispositivos. Os dados serão semelhantes ao conjunto de relatórios não corrigido original.
