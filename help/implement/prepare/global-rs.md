---
title: Conjuntos de relatórios globais no Adobe Analytics
description: Entenda as vantagens e os requisitos para usar um conjunto de relatórios global.
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# Considerações sobre o conjunto de relatórios global

Um conjunto de relatórios global é um conjunto de relatórios que coleta dados de todos os domínios e aplicativos de sua organização. Essa técnica de coleta de dados exige preparação e pode exigir coordenação entre equipes em sua organização.

## Benefícios

A Adobe recomenda implementar um conjunto de relatórios global na maioria dos casos.

* **** Dados agregados: Os conjuntos de relatórios globais permitem que você veja os eventos de KPI e de sucesso em seus sites. A segmentação e os conjuntos de relatórios virtuais podem ser usados para exibir dados específicos do site.
* **** Suporte para análises entre dispositivos: O CDA requer um conjunto de relatórios que coleta dados de vários locais, como seu site e aplicativo móvel. Dispositivos separados podem unir dados se implementados corretamente. Consulte Análises [](../../components/cda/cda-home.md) entre dispositivos no guia do usuário Componentes para obter mais informações.
* **** Não há necessidade de mais de um conjunto de relatórios: Todos os dados podem ser coletados em um único conjunto de relatórios, portanto, é menos provável que um desenvolvedor envie dados erroneamente para o conjunto de relatórios errado.
* **** Não há necessidade de rollups: Os rollups são um recurso bastante antigo que agrega dados individuais do conjunto de relatórios diariamente. Os rollups não desduplicam os dados de visita ou de visitante, o que pode resultar em números inflados. Consulte [Rollups](../../admin/c-manage-report-suites/rollup-report-suite.md) no Guia do usuário de administração para obter mais informações.

> [!NOTE] A coordenação da implementação de um conjunto de relatórios global é um projeto grande. A Adobe recomenda trabalhar com um consultor para reduzir complicações e problemas que surgem.

## Iniciar uma nova implementação com um conjunto de relatórios global

Use as diretrizes gerais a seguir para entender o processo de implementação de um conjunto de relatórios global.

1. Crie o conjunto de relatórios global no Adobe Analytics. Consulte [Criar um conjunto](../../admin/admin-console/create-report-suite.md) de relatórios no Guia do usuário administrativo para obter mais informações.
2. Trabalhe com equipes em sua organização responsáveis por cada domínio. Muitas equipes têm requisitos de relatórios específicos para a área de negócios.
3. Registre e agregue todos esses requisitos em um documento [de design da](solution-design.md)solução. Se as equipes tiverem requisitos semelhantes para uma dimensão, poderão usar a mesma variável personalizada. Por exemplo, se o site A e o site B exigirem uma dimensão de navegação estrutural, as implementações para ambos os sites podem enviar esses dados por meio da eVar1.
   > [!IMPORTANT] Certifique-se de que determinada variável personalizada seja usada de forma semelhante nos domínios. Não use a mesma eVar ou evento para fins diferentes em seus sites.
4. Verifique se cada domínio tem uma camada de dados para simplificar a coleta de dados. Os dados ainda podem ser coletados sem uma camada de dados, mas a confiabilidade e a longevidade de sua implementação diminuem, especialmente quando o site passa por reprojetos.
5. Use o Adobe Experience Platform Launch para implementar o Analytics. Sites diferentes provavelmente exigirão elementos de dados diferentes. Use regras específicas para cada domínio para garantir que cada elemento de dados seja preenchido corretamente e, em seguida, atribua esses elementos de dados às respectivas eVars e eventos. Consulte Visão geral [do](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launch no guia do usuário do Adobe Experience Platform Launch.

## Modificação de uma implementação existente com um conjunto de relatórios global

O processo de mover uma implementação existente em vários sites para um único conjunto de relatórios global requer mais tempo e coordenação entre as equipes em sua organização.

1. Determine se você deseja usar um de seus conjuntos de relatórios existentes ou começar a usar um novo conjunto de relatórios. Se você quiser alterar os usos das variáveis existentes na sua implementação, é recomendável começar com um novo conjunto de relatórios.
2. Determine uma data limite para quando deseja fazer a mudança para um conjunto de relatórios global. O melhor momento para fazer uma transferência é entre dois períodos significativos de relatório, como um trimestre fiscal ou um ano.
3. Siga as etapas acima (crie um conjunto de relatórios, reúna os requisitos de relatório em um documento de design de solução e estabeleça uma camada de dados em cada site). Ao implementar o Launch, valide sua implementação usando uma versão de desenvolvimento do site.
4. Depois de confirmar que sua implementação está funcionando no dev, coloque sua implementação do Launch em funcionamento na data limite.

## Páginas relacionadas

[Mudança da marcação de vários relatórios para um conjunto de relatórios global e conjuntos](../../components/vrs/vrs-considerations.md)de relatórios virtuais[Comparação de rollups e conjuntos de relatórios globais](../../admin/c-manage-report-suites/rollup-report-suite.md)