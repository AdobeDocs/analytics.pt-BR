---
description: Você pode implementar um método personalizado para identificar os visitantes, configurando a variável s.visitorID.
keywords: Implementação do Analytics
seo-description: Você pode implementar um método personalizado para identificar os visitantes, configurando a variável s.visitorID.
seo-title: ID personalizada do visitante
solution: Analytics
title: ID de visitante personalizada
topic: Desenvolvedor e implementação
uuid: 49881 e 27-0418-4 ecf-a 092-dcc 3 db 923 f 40
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID personalizada do visitante

Você pode implementar um método personalizado para identificar os visitantes, configurando a variável s.visitorID.

A ID personalizada do visitante pode ser usada em sites que possuem uma maneira única de identificar visitantes. Um exemplo disso é uma ID gerada quando um usuário entra no site com um nome de usuário e senha.

Caso tenha a habilidade de produzir e gerenciar as [!UICONTROL IDs de visitantes] de seus usuários, utilize os seguintes métodos para definir a ID:

| Método | Descrição |
|---|---|
| [variável s.visitorID](/help/implement/js-implementation/c-variables/page-variables.md) | Se o JavaScript é usado no navegador ou você usa outra biblioteca do AppMeasurement, é possível definir uma ID do visitante em uma variável da coleção de dados. |
| Parâmetro da string de consulta na solicitação de imagem | Isso permite transmitir a [!UICONTROL ID do visitante] à Adobe pelo parâmetro [!UICONTROL vid query string] na solicitação da imagem codificada. |
| API de inserção de dados | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the `<visitorid/>` XML element to Adobe collection servers from your servers. |
| Regravação de URL e VISTA | Algumas arquiteturas de implantação fornecem suporte ao uso da regravação de URL para manter o estado da sessão quando um cookie não pode ser definido. Em tais casos, os serviços de engenharia da Adobe podem implementar uma regra [!DNL VISTA], que procura o valor da sessão no URL da página e, em seguida, o formato e local nos valores [!UICONTROL visid]. |
>[!CAUTION]
>**As IDs de visitante personalizadas devem ser suficientemente granulares/exclusivos**: Uma implementação inválida das IDs de visitante personalizadas pode resultar em dados incorretos e desempenho de relatório inadequado. Se a ID de visitante personalizada não for exclusiva ou granular o suficiente, ou for definida incorretamente para um valor padrão comum como a string «NULL» ou «0», as ocorrências de vários visitantes diferentes serão vistas pelo Adobe Analytics como um único visitante. Essa situação resulta em dados incorretos, com contagens de visitantes muito baixo e segmentos que não funcionam corretamente para esse visitante. Uma ID de visitante personalizada não suficientemente granular também impede que os dados sejam distribuídos apropriadamente entre nós no cluster de relatórios do Analytics. Nessa situação, um nó fica sobrecarregado e não pode processar solicitações de relatório em tempo hábil. Eventualmente, todos os relatórios para o conjunto de relatórios falharão. <br>As IDs de visitante personalizadas mal implementadas podem não afetar imediatamente o desempenho do relatório, pois o Analytics geralmente pode lidar com vários meses de dados desbalanceados; no entanto, com o passar do tempo, um valor personalizado de ID de visitante mal implementado pode tornar-se problemático para o ponto de exigir que o Analytics desative o processamento para conjuntos de relatórios afetados.</br><br>Os implementadores devem seguir a orientação que um único valor personalizado de ID de visitante nunca deve ser creditado por mais de 1% do tráfego do conjunto de relatórios. Although the 1% guideline is sufficient for most report suites, the actual limit that might cause reporting performance to be impacted may be lower than 1% for very large report suites.</br>
