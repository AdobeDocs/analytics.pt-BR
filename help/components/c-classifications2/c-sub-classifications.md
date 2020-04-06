---
description: O Adobe Analytics suporta modelos de classificação de nível único e múltiplo. Uma hierarquia de classificação permite aplicar uma classificação a uma classificação.
subtopic: Classifications
title: Sobre as subclassificações
topic: Admin tools
uuid: 48bd7fc1-54a1-40ef-bc55-395338522f2d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Sobre as subclassificações

O Adobe Analytics oferece suporte a modelos de classificações de nível único e múltiplo. Uma hierarquia de classificação permite aplicar uma classificação a uma classificação.

>[!NOTE] Subclassificação é a capacidade de criar classificações das classificações. However, this is not the same as a [!UICONTROL Classification Hierarchy] used to create [!UICONTROL Hierarchy] reports. Para obter mais informações sobre hierarquias de Classificação, consulte [Hierarquias de classificação](classification-hierarchies.md).

Por exemplo:

![](assets/single-level-popup-C.png)

Cada classificação neste modelo é independente e corresponde a um novo subrelatório para a variável de relatórios selecionada. Além disso, cada classificação constitui uma coluna de dados no arquivo de dados, com o nome de classificação como o cabeçalho da coluna. Por exemplo:

| CHAVE | PROPRIEDADE 1 | PROPRIEDADE 2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

Para obter mais informações sobre o arquivo de dados, consulte  [Arquivos de dados de classificação](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).

As classificações de vários níveis são compostas de classificações pai e filho. Por exemplo:

![](assets/Multi-Level-Class-popup.png)

**Classificações principais:** uma classificação principal é qualquer classificação que tem uma classificação secundária associada. Uma classificação pode ser tanto principal como secundária. As classificações principais de nível superior correspondem às classificações de nível único (Consulte  [Classificações de nível único](/help/components/c-classifications2/c-sub-classifications.md)).

**Classificações secundárias:** uma classificação secundária é qualquer classificação que tem outra classificação como principal em vez da variável. As classificações secundárias fornecem informações adicionais sobre sua classificação pai. Por exemplo, uma [!UICONTROL Campaigns] classificação pode ter uma classificação secundária Proprietário da Campanha. [!UICONTROL Numeric] as classificações também funcionam como métricas nos relatórios de classificação.

Cada classificação, principal ou secundária, constitui uma coluna de dados no arquivo de dados. O cabeçalho da coluna para uma classificação secundária usando o seguinte formato de nomeação:

`<parent_name>^<child_name>`

Para obter mais informações sobre o formato do arquivo de dados, consulte [Arquivos de dados de classificação](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).

Por exemplo:

| CHAVE | PROPRIEDADE 1 | Propriedade 1&amp;Hat;Propriedade 1-1 | Propriedade 1&amp;Hat;Propriedade 1-2 | Propriedade 2 |
|---|---|---|---|---|
| 123 | ABC | Verde | Pequena | A12B |
| 456 | DEF | Vermelho  | Grande | C3D4 |

Embora o modelo de arquivo para uma classificação de vários níveis seja mais complexo, o poder das classificações de vários níveis é que níveis separados podem ser carregados como arquivos separados. Essa abordagem pode ser usada para minimizar a quantidade de dados que precisa ser carregada periodicamente (diariamente, semanalmente e assim por diante) ao agrupar dados em níveis de classificação que mudam ao longo do tempo em vez daqueles que não mudam.

>[!NOTE] Se a [!UICONTROL Key] coluna em um arquivo de dados estiver em branco, a Adobe gera automaticamente chaves exclusivas para cada linha de dados. Para evitar possíveis danos no arquivo ao carregar um arquivo de dados com dados de classificação de segundo nível ou superior, preencha cada linha da [!UICONTROL Key] coluna com um asterisco (*).

Consulte [Problemas comuns no upload de classificação](https://marketing.adobe.com/resources/help/pt_BR/home/index.html#kb-common-saint-upload-issues) para obter ajuda com a resolução de problemas.

## Exemplos

![](assets/sample-product-classifications.png)

>[!NOTE] Os dados de classificação do produto estão limitados aos atributos de dados diretamente relacionados ao produto. Os dados não se limitam ao modo como os produtos são categorizados ou vendidos no site. Elementos de dados como categorias de venda, nós de navegação do site ou itens de venda não são dados de classificação do produto. Em vez disso, esses elementos são capturados nas variáveis de conversão do relatório.

Ao carregar arquivos de dados para essa classificação de produto, você pode carregar os dados de classificação como um único arquivo ou como vários arquivos (veja abaixo). Separando o código de cor no arquivo 1 e o nome da cor no arquivo 2, os dados do nome da cor (que podem ter apenas algumas linhas) precisam ser atualizados somente quando novos códigos de cor forem criados. Isso elimina o campo de nome da cor (CÓDIGO&amp;Hat;COR) do arquivo 1, que é atualizado com mais frequência, e reduz o tamanho e a complexidade do arquivo ao gerar o arquivo de dados.

### Classificação do produto - Arquivo simples {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| CHAVE | NOME DO PRODUTO | DETALHES DO PRODUTO | GÊNERO | TAMANHO | CÓDIGO | CÓDIGO&amp;Hat;COR |
|---|---|---|---|---|---|---|
| 410390013 | Polo-SS | Camisa polo masculina, manga curta (M,01) | Seg | Seg | 01 | Pedra |
| 410390014 | Polo-SS | Camisa polo masculina, manga curta (L,03) | Seg | G | 03 | Urze |
| 410390015 | Polo-LS | Camisa polo feminina, manga longa (S,23) | Sex | S | 23 | Aqua |

### Classificação do produto - Vários arquivos (Arquivo 1)  {#section_A99F7D0F145540069BA4EEC0597FF13F}

| CHAVE | NOME DO PRODUTO | DETALHES DO PRODUTO | GÊNERO | TAMANHO | CÓDIGO |
|---|---|---|---|---|---|
| 410390013 | Polo-SS | Camisa polo masculina, manga curta (M,01) | Seg | Seg | 01 |
| 410390014 | Polo-SS | Camisa polo masculina, manga curta (L,03) | Seg | G | 03 |
| 410390015 | Polo-LS | Camisa polo feminina, manga longa (S,23) | Sex | S | 23 |

### Classificação do produto - Vários arquivos (Arquivo 2)  {#section_19ED95C33B174A9687E81714568D56A3}

| CHAVE | CÓDIGO | CÓDIGO&amp;Hat;COR |
|---|---|---|
| * | 01 | Pedra |
| * | 03 | Urze |
| * | 23 | Aqua |
