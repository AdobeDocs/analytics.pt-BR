---
description: O plug-in getValOnce impede que determinada variável seja definida como o valor definido anteriormente. Ele usa um cookie para determinar o último valor da variável. Se o valor atual corresponde ao valor do cookie, a variável é substituída por uma string em branco antes de ser enviada para os servidores de processamento da Adobe. Esse plug-in é útil para evitar o aumento da instância da variável de conversão quando os usuários atualizam a página ou clicam no botão Voltar.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getValOnce
topic: Developer and implementation
uuid: 82fe0da5-3bc4-4632-8c62-7b5683f6b587
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getValOnce

O plug-in getValOnce impede que determinada variável seja definida como o valor definido anteriormente. Ele usa um cookie para determinar o último valor da variável. Se o valor atual corresponde ao valor do cookie, a variável é substituída por uma string em branco antes de ser enviada para os servidores de processamento da Adobe. Esse plug-in é útil para evitar o aumento da instância da variável de conversão quando os usuários atualizam a página ou clicam no botão Voltar.

>[!IMPORTANT]
>
>Este plug-in não foi validado para ser compatível com o [AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). [Suporte a Plug-in do AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

**Parâmetros**

```js
s.eVar1=s.getValOnce(variable,cookie,expiration,minute);
```

* **Variável:** a variável que será verificada. Normalmente, equivale à variável que está sendo definida.
* **Cookie:** o nome do cookie que armazena o valor anterior que será comparado. O cookie pode ter qualquer valor.
* (Opcional) **Expiração:** o número de dias em que o cookie expirará. Se não estiver definida ou estiver definida como 0, a expiração padrão será a sessão do navegador.
* (Opcional) **Minuto:** se você definir isso como o valor da string *`m`*, o valor de expiração é definido em minutos em vez de dias. Se não estiver definido, *`days`* será a expiração padrão.

**Propriedades**

* Normalmente, esse plug-in é usado em variáveis de conversão. No entanto, é possível usá-lo em qualquer variável do [!DNL Analytics].
* Quando o JavaScript encontra essa função, ele compara o valor definido ao que está armazenado no cookie. Se o valor definido for diferente do valor do cookie, o valor definido será estabelecido. Se o valor definido for o mesmo que o valor do cookie, será retornada uma string vazia.
* O cookie só pode armazenar um único valor, ou seja, o plug-in é semelhante a apenas o último valor definido.
* O plug-in não impede que todos os valores definam a variável depois de ser definida. O plug-in só impede que o último valor seja definido várias vezes em sequência.
* Se o usuário final bloquear ou rejeitar cookies, o valor original sempre será retornado.
* A sessão do plug-in é diferente do que o [!DNL Analytics] define como uma sessão (ou visita). O[!DNL Analytics] finaliza uma sessão depois de 12 horas de atividade ou 30 minutos de inatividade. Como o plug-in usa a definição de sessão do navegador, ele só é encerrado depois que o usuário fecha a guia ou sair do navegador.

   * Se um usuário fechar sua página, abrir uma guia diferente e navegar de volta para o site em 30 minutos, o plug-in criará uma nova sessão enquanto mantém a visita do [!DNL Analytics] aberta.
   * Se um usuário mantém a janela do navegador aberta sem clicar em um link por mais de 30 minutos, a visita do [!DNL Analytics] expira enquanto mantém a sessão do navegador aberta.

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Implementação {#section_177FF7F425B64FFB83CDE15A6ACC8D21}

> [!NOTE]Se sua organização usa Canais de marketing e tem regras configuradas com base em `s.campaign`, é recomendável não usar o plug-in getValOnce ao definir o valor de `s.campaign`. Isso poderia levar à atribuição incorreta de um canal a um click-through de campanha secundária.

Para implementar esse plug-in, coloque o seguinte código no arquivo [!DNL s_code.js]

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getValOnce_v1.11 
 */ 
s.getValOnce=new Function("v","c","e","t","" 
+"var s=this,a=new Date,v=v?v:'',c=c?c:'s_gvo',e=e?e:0,i=t=='m'?6000" 
+"0:86400000,k=s.c_r(c);if(v){a.setTime(a.getTime()+e*i);s.c_w(c,v,e" 
+"==0?0:a);}return v==k?'':v");
```

Depois que o código acima for implementado, defina a variável desejada usando a função *`getValOnce`*. Os exemplos a seguir mostram como implementá-lo.

**Impedindo que o mesmo valor de campanha seja definido, se um valor duplicado for detectado dentro de 30 dias da definição do cookie:**
`s.campaign=s.getValOnce(s.campaign,'s_cmp',30);`  **Impede que o mesmo valor de eVar1 seja definido, se um valor duplicado for detectado em 30 minutos após a definição do cookie:**
`s.eVar1=s.getValOnce(s.eVar1,'s_ev1',30,'m');`  **Impede que o mesmo valor de eVar2 seja definido várias vezes na mesma sessão do navegador:**
`s.eVar2=s.getValOnce(s.eVar2,'s_ev2');`  **Observações**

* Sempre teste a instalação do plug-in para verificar se a coleta de dados ocorre como esperado antes da implantação no ambiente de produção.
* Certifique-se de excluir o cookie ou então de usar valores novos e exclusivos durante o teste, caso contrário as variáveis não serão enviadas.

