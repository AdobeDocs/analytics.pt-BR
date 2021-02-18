---
title: Conjuntos de relatórios globais no Adobe Analytics
description: Entenda as vantagens e os requisitos para usar um conjunto de relatórios global.
translation-type: ht
source-git-commit: 632fa007fecadf01e2cef67fd3c2519799636e46
workflow-type: ht
source-wordcount: '878'
ht-degree: 100%

---


# Considerações sobre o conjunto de relatórios global

Um conjunto de relatórios global é um conjunto de relatórios que coleta dados de todos os domínios e aplicativos da organização. Essa técnica de coleta de dados exige preparação e pode exigir coordenação entre as equipes da organização.

## Benefícios

A Adobe recomenda implementar um conjunto de relatórios global na maioria dos casos.

* **Dados agregados:** os conjuntos de relatórios globais permitem que você veja os eventos de KPI e de sucesso nos sites. A segmentação e os conjuntos de relatórios virtuais podem ser usados para exibir dados específicos do site.
* **Suporte para o Cross-Device Analytics:** O CDA exige um conjunto de relatórios que coleta dados de vários lugares, como sites e aplicativos móveis. Dispositivos separados podem unir dados se implementados corretamente. Consulte [Cross-Device Analytics](../../components/cda/overview.md) no guia do usuário de Componentes para obter mais informações.
* **Não há necessidade de mais de um conjunto de relatórios:** todos os dados podem ser coletados em um único conjunto de relatórios, portanto, é menos provável que um desenvolvedor envie dados erroneamente para o conjunto de relatórios incorreto.
* **Não há necessidade de rollups:** os rollups são um recurso bastante antigo que agrega dados individuais do conjunto de relatórios diariamente. Os rollups não cancelam a duplicação de dados de visita ou de visitante, o que pode resultar em números maiores. Consulte [Rollups](../../admin/c-manage-report-suites/rollup-report-suite.md) no Guia do usuário de administração para obter mais informações.
* **Poupe tempo**: os projetos da Workspace, as classificações, os segmentos e as métricas calculadas são vinculados ao mesmo conjunto de relatórios global. Os administradores gastam menos tempo gerenciando esses componentes e o controle de dados.
* **Atribuição mais precisa entre marcas:** se uma visita começar em um site, em seguida, clicar em outro de seus sites antes de acionar um evento bem-sucedido, a atribuição será coletada com precisão. Por exemplo, um visitante clica em um link de pesquisa paga e chega ao site A. Em seguida, clica em um link para o site B e faz uma compra. Um conjunto de relatórios global atribui corretamente a compra para a pesquisa paga.
* **Implementação simplificada:** como todas as marcas/sites enviam dados para o mesmo conjunto de relatórios, suas implementações em cada site são alinhadas. Esse controle imposto garante que uma dimensão ou métrica específica seja salva na mesma eVar ou evento. Os administradores, testadores, proprietários do gerenciamento de tags e analistas se beneficiam dessa simplificação.

>[!NOTE]
>
>Coordenar a implementação de um conjunto de relatórios global é um projeto grande. A Adobe recomenda trabalhar com um consultor para reduzir complicações e problemas que surgirem.

## Iniciar uma nova implementação com um conjunto de relatórios global

Use as diretrizes gerais a seguir para entender o processo de implementação de um conjunto de relatórios global.

1. Criar o conjunto de relatórios global no Adobe Analytics. Consulte [Criar um conjunto de relatórios](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) no Guia do usuário de administração para obter mais informações.
1. Trabalhe com equipes em sua organização responsáveis por cada domínio. Muitas equipes têm requisitos de relatórios específicos para a área de negócios.
1. Registre e agregue todos esses requisitos em um [documento de design da solução](solution-design.md). Se as equipes tiverem requisitos semelhantes para uma dimensão, poderão usar a mesma variável personalizada. Por exemplo, se o site A e B exigirem uma dimensão de navegação estrutural, as implementações de ambos os sites podem enviar esses dados por meio da eVar1.

   >[!IMPORTANT]
   >
   >Verifique se determinada variável personalizada é usada de forma semelhante nos domínios. Não use a mesma eVar ou evento para fins diferentes em seus sites.
1. Verifique se cada domínio tem uma camada de dados para simplificar a coleta de dados. Os dados ainda podem ser coletados sem uma camada de dados, mas a confiabilidade e a longevidade de sua implementação diminuem, especialmente quando o site passa por reformulações.
1. Use o Adobe Experience Platform Launch para implementar o Analytics. Sites diferentes provavelmente exigirão elementos de dados diferentes. Use regras específicas de cada domínio para garantir que cada elemento de dados seja preenchido corretamente e, em seguida, atribua esses elementos de dados às respectivas eVars e eventos. Consulte [Visão geral do Launch](https://docs.adobe.com/content/help/pt-BR/launch/using/overview.html) no guia do usuário do Adobe Experience Platform Launch.
1. Inclua o [Serviço da Adobe Experience Cloud ID](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html) e use a função [appendVisitorIDsTo](https://docs.adobe.com/content/help/pt-BR/id-service/using/id-service-api/methods/appendvisitorid.html). Essa função une os dados do visitante quando os usuários clicam de um domínio para outro.

## Modificar uma implementação existente com um conjunto de relatórios global

O processo de mover uma implementação existente em vários sites para um único conjunto de relatórios global requer mais tempo e coordenação entre as equipes da organização.

1. Determine se deseja usar um de seus conjuntos de relatórios existentes ou começar a usar um novo conjunto de relatórios. Caso queira alterar os usos das variáveis existentes na implementação, é recomendável começar com um novo conjunto de relatórios.
2. Determine uma data limite para quando deseja fazer a mudança para um conjunto de relatórios global. O melhor momento para fazer uma transferência é entre dois períodos significativos de relatório ou junto com as principais alterações no site. Os exemplos incluem o início de um trimestre ou ano fiscal, durante a atualização de um site ou a alteração para um novo sistema de gerenciamento de tags.
3. Siga as etapas acima (crie um conjunto de relatórios, reúna os requisitos de relatório em um documento de design de solução e estabeleça uma camada de dados em cada site). Ao implementar o Launch, valide sua implementação usando uma versão de desenvolvimento do site.
4. Depois de confirmar que a implementação está funcionando no dev, coloque sua implementação do Launch em funcionamento na data limite.

## Páginas relacionadas

[Mudança da marcação de vários conjuntos para um conjunto de relatórios global e virtual](../../components/vrs/vrs-considerations.md)
[Comparação de rollups e conjuntos de relatórios globais](../../admin/c-manage-report-suites/rollup-report-suite.md)
