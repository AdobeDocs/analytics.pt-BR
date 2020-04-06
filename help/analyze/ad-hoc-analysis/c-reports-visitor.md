---
description: Exibe informações sobre os visitantes, incluindo contagem de visitantes, fidelidade do cliente e características do visitante.
title: Relatórios de visitante
topic: Ad hoc analysis
uuid: 3e9b41d1-d6ff-47a8-aa6b-829df1040c34
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Relatórios de visitante

Exibe informações sobre os visitantes, incluindo contagem de visitantes, fidelidade do cliente e características do visitante.

## Frequência de Retorno {#concept_447A99B71E484D27A7A02888CC51FD3D}

Mostra o tempo decorrido entre as visitas de visitantes recorrentes e o número de visitas que se enquadram em cada categoria de tempo. Use o relatório para ver o tempo médio que os visitantes passam sem acessar o site e as tendências dos clientes recorrentes.

<!-- 

c_reports_return_freq.xml

 -->

Por exemplo, mostrar a métrica Pedidos neste relatório ajuda um site de varejo a entender o tempo mais eficaz entre visitas ao gerar conversão. Use essas informações para comercializar com eficácia visitantes que passaram um certo período sem visitar seu site.

É possível:

* Identifique o número de visitantes que retornam e a frequência de suas visitas de retorno.
* Avalie o apelo de seu site e a relevância para os visitantes ao longo do tempo.
* Descubra o quanto o seu site marca os clientes e com que frequência eles se sentem compelidos a voltar para mais interações ou atualizações.
* Identifique o impacto do conteúdo e das promoções de seu site em seus visitantes.

Por padrão, esse relatório tem os seguintes períodos de tempo:

* Menos de um dia
* De um a três dias
* De três a sete dias
* De sete a catorze dias
* De catorze dias a um mês
* Mais de um mês

## Número da visita {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Mostra quais números de visitas de clientes em seu site mais influenciaram suas métricas de sucesso. Um visitante que faz uma primeira visita ao seu site é contado no item de linha Visita número 1. Visitantes que retornam ao site para uma segunda visita são contados no item de linha Visita número 2 e assim por diante.

<!-- 

c_reports_visit_number.xml

 -->

Você pode usar esse relatório como um relatório de fallout para ver se os visitantes estão retornando. Também é possível adicionar uma métrica de receita para ver se você gera mais receita de visitas iniciais ou visitas subsequentes.

Por exemplo, este relatório poderia responder a questões como: Os clientes que compraram na quarta visita geraram mais receita do que aqueles que compraram na primeira visita?

É possível detalhar esse relatório por qualquer outro relatório ou variável para determinar:

* Quantas visitas normalmente são necessárias para que um usuário que clicou na campanha XYZ faça uma compra.
* Se os usuários de Tóquio, por exemplo, fazem mais visitas antes de gerar uma perspectiva de venda do que os usuários de Londres.

>[!NOTE] Se o mesmo visitante acessar o site várias vezes no mesmo período, cada número de visita especificado é incrementado para cada visita.

Este relatório baseia-se nos dados de ID do visitante passados para a Adobe em cada ocorrência realizada pelos visitantes. À medida que esses dados são recebidos, a Adobe os compara aos dados históricos da ID do visitante para determinar se a ocorrência é:

* Um novo visitante (Número de visitas igual a 1).
* Um visitante anterior continuando uma visita (o número de visitas não aumenta).
* Um visitante anterior fazendo uma nova visita (o número de visitas é aumentado em um).

>[!NOTE] Cada ID de visitante do Analytics está associada a um perfil de visitante nos servidores da Adobe. Os perfis do visitante são excluídos depois de pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie da ID do visitante.

## Fidelidade do Cliente {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Use esse relatório para ver se a sua receita é mais afetada por clientes novos ou clientes recorrentes.

<!-- 

c_reports_customerloyalty.xml

 -->

O [!UICONTROL Customer Loyalty] relatório exibe os padrões de compra dos clientes com base em quatro categorias de fidelidade:

* **Não é um cliente**: Visitantes que nunca compraram
* **Novo cliente**: Visitantes que efetuaram uma única compra
* **Cliente** recorrente: Visitantes que efetuaram duas compras
* **Cliente** fidelizado:Visitantes que efetuaram mais de 3 compras

>[!NOTE] Ao usar essas métricas, todas as visitas de usuários (ou todos os visitantes) são representados nesse relatório, independentemente da realização de compras.

O estado da fidelidade muda após o término da visita, onde ocorre um evento de compra. Por exemplo, um novo cliente (1 compra) efetua uma compra e se inscreve em um boletim informativo após a compra na mesma visita. O evento de registro no boletim informativo ainda é considerado uma interação de cliente novo, pois o estado da Fidelidade do cliente não será alterado até a próxima visita.

## Perfil do visitante {#concept_4D829198CD144DCDA667E0651F93AFC7}

Exibe informações sobre o tipo de visitante que chega ao seu site. Você pode ver coisas como a localização do visitante, o tipo de navegador e hardware de computador usado, idiomas usados e dados de provedor de serviço da Internet para seus visitantes.

<!-- 

c_reports_visitor_profile.xml

 -->

**[!UICONTROL Languages]**: Apresenta os idiomas preferidos de seus visitantes, captura o idioma padrão do navegador e exibe os idiomas que os visitantes usam com frequência em seu site.

**[!UICONTROL Domains]**: Lista as organizações e ISPs que seus visitantes usam para acessar seu site. This report differs from the [!UICONTROL Full Domains] report in that the Full Domains report registers the full ISP domain, whereas this report lists the secondary domain.

**[!UICONTROL Top Level Domains]**: Identifica as regiões do mundo de onde os visitantes vêm com base na extensão de seu domínio de origem e mostra quantos visitantes vêm desses países. Domínios que terminam em Commercial (.com), Network (.net), Education (.edu), Government (.gov) e Organization (.org) geralmente são estabelecidos nos Estados Unidos e listados separadamente dos demais domínios.

**[!UICONTROL Visitor ZIP/Postal Code]**: Exibe os CEP e códigos postais que produziram os clientes que tiveram o maior efeito nas métricas de sucesso de compra.

## GeoSegmentation {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Mostra a dinâmica geográfica de seus visitantes em tempo real, incluindo os países, estados e cidades de onde eles navegam. Você também pode obter insights importantes sobre a tecnologia e as preferências da audiência de seu site.
