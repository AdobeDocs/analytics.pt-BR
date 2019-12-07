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


# pageName

A variável contém o nome de cada página de seu site.


<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 bytes </td> 
   <td> pageName </td> 
   <td> <p>Páginas </p> <p>Caminhos </p> </td> 
   <td> URL da página </td> 
  </tr> 
 </tbody> 
</table>

A variável *`pageName`* deve ser preenchida com um valor que os usuários da empresa reconheçam. Na maioria dos casos, o valor *`pageName`* não é o URL ou o caminho para o arquivo. Os valores comuns *`pageName`* incluem nomes como "Página inicial", "Check-out", "Compra Obrigado" ou "Registro".

Tenha cuidado para não permitir que caracteres de nova linha, travessões com -em ou -en ou qualquer caractere HTML sejam exibidos no nome da página e outras variáveis. Alguns navegadores enviam caracteres de linha nova, outros não, o que faz com que os dados no Analytics sejam divididos entre dois nomes de página aparentemente idênticos. Muitos processadores de texto e clientes de email convertem automaticamente um hífen em um travessão -en ou -em durante a digitação. Como os travessões -en e -em são caracteres inválidos nas variáveis do Analytics (caracteres ASCII com códigos acima de 127), o Analytics não registrará o nome de página contendo o caractere inválido e mostrará a URL em vez disso.

Se *`pageName`* for deixado em branco, o URL será usado para representar o nome da página. Deixar *`pageName`* em branco geralmente é problemático porque o URL nem sempre pode ser o mesmo para uma página `www.mysite.com` e `mysite.com` são a mesma página com URLs diferentes).

**Sintaxe e valores possíveis** {#section_7A61EE70F1A84D26B414404998C84BA8}

A variável *`pageName`* deve conter um identificador útil para os usuários corporativos do Analytics.

```js
s.pageName="page_name"
```

Não há limitações nas variáveis *`pageName`* além das limitações padrão de variáveis.

**Exemplos** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**Configurações** {#section_58CBC68C805344A999EB47455FEBA8D5}

Os administradores têm a capacidade de alterar o nome de página visível no Analytics com a ferramenta [!UICONTROL Nomear páginas], que é potencialmente perigosa e pode afetar negativamente seus relatórios. Entre em contato com o Atendimento ao cliente da Adobe antes de usar a ferramenta [!UICONTROL Nomear páginas].

**Armadilhas, dúvidas e dicas** {#section_BB41DC9682C34385B9CAA80D5257C113}

O *`pageName`* não deve conter caracteres ilegais.
