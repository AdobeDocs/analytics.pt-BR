---
title: Módulo de integração
description: O Módulo de integração permite que os parceiros da Adobe integrem os esforços de coleta de dados à empresa.
translation-type: ht
source-git-commit: e8f22d3e9efd57de0134a3c4ff55d0ad148f3df1

---


# Módulo de integração

O Módulo de integração permite que os parceiros da Adobe integrem os esforços de coleta de dados à empresa. Essa integração oferece a oportunidade de uma conexão de dados bidirecional. Normalmente, o uso do Módulo de integração é conduzido por um parceiro da Adobe.

> [!NOTE] A solicitação de dados do parceiro na implementação pode aumentar os atrasos entre o carregamento de página e os dados enviados para os servidores de coleta de dados da Adobe. Se um visitante carregar uma nova página antes que os dados sejam enviados, essa página não será registrada.

## Fluxo de trabalho do Módulo de integração

1. Um visitante do site carrega uma página que inicia uma `get` solicitação de dados do parceiro.
2. O parceiro da Adobe recebe a solicitação `get` e compacta as variáveis apropriadas em um objeto JSON. O objeto JSON é retornado.
3. O site recebe o objeto JSON e chama `setVars` para atribuir as informações contidas no objeto JSON às variáveis do Adobe Analytics
4. Uma solicitação de imagem é enviada para os servidores de coleção de dados da Adobe.

## Implementação do Módulo de integração

Uma empresa que trabalha com um parceiro da Adobe pode usar essas etapas para começar a usar o Módulo de integração com êxito.

### Obter código do Módulo de integração

A obtenção do código do módulo requer um usuário com acesso de Administrador de produto ou que pertença a um perfil de produto com acesso ao Gerenciador de código. O método para obter o código do módulo é o mesmo para todos os métodos de implementação, incluindo o Adobe Experience Platform Launch.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
1. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
1. Na navegação da parte superior, clique em [!UICONTROL Admin] > [!UICONTROL Gerenciador de código].
1. Baixe a biblioteca JavaScript AppMeasurement mais recente.
1. Após o download, descompacte o arquivo e localize `AppMeasurement_Module_Integrate.js`.

### Coloque o Módulo de integração na implementação

A implementação do Módulo de integração no site requer acesso ao Adobe Experience Platform Launch. Se você usar uma implementação antiga do JavaScript, será necessário acessar o código-fonte do site da empresa.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade do Launch que deseja editar.
3. Clique na guia Extensões e, em seguida, clique em Configurar no Adobe Analytics.
4. Abra a opção &quot;Configurar rastreador usando código personalizado&quot; e clique em &quot;&lt;/> Abrir editor&quot;.
5. Cole o código do Módulo de integração na janela modal do código. Clique em Salvar após a conclusão.

## Métodos do Módulo de integração

Depois que o Módulo de integração tiver sido implementado, use esses métodos para configurá-lo para enviar e receber dados do parceiro desejado da Adobe.

### adicionar

O método `add` instancia um objeto do parceiro, que serve como um armazenamento intermediário de dados variáveis ao compartilhar dados entre sistemas do parceiro e a implementação. Esse método é necessário para todas as integrações. Um objeto do parceiro separado deve ser usado para cada parceiro exclusivo, se vários parceiros forem usados em uma única implementação.

```JavaScript
s.Integrate.add("<partner_name>");
```

A empresa geralmente trabalha com um parceiro da Adobe para determinar o valor do nome do parceiro.

### beacon

O método `beacon` cria uma solicitação de imagem e a aponta para o URL especificado. Essas solicitações de imagem são diferentes das solicitações de imagem padrão. O método de beacon normalmente envia dados para o parceiro da Adobe, em vez dos servidores de coleta de dados da Adobe.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

A empresa geralmente trabalha com o parceiro da Adobe para determinar o valor do nome do parceiro. As sequências de consulta incluídas no URL são opcionais e dependem do parceiro. O Módulo de integração inclui automaticamente uma sequência de consulta que contém um número aleatório para impedir o armazenamento em cache do navegador.

### atraso

A Adobe está trabalhando com equipes internamente para documentar esse método.

### get

O método `get` permite que um cliente importe variáveis do parceiro e armazene no objeto do parceiro. Quando os dados estiverem no objeto do parceiro, poderão ser atribuídos às variáveis do Analytics e enviados em uma solicitação de imagem. Esse método chama um URL, que aponta para um objeto JSON que contém os dados desejados.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Nome do parceiro:** a empresa geralmente trabalha com o parceiro da Adobe para determinar o valor do nome do parceiro.
* **URL para o objeto JSON:** o URL para um objeto JSON que contém as variáveis do parceiro a serem incorporadas em uma solicitação de imagem.
* **Parâmetros da sequência de consulta:** informações da conta do parceiro que identificam a empresa no sistema do parceiro. O parceiro da Adobe usa essas informações para identificar o conjunto de dados.

O módulo de Integração adiciona automaticamente mais sequências de consulta ao URL. Uma sequência de consulta var especifica o nome do objeto JSON que o módulo espera do parceiro. Um número aleatório também é adicionado para impedir o cache do navegador.

### pronto

A Adobe está trabalhando com equipes internamente para documentar esse método.

### useVars

O `useVars` método permite que o cliente compartilhe valores variáveis com um parceiro da Adobe.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

A empresa geralmente trabalha com um parceiro da Adobe para determinar os valores do nome do parceiro e as variáveis que o parceiro usa.

### setVars

O método `setVars` permite que o cliente preencha as variáveis do Analytics usando os dados de parceiros recuperados. Os dados do parceiro podem ser o resultado de um método `get`, uma atribuição estática ou qualquer outro mecanismo que preencha o objeto do parceiro com dados.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

A empresa geralmente trabalha com um parceiro da Adobe para determinar os valores do nome do parceiro e as variáveis que o parceiro usa.

### script

O método `script` permite que um parceiro da Adobe chame o JavaScript adicional do site parceiro, se determinadas condições forem atendidas (por exemplo, se a variável de campanha estiver definida).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

A empresa geralmente trabalha com o parceiro da Adobe para determinar o valor do nome do parceiro. As sequências de consulta incluídas no URL são opcionais e dependem do parceiro. O Módulo de integração inclui automaticamente uma sequência de consulta que contém um número aleatório para impedir o armazenamento em cache do navegador.
