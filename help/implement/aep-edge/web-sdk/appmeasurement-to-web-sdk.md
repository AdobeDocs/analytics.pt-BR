---
title: Migração do AppMeasurement para o SDK da Web
description: Atualize sua implementação do Adobe Analytics da biblioteca JavaScript do AppMeasurement para a biblioteca JavaScript do SDK da Web.
exl-id: c90246e8-0f04-4655-9204-33c0ef611b13
source-git-commit: bfafc1f8eddf82b34fb45e3d6197213f0cee0d97
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 7%

---

# Migração do AppMeasurement para o SDK da Web

Esse caminho de implementação envolve uma abordagem de migração metódica para mover de uma implementação do AppMeasurement para uma implementação de biblioteca JavaScript do SDK da Web. Outros caminhos de implementação são abordados em páginas separadas:

* [Extensão do Analytics para a extensão do SDK da Web](analytics-extension-to-web-sdk.md): adote uma abordagem suave e metódica para mover da extensão de marcas da Adobe Analytics para a extensão de marcas do SDK da Web. Essa abordagem elimina a necessidade de usar o XDM até que sua organização esteja pronta para usar os serviços da Adobe Experience Platform, como o Customer Journey Analytics. Use o objeto `data` em vez do objeto `xdm` para enviar dados ao Adobe.
* [Biblioteca JavaScript do SDK da Web](web-sdk-javascript-library.md): uma instalação do SDK da Web atualizada usando a biblioteca JavaScript do SDK da Web (`alloy.js`). Gerencie você mesmo a implementação, em vez de usar a interface das tags. Ele requer o grupo de campos Adobe Analytics ExperienceEvent, que inclui variáveis típicas do Analytics para serem incluídas no esquema XDM.
* [Extensão de tag do SDK da Web](web-sdk-tag-extension.md): uma nova instalação do SDK da Web em que você gerencia a implementação usando tags na Coleção de dados da Adobe Experience Platform. Ele requer o grupo de campos Adobe Analytics ExperienceEvent, que inclui variáveis típicas do Analytics para serem incluídas no esquema XDM.

## Vantagens e desvantagens desse caminho de implementação

O uso dessa abordagem de migração tem vantagens e desvantagens. Avalie cuidadosamente cada opção para decidir qual abordagem é a melhor para sua organização.

| Vantagens | Desvantagens |
| --- | --- |
| <ul><li>**Uso da implementação existente**: embora sejam necessárias algumas alterações de implementação, essa abordagem não exige uma implementação totalmente nova. Você pode usar sua camada de dados e código existentes com o mínimo de alterações na lógica de implementação.</li><li>**Não requer um esquema**: nesta fase da migração para o SDK da Web, você não precisa de um esquema XDM. Em vez disso, você pode preencher o objeto `data`, que envia dados diretamente para o Adobe Analytics. Quando a migração para o SDK da Web estiver concluída, você poderá criar um esquema para sua organização e usar o mapeamento de sequência de dados para preencher campos XDM aplicáveis. Se um esquema fosse necessário nesta fase do processo de migração, sua organização seria forçada a usar um esquema XDM da Adobe Analytics. O uso desse esquema torna mais difícil para sua organização usar seu próprio esquema no futuro.</li></ul> | <ul><li>**As alterações na implementação exigem intervenção do desenvolvedor**: se você quiser fazer alterações na implementação do SDK da Web, deverá trabalhar com a equipe de desenvolvimento para editar o código no site. A abordagem que [migra para a extensão de tag do SDK da Web](analytics-extension-to-web-sdk.md) evita essa desvantagem.</li><li>**Dívida técnica da implementação**: como esta abordagem usa uma forma modificada da sua implementação existente, pode ser mais difícil rastrear a lógica da implementação e realizar alterações no futuro, quando necessário.</li><li>**Requisito de mapeamento para envio de dados para a Platform**: quando sua organização estiver pronta para usar o Customer Journey Analytics, envie dados para um conjunto de dados na Adobe Experience Platform. Esta ação requer que cada campo no objeto `data` seja uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não é necessário fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li></ul> |

A Adobe recomenda seguir esse caminho de implementação nos seguintes cenários:

* Você tem uma implementação existente usando a biblioteca JavaScript do Adobe Analytics AppMeasurement. Se você tiver uma implementação usando a extensão de tag da Adobe Analytics, siga [Migrar da extensão de tag da Adobe Analytics para a extensão de tag do SDK da Web](analytics-extension-to-web-sdk.md).
* Você pretende usar o Customer Journey Analytics no futuro, mas não deseja substituir sua implementação do Analytics por uma implementação de SDK da Web do zero. Substituir sua implementação do zero no SDK da Web requer mais esforço, mas também oferece a arquitetura de implementação de longo prazo mais viável. Se a sua organização estiver disposta a realizar o esforço de uma implementação limpa do SDK da Web, consulte [Assimilar dados por meio do SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) no guia do usuário do Customer Journey Analytics.

