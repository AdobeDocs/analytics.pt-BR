---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# visitorNamespace

A variável é usada para identificar o domínio com o qual os cookies são definidos.


<!-- 

visitorNamespace.xml

 -->

*`visitorNamespace`* é usada no seu arquivo JavaScript, não exclua-a ou altere-a. Se *`visitorNamespace`* for alterado, todos os visitantes relatados no Analytics podem se tornar novos visitantes. O histórico do visitante se torna desconectado do tráfego atual e futuro. Não altere essa variável sem aprovação de um representante da Adobe.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | ns | N/D | "" |

O Analytics um cookie para identificar de forma única os visitantes do site. Se *`visitorNamespace`* não for usado, o cookie será associado ao 2o7.net. Se *`visitorNamespace`* for usado, o cookie será associado com um subdomínio de 2o7.net. Todos os visitantes do site devem ter os cookies associados ao mesmo domínio ou subdomínio.

O motivo para usar a variável *`visitorNamespace`* é evitar a possibilidade de sobrecarregar um limite de cookie de um navegador. O Internet Explorer impõe um limite de 20 cookies por domínio. Se você usar a variável *`visitorNamespace`*, os cookies do Analytics de outras empresas não entrarão em conflito com os cookies de seus visitantes.

**Sintaxe e valores possíveis** {#section_EE247FE371784CA4B6058182181F3EA1}

O valor de *`visitorNamespace`* deve ser fornecido pela Adobe e é uma string de caracteres ASCII que não contêm vírgulas, pontos, espaços ou caracteres especiais.

```js
s.visitorNamespace="company_specific_value"
```

**Identificação do visitante nos conjuntos de relatórios** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

Se você não especificar um `visitorNamespace`, cada conjunto de relatórios na empresa recebe o próprio cookie da ID de visitante gravado como `s_vi_[random string]`. Se você especificar `visitorNamespace`, o mesmo cookie `s_vi` será utilizado para todos os conjuntos de relatórios que enviam dados para o `trackingServer` especificado. Se você implementou a marcação multiconjunto, certifique-se de especificar o namespace do visitante para que o cookie seja utilizado por cada conjunto de relatórios.

**Exemplos** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Configurações** {#section_1128A2531ECC43DFA6749ECC21F050A2}

Nenhum
