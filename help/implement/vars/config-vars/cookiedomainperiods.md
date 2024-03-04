---
title: cookieDomainPeriods
description: Ajude o AppMeasurement a entender em qual domínio armazenar cookies se o domínio tiver um ponto no sufixo.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: fe33da47c109adacb8162c7165ad4c63bd65c08d
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 43%

---


# cookieDomainPeriods

O AppMeasurement determina a localização do cookie observando o domínio e seu sufixo. Para domínios como `example.com`, o AppMeasurement define cookies no local correto. No entanto, em outros domínios como o `example.co.uk`, o AppMeasurement pode definir cookies por engano no `co.uk`. A maioria dos navegadores rejeita cookies definidos nesse domínio inválido, causando problemas com a identificação do visitante.

A variável `cookieDomainPeriods` ajuda o AppMeasurement a determinar onde os cookies do Analytics são definidos, indicando que o sufixo do domínio tem um ponto extra. Essa variável permite que o AppMeasurement acomode o ponto extra no sufixo do domínio e defina os cookies no local correto.

* Para domínios como `example.com` ou `www.example.com`, essa variável não precisa ser definida. Se necessário, é possível definir essa variável como `"2"`.
* Para domínios como `example.co.uk` ou `www.example.co.jp`, defina essa variável como `"3"`.


>[!IMPORTANT]
>
>Não considere subdomínios para essa variável. Por exemplo, não defina `cookieDomainPeriods` no URL de exemplo `store.toys.example.com`. O AppMeasurement reconhece por padrão que os cookies devem ser armazenados no `example.com`, mesmo em URLs com vários subdomínios.


## Períodos de domínio de cookie, cookies de terceiros e identificação de visitante herdada

Somente quando estiver usando a identificação de visitante herdada do Adobe Analytics (em vez do serviço de identidade Experience Cloud recomendado), a configuração implícita ou explícita de `cookieDomainPeriods` podem ter implicações em como os visitantes são identificados, dependendo se os cookies de terceiros estão bloqueados ou não.

A tabela a seguir ilustra quatro cenários possíveis.

| Cenário | `cookieDomainPeriods` a configuração é ... | Cookies de terceiros estão bloqueados? | Resultado ao usar o serviço de identificação de visitante herdado do Adobe Analytics |
|:---:|---|---|---|
| 1 | <span style="color:green">Correto</span> | Não | Os visitantes são identificados com um `s_vi` cookie, definido no lado do servidor. |
| 2 | <span style="color:green">Correto</span> | Sim | Os visitantes são identificados com um fallback `s_fid` cookie, definir no lado do cliente (domínio da página própria). |
| 3 | <span style="color:red">Incorreto</span> | Não | Os visitantes são identificados com um identificador de fallback com base na combinação de agente do usuário e endereço IP. <br/>O AppMeasurement é forçado a definir cookies como cookies de terceiros.<br/> A variável `s_vi` o cookie possivelmente é definido quando `cookieDomainPeriods` não é transmitido corretamente. |
| 4 | <span style="color:red">Incorreto</span> | Sim | Os visitantes são identificados com um identificador de fallback com base na combinação de agente do usuário e endereço IP.<br/>O AppMeasurement é forçado a definir cookies como cookies de terceiros que estão bloqueados, de modo que nenhum cookie é definido. |

>[!CAUTION]
>
>Você pode ter configurado inadvertidamente `cookieDomainPeriods` <span style="color:red">incorreto</span> (deixando-o no valor padrão de `"2"`) ao usar domínios como `example.co.uk`. Essa configuração implícita incorreta resulta no fato de que você está identificando visitantes seguindo o cenário 3 ou 4.
>
>O AppMeasurement versão 2.26.x ou posterior configura `cookieDomainPeriods` automaticamente com o valor correto, para que somente os cenários 1 ou 2 sejam possíveis. Ao atualizar para a versão 2.26.x ou posterior do AppMeasurement, ao identificar os visitantes incorretamente no momento (cenário 3 ou 4), a atualização tem grandes implicações.
>
>* Os identificadores de visitantes estão sendo redefinidos e os visitantes aparecerão como novos visitantes. Não haverá como vincular a nova atividade ao identificador de visitante anterior.
>* Os cookies são definidos (como para rastreamento de link ou Activity Map, por exemplo,`s_sq` cookie), resultando em diferenças repentinas nos relatórios.
>
>Ao configurar corretamente `cookieDomainPeriods` melhorará a funcionalidade do AppMeasurement e do Analytics, é recomendável avaliar se você é afetado pelas alterações resultantes da atualização da biblioteca do AppMeasurement.
>
> Consulte [Cookies do Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=pt-BR) para obter mais informações sobre os cookies que o AppMeasurement usa.

## Períodos de domínio de cookie usando o SDK da Web

O SDK da Web pode determinar o domínio de armazenamento de cookies correto sem essa variável.

## Períodos de domínio de cookie usando a extensão Adobe Analytics

Pontos de domínio é um campo da opção [!UICONTROL Cookies] ao configurar a extensão Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
1. Expanda a opção [!UICONTROL Cookies], que revela o campo [!UICONTROL Períodos de domínio].

Defina esse campo como `3` somente em domínios que contenham um ponto no sufixo. Caso contrário, esse campo poderá ser deixado em branco.

## Períodos de domínio de cookie no AppMeasurement de código e no editor de código personalizado da extensão do Analytics

Você pode definir a variável `cookieDomainPeriods` na biblioteca JavaScript do AppMeasurement ou no editor de código personalizado da extensão do Analytics.

A variável `cookieDomainPeriods` é uma cadeia de caracteres normalmente definida como `"3"`, somente em domínios que contêm um ponto no sufixo. Seu valor padrão é `"2"`, que acomoda a maioria dos domínios.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
