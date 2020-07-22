---
title: Perguntas frequentes sobre a Análise entre dispositivos
description: Perguntas frequentes sobre o Cross-Device Analytics
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1301'
ht-degree: 52%

---


# Perguntas frequentes

## Como posso usar o CDA para ver como as pessoas mudam de um tipo de dispositivo para outro?

Você pode usar uma visualização de Fluxo com a dimensão Tipo de dispositivo móvel.

1. Faça logon no Adobe Analytics e crie um novo projeto em branco da Workspace.
2. Clique na guia Visualizações à esquerda e arraste uma visualização de Fluxo para a tela à direita.
3. Clique na guia Componentes à esquerda e arraste a dimensão &quot;Tipo de dispositivo móvel&quot; para o local central chamado &quot;Dimensão ou item&quot;.
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

## Posso ver como as pessoas se movem entre diferentes experiências de usuário (por exemplo, navegador de desktop vs. navegador móvel vs. aplicativo móvel)?

Usar o Tipo de dispositivo móvel como ilustrado acima permite ver como as pessoas se movem entre tipos de dispositivo móvel e tipos de dispositivo de desktop. Entretanto, talvez você queira distinguir os navegadores de desktop dos navegadores móveis. Uma maneira de fazer isso é criar uma eVar que registre se a experiência ocorreu em um navegador de desktop, navegador móvel ou aplicativo móvel. Em seguida, crie um Fluxograma conforme descrito acima, usando sua eVar &quot;experiência&quot;, em vez da dimensão Tipo de dispositivo móvel. Isso fornece uma visão um pouco diferente sobre o comportamento entre dispositivos.

## Até que ponto o CDA compila os visitantes?

A Adobe mantém os dados de identificação do dispositivo por aproximadamente 30 dias. Se um dispositivo não for inicialmente identificado, mas for identificado posteriormente em 30 dias, o CDA volta e reafirma esse dispositivo como pertencente à pessoa identificada em até 30 dias no passado. Se algum comportamento não identificado de um usuário sair da janela de lookback de 30 dias, essa parte da jornada do usuário não é compilada.

* **Se estiver usando um gráfico** de dispositivo, a Adobe mantém os mapeamentos de dispositivo no Gráfico cooperativo e no Gráfico privado por aproximadamente 6 meses. Uma ECID que não tem atividade por mais de seis meses é removida do gráfico. Os dados já agrupados no CDA não são afetados, mas as ocorrências subsequentes desse ECID são tratadas como uma nova pessoa.

## Como o CDA trata as ocorrências com carimbos de data e hora?

A Adobe trata as ocorrências com carimbos de data e hora como se fossem recebidas no momento do carimbo de data e hora, e não quando a Adobe recebeu a ocorrência. As ocorrências com carimbo de data e hora com mais de 1 mês nunca são costuradas, pois estão fora do intervalo que a Adobe usa para costurar.

## Como o CDA se compara às IDs de visitante personalizadas?

Using a custom visitor ID is a legacy method to [connect users across devices](/help/implement/js/xdevice-visid/xdevice-connecting.md). Com uma ID de visitante personalizada, você usa a variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md) para definir explicitamente a ID usada para a lógica do visitante. A variável `visitorID` substitui todas as IDs baseadas em cookies presentes.

As IDs de visitante personalizadas têm vários efeitos colaterais indesejados que o CDA supera ou minimiza. For example, the custom visitor ID methodology has no [replay](replay.md) capabilities. Se um usuário for autenticado no meio de uma visita, a primeira parte da visita será associada a uma ID de visitante diferente da última parte da visita. As IDs de visitante separadas resultam no aumento de visitas e visitantes. O CDA reafirma os dados históricos para que ocorrências não autenticadas pertençam à pessoa correta.

## É possível atualizar da ID de visitante personalizada para o CDA?

Os clientes que já usam a ID de Visitante personalizada podem atualizar para o CDA sem nenhuma alteração de implementação. A `visitorID` variável ainda é usada no conjunto de relatórios de origem. No entanto, o CDA ignora a `visitorID` variável no conjunto de relatórios virtual se um usuário se autenticar.

## Como o gráfico de dispositivos trata os dispositivos compartilhados?

Em algumas situações, é possível que várias pessoas façam logon no mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou um quiosque em uma loja de varejo.

* **Se estiver usando um gráfico** de dispositivos, a capacidade de lidar com dispositivos compartilhados é limitada. O gráfico de dispositivos usa um algoritmo para determinar a propriedade de um &quot;cluster&quot; e pode ser alterado sempre que o cluster for publicado. Os usuários do dispositivo compartilhado estão sujeitos ao cluster ao qual pertencem.
* **Se estiver usando a sutura** baseada em campo, a prop ou eVar que você escolher para ajudar a identificar usuários conectados substituirá outros identificadores. Os dispositivos compartilhados são considerados pessoas separadas, mesmo se forem originários do mesmo dispositivo.

