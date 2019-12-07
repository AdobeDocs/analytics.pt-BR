---
description: As empresas usam o Analytics para determinar o sucesso de uma campanha por email.
keywords: Analytics Implementation
title: Acompanhamento de email externo
topic: Developer and implementation
uuid: fa450f45-14cf-4d0d-a87c-14a946512a9b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Acompanhamento de email externo

As empresas usam o Analytics para determinar o sucesso de uma campanha por email.

O[!DNL Analytics] pode informar os dados de análise da campanha por email usando diversas métricas principais, incluindo as seguintes:

| Métrica | Descrição |
|---|---|
| Click-throughs | Exibe o número de click-throughs rastreados do email para a página inicial. |
| Compras e/ou sucessos | Exibe o número de compras resultantes do email. |
| Pedidos | Exibe o número de pedidos realizados como resultado do email. |
| Rendimento | Exibe o valor em dólar por visita gerado pelo email. |
| Conversão | Exibe o número de clientes potenciais, registros e outros eventos bem-sucedidos gerados pelo email. |

As modificações no corpo do email HTML e a biblioteca JavaScript são necessárias para capturar as métricas principais mostradas acima.

## Implementação {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

Existem várias etapas a seguir com o objetivo de exibir com êxito os dados de análise da campanha por email. As etapas são descritas abaixo.

1. Criar códigos de rastreamento exclusivos.

   Com frequência, os usuários pedem recomendações de rastreamento para cada campanha exclusiva. Isso fica totalmente a critério deles, com base no que funciona melhor. Cada usuário é diferente. A Adobe recomenda que cada usuário gere códigos de rastreamento amigáveis, como mostrado no exemplo abaixo:

   * sc_cid=A1123A321 &gt; "A" sinaliza uma campanha afiliada
   * sc_cid=EM033007 &gt; "EM" sinaliza uma campanha por email
   * sc_cid=GG987123 &gt; "GG" significa Google e é uma campanha de pesquisa paga
   Entre em contato com o Adobe [!DNL Customer Care] para obter detalhes sobre a configuração e o uso de códigos de rastreamento.

1. Adicione parâmetros da string de consulta aos links de email HTML.

   Para rastrear um click-through do usuário e os eventos bem-sucedidos subsequentes, um parâmetro da string de consulta deve ser adicionado a cada link dentro do email HTML. É possível rastrear cada link separadamente ou todos eles juntos. Cada link pode ter um código de rastreamento exclusivo ou todos os links podem ter o mesmo código de rastreamento. Considere o link hipotético a seguir dentro do email de um site:

   ```js
   <a href="https://www.mycompany.com/index.asp">Visit our home page</a>
   ```

   Os parâmetros da string de consulta a seguir ?sc_cid=112233B devem ser adicionados ao link acima:

   ```js
   <a href= "https://www.mycompany.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. Atualize a biblioteca JavaScript.

   A alteração do código no arquivo JavaScript, [!DNL s_code.js], permite capturar a quantidade de usuários (e quais usuários) que efetuaram click-through pelo email e participaram dos eventos bem-sucedidos subsequentes. Existem duas etapas para atualizar a biblioteca JavaScript.

   1. Personalize [!DNL s_code.js] chamando o parâmetro [!UICONTROL getQueryParam].

      O arquivo [!DNL s_code.js]   deve ser colocado em um local no servidor da Web em que cada página da Web possa acessá-lo. A função *`doPlugins`* nesse arquivo deve ser alterada para que capture os parâmetros da sequência de consulta nos links de email. Por exemplo:

      ```js
      /* Plugin Config */ 
      s.usePlugins=true 
      function s_doPlugins(s) { 
       /* Add calls to plugins here */ 
       // External Campaigns 
      s.campaign=s.getQueryParam('source') 
      } 
      s.doPlugins=s_doPlugins 
      ```

      Cada parâmetro da string de consulta que deve ser copiada em uma variável deve ter uma chamada de [!UICONTROL getQueryParam]. No exemplo acima, o parâmetro da string de consulta [!UICONTROL sc_cid] é copiado em  *`campaign`*.

      Somente a primeira chamada para [!UICONTROL getQueryParam] é necessária para capturar click-throughs. Entre em contato com o Adobe [!DNL Customer Care] para implementar esta função e garantir que sua versão do arquivo JavaScript contenha o plug-in [!UICONTROL getQueryParam].

   1. Verifique se o código para colar as tags do JavaScript estão em todas as páginas iniciais. Este código para colar deve mencionar a versão do [!DNL s_code.js] alterada na Parte A.

      É importante ter em mente os pontos a seguir ao atualizar a biblioteca de JavaScript. Esses pontos são listados abaixo.

      * O parâmetro da string de consulta [!UICONTROL _cid] deve estar visível no URL da página inicial final, caso contrário não haverá registros de conversão de click-throughs.
      * O parâmetro [!UICONTROL sc_cid] é um exemplo de parâmetro da string de consulta. É possível usar e capturar qualquer parâmetro de string de consulta por meio do plug-in [!UICONTROL getQueryParam]. Verifique se os parâmetros da string de consulta são usados apenas para o rastreamento da campanha. Sempre que os parâmetros forem exibidos em uma string de consulta, seus valores serão copiados em *`campaign`*.

1. Use [!UICONTROL SAINT] para classificar os códigos de rastreamento de campanha.

   A [!UICONTROL ferramenta de gerenciamento de campanha, SAINT,] pode ser usada para converter códigos de rastreamento em nomes amigáveis. Ela pode ser usada para resumir o sucesso de cada campanha por email. A etapa 5 abaixo destaca o processo necessário para configurar uma campanha por email.

1. Consulte a definição de caminho por campanha por email (opcional).

   A análise de definição de caminho por campanha por email pode ser feita da mesma forma que para outras campanhas. É possível usar uma variável para mostrar a definição de caminho por campanha, como explicado nas etapas a seguir:

   1. Consulte o Adobe [!DNL Customer Care] para saber como ativar a definição de caminho para uma variável [!UICONTROL Custom Insight] (prop)

   1. Em todas as páginas, copie o nome da página na [!DNL s.prop] designada. 
   1. Na página inicial do email, anexe o nome da campanha de email à prop. O resultado exibido será mostrado abaixo:

      ```js
      s.prop1="Home Page : 123456"
      ```

      Quando a definição do caminho é ativada para a variável [!UICONTROL Custom Insight], você pode usar os relatórios [!UICONTROL Caminho] (como [!UICONTROL Fluxo da próxima página] ou [!UICONTROL Fallout]) para ver a navegação do visitante a partir da página de aterrissagem. 

