---
description: Você pode implementar um método personalizado para identificar os visitantes, configurando a variável s.visitorID.
keywords: Analytics Implementation
title: ID de visitante personalizada
topic: Developer and implementation
uuid: 49881e27-0418-4ecf-a092-dcc3db923f40
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# ID de visitante personalizada

Você pode implementar um método personalizado para identificar os visitantes, configurando a variável s.visitorID.

A ID personalizada do visitante pode ser usada em sites que possuem uma maneira única de identificar visitantes. Um exemplo disso é uma ID gerada quando um usuário entra no site com um nome de usuário e senha.

Caso tenha a habilidade de produzir e gerenciar as [!UICONTROL IDs de visitantes] de seus usuários, utilize os seguintes métodos para definir a ID:

| Método | Descrição |
|---|---|
| [variável s.visitorID](/help/implement/js-implementation/page-variables/page-variables.md) | Se o JavaScript é usado no navegador ou você usa outra biblioteca do AppMeasurement, é possível definir uma ID do visitante em uma variável da coleção de dados. |
| Parâmetro da string de consulta na solicitação de imagem | Isso permite transmitir a [!UICONTROL ID do visitante] à Adobe pelo parâmetro [!UICONTROL vid query string] na solicitação da imagem codificada. |
| API de inserção de dados | Em dispositivos que usam protocolos sem fio que não aceitam o JavaScript, é possível enviar uma publicação XML com o elemento XML `<visitorid/>` para os seus servidores; basta usar os servidores de coleta da Adobe. |
| Regravação de URL e VISTA | Algumas arquiteturas de implantação fornecem suporte ao uso da regravação de URL para manter o estado da sessão quando um cookie não pode ser definido. Em tais casos, os serviços de engenharia da Adobe podem implementar uma regra [!DNL VISTA], que procura o valor da sessão no URL da página e, em seguida, o formato e local nos valores [!UICONTROL visid]. |
>[!CAUTION]
>**As IDs de visitante personalizadas devem ser suficientemente granulares/exclusivas**: uma implementação inválida de IDs de visitante personalizadas pode levar a dados incorretos e a um desempenho de relatório insatisfatório. Se a ID de visitante personalizada não for exclusiva ou granular o suficiente, ou estiver definida incorretamente para um valor padrão comum, como a string "NULL" ou "0", as ocorrências de muitos visitantes diferentes serão vistas pelo Adobe Analytics como um único visitante. Essa situação resulta em dados incorretos, onde as contagens de visitantes são muito baixas e os segmentos não funcionam corretamente para o visitante. Uma ID de visitante personalizada insuficientemente granular também impede que os dados sejam distribuídos corretamente entre nós no cluster de relatórios do Analytics. Nessa situação, um nó fica sobrecarregado e não pode processar as solicitações de relatório em tempo hábil. Eventualmente, ocorrerá falha em todos os relatórios do conjunto de relatórios. <br>IDs de visitante personalizadas mal implementadas podem não afetar imediatamente o desempenho do relatório, pois o Analytics pode lidar com dados desbalanceados que valem vários meses; no entanto, com o tempo, um valor de ID de visitante personalizado mal implementado pode se tornar problemático a ponto de exigir que o Analytics desative o processamento de conjuntos de relatórios afetados.</br><br>Os implementadores devem seguir a diretriz de que um único valor de ID de visitante personalizado nunca deve ser creditado por mais de 1% do tráfego do conjunto de relatórios. Embora a diretriz de 1% seja suficiente para a maioria dos conjuntos de relatórios, o limite real que pode causar impacto no desempenho dos relatórios pode ser inferior a 1% para conjuntos de relatórios muito grandes.</br>
