---
description: Um grupo de relatórios com base na análise de caminho. Tecnicamente, a definição de caminho significa mover de um nome de página para outro (de um valor para outro).
title: Definição de caminho
topic: Reports
uuid: c4ff9fa8-e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Definição de caminho

Um grupo de relatórios com base na análise de caminho. Tecnicamente, a definição de caminho significa mover de um nome de página para outro (de um valor para outro).

Use o [Fluxo da Analysis Workspace](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/flow.html) para opções de caminho mais flexíveis.

>[!NOTE] Para ativar a definição de caminho, vá para **[!UICONTROL Admin > Report Suites > Edit Settings > Traffic > Traffic Variables]**. Para habilitar o caminho nos relatórios do Servidor e da Seção do site, entre em contato com o Atendimento ao Cliente.

Se você precisar saber a ordem na qual os valores são coletados, será necessário ativar a definição de caminho para a variável que coleta esses valores. A definição de caminho é ativada por padrão para páginas. A definição de caminho não está ativada para nenhuma props por padrão, pois é adequada somente em alguns casos. Entre em contato com o Atendimento ao cliente para ativar a definição de caminho em uma prop.

>[!NOTE] Na Ad Hoc Analysis, ao ativar classificações em uma prop, as métricas de definição de caminho se tornam disponíveis para todas as classificações definidas para a prop ativada.

**Exemplo - Definição de caminho em seções do site**

Ativar a definição de caminho para a variável *`s.channel`* permite que você acompanhe como os visitantes do site se movem entre Seções do site (conforme o valor muda).

![](assets/path_sections.png)

A definição de caminho está disponível em vários relatórios de caminhos, como [!UICONTROL Next Site Section Flow], que exibe como os visitantes se movem pelos grupos de páginas ou seções do site.

![](assets/paths_report.png)

**Exemplo - Definição de caminho em pesquisas**

Esse mesmo conceito de ir de um valor a outro valor também se aplica a outras variáveis de tráfego, incluindo *`s.props`*. Por exemplo, se você ativar a definição de caminho do Termo de pesquisa interna *`s.prop`*, poderá ver o caminho que os visitantes seguem pelos termos de pesquisa.

**Exemplo - Definição de caminho por status de logon**

Talvez você queira saber como as pessoas percorrem seu site com base no status de login de um visitante. Para ver essas informações, você não deve consultar os relatórios de definição de caminho para o status de logon, pois eles mostrariam como os visitantes alteraram valores nesse relatório ou como os visitantes podem ter mudado de conectado para logout. Em vez disso, concatene o valor do segmento com a variável *`s.pageName`* e, então, defina o caminho da variável resultante. Este é um exemplo de código para definição de caminho de página por status do membro:

```js
s.pageName="Home Page"; 
s.prop18="Gold"; // Member Status 
s.prop19=s.prop18 + ":" + s.pageName;
```

Em seguida, ative a definição de caminho para *`s.prop19`* para ver como os membros caminham pelas páginas.

>[!NOTE] Se você usar a análise ad hoc, você pode segmentar os caminhos de página sem a necessidade de concatenar valores de segmentos e aplicar qualquer segmento aos relatórios de definição de caminho.

