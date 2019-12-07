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


# eVarN

As variáveis [!UICONTROL eVar] são usadas para criar relatórios personalizados.


<!-- 

eVarN.xml

 -->

Quando uma eVar é definida com um valor para um visitante, o valor é lembrado até ser expirado. Todos os eventos bem-sucedidos que um visitante encontra enquanto o valor eVar está ativo são contabilizados para o valor eVar.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 255 Bytes | V1-v75 ( [ou v100 ou v250](/help/implement/js-implementation/page-variables/page-variables.md)) | Conversão personalizada | "" |

**Expiração**

As `eVars` expiram depois de um período definido por você. Depois que a eVar expira, ela não recebe mais crédito por eventos bem-sucedidos. As eVars também podem ser configuradas para expirar em eventos bem-sucedidos. Por exemplo, se você tiver uma promoção interna que expira no fim de uma visita, a promoção interna recebe crédito apenas pelas compras ou registros ocorridos durante a visita em que foi ativada.

Existem duas formas de determinar a expiração de uma eVar:

* É possível definir a eVar para expirar depois de um período ou evento especificado.
* É possível forçar a expiração de uma eVar, o que é útil quando se estabelece um novo objetivo para uma variável.

Se uma eVar for usada em maio para refletir promoções internas e expirar depois de 21 dias, e em junho ela for usada para capturar as palavras-chaves da pesquisa interna, no dia 1º de junho você deverá forçar a expiração da variável ou redefini-la. Com isso, você ajudará a manter os valores da promoção interna fora dos relatórios de junho.

**Uso de maiúsculas e minúsculas**

As eVars não fazem distinção de letras maiúsculas e minúsculas, mas são exibidas com essa diferenciação na primeira ocorrência. Por exemplo, se a primeira instância da eVar1 for definida como "Conectado" mas todas as instâncias subsequentes forem transmitidas como "conectado", os relatórios sempre mostrarão "Conectado" como valor da eVar.

**Contadores**

Embora as eVars sejam usadas com mais frequência para reter valores da string, elas também podem ser configuradas para atuar como contadores. As eVars são úteis como contadores quando você está tentando contar o número de ações adotadas por um usuário antes de um evento. Por exemplo, você pode usar uma eVar para capturar o número de pesquisas internas antes da compra. Sempre que um visitante pesquisar, a eVar deverá conter um valor de "+1". Se um visitante pesquisar quatro vezes antes de uma compra, você verá uma instância para cada contagem total: 1,00, 2,00, 3,00 e 4,00. No entanto, somente a 4,00 receberá crédito pelo evento da compra (Pedidos e métricas de receita).  Somente números positivos são permitidos como valores de um contador eVar.

**Sub-relações**

Um requisito comum de um relatório eVar personalizado é a capacidade de desmembrar um relatório eVar personalizado em outro. Por exemplo, se uma eVar contiver gênero e outra contiver salário, você poderá fazer a seguinte pergunta: entre as visitantes do sexo feminino de meu site, quanta receita foi gerada por mulheres que ganham mais de US$ 50,000 por ano. Todas as eVar que forem totalmente sub-relacionadas permitem esse tipo de desmembramento nos relatórios. Por exemplo, se a eVar gênero tiver sub-relações totais ativadas, todos os outros relatórios eVar personalizados poderão ser desmembrados por gênero e o gênero poderá ser desmembrado por todos os outros. Para ver a relação entre dois relatórios, somente um deles precisa ter as sub-relações totais ativadas. Por padrão, os relatórios de Campanha, Produtos e Categoria são totalmente sub-relacionados (qualquer eVar pode ser detalhado por campanha ou produtos).

**Sintaxe e valores possíveis**

Embora seja possível renomear a eVars, ela deve ser sempre mencionada no arquivo JavaScript pela eVarX, onde X é um número entre 1 e 75 ([ou 100 ou 250](/help/implement/js-implementation/page-variables/page-variables.md)).

```js
s.eVarX="value"
```

Quando não forem usadas como um contador, as eVars terão as mesmas limitações que todas as demais variáveis. Se a eVar for um "contador", espera-se que ela receba valores numéricos, como "1" ou "2,5". Se mais que duas casas decimais forem fornecidas, o contador da eVar é arredondado por duas casas decimais. Um contador eVar não pode conter números negativos.

**Exemplos**

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Configurações**

As eVars podem ser configuradas em Analytics &gt; Admin &gt; Conjuntos de relatórios &gt; Editar configurações &gt; Conversão &gt; Variáveis de conversão]. Todas as eVars podem ser configuradas com Nome, Tipo, Alocação, Expirar após ou Redefinir. Cada configuração é tratada separadamente.

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Configuração </th> 
   <th class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nome </td> 
   <td> Permite alterar o nome do relatório eVar no <span class="keyword">Analytics </span>. <p>A eVar ainda deve ser mencionada como s.eVarX no código JavaScript, independentemente do nome fornecido ao relatório no <span class="keyword">Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Tipo </td> 
   <td> Permite mostrar se a eVar é uma string de texto ou um contador. </td> 
  </tr> 
  <tr> 
   <td> Alocação </td> 
   <td> Usada para configurar qual valor da eVar recebe crédito pelos eventos bem-sucedidos. <p>Se Alocação for definida como "Mais recente (último)", B receberá o crédito. </p> <p>Se Alocação for definida como "Valor original (primeiro)", A receberá o crédito. </p> <p>Se Alocação for definida como "Linear", A e B recebem o crédito por metade do valor de compra. </p> </td> 
  </tr> 
  <tr> 
   <td> Expirar após </td> 
   <td> Permite determinar se uma eVar expira em um evento específico, como compra, ou depois de um período predefinido. </td> 
  </tr> 
  <tr> 
   <td> Redefinir </td> 
   <td> Se você marcar a caixa de seleção <span class="wintitle">Redefinir</span> para uma eVar e clicar em <span class="wintitle">Salvar</span> na parte inferior da página, todos os valores dessa eVar serão expirados imediatamente. Depois disso, somente novos valores da eVar receberão crédito por eventos bem-sucedidos. </td> 
  </tr> 
 </tbody> 
</table>

**Armadilhas, dúvidas e dicas**

* Diferente das variáveis [!UICONTROL prop], as variáveis eVar não têm permissão para serem listas de valores delimitados. Se você preencher uma eVar com uma lista de valores, por exemplo, "um,dois,três", a string exata será exibida nos relatórios.
* Os contadores eVar não podem conter números negativos.
