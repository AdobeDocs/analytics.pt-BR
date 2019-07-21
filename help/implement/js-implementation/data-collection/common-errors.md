---
description: As seções a seguir descrevem erros comuns nas contas dinâmicas.
keywords: Implementação do Analytics
seo-description: As seções a seguir descrevem erros comuns nas contas dinâmicas.
seo-title: Erros comuns
solution: Analytics
subtopic: Solução de problemas
title: Erros comuns
topic: Desenvolvedor e implementação
uuid: 04345355-60 cc -4678-81 c 3-31 0 c 86752 df 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Erros comuns

As seções a seguir descrevem erros comuns nas contas dinâmicas.

## Conta codificada {#section_FB6F89BF317F45D387C00986ACA690BC}

Se você desejar enviar sempre dados a um conjunto de relatórios específico, defina [!UICONTROL s_dynamicAccountSelection] como false (ou as variáveis podem ser removidas juntas:

```js
var s_account="defaultreportsuiteid" 
REMOVE: s.dynamicAccountSelection=true 
REMOVE: s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

Nesse caso, defaultreportsuiteid é sempre usada depois que as outras duas linhas são removidas.

## Posicionamento do código {#section_05375CB2EF5A414794BC8209C906AEEB}

Defining *`s_account`* after the lines of code does not override the dynamic account selection, as shown below.

```js
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
s_account="anotherreportsuiteid" 
```

No exemplo acima, a conta "anotherreportsuiteid" substitui "defaultreportsuiteid", mas não substitui nenhuma ocorrência de [!UICONTROL s.dynamicAccountList]. A função que avalia [!UICONTROL s.dynamicAccountList] é executada bem mais tarde no arquivo .JS.

## Marcação de vários relatórios {#section_6C014FA9B87D4622B483BCDE4281D2A9}

A marcação de vários relatórios pode ser usada juntamente com a seleção da conta dinâmica, como mostrado abaixo.

```js
s.dynamicAccountSelection=true 
s.dynamicAccountList="suiteid1,suiteid2=client.com" 
```

## Correspondência da conta dinâmica {#section_647AB47B38D640D6BCC853FDA4E4342D}

Não coloque as variáveis de [!UICONTROL correspondência da conta dinâmica] entre aspas. As opções são exibidas abaixo.

| Host/Nome de domínio | Nenhuma |
|---|---|
| String de consulta | s.dynamicAccountMatch=(window.location.search?window.location.search:"?") |
| Host/domínio e caminho | s.dynamicAccountMatch=window.location.host+window.lcation.pathname |
| Caminho e string de consulta | s.dynamicAccountMatch=window.location.pathname+(window.location.search?window.location.search""?") |
| URL completo | s.dynamicAccountMatch=window.location.href |

