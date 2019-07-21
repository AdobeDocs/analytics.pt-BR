---
description: Existem outros requisitos e configurações para a implementação do Analytics sem JavaScript.
keywords: Implementação do Analytics; diferenciação entre maiúsculas e minúsculas; codificar parâmetros de consulta; caracteres inválidos; solicitações de imagem seguras; comprimento máximo da variável; fazendo referência; url; cache; namespace
seo-description: Existem outros requisitos e configurações para a implementação do Analytics sem JavaScript.
seo-title: Implementação sem diretrizes do javascript
solution: Analytics
title: Implementação sem diretrizes do javascript
topic: Desenvolvedor e implementação
uuid: c 672 dd 63-1 c 74-4 f 66-8992-9257 c 5 a 75 e 36
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implementação sem diretrizes do javascript

Existem outros requisitos e configurações para a implementação do Analytics sem JavaScript.

Você pode exibir o código de amostra para compreender melhor a implementação. As informações a seguir descrevem os requisitos e configurações adicionais:

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**Diferenciação de maiúsculas e minúsculas**

The parameter names (`pageName`, `purchaseID`, and so forth) are case-sensitive and will not properly record data unless they appear as designated in the table displayed in [Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md).

**Codificar parâmetros de consulta**

Os valores de cada parâmetro de string de consulta deve ser codificado em URL. URL encoding converts characters that are normally illegal when appearing in a query string, such as a space character, into an encoded character beginning with `%`. Por exemplo, um caractere de espaço é convertido em `%20`.

A versão JavaScript desta função é chamada de escape (e para decodificação, unescape). O Microsoft IIS versão 5.0 também inclui uma função Escape e Unescape para codificação das sequências de consulta. Outras linguagens de script do servidor da Web também oferecem utilitários de codificação/descodificação.

**Tamanho máximo de variável**

Cada variável tem um tamanho máximo. Esse tamanho é especificado para cada variável em [Variáveis do Analytics](../../../implement/js-implementation/c-variables/sc-variables.md). Exceder o tamanho máximo de uma variável faz com que o valor essa variável fique truncado para armazenamento e seja exibido no Analytics.

**Caracteres Inválidos**

Caracteres com códigos de caracteres acima de 128 decimais são inválidos, assim como os códigos de caracteres de não impressão abaixo de 128. A formatação HTML ("&lt;h1&gt;") também é inválida, como símbolos de marca comercial, marca registrada e copyright.

**Seguro (&lt; https: &gt; vs. Non-Secure (&lt; http: &gt;) Solicitações de imagem**

Nas páginas acessadas via https (protocolo seguro), a parte do URL da solicitação de imagem é alterada para acomodar um conjunto diferente de servidores de coleta de dados.

As informações a seguir ilustram os urls diferentes usados para solicitações de imagem seguras e não seguras.

* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. A Adobe usa vários centros de dados e é necessário implementar a URL correta atribuída à sua organização. Todos os códigos obtidos por download do Admin Console dentro da conta de sua empresa têm o centro de dados correto fornecido automaticamente. O código fornecido de fontes externas pode precisar ser corrigido para apontar para o centro de dados correto.
* Para clientes que usam vários conjuntos de relatórios, eles devem ser listados apenas na seção do diretório, e não na seção do domínio do URL, como mostrado abaixo.
* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. A Adobe usa vários centros de dados e é necessário implementar a URL correta atribuída à sua organização.

**URL e URL de referência**

The URL and Referring URL may be populated from the server in the `g=` and `r=` variables. Use the Request ServerVariables (`HTTP\_REFERRER`) or Request ServerVariables `(URL) (IIS/ASP)`, or the appropriate variable for your server/scripting technology. The referring URL `( r=)` is extremely important for tracking referring URLs, domains, search engines, and search terms.

Se pagename não estiver sendo usado, é fundamental que o campo URL atual seja preenchido unicamente. If neither pageName nor Current URL `(g=)` is populated, the record is invalid and is not processed. No mínimo, a URL é um campo necessário para processar o registro.

**Efeitos de armazenamento em cache**

As páginas HTML e outras páginas da Web podem ser armazenadas em cache por navegadores ou servidores que estejam entre o visitante e o site que está oferecendo conteúdo. O armazenamento em cache evita uma contagem precisa de exibições de página e outros eventos, a menos que uma técnica de "bloqueio de cache" seja empregada.

O JavaScript padrão da Adobe inclui um método dinâmico para alterar a solicitação de imagem e evitar o armazenamento em cache de paginas e imagens, permitindo uma contagem precisa de exibições de página.

Entretanto, na criação de uma solicitação de imagem do lado do servidor, essa aleatoriedade não ocorre. Os recarregamentos de página e as páginas em cache (no cache do browser ou em um servidor proxy) não são contados em determinados casos, no uso de solicitações de imagem do lado do servidor.

SSL (`https:`) pages are not, by definition, ever cached so this warning applies only to non-secure (`http:`) pages. Additionally, pages with parameters (`https://www.samplesite.com/page.asp?parameter=1`) or certain file extensions (`.asp`, `.jsp`, etc.) também não são armazenadas em cache.

Os exemplos abaixo também ilustram uma solução de JavaScript mínima que monta primariamente o lado do servidor de solicitação de imagem e se prende a um número aleatório no navegador. Esse método supera o armazenamento em cache que seria encontrado em páginas HTML estáticas acessadas através de https: protocolo.

**Variável nameSpace**

O parâmetro da string de consulta nameSpace é necessário para implementações que não são JavaScript.

Exemplo: ns=nameSpace

Entre em contato com seu consultor Adobe ou gerente de conta para obter o valor de nameSpace de sua organização.
