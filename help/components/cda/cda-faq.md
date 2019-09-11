---
title: Perguntas frequentes sobre o análise entre dispositivos
description: Perguntas frequentes sobre a Análise entre dispositivos
translation-type: tm+mt
source-git-commit: 40d8ecae1ac7e0a1df4a2df17f5104bee6ecf336

---


# Perguntas frequentes

> [!NOTE] A documentação do Análise entre dispositivos está sujeita a alterações à medida que o recurso é desenvolvido. Consulte regularmente para atualizações.

**Como posso usar o CDA para ver como as pessoas se movimentam de um tipo de dispositivo para outro?**

Você pode usar uma visualização de Fluxo com a dimensão Tipo de dispositivo móvel.

1. Faça logon no Adobe Analytics e crie um novo projeto em branco do Workspace.
2. Clique na guia Visualizações à esquerda e arraste uma visualização de Fluxo para a tela à direita.
3. Clique na guia Componentes à esquerda e arraste a dimensão «Tipo de dispositivo móvel» para o local central «Dimensão ou Item».
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito para expandir ou recolher colunas. Diferentes dimensões também podem ser usadas no mesmo relatório de fluxo.

**É possível ver como as pessoas se movem entre diferentes experiências do usuário (por exemplo, navegador de desktop vs. navegador móvel vs. aplicativo móvel)?**

O uso do Tipo de dispositivo móvel como ilustrado acima permite ver como as pessoas se movem entre tipos de dispositivo móvel e tipos de dispositivo de desktop. No entanto, você pode diferenciar navegadores de desktop de navegadores móveis. Uma maneira de fazer isso é criar uma evar que registra se a experiência ocorreu em um navegador de desktop, navegador móvel ou aplicativo móvel. Em seguida, crie um diagrama de Fluxo conforme descrito acima, usando sua evar "experiência" em vez da dimensão Tipo de dispositivo móvel. Isso proporciona uma visão um pouco diferente sobre o comportamento entre dispositivos.

**Qual o nível de retorno de visitantes CDA?**

* A Adobe mantém dados de agrupamento de dispositivo por aproximadamente 30 dias. Se um dispositivo não for identificado de forma intencional pelo Gráfico de cooperação ou Gráfico privado, mas é identificado posteriormente em 30 dias, a CDA voltará e declara novamente o dispositivo como pertencendo a uma pessoa identificada até 30 dias no passado. Se alguns do comportamento não identificado de um usuário ficarem fora da janela de retrospectiva de 30 dias, a parte da jornada do usuário não será encadeada.
* A Adobe mantém mapeamentos de dispositivos no Gráfico de co-op e em Gráfico privado por aproximadamente 6 meses. Um ECID que não tem atividade por mais de seis meses é removido do gráfico. Os dados já empilhados no CDA não são afetados, mas as ocorrências subsequentes para o ECID são tratadas como um novo indivíduo.

**Como a CDA lida com ocorrências com carimbos de data e hora?**

A Adobe trata ocorrências com carimbo de data e hora como se fossem recebidas no momento do carimbo de data e hora, não quando a Adobe recebeu a ocorrência. Ocorrências com carimbos de data e hora anteriores ao 1 mês não podem ser encaixadas, já que são consideradas fora do intervalo a Adobe mantém os dados usados para a divisão.
