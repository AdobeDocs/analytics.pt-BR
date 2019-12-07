---
description: Existem outros requisitos e configurações para a implementação do Analytics sem JavaScript.
keywords: Analytics Implementation;case sensitive;encode query parameters;invalid characters;secure image requests;maximum variable length;referring;url;caching;namespace
title: Implementar sem diretrizes do JavaScript
topic: Developer and implementation
uuid: c672dd63-1c74-4f66-8992-9257c5a75e36
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementar sem diretrizes do JavaScript

Existem outros requisitos e configurações para a implementação do Analytics sem JavaScript.

Você pode exibir o código de amostra para compreender melhor a implementação. As informações a seguir destacam os requisitos e configurações adicionais:

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**Diferenciação de maiúsculas e minúsculas**

Os nomes de parâmetro (`pageName`, `purchaseID` e assim por diante) fazem distinção entre maiúsculas e minúsculas e não gravarão dados adequadamente, a menos que eles sejam exibidos conforme designado na tabela exibida em [Parâmetros de consulta](/help/implement/js-implementation/data-collection/query-parameters.md).

**Codificar parâmetros de consulta**

Os valores de cada parâmetro de string de consulta deve ser codificado em URL. A codificação de URL converte caracteres que normalmente são inválidos quando aparecem em uma sequência de consulta, como um caractere de espaço, em um caractere codificado que começa com `%`. Por exemplo, um caractere de espaço é convertido em `%20`.

A versão JavaScript desta função é chamada de escape (e para decodificação, unescape). O Microsoft IIS versão 5.0 também inclui uma função Escape e Unescape para codificação das sequências de consulta. Outras linguagens de script do servidor da Web também oferecem utilitários de codificação/descodificação.

**Tamanho máximo de variável**

Cada variável tem um tamanho máximo. Esse tamanho é especificado para cada variável em [Variáveis do Analytics](/help/implement/js-implementation/c-variables/sc-variables.md). Exceder o tamanho máximo de uma variável faz com que o valor essa variável fique truncado para armazenamento e seja exibido no Analytics.

**Caracteres Inválidos**

Caracteres com códigos de caracteres acima de 128 decimais são inválidos, assim como os códigos de caracteres de não impressão abaixo de 128. A formatação HTML ("&lt;h1&gt;") também é inválida, como símbolos de marca comercial, marca registrada e copyright.

**Solicitações de imagem segura (&lt;https:&gt;) versus não segura (&lt;http:&gt;)**

Nas páginas acessadas via https (protocolo seguro), a parte do URL da solicitação de imagem é alterada para acomodar um conjunto diferente de servidores de coleta de dados.

As informações a seguir ilustram os URLs diferentes usados para solicitações de imagens seguras e não seguras.

* O * `*` no URL acima significa uma URL específica do centro de dados fornecida a você pelo seu Consultor Adobe. A Adobe usa vários centros de dados e é necessário implementar a URL correta atribuída à sua organização. Todos os códigos obtidos por download do Admin Console dentro da conta de sua empresa têm o centro de dados correto fornecido automaticamente. O código fornecido de fontes externas pode precisar ser corrigido para apontar para o centro de dados correto.
* Para clientes que usam vários conjuntos de relatórios, eles devem ser listados apenas na seção do diretório, e não na seção do domínio do URL, como mostrado abaixo.
* O * `*` no URL acima significa uma URL específica do centro de dados fornecida a você pelo seu Consultor Adobe. A Adobe usa vários centros de dados e é necessário implementar a URL correta atribuída à sua organização.

**URL e URL de referência**

O URL e o URL de referência podem ser preenchidos pelos servidores nas variáveis `g=` e `r=`. Use Request ServerVariables (`HTTP\_REFERRER`), Request ServerVariables `(URL) (IIS/ASP)` ou a variável apropriada para sua tecnologia de servidor/scripts. O URL de referência `( r=)` é extremamente importante para rastrear URLs de referência, domínios, mecanismos de pesquisa e termos de pesquisa.

Se pageName não estiver sendo usado, é fundamental que o campo URL atual seja preenchido unicamente. Se pageName ou Current URL `(g=)` não for preenchido, o registro será inválido e não será processado. No mínimo, a URL é um campo necessário para processar o registro.

**Efeitos de armazenamento em cache**

As páginas HTML e outras páginas da Web podem ser armazenadas em cache por navegadores ou servidores que estejam entre o visitante e o site que está oferecendo conteúdo. O armazenamento em cache impede uma contagem precisa de exibições de página e outros eventos, a menos que a técnica de "impedimento de cache" seja empregada.

O JavaScript padrão da Adobe inclui um método dinâmico para alterar a solicitação de imagem e evitar o armazenamento em cache de paginas e imagens, permitindo uma contagem precisa de exibições de página.

Entretanto, na criação de uma solicitação de imagem do lado do servidor, essa aleatoriedade não ocorre. Os recarregamentos de página e as páginas em cache (no cache do browser ou em um servidor proxy) não são contados em determinados casos, no uso de solicitações de imagem do lado do servidor.

As páginas SSL (`https:`) não são, por definição, jamais armazenadas em cache, portanto, este aviso se aplica apenas a páginas não seguras (`http:`). Além disso, as páginas com parâmetros (`https://www.samplesite.com/page.asp?parameter=1`) ou determinadas extensões de arquivos (`.asp`, `.jsp`, etc.) também não são armazenadas em cache.

Os exemplos abaixo também ilustram uma solução de JavaScript mínima que monta primariamente o lado do servidor de solicitação de imagem e se prende a um número aleatório no navegador. Esse método supera o armazenamento em cache que seria encontrado nas páginas HTML estáticas acessadas pelo protocolo https:.

**Variável nameSpace**

O parâmetro da string de consulta nameSpace é necessário para implementações que não são JavaScript.

Exemplo: ns=nameSpace

Entre em contato com seu consultor Adobe ou gerente de conta para obter o valor de nameSpace de sua organização.
