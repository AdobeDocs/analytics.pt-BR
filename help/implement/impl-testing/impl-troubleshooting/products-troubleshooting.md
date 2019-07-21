---
description: A variável s.products pode ser a variável mais sintaticamente complexa usada pela coleta de dados.
keywords: Implementação do Analytics
seo-description: A variável s.products pode ser a variável mais sintaticamente complexa usada pela coleta de dados.
seo-title: Erros comuns na variável Produtos
solution: Analytics
subtopic: Solução de problemas
title: Erros comuns na variável Produtos
topic: Desenvolvedor e implementação
uuid: 94075 c 56-37 c 3-44 de-bf 37-1 dfd 228 c 6665
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Erros comuns na variável Produtos

A variável s.products pode ser a variável mais sintaticamente complexa usada pela coleta de dados.

Os sinais de vírgula, ponto-e-vírgula, barra vertical e igual têm funções específicas na variável. Ela não tem um tamanho máximo, mas cada entrada de produto específica não pode exceder 100 bytes (incluindo caracteres de vários bytes). Erros na implementação desta variável são compreensíveis, mas infelizmente para desenvolvedores, a [!UICONTROL s.products] com frequência é a variável mais importante do site, pois possibilita o rastreamento da receita, das unidades, nomes de produtos e assim por diante.

Estes são alguns erros extremamente fáceis de cometer e que podem causar problemas de implementação.

Verifique se os totais de sua [!UICONTROL categoria], [!UICONTROL nome de produto] e [!UICONTROL receita] estão desprovidos de vírgulas e ponto-e-vírgulas. A vírgula é usada para separar entradas na string de [!UICONTROL s.products]. Isso ocorre quando você tem dois produtos na mesma transação, o ponto-e-vírgula é usado para delimitar campos em uma entrada. Se você usar uma vírgula ou ponto-e-vírgula de outra forma, a coleta de dados suporá que você está separando entradas de produtos. Considere o exemplo a seguir:

```js
s.products="widgets;large widget, 40′x40′;1;19.99,wugs;tiny wug;2;1,999.98";
```

Nesta implementação, o desenvolvedor provavelmente pretendia que a coleta de dados tivesse a leitura como a seguinte:

Categoria 1: widgets

Produto 1: widget grande, 40 pol. x 40 pol.

Unidades: 1: 1

Receita: 1: 19,99

Categoria 2: perucas

Produto 2: peruca pequena

Unidades 2: 2

Receita 2: 1.999,98

Observe as vírgulas nas entradas Produto 1 e Receita 2. Elas indicam uma nova entrada de produto. A coleta de dados interpretaria desta forma:

Categoria 1: widgets

Produto 1: widget grande

Categoria 2: 40 pol. x 40 pol.

Produto 2: 1

Unidades 2: 19,99

Categoria 3: perucas

Produto 3: peruca pequena

Unidades 3: 2

Receita 3: 1

Categoria 4: 999,98

Um erro como esse com frequência resulta em valores numéricos não esperados no relatório [!UICONTROL Produtos], pois o campo de unidades é gravado como nome do produto. Se você vir nomes de produto inválidos no seu relatório [!UICONTROL Produtos], examine a implementação da variável [!UICONTROL s.products] para verificar o mau uso dos caracteres reservados, como a vírgula.

Os nomes do produto e da categoria não devem conter caracteres sem suporte. Isso pode ser especialmente difícil na string [!UICONTROL s.products], pois nomes de produto com frequência têm probabilidade de conterem caracteres como ™, © e ®. Esses caracteres devem ser retirados dos valores de produto e categoria antes de serem inseridos em [!UICONTROL s.products]. Você também precisa garantir que os símbolos de moeda não sejam incluídos nos valores de receita. Os caracteres com suporte são números de 1 a 127 da tabela ASCII.

Se você não estiver transmitindo uma categoria de produto na string de produto, verifique se incluiu um ponto-e-vírgula (;) onde a categoria de produto é normalmente exibida, como mostrado abaixo:

```js
s.products=";product name"
```

Nesse caso, o ponto-e-vírgula representa um espaço reservado para a categoria do produto. Se o ponto-e-vírgula for deixado fora da string do produto, o "nome do produto" será contado como categoria, o número de unidades será contado como nome do produto, a receita será contado como as unidades e assim por diante.
