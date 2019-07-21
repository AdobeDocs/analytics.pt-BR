---
description: A variável pageName deve ser preenchida com um identificador de página intuitivo, de fácil leitura.
keywords: Implementação do Analytics
seo-description: A variável pageName deve ser preenchida com um identificador de página intuitivo, de fácil leitura.
seo-title: Estratégias de nomenclatura de página
solution: Analytics
title: Estratégias de nomenclatura de página
topic: Desenvolvedor e implementação
uuid: a 829 d 0 c 7-6 ebf -459 a-b 403-5 e 9 c 05161 e 5 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Estratégias de nomenclatura de página

A variável pageName deve ser preenchida com um identificador de página intuitivo, de fácil leitura.

You can determine the best way of populating the *`pageName`* variable by looking at the structure of your website. The methods listed below outline various ways of populating the *`pageName`* variable.

While the *`pageName`* variable is central to identifying user behavior, Adobe recommends using multiple variables to indicate page information. As melhores estratégias de nomenclatura utilizam uma variável diferente para cada nível de hierarquia dento do site, como mostrado abaixo:

* A variável *`channel`* pode ser usada para indicar a seção do site.
* *`pageName`* A variável pode ser usada para mostrar o tipo de conteúdo.
* Uma variável [!UICONTROL custom insight] (prop1) pode ser usada para conteúdo detalhado.

Os níveis de detalhes variam, dependendo da propriedade, como mostrado abaixo:

| Variável | Nível de Detalhe | Exemplo |
|---|---|---|
| Canal | Seção Geral | Eletrônicos |
| Prop1 | Subseção | Esportes: Esportes Locais |
| PageName | Descrição de Conteúdo Geral | Empréstimos: Hipoteca da Casa: Comparação de Taxa |
| Prop2 | Descrição de Conteúdo Detalhada | Eletrônicos : Notebook PC : Espec. Detalhadas : IBM Thinkpad T20 |

Quanto mais em camada o site estiver dividido, mais as variáveis devem ser usadas para identificar o conteúdo da página. As empresas também encontram valor na permissão de sobreposição entre as variáveis. Por exemplo, uma variável mais detalhada pode conter informações não somente sobre o produto sendo visualizado, mas também sobre a seção e a subseção. Esta estratégia pode ser especialmente útil quando um produto ou artigo aparecer em mais de uma seção do site.

As estratégias de nomenclatura de página a seguir descrevem como preencher a *`pageName`* variável. Enquanto tenta escolher a estratégia de nomeação da página mais fácil de implementar, a estratégia de nomeação da página determina a usabilidade de todos os Relatórios de [!UICONTROL Caminho] e de [!UICONTROL Página]. Tenha cuidado ao decidir como as páginas serão nomeadas.

## Nome exclusivo para cada página {#section_24704CA39E2F4C00ACEAFF39CA0A921B}

O método mais valioso para nomear páginas é fornecer a cada página um identificador exclusivo que é facilmente compreendido por todos os usuários do [!DNL Analytics] na sua organização. Exemplos de nomes de página incluem Homepage, Início do departamento de eletrônicos e Esportes : Esportes locais : Escola.

A maioria dos usuários do [!DNL Analytics] considera os nomes hierárquicos de página úteis para identificação da localização da página no site, e o seu objetivo. A tabela a seguir contém algumas amostras de nomes de página para diversos setores:

| Conversão | Mídia | Finanças |
|---|---|---|
| Página inicial | Página inicial | Página inicial |
| Eletrônicos | Tecnologia | Empréstimos para habitação |
| Eletrônicos : notebook PCs | Tecnologia : novos gadgets | Empréstimos para habitação : comparação de taxa |
| Eletrônicos: notebook PCs : página de produto | Tecnologia : novos gadgets : página de artigo | Empréstimos para habitação : comparação de taxas : 10 anos fixos |

## Caminho do arquivo (sem ser o URL completo) {#section_37FDCDA00DA84B3D9B8AB4290555FF34}

Para alguns sites, o caminho do arquivo é claro e, portanto, lido facilmente. Um usuário corporativo poder ler uma URL e determinar a página à qual o caminho de arquivo se refere. Se esse for o caso do site, você pode utilizar uma variável do lado do servidor para preencher o caminho para o arquivo para uma *`pageName`* conforme mostrado abaixo:

```js
s.pageName="<%= file_path %>"
```

Adobe does not recommend leaving the *`pageName`* blank, (which results in using the full URL of the page) even though you may be tempted to do so. The following side-effects are caused by leaving the *`pageName`* variable blank and using the *`pageURL`* as the page identifier.

* O domínio e o caminho de uma página podem nem sempre ser exibidos de forma idêntica. Por exemplo, a seguir as quatro URLs retornam uma única página:

   * `https://www.mysite.com/index.jsp`
   * `https://www.mysite.com`
   * `https://mysite.com/index.jsp`
   * `https://mysite.com/`
   If the *`pageName`* is left blank, each of these page names would occupy a separate entry in reports.

* Algumas páginas (p. ex. formulários) publicam para elas mesmas, desse modo apagando qualquer distinção entre o formulário original e a saída de resultado.
* Quando a sua página é traduzida para outro idioma por mecanismos de pesquisa e outras ferramentas online, a URL da página é a URL do mecanismo de pesquisa (não a URL de seu site).

## HTML (document.title) {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

If you have invested time into making your HTML titles readable and intuitive, you might consider using the same title as the value in the *`pageName`* variable. Adobe recommends using a server-side variable to populate the *`pageName`* rather than using JavaScript's [!DNL document.title]. Alguns navegadores interpretam o título HTML de forma diferente que outros, o que pode fazer com que o [!DNL Analytics] receba nomes de página diferentes de navegadores diferentes.

A prática recomendada para utilizar o título HTML é copiar os títulos existentes de cada página para uma variável separada ou elemento de gerenciamento de conteúdo. Quando você decidir fazer alterações no título de HTML para otimização do mecanismo de pesquisa ou outros fins, os nomes de página do [!DNL Analytics] não serão afetados. Se um nome de página for alterado no [!DNL Analytics], ela se tornará uma nova página e não estará conectada com o nome de página antigo, independentemente do URL associada.
