---
title: Perguntas frequentes sobre a Análise entre dispositivos
description: Perguntas frequentes sobre o Cross-Device Analytics
translation-type: tm+mt
source-git-commit: e7a78c2ac21042f57487c1c230e1c96318810429

---


# Perguntas frequentes

> [!NOTE] A documentação do Cross-Device Analytics está sujeita a alterações à medida que o recurso for sendo desenvolvido. Verifique regularmente se há atualizações.

**Como posso usar o CDA para ver como as pessoas se movem de um tipo de dispositivo para outro?**

Você pode usar uma visualização de Fluxo com a dimensão Tipo de dispositivo móvel.

1. Faça logon no Adobe Analytics e crie um novo projeto em branco do Workspace.
2. Clique na guia Visualizações à esquerda e arraste uma visualização de Fluxo para a tela à direita.
3. Clique na guia Componentes à esquerda e arraste a dimensão 'Tipo de dispositivo móvel' para o local central chamado 'Dimensão ou item'.
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

**Posso ver como as pessoas se movem entre diferentes experiências de usuário (por exemplo, navegador de desktop vs. navegador móvel vs. aplicativo móvel)?**

Usar o Tipo de dispositivo móvel como ilustrado acima permite ver como as pessoas se movem entre tipos de dispositivos móveis e tipos de dispositivos de desktop. Entretanto, talvez você queira distinguir os navegadores desktop dos navegadores móveis. Uma maneira de fazer isso é criar uma eVar que registre se a experiência ocorreu em um navegador de desktop, navegador móvel ou aplicativo móvel. Em seguida, crie um diagrama de Fluxo conforme descrito acima, usando sua eVar "experiência" em vez da dimensão Tipo de dispositivo móvel. Isso fornece uma visão um pouco diferente sobre o comportamento entre dispositivos.

**Até que ponto o CDA recosta os visitantes?**

* A Adobe mantém os dados de identificação do dispositivo por aproximadamente 30 dias. Se um dispositivo não for inicialmente identificado pelo Gráfico cooperativo ou Gráfico privado, mas for identificado posteriormente em 30 dias, o CDA volta e reafirma esse dispositivo como pertencente à pessoa identificada em até 30 dias no passado. Se algum comportamento não identificado de um usuário cair fora da janela de retrospectiva de 30 dias, essa parte da jornada do usuário não é costurada.
* A Adobe mantém os mapeamentos de dispositivos no Gráfico cooperativo e no Gráfico privado por aproximadamente 6 meses. Um ECID que não tem atividade por mais de seis meses é removido do gráfico. Os dados já agrupados no CDA não são afetados, mas as ocorrências subsequentes desse ECID são tratadas como um novo indivíduo.

**Como o CDA lida com ocorrências com carimbos de data e hora?**

A Adobe trata as ocorrências com carimbos de data e hora como se fossem recebidas no momento do carimbo de data e hora, e não quando a Adobe recebeu a ocorrência. Ocorrências com carimbo de data e hora com mais de 1 mês não podem ser agrupadas, pois são consideradas fora do intervalo, a Adobe mantém os dados usados para costurar.

**Como o CDA se compara à ID de visitante personalizada?**

[A ID](../../implement/js-implementation/c-unique-visitors/visid-custom.md) de visitante personalizada é um método herdado para [conectar usuários em dispositivos](../../implement/js-implementation/xdevice-visid/xdevice-connecting.md). Com uma ID de visitante personalizada, você usa a `s.visitorID` variável para definir explicitamente a ID usada para a lógica do visitante. A `s.visitorID` variável substitui todas as IDs baseadas em cookies presentes. Consulte [Identificar visitantes](../../implement/js-implementation/c-unique-visitors/visid-overview.md) únicos no guia Implementar do usuário para obter mais informações.

As IDs de visitante personalizadas têm vários efeitos colaterais indesejados que o CDA foi projetado para superar ou minimizar. Por exemplo, a metodologia de ID de visitante personalizada não tem recursos de pesquisa. Se um usuário se autenticar no meio de uma visita, a primeira parte da visita associará a uma ID de visitante diferente da última parte da visita. As IDs de visitante separadas resultam na inflação da visita e do visitante. A janela de pesquisa de 30 dias do CDA permite que ele recue a tempo para reafirmar o comportamento anterior como pertencente à mesma pessoa, reunindo um comportamento inautenticado entre dispositivos com comportamento autenticado entre dispositivos com inflação zero ou mínima.

**É possível atualizar da ID de visitante personalizada para o CDA?**

Os clientes que já usam a ID de visitante personalizada podem atualizar para o CDA. O `s.visitorID` ainda substitui as IDs baseadas em cookies subjacentes no conjunto de relatórios base. Entretanto, no conjunto de relatórios virtual, o CDA ignora `s.visitorID` os dispositivos identificados pelo gráfico de dispositivos.

**Como o gráfico de dispositivos lida com dispositivos compartilhados?**

Em algumas situações, é possível que várias pessoas façam logon a partir do mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou quiosque em uma loja de varejo. Nesses casos, a ID sincroniza com o gráfico de dispositivos desses dispositivos compartilhados indica que vários usuários se associam a esse dispositivo ao longo do tempo. O gráfico do dispositivo (seja Co-op ou Gráfico privado) não vincula o ECID nesse dispositivo a nenhum desses usuários. Em vez disso, o gráfico vincula o ECID a um "cluster" que inclui todos os usuários associados. O gráfico tenta manter esse cluster o mais estável possível, em vez de alternar continuamente a ECID entre clusters ao longo do tempo. Como resultado, o CDA não pode distinguir entre usuários individuais em um dispositivo compartilhado. Todos os usuários do dispositivo compartilhado são considerados uma única "pessoa" no CDA.

**Como o gráfico de dispositivos lida com situações em que uma única pessoa tem MUITOS dispositivos/ECIDs?**

Em algumas situações, um utilizador individual pode associar - se a um grande número de ECIDs. Isso pode ocorrer se o indivíduo usar muitos navegadores ou aplicativos, e pode ser exacerbado se frequentemente limpar os cookies ou usar o modo de navegação privado ou incognitivo do navegador. O gráfico do dispositivo limita o número de ECIDs que se vinculam a uma determinada ID de usuário para 200. Se uma ID de usuário estiver associada a muitos ECIDs, o gráfico de dispositivo presumirá que a ID de usuário é inválida e removerá o cluster associado a essa ID de usuário. A ID de usuário é então bloqueada para não ser reclusterizada no futuro. O resultado no CDA é que o comportamento da ID do usuário não é costurado em dispositivos.
