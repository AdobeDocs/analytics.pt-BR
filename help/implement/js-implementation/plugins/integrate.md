---
title: Módulo de integração
seo-title: Módulo de integração para o Adobe Analytics
description: O Módulo Integrate permite aos parceiros da Adobe integrar seus esforços de coleta de dados à organização.
seo-description: O Módulo Integrate permite aos parceiros da Adobe integrar seus esforços de coleta de dados à organização.
translation-type: tm+mt
source-git-commit: dae73042ace20eded9d0caf690a14203827f903a

---


# Módulo de integração

O Módulo Integrate permite aos parceiros da Adobe integrar seus esforços de coleta de dados à organização. Essa integração fornece a oportunidade de uma conexão de dados bidirecional. Normalmente, o uso do Módulo de integração é direcionado por um parceiro da Adobe.

> [!NOTE] Solicitar dados de parceiro na implementação pode aumentar os atrasos entre o carregamento da página e os dados enviados para os servidores de coleta de dados da Adobe. Se um visitante carregar uma nova página antes dos dados serem enviados, essa página não será gravada.

## Fluxo de trabalho do Módulo de integração

1. A visitor to your site loads a page that initiates a `get` request for partner data.
2. The Adobe partner receives the `get` request and packages the appropriate variables in a JSON object. O objeto JSON é retornado.
3. Your site receives the JSON object and calls `setVars` to assign the information contained in the JSON object to Adobe Analytics variables
4. Uma solicitação de imagem é enviada para os servidores de coleção de dados da Adobe.

## Implementação do módulo de integração

Uma organização que trabalha com um parceiro da Adobe pode usar essas etapas para começar a usar o Módulo de integração.

### Obter o código do Módulo de integração

Obter o código do módulo requer um usuário com acesso ao Administrador de produto ou pertencente a um perfil de produto com acesso ao Gerenciador de código. O método para obter o código do módulo é o mesmo para todos os métodos de implementação, incluindo o Adobe Experience Platform Launch.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Clique no ícone de 9-quadrado na parte superior direita e clique no logotipo colorido do Analytics.
1. In the top navigation, click [!UICONTROL Admin] &gt; [!UICONTROL Code Manager].
1. Baixe a biblioteca mais recente do appmeasurement do javascript.
1. Once downloaded, unzip the file and locate `AppMeasurement_Module_Integrate.js`.

### Colocar o módulo de integração na sua implementação

Implementar o módulo de integração no site requer acesso à Adobe Experience Platform Launch. Se você usar uma implementação de javascript herdada, é necessário acessar o código fonte do site da sua organização.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. Clique na propriedade Launch que pretende editar.
3. Clique na guia Extensões e clique em Configurar sob o Adobe Analytics.
4. Abra o menu «Configurar rastreador usando o esquema personalizado» e clique em «&lt;/&gt; Abrir editor».
5. Cole o código do Módulo de integração na janela modal do código. Clique em Salvar uma vez concluída.

## Métodos do módulo Integrar

Depois que o Módulo de integração for implementado, use esses métodos para configurá-lo para enviar e receber dados do parceiro da Adobe desejado.

### add

The `add` method instantiates a partner object, which serves as an intermediate store of variable data when sharing data between partner systems and your implementation. Esse método é necessário para todas as integrações. Um objeto de parceiro separado deve ser usado para cada parceiro único se vários parceiros forem usados em uma única implementação.

```JavaScript
s.Integrate.add("<partner_name>");
```

Sua organização geralmente trabalha com um parceiro da Adobe para determinar o valor do nome do parceiro.

### beacon

`beacon` O método cria uma solicitação de imagem e o aponta para o URL especificado. Essas solicitações de imagem são diferentes das solicitações de imagem padrão. O método beacon normalmente envia dados para o parceiro da Adobe em vez dos servidores de coleta de dados da Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

Em geral, sua organização trabalha com o parceiro da Adobe para determinar o valor do nome do parceiro. As sequências de consulta incluídas no URL são opcionais e dependem do parceiro. O Módulo Integrate inclui automaticamente uma sequência de consulta contendo um número aleatório para impedir o armazenamento em cache do navegador.

### delay

A Adobe está trabalhando com equipes internamente para obter este método documentado.

### get

`get` O método permite que um cliente importe variáveis de parceiro de importação e as armazene no objeto parceiro. Quando os dados estão no objeto parceiro, eles podem ser atribuídos a variáveis do Analytics e enviados em uma solicitação de imagem. Este método chama um URL, que aponta para um objeto JSON que contém dados desejados.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Nome do parceiro:** Em geral, sua organização trabalha com o parceiro da Adobe para determinar o valor do nome do parceiro.
* **URL para objeto JSON:** O URL para um objeto JSON que contém as variáveis de parceiro para incorporar em uma solicitação de imagem.
* **Parâmetros da string de consulta:** Informações de conta do parceiro que identificam sua organização no sistema do parceiro. O parceiro da Adobe usa essas informações para identificar seu conjunto de dados.

O módulo Integrate adiciona automaticamente mais strings de consulta ao URL. Uma sequência de consulta var especifica o nome do objeto JSON que o módulo espera de volta do parceiro. Um número aleatório também é adicionado para impedir o armazenamento em cache do navegador.

### ready

A Adobe está trabalhando com equipes internamente para obter este método documentado.

### Usevars

`useVars` O método permite que o cliente compartilhe valores de variáveis com um parceiro da Adobe.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

A sua organização normalmente trabalha com um parceiro da Adobe para determinar os valores para o nome do parceiro e as variáveis que o parceiro usa.

### Setvars

The `setVars` method lets the client populate Analytics variables using partner data retrieved. Partner data can be the result of a `get` method, a static assignment, or any other mechanism that populates the partner object with data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

A sua organização normalmente trabalha com um parceiro da Adobe para determinar os valores para o nome do parceiro e as variáveis que o parceiro usa.

### script

The `script` method lets an Adobe partner to call additional JavaScript from the partner site if certain conditions are met (for example, if the campaign variable is set).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

Em geral, sua organização trabalha com o parceiro da Adobe para determinar o valor do nome do parceiro. As sequências de consulta incluídas no URL são opcionais e dependem do parceiro. O Módulo Integrate inclui automaticamente uma sequência de consulta contendo um número aleatório para impedir o armazenamento em cache do navegador.
