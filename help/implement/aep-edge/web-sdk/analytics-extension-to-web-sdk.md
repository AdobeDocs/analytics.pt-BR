---
title: Migração da extensão de tag do Adobe Analytics para a extensão de tag da Web SDK
description: Atualize a implementação do Analytics nas tags de Coleção de dados da Adobe Experience Platform para usar a extensão Web SDK.
exl-id: 691c29ca-d169-4ef8-9f91-d0375166796d
source-git-commit: 7bd4a188e5a2171260f1f0696d8bebad854dba4a
workflow-type: tm+mt
source-wordcount: '1706'
ht-degree: 6%

---

# Migração da extensão de tag do Adobe Analytics para a extensão de tag da Web SDK

Esse caminho de implementação envolve uma abordagem de migração metódica para mover da extensão de tag da Adobe Analytics para a extensão de tag da Web SDK. Outros caminhos de implementação são abordados em páginas separadas:

* [Biblioteca JavaScript do AppMeasurement para Web SDK](appmeasurement-to-web-sdk.md): uma abordagem suave e metódica para migrar para o Web SDK, exceto por não usar marcas. Em vez disso, você remove manualmente a biblioteca de coleta de dados do Adobe Analytics (`AppMeasurement.js`) e a substitui pela biblioteca JavaScript do Web SDK (`alloy.js`).
* [Extensão de marca do Web SDK](web-sdk-tag-extension.md): uma nova instalação do Web SDK em que você gerencia a implementação usando marcas na Coleção de Dados da Adobe Experience Platform. Ele requer o grupo de campos Adobe Analytics ExperienceEvent, que inclui variáveis típicas do Analytics para serem incluídas no esquema XDM.
* [Biblioteca JavaScript do Web SDK](web-sdk-javascript-library.md): uma nova instalação do Web SDK usando a biblioteca JavaScript do Web SDK (`alloy.js`). Gerencie você mesmo a implementação, em vez de usar a interface das tags. Ele requer o grupo de campos Adobe Analytics ExperienceEvent, que inclui variáveis típicas do Analytics para serem incluídas no esquema XDM.

## Vantagens e desvantagens desse caminho de implementação

O uso dessa abordagem de migração tem vantagens e desvantagens. Avalie cuidadosamente cada opção para decidir qual abordagem é a melhor para sua organização.

| Vantagens | Desvantagens |
| --- | --- |
| <ul><li>**Nenhuma alteração de código no site**: como a implementação já tem marcas instaladas, todas as atualizações de migração podem ser feitas na interface de marcas.</li><li>**Usa sua implementação existente**: esta abordagem não requer uma implementação nova. Embora isso exija novas ações de regra, é possível reutilizar os elementos de dados existentes e as condições da regra com o mínimo de alterações.</li><li>**Não requer um esquema**: nesta fase de migração para o Web SDK, você não precisa de um esquema XDM. Em vez disso, você pode preencher o objeto `data`, que envia dados diretamente para o Adobe Analytics. Quando a migração para o Web SDK estiver concluída, você poderá criar um esquema para sua organização e usar o mapeamento de fluxo de dados para preencher campos XDM aplicáveis. Se um esquema fosse necessário nesta fase do processo de migração, sua organização seria forçada a usar um esquema XDM da Adobe Analytics. O uso desse esquema torna mais difícil para sua organização usar seu próprio esquema no futuro.</li></ul> | <ul><li>**Débito técnico de implementação**: como esta abordagem usa uma forma modificada de sua implementação existente, pode ser mais difícil rastrear a lógica de implementação e realizar alterações quando necessário. O código personalizado pode ser particularmente difícil de depurar.</li><li>**Requisito de mapeamento para envio de dados para a Platform**: quando sua organização estiver pronta para usar o Customer Journey Analytics, envie dados para um conjunto de dados na Adobe Experience Platform. Esta ação requer que cada campo no objeto `data` seja uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não é necessário fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li></ul> |

A Adobe recomenda seguir esse caminho de implementação nos seguintes cenários:

* Você tem uma implementação existente usando a extensão de tag da Adobe Analytics. Se você tiver uma implementação usando o AppMeasurement, siga [Migrar do AppMeasurement para o Web SDK](appmeasurement-to-web-sdk.md).
* Você pretende usar o Customer Journey Analytics no futuro, mas não deseja substituir sua implementação do Analytics por uma implementação do Web SDK do zero. Substituir sua implementação do zero no Web SDK requer mais esforço, mas também oferece a arquitetura de implementação de longo prazo mais viável. Se a sua organização estiver disposta a realizar o esforço de uma implementação limpa do Web SDK, consulte [Assimilar dados por meio do Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) no guia do usuário do Customer Journey Analytics.

## Etapas necessárias para migrar para o Web SDK

