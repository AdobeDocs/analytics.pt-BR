---
description: Disponível na Analysis Workspace e no Construtor de segmentos
title: Visitantes com Experience Cloud ID
uuid: 47ebd3d6-a921-4e51-ac7a-b8d5fb9565e0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visitantes com Experience Cloud ID

Disponível na Analysis Workspace e no Construtor de segmentos

Exibe o número de visitantes com uma Experience Cloud ID. Você pode entender quais páginas têm o Serviço de identidade implantado e quantos visitantes podem ser compartilhados com outras soluções da Experience Cloud. Também é possível usar essa métrica em segmentos que são compartilhados com a Experience Cloud.

>[!IMPORTANT]
>
>For this metric to appear, you have to have the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) running for the report suite.

## Depurar a configuração da Experience Cloud ID {#section_679E62142A3E46548FF8FBDA46568005}

The [!UICONTROL Visitors with Experience Cloud ID] metric is a useful metric in Adobe Analytics intended to help you find and debug your [!UICONTROL Identity Service]setup. A métrica é uma contagem do número de visitantes em um conjunto de relatórios ao qual foi atribuída uma Experience Cloud ID do Serviço de identidade. Essa métrica pode ser muito útil ao diagnosticar o porquê de certas integrações da Experience Cloud não estarem compartilhando quantos visitantes conforme o esperado ou identificando áreas do site que podem ainda não ter a MCID implantada.

Para usar a métrica Visitantes com Experience Cloud ID, apenas arraste-a para qualquer relatório como uma métrica, como neste relatório de [!UICONTROL Páginas]:

![](assets/metric-mcvid1.png)

Nesse exemplo, note que cada página possui o mesmo número de Visitantes únicos quanto de Visitantes com uma Experience Cloud ID. No entanto, o número total de Visitantes únicos é maior que o número total de Visitantes com Experience Cloud ID. Para encontrar as páginas que não estão configurando a MCID para todos os visitantes, [crie uma métrica calculada](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_build_metrics.html) com a definição a seguir:

![](assets/metric-mcvid2.png)

Ao adicionar a métrica calculada ao relatório, é possível classificar o relatórios de Páginas, de forma que as páginas com os maiores números de visitantes sem MCID apareçam:

![](assets/metric-mcvid3.png)

Agora você pode ver rapidamente que as páginas "Exibições rápidas do produto" não foram implementadas corretamente com o Serviço de identidade e devem ser atualizadas o mais rápido possível. Um relatório semelhante pode ser construído em qualquer tipo de dimensão, tal como tipo de navegador, seção do site ou tipos de conteúdo.

Depois de identificar as páginas que têm visitantes sem uma MCID, você deve ser capaz de levá-las de volta à sua equipe de implementação para que possam corrigir essas páginas.

Em alguns casos, é possível encontrar um pequeno número de MCIDs que não estão configuradas para alguns visitantes, mesmo que o Serviço da MCID tenha sido implantando na página. Nesses casos, é possível que aconteça devido a um erro comum na configuração do JavaScript do Analytics ou na configuração do DTM na qual a função AppMeasurement é iniciada antes de fornecer um conjunto de relatórios. Para evitar essas falhas, lembre-se de [inserir o código de núcleo do AppMeasurement](https://marketing.adobe.com/resources/help/en_US/sc/implement/dtm/t_appmeasurement-code.html) corretamente.

Esteja ciente de que qualquer segmento baseado na página "Exibições rápidas do produto" (como mostrado acima) compartilhada com a Experience Cloud provavelmente terá uma taxa de correspondência muito baixa com outras soluções da Experience Cloud. Para verificar a cobertura da MCID para qualquer segmento, é possível construir um relatório como o apresentado a seguir:

![](assets/metric-mcvid4.png)

Nesta tabela, que compara o número de Visitantes únicos com os Visitantes com uma Experience Cloud ID, é fácil ver que o "Segmento 1" não tem 100% de cobertura MCID, enquanto o "Segmento 2" tem. Isso significa que se eu compartilhasse o Segmento 1 com a Experience Cloud, poderia compartilhar com apenas 2.186 do total de 3.859 visitantes.
