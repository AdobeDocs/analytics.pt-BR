---
title: Perguntas frequentes sobre a Análise entre dispositivos
description: Perguntas frequentes sobre o Cross-Device Analytics
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Perguntas frequentes

> [!NOTE] A documentação do Cross-Device Analytics está sujeita a alterações à medida que o recurso for sendo desenvolvido. Verifique regularmente se há atualizações.

**Como posso usar o CDA para ver como as pessoas mudam de um tipo de dispositivo para outro?**

Você pode usar uma visualização de Fluxo com a dimensão Tipo de dispositivo móvel.

1. Faça logon no Adobe Analytics e crie um novo projeto em branco da Workspace.
2. Clique na guia Visualizações à esquerda e arraste uma visualização de Fluxo para a tela à direita.
3. Clique na guia Componentes à esquerda e arraste a dimensão &quot;Tipo de dispositivo móvel&quot; para o local central chamado &quot;Dimensão ou item&quot;.
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

**Posso ver como as pessoas se movem entre diferentes experiências de usuário (por exemplo, navegador de desktop vs. navegador móvel vs. aplicativo móvel)?**

Usar o Tipo de dispositivo móvel como ilustrado acima permite ver como as pessoas se movem entre tipos de dispositivo móvel e tipos de dispositivo de desktop. Entretanto, talvez você queira distinguir os navegadores de desktop dos navegadores móveis. Uma maneira de fazer isso é criar uma eVar que registre se a experiência ocorreu em um navegador de desktop, navegador móvel ou aplicativo móvel. Em seguida, crie um Fluxograma conforme descrito acima, usando sua eVar &quot;experiência&quot;, em vez da dimensão Tipo de dispositivo móvel. Isso fornece uma visão um pouco diferente sobre o comportamento entre dispositivos.

**Até que ponto o CDA compila os visitantes?**

* A Adobe mantém os dados de identificação do dispositivo por aproximadamente 30 dias. Se um dispositivo não for identificado inicialmente pelo Gráfico cooperativo ou Gráfico privado, mas for identificado posteriormente em 30 dias, o CDA volta e reafirma esse dispositivo como pertencente à pessoa identificada em até 30 dias retroativamente. Se algum comportamento não identificado de um usuário sair da janela de lookback de 30 dias, essa parte da jornada do usuário não é compilada.
* A Adobe mantém os mapeamentos de dispositivo no Gráfico cooperativo e no Gráfico privado por aproximadamente 6 meses. Uma ECID que não tem atividade por mais de seis meses é removida do gráfico. Os dados já compilados no CDA não são afetados, mas as ocorrências subsequentes dessa ECID são tratadas como um novo indivíduo.

**Como o CDA trata as ocorrências com carimbos de data e hora?**

A Adobe trata as ocorrências com carimbos de data e hora como se fossem recebidas no momento do carimbo de data e hora, e não quando a Adobe recebeu a ocorrência. Ocorrências com carimbo de data e hora com mais de 1 mês não podem ser compiladas, pois são consideradas fora do intervalo em que a Adobe mantém os dados usados para compilação.

**Como o CDA se compara à ID de visitante personalizada?**

A [ID de visitante personalizada](/help/implement/vars/config-vars/visitorid.md) é um método herdado para [conectar os usuários aos dispositivos](/help/implement/js/xdevice-visid/xdevice-connecting.md). Com uma ID de visitante personalizada, você usa a variável `s.visitorID` para definir explicitamente a ID usada para a lógica do visitante. A variável `s.visitorID` substitui todas as IDs baseadas em cookies presentes.

As IDs de visitante personalizadas têm vários efeitos colaterais indesejados que o CDA foi projetado para superar ou minimizar. Por exemplo, a metodologia de ID de visitante personalizada não tem recursos de lookback. Se um usuário for autenticado no meio de uma visita, a primeira parte da visita será associada a uma ID de visitante diferente da última parte da visita. As IDs de visitante separadas resultam no aumento de visitas e visitantes. A janela de lookback de 30 dias do CDA permite retroceder no tempo para reafirmar o comportamento anterior como pertencente à mesma pessoa, aproximando o comportamento não autenticado de vários dispositivos do comportamento autenticado de vários dispositivos com aumento mínimo ou nenhum aumento.

**É possível atualizar da ID de visitante personalizada para o CDA?**

Os clientes que já usam a ID de visitante personalizada podem atualizar para o CDA. O `s.visitorID` ainda substitui as IDs baseadas em cookies subjacentes no conjunto de relatórios base. Entretanto, no conjunto de relatórios virtual, o CDA ignora o `s.visitorID` para os dispositivos identificados pelo gráfico de dispositivos.

**Como o gráfico de dispositivos trata os dispositivos compartilhados?**

Em algumas situações, é possível que várias pessoas façam logon no mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou um quiosque em uma loja de varejo. Nesses casos, a ID é sincronizada com o gráfico desses dispositivos compartilhados, indicando que vários usuários foram associados a esse dispositivo ao longo do tempo. O gráfico de dispositivos (seja gráfico Cooperativo ou Privado) não vincula a ECID nesse dispositivo a nenhum desses usuários. Em vez disso, o gráfico vincula o ECID a um &quot;cluster&quot; que inclui todos os usuários associados. O gráfico tenta manter esse cluster o mais estável possível, em vez de alternar continuamente a ECID entre clusters ao longo do tempo. Como resultado, o CDA não pode distinguir entre usuários individuais em um dispositivo compartilhado. Todos os usuários do dispositivo compartilhado são considerados uma única &quot;pessoa&quot; no CDA.

**Como o gráfico de dispositivos lida com situações em que uma única pessoa tem MUITOS dispositivos/ECIDs?**

Em algumas situações, um usuário individual pode ser associado a um grande número de ECIDs. Isso pode ocorrer se o indivíduo usar muitos navegadores ou aplicativos e pode ser exacerbado se ele limpar os cookies com frequência ou usar o modo de navegação privado ou incognitivo do navegador. O gráfico de dispositivos limita o número de ECIDs vinculadas a determinada ID de usuário a 200. Se uma ID de usuário estiver associada a muitas ECIDs, o gráfico de dispositivos presumirá que a ID de usuário é inválida e removerá o cluster associado a essa ID de usuário. A ID de usuário é incluída na blacklist para não ser reagrupada no futuro. O resultado no CDA é que o comportamento da ID do usuário não é compilado em todos os dispositivos.
