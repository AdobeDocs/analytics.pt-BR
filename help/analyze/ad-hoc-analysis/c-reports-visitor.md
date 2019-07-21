---
description: Exibe informações sobre visitantes, incluindo informações como contagem de visitantes, fidelidade do cliente e características do visitante.
seo-description: Exibe informações sobre visitantes, incluindo informações como contagem de visitantes, fidelidade do cliente e características do visitante.
seo-title: Relatórios de visitante
solution: Analytics
title: Relatórios de visitante
topic: Ad Hoc Analysis
uuid: 3 e 9 b 41 d 1-d 6 ff -47 a 8-aa 6 b -829 df 1040 c 34
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Relatórios de visitante

Exibe informações sobre visitantes, incluindo informações como contagem de visitantes, fidelidade do cliente e características do visitante.

## Frequência de retorno {#concept_447A99B71E484D27A7A02888CC51FD3D}

Mostra o tempo decorrido entre as visitas de clientes recorrentes e o número de visitas que se encaixa em cada categoria de tempo. Use o relatório para ver o tempo médio que os visitantes passam sem acessar site e as tendências dos clientes recorrentes.

<!-- 

c_reports_return_freq.xml

 -->

Por exemplo, mostrar a métrica Pedidos nesse relatório ajuda um site de varejo a entender o tempo mais eficaz entre visitas para gerar uma conversão. Use essas informações para atingir com eficácia os clientes que passaram um determinado período sem visitar o site.

É possível:

* Identificar o número de visitantes de retorno e a frequência de suas visitas de retorno.
* Avaliar o apelo do site e a relevância que ele tem para os visitantes ao longo do tempo.
* Descobrir o quanto o site marca os clientes e com que frequência eles se sentem compelidos a voltar para mais interações ou atualizações.
* Identificar o impacto do conteúdo e das promoções do site sobre os visitantes.

Por padrão, esse relatório tem as seguintes durações de tempo:

* Menos de um dia
* De um a três dias
* De três a sete dias
* De sete a quatorze dias
* De quatorze dias a um mês
* Mais de um mês

## Número de visitas {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Mostra quais números de visitas de clientes em seu site mais influenciaram suas métricas de sucesso. Um visitante que faz uma primeira visita ao seu site é contado no item de linha Visita número 1. Os visitantes que retornam ao site para uma segunda visita são contados no item de linha Visita número 2 e assim por diante.

<!-- 

c_reports_visit_number.xml

 -->

Você pode usar esse relatório como um relatório de fallout para ver se os visitantes estão retornando. Também é possível adicionar uma métrica de receita para ver se você gera mais receita com visitas iniciais ou com visitas subsequentes.

Por exemplo, esse relatório pode responder a perguntas como: os clientes que compraram em sua quarta visita geraram mais receita do que aqueles que compraram na primeira visita?

Você pode dividir o relatório de acordo com qualquer variável para determinar:

* Quantas visitas normalmente são necessárias para que um usuário que clicou na campanha XYZ realize uma compra.
* Se os usuários de Tóquio, por exemplo, fazem mais visitas antes de gerar uma perspectiva de venda em comparação aos usuários de Londres.

>[!NOTE]
>
>Se o mesmo visitante visitar seu site várias vezes no mesmo período, cada número de visita especificado será incrementado para cada visita.

Esse relatório é baseado nos dados de ID do visitante passados para a Adobe a cada acesso dos visitantes. Conforme esses dados são recebidos, a Adobe os compara aos dados históricos de ID de visitantes para determinar se o acesso é:

* Um novo visitante (o número de visitas é igual a 1).
* Um visitante anterior continuando uma visita (o número de visitas não aumenta).
* Um visitante anterior fazendo uma nova visita (o número de visitas é incrementado em um).

>[!NOTE]
>
>Cada ID de visitante do Analytics está associada a um perfil de visitante em servidores da Adobe. Os perfis do visitante são excluídos depois de pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie da ID do visitante.

## Fidelidade do cliente {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Use esse relatório para ver se a sua receita é mais afetada por clientes novos ou clientes recorrentes.

<!-- 

c_reports_customerloyalty.xml

 -->

O relatório de [!UICONTROL Fidelidade do cliente] exibe padrões de compras de por clientes com base em quatro categorias de fidelidade:

* **Não é um cliente**: visitantes que nunca efetuaram uma compra
* **Novo cliente**: visitantes que efetuaram uma única compra
* **Cliente antigo** clientes que efetuaram 2 compras
* **Cliente fiel** clientes que efetuaram 3 ou mais compras

>[!NOTE]
>
>Ao usar essas métricas, todas as Visitas do usuário (ou todos os Visitantes) são representadas neste relatório, independentemente da Visita (ou Visitante) incluir uma compra.

O estado da fidelidade muda após a conclusão da visita na qual ocorre um evento de compra. Por exemplo, um novo cliente (1 compra) realiza uma compra e se registra em um boletim informativo na mesma visita após a compra. O evento de registro no boletim informativo ainda é considerado uma interação de cliente novo, pois o estado da fidelidade do cliente não será alterado até a próxima visita.

## Perfil do visitante{#concept_4D829198CD144DCDA667E0651F93AFC7}  

Exibe informações sobre o tipo de visitante que acessa o seu site. Você pode ver informações como a localização do visitante, tipo de navegador e hardware de computador usado, idioma usado e dados do provedor de serviços da Internet de seus visitantes.

<!-- 

c_reports_visitor_profile.xml

 -->

** [!UICONTROL Languages] **: Displays your visitors’ preferred languages, captures the default browser language, and displays the languages that visitors use most often on your site.

** [!UICONTROL Domains] **: Lists the organizations and ISPs your visitors use to access your site. Este relatório é diferente do relatório de [!UICONTROL Domínios completos] porque o relatório de Domínios completos registra o domínio completo do ISP e este relatório indica o domínio secundário.

** [!UICONTROL Top Level Domains] **: Identifies world regions that visitors come from based on their originating domain extension, and shows how many visitors come from these countries. Domínios que terminam em Commercial (.com), Network (.net), Education (.edu), Government (.gov) e Organization (.org) geralmente são estabelecidos nos Estados Unidos e listados separadamente dos outros países.

** [!UICONTROL Visitor ZIP/Postal Code] **: Displays the zip and postal codes that produced the customers that had the greatest effect on purchase success metrics.

## GeoSegmentation {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Mostra a dinâmica geográfica dos seus visitantes em tempo real, incluindo países, estados e cidades das quais eles estão navegando. Você também pode obter informações importantes sobre a tecnologia e as preferências do público-alvo do seu site.
