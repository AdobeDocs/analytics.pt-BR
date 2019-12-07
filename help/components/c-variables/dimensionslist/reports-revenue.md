---
description: Mede a quantia de receita gerada por todos os seus produtos durante um período específico.
title: Receita
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Receita

Mede a quantia de receita gerada por todos os seus produtos durante um período específico.

Use Receita para ver o sucesso geral e a tendência do seu site. Você pode também usá-lo para destacar os períodos em que o site obteve sucesso, para descobrir a fonte, e usar isso para futuras campanhas.

## Relatório de Propriedades Gerais {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* Existem requisitos que devem ser atendidos para que esse relatório colete dados de forma bem sucedida. Deve ocorrer o seguinte dentro da mesma solicitação de imagem:

   * Um evento de [!UICONTROL compra] deve ser disparado no `s.events`. 

   * A variável `products` deve ser definida com um número no campo de preço.
   * Por exemplo, isso passaria US$35.99 para o relatório da receita:

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* Quando mais de um produto está presente na variável [!UICONTROL s.products], todos contam no relatório de receita. Por exemplo, [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] passaria de USD$ 9 na receita para o relatório.

   >[!NOTE]
   >
   >A receita não é multiplicada se a quantidade for aumentada em um único produto. Por exemplo, [!DNL s.products="Womens;Socks;5;4.50"] não passa US$ 22,50 para o relatório, mas sim US$ 4,50. Certifique-se de que a sua implementação passa a receita total para a quantidade listada ([!DNL s.products="Womens;Socks;5;22.50"]).

* [!UICONTROL Receita] arredonda a quantia total por um período para o valor monetário mais próximo. Não arredonda cada produto individual ou clique.
* Como o Analytics arredonda cada dia para o valor inteiro mais próximo, a comparação do montante de cada dia ao total mensal está fora por uma quantia bem pequena. Isso se deve ao fato de o total mensal não ser o montante de cada dia arredondado, é o montante absoluto arredondado para o valor inteiro mais próximo.
* Você pode criar um relatório que não arredonde receita para o valor inteiro mais próximo usando um [métrica calculada](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/).
* A menos que a variável `purchaseID` seja usada, os usuários que atualizam a página poderão aumentar a receita enviando estes dados várias vezes para a Adobe.
* Os detalhamentos por hora são baseados na zona de tempo do conjunto de relatórios.
* Este relatório não contém itens de linha. Só pode ser visualizado no formato padrão.
* A granularidade de hora, dia, semana, mês, trimestre e ano pode ser aplicada. Essas granularidades estão disponíveis dependendo do intervalo da data do relatório.
* Este relatório pode ser detalhado através dos seguintes relatórios (dependendo das configurações de organização e do conjunto de relatórios):

   * Relatório de [!UICONTROL Tempo de permanência por visita].
   * Relatório de [!UICONTROL Páginas e Seções do Site].
   * Relatório de [!UICONTROL Vídeo].
   * Relatório de [!UICONTROL Profundidade da página e das Páginas de entrada].
   * A maioria dos relatórios das [!UICONTROL Fontes de tráfego], inclusive os relatórios de [!UICONTROL Palavras-chave de pesquisa], [!UICONTROL Mecanismos de pesquisa],e [!UICONTROL Domínios de referência].

   * Relatório do [!UICONTROL Código de rastreamento] e todos os relatórios de classificação associados.
   * O relatório da [!UICONTROL Variável de produtos] e todos os relatórios de classificação associados. Relatórios de [!UICONTROL Categorias] também.

   * Quase todos os relatórios de [!UICONTROL Perfil do Visitante], salvo os relatórios de [!UICONTROL Segmentação geográfica].

   * Todos os relatórios das variáveis da [!UICONTROL Conversão Personalizada] com sub-relações básicas.

* Detalhamentos não estão disponíveis por hora.

## Propriedades específicas do produto {#section_ED87FFD020634453AABE86B0248BE69B}

* Este relatório pode ser acessado indo até **[!UICONTROL Conversão]** &gt; **[!UICONTROL Compras]** &gt; **[!UICONTROL Receita]**.

* Detalhamentos das [!UICONTROL Fontes de tráfego] podem ser encontradas nos [!UICONTROL Métodos de descoberta].

* Este relatório pode ser acessado indo até **[!UICONTROL Métricas do Site]** &gt; **[!UICONTROL Compras]** &gt; **[!UICONTROL Receita]**.

* Além de todos os detalhamentos listados anteriormente, os detalhamentos do [!UICONTROL Canal de Marketing de First e Last Touch] estão disponíveis.

* Este relatório pode ser acessado indo até **[!UICONTROL Métrica do Site]** &gt; **[!UICONTROL Compras]** &gt; **[!UICONTROL Receita]**.

* Além dos detalhamentos mencionados previamente, as variáveis da [!UICONTROL Lista] e as variáveis atuais de [!UICONTROL Vídeo] podem ser usadas.

* Este relatório pode utilizar segmentos.

* É possível pode detalhar cada item neste relatório por todos os outros relatórios e variáveis, permitindo que você visualize os detalhes através de qualquer granularidade que desejar.
* Você pode usar todas as métricas de [!UICONTROL conversão] e [!UICONTROL tráfego] junto com a [!UICONTROL Receita]. Você pode usar alocações diferentes para todas as métricas de [!UICONTROL conversão].

* Este relatório pode utilizar segmentos múltiplos altamente avançados.

Se este relatório não estiver disponível no local especificado, verifique com os administradores. Eles podem ter alterado o nome padrão ou a estrutura do menu para servir melhor as necessidades exclusivas da sua empresa.
