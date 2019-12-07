---
description: Exibe informações sobre os visitantes, incluindo coisas como contagem de visitantes, fidelidade do cliente e características do visitante.
title: Relatórios de visitante
topic: Ad hoc analysis
uuid: 3e9b41d1-d6ff-47a8-aa6b-829df1040c34
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Relatórios de visitante

Exibe informações sobre os visitantes, incluindo coisas como contagem de visitantes, fidelidade do cliente e características do visitante.

## Frequência de Retorno {#concept_447A99B71E484D27A7A02888CC51FD3D}

Mostra o tempo decorrido entre as visitas de clientes recorrentes e o número de visitas que se encaixa em cada categoria de tempo. Use o relatório para ver o tempo médio que os visitantes passam sem acessar o site e as tendências dos clientes recorrentes.

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

## Número da visita {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Mostra quais números de visitas de clientes em seu site mais influenciaram suas métricas de sucesso. Um visitante que faz uma primeira visita ao seu site é contado no item de linha Visita número 1. Os visitantes que retornam ao site para uma segunda visita são contados no item de linha Visita número 2 e assim por diante.

<!-- 

c_reports_visit_number.xml

 -->

Você pode usar esse relatório como um relatório de fallout para ver se os visitantes estão retornando. Também é possível adicionar uma métrica de receita para ver se você gera mais receita com visitas iniciais ou com visitas subsequentes.

Por exemplo, esse relatório pode responder a perguntas como: os clientes que compraram em sua quarta visita geraram mais receita do que aqueles que compraram na primeira visita?

Você pode dividir o relatório de acordo com qualquer variável para determinar:

* Quantas visitas normalmente são necessárias para que um usuário que clicou na campanha XYZ realize uma compra.
* Se os usuários de Tóquio, por exemplo, fazem mais visitas antes de gerar uma perspectiva de venda em comparação aos usuários de Londres.

> [!NOTE] Se o mesmo visitante visitar seu site várias vezes no mesmo período, cada número de visita especificado será incrementado para cada visita.

Esse relatório é baseado nos dados de ID do visitante passados para a Adobe a cada acesso dos visitantes. Conforme esses dados são recebidos, a Adobe os compara aos dados históricos de ID de visitantes para determinar se o acesso é:

* Um novo visitante (o número de visitas é igual a 1).
* Um visitante anterior continuando uma visita (o número de visitas não aumenta).
* Um visitante anterior fazendo uma nova visita (o número de visitas é incrementado em um).

> [!NOTE] Cada ID de visitante do Analytics está associada a um perfil de visitante nos servidores da Adobe. Os perfis do visitante são excluídos depois de pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie da ID do visitante.

## Fidelidade do Cliente {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Use esse relatório para ver se a sua receita é mais afetada por clientes novos ou clientes recorrentes.

<!-- 

c_reports_customerloyalty.xml

 -->

O relatório de [!UICONTROL Fidelidade do cliente] exibe padrões de compras de por clientes com base em quatro categorias de fidelidade:

* **Não é um cliente**: visitantes que nunca efetuaram uma compra
* **Novo cliente**: visitantes que efetuaram uma única compra
* **Cliente antigo** clientes que efetuaram 2 compras
* **Cliente fiel** clientes que efetuaram 3 ou mais compras

> [!NOTE] Ao usar essas métricas, todas as Visitas do usuário (ou todos os Visitantes) são representados neste relatório, independentemente de a Visita (ou o Visitante) ter incluído uma compra.

O estado da fidelidade muda após a conclusão da visita na qual ocorre um evento de compra. Por exemplo, um novo cliente (1 compra) realiza uma compra e se registra em um boletim informativo na mesma visita após a compra. O evento de registro no boletim informativo ainda é considerado uma interação de cliente novo, pois o estado da Fidelidade do cliente não será alterado até a próxima visita.

## Perfil do visitante {#concept_4D829198CD144DCDA667E0651F93AFC7}

Exibe informações sobre o tipo de visitante que acessa o seu site. Você pode ver informações como a localização do visitante, tipo de navegador e hardware de computador usado, idioma usado e dados do provedor de serviços da Internet de seus visitantes.

<!-- 

c_reports_visitor_profile.xml

 -->

**[!UICONTROL Idiomas]**: Exibe os idiomas preferenciais dos visitantes, captura o idioma padrão do navegador e exibe os idiomas que os visitantes usam com mais frequência no site.

**[!UICONTROL Domínios]**: indica as organizações e ISPs que seus visitantes utilizam para acessar o seu site. Este relatório é diferente do relatório de [!UICONTROL Domínios completos] porque o relatório de Domínios completos registra o domínio completo do ISP e este relatório indica o domínio secundário.

**[!UICONTROL Domínios de nível superior]**: identifica as regiões do mundo das quais os visitantes vêm com base na sua extensão de domínio de origem, e mostra quantos visitantes vêm desses países. Domínios que terminam em Commercial (.com), Network (.net), Education (.edu), Government (.gov) e Organization (.org) geralmente são estabelecidos nos Estados Unidos e listados separadamente dos outros países.

**[!UICONTROL Código postal/CEP do visitante]**: mostra os códigos postais e o CEP dos clientes de maior efeito nas métricas de sucesso de compras.

## GeoSegmentation {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Mostra a dinâmica geográfica dos seus visitantes em tempo real, incluindo países, estados e cidades das quais eles estão navegando. Você também pode obter informações importantes sobre a tecnologia e as preferências do público-alvo do seu site.
