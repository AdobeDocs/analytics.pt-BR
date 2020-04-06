---
description: Essas alterações na forma como as métricas calculadas funcionam no Analytics podem afetar você.
title: Perguntas frequentes
uuid: 9b7f1cd1-b969-4b15-8af1-969d816b65b8
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Perguntas frequentes

Essas alterações no funcionamento das métricas calculadas do [!DNL Analytics] podem afetar você.

[Como faço para acessar o Criador de métricas calculadas?](/help/components/c-calcmetrics/cm-transition.md#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1)

[Como faço para acessar o Gerenciador de métricas calculadas?](/help/components/c-calcmetrics/cm-transition.md#section_DD0BD13E9EC940268EBE8BC88241A152)

[Por que vejo tantas métricas calculadas com o mesmo nome?](/help/components/c-calcmetrics/cm-transition.md#section_E15C5B6CCC58498CAEC3FBDA8988F0A1)

[O que aconteceu com minhas métricas calculadas globais?](/help/components/c-calcmetrics/cm-transition.md#section_7351D4C7361F4ABAA1B43F8E89AAD211)

[O que aconteceu com as métricas calculadas globais que foram compartilhadas com empresas de logon?](/help/components/c-calcmetrics/cm-transition.md#section_59E5CD948ED643AE9AD3D2E4277647F8)

[O que aconteceu com a métricas calculadas com uma classificação Numérico ou Numérico2?](/help/components/c-calcmetrics/cm-transition.md#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B)

[O que aconteceu com as métricas vitalícias?](/help/components/c-calcmetrics/cm-transition.md#section_AEDB02EF24584DAD8731BED9DDCE4F48)

[O que preciso saber sobre métricas calculadas baseadas em métricas diárias/semanais/mensais/trimestrais/anuais de Visitantes únicos?](/help/components/c-calcmetrics/cm-transition.md#section_E9A77EBB41CE4881B196CC1C282B2DF3)

[E com relação a métricas calculadas criadas ou gerenciadas com os métodos da antiga API do conjunto de relatórios?](/help/components/c-calcmetrics/cm-transition.md#section_13ED1BAD02634674BDAEB479B060A4B6)

[Os dados atuais suportam todos os tipos de métricas calculadas?](/help/components/c-calcmetrics/cm-transition.md#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2)

[O que significa &quot;Nenhum nome fornecido&quot; quando exibido junto com métricas calculadas migradas?](/help/components/c-calcmetrics/cm-transition.md#section_C90CBB72A67644F38D583301981F8D03)

[O que acontece com as métricas calculadas de um usuário caso ele seja excluído?](/help/components/c-calcmetrics/cm-transition.md#section_42ED4C15830540879C4A161423690E5A)

[Por que vejo métricas calculadas &quot;desconhecidas&quot; que não são válidas para outros conjuntos de relatórios, apesar de terem sido criadas e aplicadas a esses conjuntos?](/help/components/c-calcmetrics/cm-transition.md#section_6772818EFDED46E9B7095D64C3B77211)

[Por que as alterações que fiz em minhas métricas calculadas herdadas não foram salvas?](/help/components/c-calcmetrics/cm-transition.md#section_81CDEFCA1FD542579AF183DA1494EAF0)

[Porque minhas métricas calculadas não são exibidas no Relatório de canais de marketing?](/help/components/c-calcmetrics/cm-transition.md#section_FC350359A775433AB5F43C7CAB304D62)

[Por que algumas métricas calculadas mostram fórmulas sem o parênteses que adicionei?](/help/components/c-calcmetrics/cm-transition.md#section_AC0D1E9714AD487F9A1C73359F518B5E)

[(Somente Ad Hoc Analysis) As métricas calculadas com definições de segmentos em linha ou integrados ainda são suportadas?](/help/components/c-calcmetrics/cm-transition.md#section_B25C924A282F49388AB604E3D826F44C)

[(Somente Report Builder) Por que as métricas calculadas desapareceram das minhas solicitações?](/help/components/c-calcmetrics/cm-transition.md#section_DA4792FE5D7945218CD5E6328DE08E82)

[Como funcionam os Totais das métricas calculadas?](/help/components/c-calcmetrics/cm-transition.md#section_57BA3A299C7948ABB82B0392A9B0F33E)

## Como faço para acessar o Criador de métricas calculadas? {#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1}

* Click **[!UICONTROL + Add]** at the top of the Calculated Metric Manager, or
* In any Analytics report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Add]**.

## Como faço para acessar o Gerenciador de métricas calculadas? {#section_DD0BD13E9EC940268EBE8BC88241A152}

* Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Components]** in the left navigation. Em seguida, clique em **[!UICONTROL Calculated Metrics]**.

* In any [!DNL Analytics] report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Manage]**.

## Por que vejo tantas métricas calculadas com o mesmo nome? {#section_E15C5B6CCC58498CAEC3FBDA8988F0A1}

(Anteriormente, as métricas calculadas globais não eram de propriedade de nenhum usuário administrativo específico e ficavam visíveis para todos os usuários desse conjunto de relatórios. As métricas foram segregadas pelo conjunto de relatórios. Se uma métrica em um conjunto de relatórios tiver o mesmo nome de uma métrica em um conjunto de relatórios diferente, ela simplesmente aparecerá para os usuários como a mesma métrica quando eles alternarem entre conjuntos de relatórios.)

Agora, as métricas não são mais segregadas pelos conjuntos de relatórios. Se uma métrica em um conjunto de relatórios tiver o mesmo nome de uma métrica em um conjunto de relatórios diferente, ambas estarão visíveis no Criador de métricas calculadas, bem como no Seletor de métricas, e poderão aparecer como métricas de duplicado mesmo que elas possam ou não ter a mesma definição.

Você verá várias métricas calculadas com um mesmo nome (mas criadas em conjuntos de relatórios diferentes) somente se desmarcar a caixa de seleção (Somente `<report suite>`), conforme mostrado aqui:

![](assets/report_suite.png)

**O que você precisa fazer**

Considere consolidar métricas calculadas com nomes e definições semelhantes, mas tenha cuidado ao fazer isso. Você pode verificar o conjunto de relatórios em busca de uma métrica calculada no Gerenciador de métricas calculadas para verificar seu conjunto de relatórios original. Você também deve verificar as definições de métricas ao excluir duplicados potenciais para garantir que esteja consolidando as métricas corretamente.

>[!NOTE] Ainda que as métricas calculadas não estejam mais vinculadas a um conjunto específico de relatórios e possam ser usadas em qualquer conjunto de relatórios visível para a empresa de logon, o conjunto de relatórios no qual a métrica calculada foi criada ou salva pela última vez ainda pode ser visualizado no Gerenciador de métricas calculadas.

>[!NOTE] Mesmo que uma métrica calculada seja excluída, os marcadores ou relatórios de painel que referenciam a métrica ainda funcionarão.

## O que aconteceu com minhas métricas calculadas globais? {#section_7351D4C7361F4ABAA1B43F8E89AAD211}

Anteriormente, um administrador podia criar métricas calculadas (conhecidas como &quot;métricas calculadas globais&quot; ou &quot;métricas calculadas do conjunto de relatórios&quot;) em um conjunto de relatórios utilizando as ferramentas administrativas. 

As métricas calculadas globais agora são de propriedade do primeiro usuário administrador na lista de logon dos usuários administradores. Eles serão compartilhados com &quot;Todos&quot; por padrão. Esse padrão segue o mesmo modelo de compartilhamento e planos de migração que os segmentos.

**O que você precisa fazer**

Nada. No entanto, o novo proprietário Administrador deve ter cuidado ao modificar ou excluir essas métricas calculadas; elas podem ser usadas em vários relatórios e painéis marcados.

>[!NOTE] Mesmo que uma métrica calculada seja excluída, os marcadores ou relatórios de painel que referenciam a métrica ainda funcionarão.

## O que aconteceu com as métricas calculadas globais que foram compartilhadas com empresas de logon? {#section_59E5CD948ED643AE9AD3D2E4277647F8}

Anteriormente, um administrador podia criar métricas calculadas (conhecidas como &quot;métricas calculadas globais&quot; ou &quot;métricas calculadas do conjunto de relatórios&quot;) em um conjunto de relatórios utilizando as ferramentas administrativas. Essas métricas podem ser &quot;compartilhadas&quot; nas empresas de logon, adicionando o conjunto de relatórios a várias empresas de logon.)

As métricas calculadas globais não podem mais ser compartilhadas entre empresas de logon. Eles não estão mais vinculados ou vinculados a um conjunto de relatórios específico, mas estão vinculados a uma empresa de logon específica. Métricas calculadas que foram compartilhadas em empresas de logon

* Foram migradas para todas as empresas de logon com acesso a esse conjunto de relatórios.
* Aplicadas ao padrão &quot;compartilhado com todos&quot;.
* Serão cópias independentes de todas as outras empresas de logon.

>[!NOTE] Caso a métrica calculada tenha sido usada em um marcador, painel, alerta ou relatório programado, a edição de uma nova cópia NÃO afetará a métrica calculada mantida.

## O que aconteceu com a métricas calculadas com uma classificação Numérico ou Numérico2? {#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B}

(Previously, calculated metrics with a Numeric or Numeric2 classification were only visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs.)

Now, calculated metrics with a Numeric or Numeric2 classification will continue to be visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs. Contudo, elas não serão mais suportadas em nenhum relatório com um segmento aplicado.

Além disso, as métricas calculadas com uma classificação Numérico ou Numérico2 não serão suportadas nos seguintes componentes: [!UICONTROL Ad Hoc Analysis], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] relatórios [!UICONTROL Anomaly Detection]e [!UICONTROL Contribution Analysis]. Ao criar ou editar uma métrica calculada com uma classificação Numérico ou Numérico2, você verá um aviso de compatibilidade informando que a métrica calculada não é compatível com determinadas áreas do produto.

**O que você precisa fazer**

Evite criar métricas calculadas com classificações Numérico1 ou Numérico2 se a métrica for usada com um segmento ou com qualquer um dos componentes não compatíveis.

## O que aconteceu com as métricas vitalícias? {#section_AEDB02EF24584DAD8731BED9DDCE4F48}

Métricas vitalícias não são mais suportadas ou exibidas na interface do usuário do [!UICONTROL Reports & Analytics] ou em qualquer outra interface do usuário. Eles não podem ser consultados pela API de relatório.

Todos os marcadores, painéis, relatórios programados ou alertas que continham uma métrica vitalícia continuarão a ser executados sem essa métrica, contanto que pelo menos uma outra métrica válida também esteja no relatório. Se a única métrica no marcador, painel, relatório programado ou alerta for uma métrica vitalícia, o relatório não será mais executado.

## O que preciso saber sobre métricas calculadas baseadas em métricas diárias/semanais/mensais/trimestrais/anuais de Visitantes únicos? {#section_E9A77EBB41CE4881B196CC1C282B2DF3}

Calculated metrics based on Unique Visitor metrics will be visible in the following [!DNL Analytics] components: [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and Reporting API.

No entanto, essas métricas não serão suportadas nos seguintes componentes: [!UICONTROL Segments], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] relatórios [!UICONTROL Anomaly Detection]e [!UICONTROL Contribution Analysis]. Ao criar ou editar uma métrica calculada baseada em métricas de Visitantes únicos, você verá um aviso de compatibilidade informando que a métrica não é compatível com determinadas áreas do produto.

Você usa uma métrica básica de Visitante único em um relatório com um segmento. É possível criar uma métrica calculada baseada em uma métrica de Visitantes únicos; contudo, essa métrica calculada não pode ser aplicada a um relatório com um segmento, e nem pode ter um segmento integrado a ela.

## O que acontece com as métricas calculadas criadas ou gerenciadas com os métodos da antiga API de conjunto de relatórios? {#section_13ED1BAD02634674BDAEB479B060A4B6}

Anteriormente, salvar uma métrica calculada com o método da API (1.3 ou 1.4) ReportSuite.SaveCalculatedMetrics era o mesmo que criar ou atualizar uma métrica calculada no Admin Console. O mesmo se aplica a ReportSuite.DeleteCalculatedMetrics. Além disso, a lista de métricas calculadas exibida no Admin Console ou ao chamar ReportSuite.GetCalculatedMetrics era a mesma.

Agora, os métodos da API (1.3 ou 1.4) ReportSuite CalculatedMetrics continuarão a salvar, excluir e recuperar métricas calculadas usando o armazenamento antigo. As métricas calculadas existentes serão migradas e estarão visíveis no novo Criador de métricas calculadas. **As novas métricas calculadas criadas com os métodos da API estarão visíveis somente na API. Eles ainda serão utilizáveis na API do Relatórios.**

**O que você precisa fazer**

Se precisar usar a API e o Criador de métricas calculadas, você deve parar de usar os métodos da API ReportSuite CalculatedMetrics e usar os novos métodos da API CalculatedMetrics (Get, Save, Delete e GetFunctions).

## Os dados atuais suportam todos os tipos de métricas calculadas? {#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2}

Os dados atuais não suportam métricas calculadas que contêm segmentos ou funções estatísticas. As únicas funções compatíveis são as funções matemáticas básicas, como adição, exclusão, multiplicação, divisão e negação (-x).

## O que significa &quot;Nenhum nome fornecido&quot; quando exibido junto com as métricas calculadas migradas? {#section_C90CBB72A67644F38D583301981F8D03}

&quot;Nenhum nome fornecido&quot; significa que nenhum nome de métrica está associado a esta métrica migrada (apenas uma fórmula sem um nome descritivo).

## O que acontece com as métricas calculadas de um usuário se ele for excluído? {#section_42ED4C15830540879C4A161423690E5A}

Todas as métricas calculadas que esse usuário criou também são excluídas. No entanto, as métricas calculadas excluídas ainda funcionarão como parte de marcadores salvos, painéis ou relatórios agendados.

## Por que vejo métricas calculadas &quot;desconhecidas&quot; que não são válidas para outros conjuntos de relatórios, apesar de terem sido criadas e aplicadas a esses conjuntos? {#section_6772818EFDED46E9B7095D64C3B77211}

A interface do usuário exibe &quot;desconhecido&quot; caso a métrica calculada contenha métricas ou dimensões base que não existem para o conjunto de relatórios selecionado.

## Por que as alterações que fiz em minhas métricas calculadas herdadas não foram salvas? {#section_81CDEFCA1FD542579AF183DA1494EAF0}

Isso pode ocorrer devido ao momento da migração para o novo banco de dados de métricas calculadas, que ocorreu entre 15 de junho e 18 de junho de 2015.

**O que você precisa fazer**

Será necessário refazer as alterações feitas nas métricas herdadas.

## Porque minhas métricas calculadas não são exibidas no Relatório de canais de marketing? {#section_FC350359A775433AB5F43C7CAB304D62}

(Anteriormente, todas as métricas calculadas eram listadas no seletor de métricas nos relatórios de Canais de marketing com a opção Primeiro contato e Último contato.)

Agora, somente as métricas calculadas com o tipo de alocação definido especificamente para Primeiro contato ou Último contato no construtor de métricas calculadas estarão disponíveis no seletor de métricas nos relatórios de Canais de marketing. Observe que qualquer métrica calculada já aplicada aos relatórios de Canal de marketing continuará a ser aplicada e a funcionar como antes. Para criar uma métrica calculada para Canais de marketing, clique no ícone de configuração no construtor de métricas e selecione Primeiro contato ou Último contato como o tipo de alocação. Lembre-se de que isso tornará a métrica calculada compatível apenas com os relatórios de Canal de marketing, e ela não poderá ser usada em nenhum outro relatório.

## Por que algumas métricas calculadas mostram fórmulas sem o parênteses que adicionei? {#section_AC0D1E9714AD487F9A1C73359F518B5E}

Durante a migração, a Adobe removeu parênteses desnecessários de algumas fórmulas. Somente parênteses que não afetam a forma como a métrica é calculada foram removidos. Isso não modifica os dados; apenas simplifica a fórmula.

## (Somente Ad Hoc Analysis) As métricas calculadas com definições de segmentos em linha ou integrados ainda são suportadas? {#section_B25C924A282F49388AB604E3D826F44C}

As métricas calculadas criadas na análise ad hoc podiam conter previamente definições de segmentos em linha. Isso não é mais possível.

**O que você precisa fazer**

É necessário salvar o segmento explicitamente. As métricas calculadas existentes com definições de segmento em linha continuarão a ser executadas corretamente e poderão ser exibidas na Ad Hoc Analysis, mas não poderão ser salvas sem que você salve explicitamente o segmento.

## (Somente Report Builder) Por que as métricas calculadas desapareceram das minhas solicitações? {#section_DA4792FE5D7945218CD5E6328DE08E82}

Caso a solicitação tenha sido criada na v5.2 e possuir as métricas calculadas, elas não estarão visíveis na v5.1 (ou nas versões mais recentes). Isso ocorre porque as métricas calculadas agora usam IDs globais (IDs não específicas do conjunto de relatórios).

**O que você precisa fazer**

É necessário atualizar para a v5.2 para poder ver essas métricas.

## Como funcionam os Totais das métricas calculadas? {#section_57BA3A299C7948ABB82B0392A9B0F33E}

When [!UICONTROL Reports & Analytics] shows a calculated metrics total in [!UICONTROL Reports & Analytics], it&#39;s just applying the formula to the total. Por exemplo, o total para a métrica calculada Pedidos/Visita pega o Total de pedidos e os divide pelo Total de visitas. Em alguns casos, no entanto, o total da métrica calculada não é apenas a soma dos itens de linha, mas um total para o site.

Exemplo 1: Visitantes para um termo de pesquisa: o mesmo visitante pode ter pesquisado vários termos, portanto, nesse caso, o total de visitantes não é igual à soma dos itens de linha.

Exemplo 2: visualizações de página em produtos: no carrinho, pode haver vários produtos, portanto, há várias visualizações de página para o carrinho. Para obter mais informações sobre como comparar a soma dos itens de linha aos totais do relatório, consulte [este artigo](https://helpx.adobe.com/br/analytics/kb/sum-line-items-different-from-total.html)da base de conhecimento.