As etapas a seguir contêm objetivos concretos a serem atingidos. Clique em cada etapa para obter instruções detalhadas sobre como realizá-la.

+++**1. Criar e configurar uma sequência de dados**

Crie um fluxo de dados na Coleção de dados da Adobe Experience Platform. Ao enviar dados para esse fluxo de dados, ele encaminha dados para a Adobe Analytics. No futuro, esse mesmo fluxo de dados encaminha dados para o Customer Journey Analytics.

1. Navegue até [experience.adobe.com](https://experience.adobe.com) e faça logon usando suas credenciais.
1. Use a página inicial ou o seletor de produto no canto superior direito para navegar até **[!UICONTROL Coleção de dados]**.
1. Na navegação à esquerda, selecione **[!UICONTROL Datastreams]**.
1. Selecione **[!UICONTROL Novo fluxo de dados]**.
1. Insira o nome desejado e selecione **[!UICONTROL Salvar]**.
1. Depois que a sequência de dados for criada, selecione **[!UICONTROL Adicionar Serviço]**.
1. No menu suspenso do serviço, selecione **[!UICONTROL Adobe Analytics]**.
1. Insira a mesma ID de conjunto de relatórios do site para o qual você envia dados de análise. Clique em **[!UICONTROL Salvar]**.

![Adicionar serviço Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

Seu fluxo de dados agora está pronto para receber e transmitir dados para a Adobe Analytics.

+++

+++**2. Adicionar a extensão Web SDK à sua propriedade de marca**

Esta seção prepara a tag para a maior parte do esforço de migração que ocorrerá na próxima etapa.

1. Clique no ícone de hambúrguer na parte superior esquerda da interface do Adobe Experience Platform e selecione **[!UICONTROL Tags]**.
1. Selecione a propriedade de tag desejada.
1. Na navegação à esquerda da propriedade da marca, selecione **[!UICONTROL Extensões]**.
1. Selecione **[!UICONTROL Catálogo]** próximo à parte superior para ver uma lista de todas as extensões disponíveis.
1. Procure e selecione a extensão **[!UICONTROL Adobe Experience Platform Web SDK]** e clique em **[!UICONTROL Instalar]** à direita.

   ![Catálogo](assets/catalog.png) {style="border:1px solid lightslategray"}

1. As definições de configuração de extensão são exibidas. Localize a seção Fluxos de dados e selecione o fluxo de dados criado na etapa anterior.

   ![Seleção de sequência de dados](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Selecione **[!UICONTROL Salvar]**.

A propriedade da tag agora tem o Web SDK instalado.

+++

+++**3. Criar um elemento de dados de objeto de dados**

O elemento de dados do objeto de dados fornece uma estrutura intuitiva para configurar uma carga que o Web SDK usa para enviar para um fluxo de dados. A maioria das regras que você atualiza na etapa a seguir interage com esse elemento de dados.

1. Na navegação à esquerda da interface de tags, selecione **[!UICONTROL Elementos de Dados]**.
1. Selecione **[!UICONTROL Adicionar elemento de dados]**
1. Atribua ao elemento de dados as seguintes configurações:
   * [!UICONTROL Nome]: qualquer item desejado, como &quot;Camada de dados&quot; ou &quot;Objeto de dados&quot;
   * [!UICONTROL Extensão]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Tipo de Elemento de Dados]: [!UICONTROL Variável]
   * As caixas de seleção podem permanecer como estão
1. À direita, selecione as seguintes configurações:
   * Botão de opção de propriedade: [!UICONTROL Dados]
   * Solução: [!UICONTROL Adobe Analytics]
1. Selecione **[!UICONTROL Salvar]**.

![Criar elemento de dados](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Agora, a propriedade da tag tem tudo o que é necessário para atualizar cada regra.

+++

+++**4. Atualizar regras para usar a extensão Web SDK em vez da extensão do Analytics**

Essa etapa contém a maior parte do esforço necessário para migrar para o Web SDK e requer conhecimento de como a implementação funciona. Um exemplo é fornecido abaixo de como editar uma regra de tag típica. Atualize todas as regras de tag na implementação para substituir todas as referências à extensão do Adobe Analytics pela extensão do Web SDK.

1. Na navegação à esquerda da interface de tags, selecione **[!UICONTROL Regras]**.
1. Selecione uma regra para editar.
1. Selecione a ação **[!UICONTROL Adobe Analytics - Definir Variáveis]**
1. Observe todas as variáveis do Analytics definidas nesta regra. Inclua as variáveis definidas nos menus suspensos e as variáveis definidas no código personalizado.
1. Altere a [!UICONTROL Configuração da ação] para as seguintes configurações:
   * [!UICONTROL Extensão]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Tipo de ação]: atualizar variável
1. Certifique-se de que o objeto de dados esteja selecionado no menu suspenso à direita.
1. Defina as variáveis do Analytics com os mesmos valores que foram configurados na extensão do Analytics.
   * As variáveis definidas na interface de tags podem ser traduzidas diretamente para os mesmos valores.
   * As variáveis de string definidas no código personalizado exigem ajustes mínimos. Em vez de usar o objeto `s`, use `data.__adobe.analytics`. Por exemplo, `s.eVar1` seria traduzido para `data.__adobe.analytics.eVar1`.
   * As variáveis de configuração e chamadas de método do Analytics no código personalizado podem exigir lógica de implementação modificada. Consulte cada [variável](/help/implement/vars/overview.md) respectiva para determinar como atingir seu equivalente usando o Web SDK.
1. Depois que toda a lógica da regra for replicada usando a extensão Web SDK, selecione **[!UICONTROL Manter alterações]**.
1. Repita essas etapas para cada configuração de ação que usa a extensão Adobe Analytics para definir valores. Essa etapa inclui as variáveis definidas usando a interface de tags e as definidas usando o código personalizado. Blocos de código personalizados não podem fazer referência ao objeto `s` em nenhum lugar.

As etapas acima se aplicam apenas às regras que definem valores. As etapas a seguir substituem todas as ações que usam a [!UICONTROL Configuração de Ação] [!UICONTROL Enviar Beacon].

1. Selecione uma regra que envie um sinal.
1. Selecione a ação **[!UICONTROL Adobe Analytics - Enviar beacon]**.
1. Anote o valor atual do botão de opção [!UICONTROL Rastreamento] à direita ([`s.t()`](../../vars/functions/t-method.md) ou [`s.tl()`](../../vars/functions/tl-method.md)).
1. Altere a [!UICONTROL Configuração da ação] para as seguintes configurações:
   * [!UICONTROL Extensão]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Tipo de ação]: [!UICONTROL Enviar evento]
1. À direita, altere as configurações da ação para o seguinte:
   * [!UICONTROL Tipo]: Para `s.t()`, use **[!UICONTROL Exibições de Página de Detalhes da Página da Web]**. Para `s.tl()`, use **[!UICONTROL Cliques de Link de Interação na Web]**. Se você usar [`s.tl()`](../../vars/functions/tl-method.md), também deverá incluir os seguintes campos no objeto de dados. Estes campos estão listados em [!UICONTROL Propriedades adicionais] ao executar a configuração da ação [!UICONTROL Atualizar variável]:
      * [Nome do link](../../vars/functions/tl-method.md)
      * [Tipo de link](../../vars/functions/tl-method.md)
      * [URL do link](../../vars/config-vars/linkurl.md)
1. Selecione **[!UICONTROL Manter alterações]**.
1. Repita essas etapas para cada configuração de ação que usa o Adobe Analytics para enviar um beacon.

+++

+++**5. Publicar regras atualizadas**

A publicação de regras atualizadas segue o mesmo fluxo de trabalho de qualquer outra alteração na configuração de tags.

1. Na navegação à esquerda da interface das tags, selecione **[!UICONTROL Fluxo de Publicação]**.
1. Selecione **[!UICONTROL Adicionar biblioteca]**.
1. Nomeie essa tag de confirmação, como &quot;Atualizar para o Web SDK&quot;.
1. Selecione **[!UICONTROL Adicionar Todos Os Recursos Alterados]**.
1. Selecione **[!UICONTROL Salvar]**.
1. O fluxo de trabalho de publicação exibe um ponto laranja, indicando que está sendo criado. Quando o ponto ficar verde, as alterações estarão disponíveis no ambiente de desenvolvimento.
1. Teste as alterações no ambiente de desenvolvimento para garantir que todas as regras sejam acionadas corretamente e que o objeto de dados seja preenchido com os valores esperados.
1. Quando estiver pronto, envie a biblioteca para aprovação, crie para preparo e, em seguida, aprove e publique para produção.

![Fluxo de publicação](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Desabilitar extensão do Analytics**

Quando a implementação de tag estiver totalmente no Web SDK, você poderá desativar a extensão do Adobe Analytics.

1. Na navegação à esquerda da interface de tags, selecione **[!UICONTROL Extensões]**.
1. Localize e selecione a extensão [!UICONTROL Adobe Analytics]. À direita, selecione **[!UICONTROL Desativar]**.
1. Siga o mesmo fluxo de trabalho de publicação acima para publicar a remoção da extensão do [!UICONTROL Adobe Analytics].
1. Depois que a extensão for desativada na produção, você poderá desinstalá-la totalmente. Selecione a extensão, o menu de três pontos à direita e selecione **[!UICONTROL Desinstalar]**.
1. Siga o mesmo fluxo de trabalho de publicação acima para publicar essas alterações na produção.

+++

Neste ponto, a implementação do Analytics está totalmente no Web SDK e está preparada adequadamente para mudar para o Customer Journey Analytics no futuro.
