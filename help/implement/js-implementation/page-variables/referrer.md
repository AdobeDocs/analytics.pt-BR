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


# referenciador

A variável pode ser usada para restaurar as informações de referência perdidas.


<!-- 

referrer.xml

 -->

Normalmente, os redirecionamentos do lado do servidor e de JavaScript são usados para rotear visitantes até os locais apropriados. No entanto, quando um navegador é redirecionado, a URL original de referência fica perdida.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 255 bytes | R | Tráfego &gt; Localização de métodos de conversão &gt; Localização de métodos | document.referrer |

Muitas empresas usam redirecionamentos em muitos locais em seus sites. Por exemplo, um visitante pode ser enviado por meio de um redirecionamento de um resultado de pesquisa pago de mecanismo de pesquisa. Quando um navegador é redirecionado, normalmente a referrer fica perdida. A variável A variável *`referrer`* pode ser usada para restaurar o valor original *`referrer`* na primeira página após um redirecionamento. A *`referrer`* pode ser preenchida no lado do servidor ou por meio de JavaScript na sequência de consulta.

Para o Analytics registrar um referenciador, ele deve ser "bem formado", ou seja, deve seguir o formato padrão de URL, com protocolo e localização apropriada.

**Sintaxe e valores possíveis** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

Somente valores compatíveis com URL devem estar na *`referrer`*. Certifique-se de que a string seja codificada para URL (sem espaços).

**Exemplos** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**Configurações** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

A *`referrer`* deve ter a aparência de um URL padrão e incluir um protocolo.