## Etapas necessárias para migrar para o SDK da Web

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

Seu fluxo de dados agora está pronto para receber e transmitir dados para a Adobe Analytics. Observe a ID de sequência de dados, pois essa ID é necessária ao configurar o SDK da Web no código.

+++

+++**2. Instalar a biblioteca JavaScript do SDK da Web**

Referencie a versão mais recente de `alloy.js` para que suas chamadas de método possam ser usadas. Consulte [Instalar o SDK da Web usando a biblioteca JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) para obter detalhes e blocos de código a serem usados.

+++

+++**3. Configurar o SDK da Web**

Configure sua implementação para apontar para a sequência de dados criada na etapa anterior usando o comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) do SDK da Web. O comando `configure` deve ser definido em todas as páginas, para que você possa incluí-lo junto com o código de instalação da biblioteca.

Use as propriedades [`datastreamId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/datastreamId) e [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) no comando `configure` do SDK da Web:

* Defina o `datastreamId` com a ID de sequência de dados recuperada da etapa anterior.
* Defina o `orgId` para a organização IMS da sua organização.

```js
alloy("configure", {
    datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
    orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Opcionalmente, é possível definir outras propriedades no comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview), dependendo dos requisitos de implementação da organização.

+++

+++**4. Atualizar lógica de código para usar uma carga JSON**

Altere a implementação do Analytics para que ela não dependa do objeto `AppMeasurement.js` ou `s`. Em vez disso, defina as variáveis em um objeto JavaScript formatado corretamente, que é convertido em um objeto JSON quando enviado para o Adobe. Ter uma [camada de dados](../../prepare/data-layer.md) no site ajuda muito na definição de valores, pois você pode continuar fazendo referência a esses mesmos valores.

Para enviar dados para o Adobe Analytics, a carga do SDK da Web deve usar `data.__adobe.analytics` com todas as variáveis de análise definidas neste objeto. As variáveis nesse objeto compartilham nomes e formatos idênticos aos de suas contrapartes da variável AppMeasurement. Por exemplo, se você definir a variável `products`, não a divida em objetos individuais, como faria com o XDM. Em vez disso, inclua-o como uma cadeia de caracteres exatamente é se você definir a variável `s.products`:

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

Por fim, esta carga contém todos os valores desejados e todas as referências ao objeto `s` na sua implementação são removidas. Você pode usar qualquer um dos recursos fornecidos pelo JavaScript para definir esse objeto de carga, incluindo a notação de pontos para definir valores individuais.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {analytics: {}}}};
dataObj.data.__adobe.analytics.pageName = window.document.title;
dataObj.data.__adobe.analytics.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{analytics:{...a}}}};
```

+++

+++**5. Atualizar chamadas de método para usar o SDK da Web**

Atualize todas as instâncias nas quais você chama [`s.t()`](../../vars/functions/t-method.md) e [`s.tl()`](../../vars/functions/tl-method.md), substituindo-as pelo comando [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview). Há três cenários a serem considerados:

* **Rastreamento de exibição de página**: substitua a chamada de rastreamento de exibição de página pelo comando `sendEvent` do SDK da Web:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Rastreamento automático de links**: a propriedade de configuração [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) está habilitada por padrão. Ela define automaticamente as variáveis de rastreamento de link corretas para enviar dados ao Adobe Analytics. Para desabilitar o rastreamento automático de links, defina esta propriedade como `false` no comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview).

* **Rastreamento manual de links**: o SDK da Web não tem comandos separados entre chamadas pageview e não pageview. Forneça essa distinção no objeto de carga.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.analytics.linkName = "Example custom link";
  dataObj.data.__adobe.analytics.linkType = "o";
  dataObj.data.__adobe.analytics.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Validar e publicar alterações**

Depois de remover todas as referências ao AppMeasurement e ao objeto `s`, publique as alterações no ambiente de desenvolvimento para validar se a nova implementação funciona. Depois de validar que tudo funciona corretamente, você poderá publicar suas atualizações para produção.

Se tiver sido migrado corretamente, `AppMeasurement.js` não será mais necessário no site, e todas as referências a esse script poderão ser removidas.

+++

Neste ponto, a implementação do Analytics está totalmente no SDK da Web e está preparada adequadamente para mudar para o Customer Journey Analytics no futuro.
