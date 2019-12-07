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


# Variável de lista

Também conhecidas como List Var. Semelhante a como Propriedades de lista funcionam, a List Vars permitem vários valores na mesma solicitação de imagem. Também atuam de forma semelhante a eVars, que persistem além da solicitação de imagem na qual foram definidas. É possível usar essas variáveis para ver a causa e o efeito entre vários elementos em uma única página, como listas de produtos, listas de desejos, listas de refinamentos de pesquisa ou listas de anúncios de exibição.


<!-- 

listN.xml (bob edit)

 -->

**Considerações**

* List Vars lembram dos valores específicos fazendo referência ao cookie VisitorID no navegador do visitante.
* Um limite máximo de 250 valores é armazenado de uma vez por visitante. Se a quantidade de 250 valores por visitante for excedida, os 250 valores mais recentes serão usados. A expiração desses valores tem por base a expiração configurada da variável.
* Cada valor delimitado pode conter um máximo de 255 caracteres (ou menos se estiver usando caracteres multibyte). Esse é o comprimento máximo para cada elemento.
* Não há limite para o número de caracteres nesta variável. A única exceção a essa limitação está nos navegadores Internet Explorer mais antigos, que impõem uma limitação de 2.083 caracteres a todas as solicitações de URL.
* Um total de três List Vars estão disponíveis por conjunto de relatórios.
* Utilizar List Vars exige código H23 ou superior.
* É possível classificar Vars de lista.
* Se valores duplicados forem definidos na mesma solicitação de página, as vars de lista cancelam a duplicata de todas as instâncias e seus valores.
* As vars de lista mais granulares podem ser segmentadas no nível da ocorrência (ou exibição da página). Se você tiver uma list var com três valores na mesma solicitação de imagem, quaisquer regras de segmento que correspondam a um valor inserirão os três no relatório. Por outro lado, se uma regra de exclusão for definida e corresponder a um único valor, todos os três valores serão excluídos.

**Configuração** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

É possível acessar a configuração no Admin Console e atualizá-la sem precisar envolver o Atendimento ao cliente da Adobe:

1. Vá para **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Conjuntos de relatórios]**
1. Selecione o conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Conversão]** &gt; **[!UICONTROL Listar variáveis]**.

* **Nome**: cada valor delimitado pode conter um máximo de 255 caracteres (ou menos se estiver usando caracteres multibyte). Esse é o comprimento máximo para cada elemento.
* **Delimitador de valor**: O caractere usado para separar valores na List Var. Com maior frequência, são caracteres como vírgulas, dois pontos, barras verticais, ou algo parecido.

   >[!NOTE]
   >
   >Caracteres multibyte não são suportados como delimitadores em Vars de lista. O delimitador deve ser de byte único.

* **Expiração**: Parecida com a expiração de eVar, determina a quantidade de tempo que pode ocorrer entre a List Var e o evento de conversão para que sejam relacionados.

   * **Em uma exibição de página ou nível de visita**: Eventos bem-sucedidos além de exibição de página ou visita não vinculariam a qualquer valor na List Var.
   * **Com base no período, como dia, semana, mês, etc.**: Eventos bem-sucedidos além do período especificado não vinculariam a qualquer valor na List Var. Um número personalizado de dias também pode ser definido aqui.
   * **Eventos de conversão específicos**: Quaisquer outros eventos de bem-sucedidos acionados depois do evento específico designado não vinculariam a qualquer valor na List Var.
   * **Nunca**: Qualquer período pode ser passar entre a List Var e o evento bem-sucedido.

* **Alocação**: Essa configuração determina como os eventos de sucesso dividem crédito entre os valores:

   * **Total**: todos os valores de variável anteriores à expiração da variável obtêm crédito total por eventos bem-sucedidos.
   * **Linear**: todos os valores de variável anteriores à expiração da variável obtêm crédito dividido para eventos bem-sucedidos.
   * Os valores da variável nunca são sobrescritos, mas sim adicionados aos valores que obtêm crédito para eventos bem-sucedidos.

* **Valores máx.**: designa o número de valores ativos permitidos para essa variável de lista. Por exemplo, se for definido como 3, somente os últimos 3 valores capturados são salvos e qualquer valor anterior capturado é descartado. Observe que se diversos valores da mesma var de lista são enviados na mesma ocorrência que você restringiu o uso de valores de máximo, cada valor terá o mesmo carimbo de data e hora e não há garantia de qual valor é salvo.

   Um limite máximo de 250 valores é armazenado de uma vez por visitante. Se a quantidade de 250 valores por visitante for excedida, os 250 valores mais recentes serão usados. A expiração desses valores tem por base a expiração configurada da variável.

   A configuração Valores máx. é útil para limitar a atribuição para um número específico de valores. Por exemplo, se uma var de lista está definida como "A,B,C" na primeira página de uma visita, em seguida, definida como "X,Y,Z" na próxima página, a atribuição é distribuída para esses seis valores com base na alocação. Se você deseja limitar a atribuição somente a "X,Y,Z", você pode definir os valores máximos como três.

Para configurar ou editar Vars de lista, acesse **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Conjuntos de relatórios]** &gt; **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Conversão]** &gt; **[!UICONTROL Variáveis de lista]**.

**Exemplos de implementação** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

Cada um dos exemplos a seguir usam uma vírgula como delimitador de valor.

**Definição de um valor único na List Var:**

```js
s.list1="Cat";
```

**Transmissão de valores múltiplos:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Atribuição de uma receita à List Var:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

Este resultado mostraria três itens de linha com R$ 50 de receita em cada. (Banner publicitário superior; Anúncio na barra lateral e Campanha interna 1.) Observe que o total deste relatório remove a duplicação da receita, de forma que o total também reflete R$ 50.

**Atribuição de receita a uma List Var que tenha sido definida várias vezes durante uma visita:**

**Alocação**: Total

**Expiração**: Visita

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Página 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (não definido) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Resultado**: Todos os valores definidos na list var 1 em qualquer momento durante a visita (valor1, valor2, valor3, valor4, valor5, valor6) obtêm crédito total para a compra.

