---
title: Parâmetros de consulta para coleta de dados
description: Lista todos os parâmetros da string de consulta usados em solicitações de imagem.
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Parâmetros de consulta para coleta de dados

A tabela a seguir lista todos os parâmetros da string de consulta que a Adobe usa em solicitações de imagem. Essas informações podem ser usadas ao depurar usando analisadores [de](packet-monitor.md)pacote, ao codificar solicitações [de imagem](../other/hardcoded.md)pesada ou ao usar Variáveis [](../vars/page-vars/dynamic-variables.md)dinâmicas.

| Parâmetro | Variável de implementação do Analytics | Descrição |
| --- | --- | --- |
| `aamlh` | Nenhum | Dica de localização do Audience Manager. Usada na integração do Perfil compartilhado da Experience Cloud. |
| `aamb` | Nenhum | Blob do Audience Manager. Usada na integração do Perfil compartilhado da Experience Cloud. |
| `aid` | Nenhum | ID de visitante do Analytics. |
| `AQB` | Nenhum | Indica o início de uma string de consulta de solicitação de imagem. |
| `AQE` | Nenhum | Indica o fim de uma solicitação de imagem, o que significa que a solicitação não foi truncada. |
| `bh` | Nenhum | Altura do navegador (em pixels). Usada na dimensão Altura do navegador. |
| `bw` | Nenhum | Largura do navegador (em pixels). Usada na dimensão Largura do navegador. |
| `c` | Nenhum | Qualidade de cor (em bits). Usada na dimensão de Profundidade de cor. |
| `c.` | `contextData` | Indica o início das variáveis de dados de contexto. Nunca contém um valor. |
| `.c` | `contextData` | Indica o fim das variáveis de dados de contexto. Nunca contém um valor. |
| `c1` - `c75` | `prop1` - `prop75` | Variáveis de tráfego personalizadas. |
| `cc` | `currencyCode` | O tipo de moeda usado na ocorrência. |
| `cdp` | `cookieDomainPeriods` | O número de períodos em um domínio. Usado para ajudar a armazenar cookies corretamente. |
| `ce` | `charSet` | A codificação de caracteres da solicitação de imagem. |
| `cl` | `cookieLifetime` | A duração do cookie do visitante. |
| `ch` | `channel` | Usado na dimensão Seções do site. |
| `cp` | Nenhum | Usada na dimensão Tipo de ocorrência. |
| `ct` | Nenhum | Usada na dimensão Tipo de conexão. |
| `D` | `dynamicVariablePrefix` | Indica o que usar para variáveis dinâmicas. |
| `ev` | `events` | Encurtar para a string de `events` consulta. |
| `events` | `events` | Lista de eventos separada por vírgulas na página. |
| `g` | `pageURL` | O URL atual da página, até 255 bytes. |
| `-g` | `pageURL` | URLs maiores que 255 bytes são divididos. Os primeiros 255 bytes aparecem no `g` parâmetro e todos os bytes restantes aparecem no `-g` parâmetro. |
| `gn` | `pageName` | Encurtar para a string de `pageName` consulta. |
| `gt` | `pageType` | Encurtar para a string de `pageType` consulta. |
| `h1` - `h5` | `hier1` - `hier5` | Variáveis de hierarquia. |
| `hp` | Nenhum | Não está mais em uso. Em versões anteriores do Adobe Analytics, determinado se o URL atual era a página inicial do navegador. |
| `j` | Nenhum | A versão do JavaScript instalada no navegador. |
| `k` | Nenhum | Usado na dimensão Suporte a cookies. |
| `l1` - `l3` | `list1` - `list3` | Listar variáveis. |
| `mid` | Nenhum | ID de visitante da Experience Cloud. |
| `ndh` | Nenhum | Sinalizador que indica se a solicitação de imagem se originou do AppMeasurement. |
| `ns` | `visitorNameSpace` | Ajuda a determinar onde os cookies são definidos. |
| `oid` | `objectID` | Identificador de objeto para a última página. Usado no Activity Map. |
| `ot` | Nenhum | Nome do objeto para a última página. Usado em versões anteriores do Activity Map. |
| `p` | Nenhum | Não está mais em uso. Lista de plug-ins usados no navegador. |
| `pageName` | `pageName` | Usado na dimensão Página. |
| `pageType` | `pageType` | Usada na dimensão Páginas não encontradas. |
| `pccr` | Nenhum | Definido somente para novos visitantes e sempre definido como `true`. Impede redirecionamentos infinitos. |
| `pe` | `linkType` | Determina o tipo de link personalizado. |
| `pev1` | Nenhum | O URL no qual o link personalizado ocorreu. |
| `pev2` | Nenhum | Nome amigável do link personalizado. |
| `pev3` | Nenhum | Não está mais em uso. Marcos rastreados em versões anteriores do relatório de vídeo. |
| `pf` | Nenhum | bandeira da plataforma; somente para uso da Adobe. Não alterar. |
| `pid` | Nenhum | Identificador da página da última página. Usado em versões anteriores do Activity Map. |
| `pidt` | Nenhum | Tipo de identificador de página para a última página. Usado em versões anteriores do Activity Map. |
| `pl` | `products` | Encurtar para a string de `products` consulta. |
| `products` | `products` | Variável products. |
| `purchaseID` | `purchaseID` | Usado para desduplicar compras. |
| `r` | `referrer` | URL de referência da ocorrência. |
| `s` | Nenhum | Usada na dimensão Resoluções do monitor. Resolução da tela, em `width x height`. |
| `server` | `server` | Dimensão do servidor. |
| `sv` | `server` | Encurtar para a string de `server` consulta. |
| `state` | `state` | Dimensão de estado. |
| `t` | Nenhum | Data/hora da ocorrência gerada. Usa o formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` é data/hora no JavaScript. Mês `0` é janeiro, enquanto mês `11` é dezembro.<br>- `w` é o dia da semana. `0` é domingo, enquanto `6` é sábado.<br>- `o` é o desvio GMT negativo em minutos. Por exemplo, `420` é GMT-7. |
| `ts` | `timestamp` | O carimbo de data e hora personalizado definido com a ocorrência. Normalmente é usado para rastreamento offline. |
| `v` | Nenhum | Usada na dimensão Habilitada para Java. |
| `v0` | `campaign` | Dimensão de Código de rastreamento. |
| `v1` - `v250` | `evar1` - `eVar250` | Dimensões de conversão personalizadas. |
| `vid` | `visitorID` | Variável da ID do visitante. |
| `vmk` | `vmk` | Não está mais em uso. Ajuda a migrar de cookies de terceiros para cookies primários. |
| `vvp` | `variableProvider` | Usada nos Conectores de dados. |
| `xact` | `transactionID` | Usado com fontes de dados para vincular dados. |
| `zip` | `zip` | Usado na dimensão CEP. |