## Como o CDA lida com situações em que uma única pessoa tem MUITOS dispositivos/ECIDs?

Em algumas situações, um usuário individual pode ser associado a um grande número de ECIDs. Isso pode ocorrer se o indivíduo usar muitos navegadores ou aplicativos e pode ser exacerbado se ele limpar os cookies com frequência ou usar o modo de navegação privado ou incognitivo do navegador.

* **Se estiver usando um gráfico** de dispositivo, o CDA limita o número de ECIDs que se vinculam a uma determinada ID de usuário para 50. Se uma ID de usuário estiver associada a muitos ECIDs, o gráfico de dispositivo assumirá que a ID de usuário é inválida e removerá o cluster associado a essa ID de usuário. A ID de usuário é adicionada a uma lista de bloqueios para evitar que ela seja adicionada a qualquer cluster no futuro. O resultado no relatórios é que a ID do usuário não é costurada em dispositivos.
* **Se estiver usando a sutura** baseada em campo, o número de dispositivos é irrelevante em favor da prop/eVar que você escolher para ajudar a identificar os usuários conectados. Um único usuário pode pertencer a qualquer número de dispositivos sem afetar a capacidade do CDA de unir os dispositivos.

## Qual é a diferença entre a métrica de Pessoas no CDA e a métrica de Visitantes únicos fora do CDA?

The [People](/help/components/metrics/people.md) metric is similar to the [Unique Visitors](/help/components/metrics/unique-visitors.md) metric in that it reports on the number of unique individuals. No entanto, ao usar o Cross-Device Analytics, visitantes únicos são combinados quando, de outra forma, são registrados como dois visitantes exclusivos separados fora do CDA. A métrica &quot;Pessoas&quot; substitui a métrica &quot;Visitantes únicos&quot; quando o Cross-device Analytics está ativado.

## Qual é a diferença entre a métrica “Dispositivos únicos” no CDA e a métrica “Visitantes únicos” fora do CDA?

Essas duas métricas são aproximadamente equivalentes umas às outras.

## É possível incluir métricas do CDA usando a API 2.0?

Sim. O Analysis Workspace usa a API 2.0 para solicitar dados dos servidores da Adobe e você pode visualizar chamadas de API usadas pela Adobe para criar seus próprios relatórios:

1. Enquanto estiver conectado ao Analysis Workspace, vá para [!UICONTROL Ajuda] > [!UICONTROL Ativar depurador].
2. Clique no ícone de depuração no painel desejado e selecione a visualização e a hora da solicitação.
3. Localize a solicitação JSON, que você pode usar na chamada de API para a Adobe.

## O Cross-Device Analytics pode unir visitantes únicos. É possível unir as visitas?

Sim. Se um indivíduo enviar ocorrências de dois dispositivos separados dentro do tempo limite de visita do conjunto de relatórios virtual (30 minutos por padrão), eles serão agrupados na mesma visita.

## Qual é a ID de visitante mais avançada que o CDA usa? Posso exportá-la para fora do Adobe Analytics?

* **Se estiver usando um gráfico** de dispositivo, uma ID personalizada com base em seu cluster será o identificador principal.
* **Se estiver usando a sutura** baseada em campo, uma ID personalizada com base na prop/eVar escolhida é o identificador principal.

Ambos os identificadores são calculados pela Adobe no momento em que o relatório é executado, também conhecido como processamento [em tempo de](../vrs/vrs-report-time-processing.md)relatório. A natureza do processamento do tempo de relatório significa que ele não é compatível com Data warehouse, feeds de dados ou outros recursos de exportação que o Adobe oferta.

## Como posso me mover do gráfico do dispositivo para a costura baseada em campo, ou vice-versa?

Se você quiser trocar os métodos de identificação de CDA, entre em contato com o Gerente de conta de sua organização. O Gerente de conta pode provisionar seu conjunto de relatórios para o método desejado para identificar pessoas. *Os dados históricos agrupados do método anterior são perdidos.*

## Como a Adobe lida com limites exclusivos para uma eVar usada na identificação baseada em campo?

O CDA extrai itens de dimensão eVar antes de serem otimizados para o relatórios. Você não precisa se preocupar com limites únicos para fins de CDA. No entanto, se você tentou usar essa prop/eVar em um projeto do Workspace, ainda é possível ver o item de dimensão [(tráfego baixo)](/help/technotes/low-traffic.md) .
