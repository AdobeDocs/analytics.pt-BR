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



# hierN

A [!UICONTROL variável de hierarquia] determina a localização de uma página da hierarquia do site.


<!-- 

hierN.xml

 -->

Essa variável é útil para sites com mais de três níveis na estrutura do site. Por exemplo, um site jornalístico pode ter quatro níveis na seção de Esporte: Esportes, Esportes locais, Beisebol e Red Sox. Se alguém visitar a página Beisebol, as páginas Esportes, Esportes locais e Beisebol refletirão essa visita.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 255 Bytes | H1-H5 | Hierarquia | "" |

Há cinco variáveis de [!UICONTROL hierarquia] disponíveis, que devem ser ativadas pelo Atendimento ao cliente da Adobe. Quando a hierarquia é ativada, você deve escolher um delimitador para a variável e o número máximo de níveis para a hierarquia. Por exemplo, se o delimitador for uma vírgula, a hierarquia de esportes pode ser exibida como o seguinte.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Verifique se nenhum dos nomes da sua seção inclui o delimitador. Por exemplo, se uma de suas seções for chamada "Técnico Griffin, Jim", você deverá escolher um delimitador diferente de vírgula. Cada seção da hierarquia é limitada a 255 bytes, com limite total de variável de 255 bytes. Depois que um delimitador é escolhido (no momento da criação da hierarquia), ele não é alterado facilmente.

Contate o Atendimento ao cliente da Adobe para obter instruções sobre a alteração do delimitador de uma hierarquia existente. Os delimitadores também pode consistir em vários caracteres, como || ou /|\, que têm uma probabilidade menor de aparecer na seção de hierarquia.

**Sintaxe e valores possíveis** {#section_0739948A68A2420DAB1CBEA3115A5A66}

Não coloque espaço entre cada delimitador. No exemplo de sintaxe a seguir, N é um número entre um e cinco.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Não use o delimitador, exceto para delimitar os níveis da hierarquia. O delimitador pode ser qualquer caractere ou caracteres de sua escolha.

**Exemplos** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Configurações** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* O delimitador não pode ser alterado depois que a hierarquia é configurada. Se for necessário alterar o delimitador da sua hierarquia, entre em contato com o Atendimento ao cliente da Adobe.
* Não é possível alterar o número de níveis depois que a hierarquia é configurada.

> [!NOTE] As alterações nas hierarquias pode resultar em encargos de serviço.

