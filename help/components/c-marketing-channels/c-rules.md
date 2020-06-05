---
title: Regras de processamento para Canais de marketing
description: As regras de processamento de Canal de marketing determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal. As regras processam cada acesso que um visitante faz ao seu site. Quando uma regra não atende aos critérios de um canal, ou se as regras não foram configuradas corretamente, o sistema atribui o acesso a Nenhum canal identificado.
translation-type: tm+mt
source-git-commit: acdaebf3c96d7cf1f0e5fed4a459968a83c89fbd
workflow-type: tm+mt
source-wordcount: '2048'
ht-degree: 71%

---


# Regras de processamento para Canais de marketing

As regras de processamento de Canais de marketing determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal, processando cada ocorrência que um visitante faz em seu site. As regras são processadas na ordem especificada e, quando uma regra é atendida, o sistema para de processar as regras restantes.

![](assets/buckets_2.png)

Observações adicionais sobre o processamento :
* Os dados coletados com essas regras são totalmente permanentes, e as regras alteradas após a coleta dos dados não são retroativas. É altamente recomendado analisar e considerar todas as circunstâncias antes de salvar as [!UICONTROL Regras de processamento de Canal de marketing] para reduzir a coleção de dados nos canais errados.
* O relatório pode processar até 25 canais simultaneamente.
* As regras podem acessar variáveis definidas pelo VISTA, mas não podem acessar dados excluídos pelo VISTA.
* Dois canais de marketing nunca recebem crédito pelo mesmo evento (como compras ou cliques). Dessa forma, os canais de marketing diferem das eVars (já que duas eVars podem receber crédito pelo mesmo evento).
* Se houver uma cobertura de falha de suas regras, você poderá ver [Nenhum Canal identificado.](/help/components/c-marketing-channels/c-faq.md)

## Pré-requisitos

* Revise as informações conceituais em [Introdução aos Canais](/help/components/c-marketing-channels/c-getting-started-mchannel.md)de marketing.
* Crie um ou mais canais para poder atribuir regras a eles. Consulte [Adicionar canais de marketing.](/help/components/c-marketing-channels/c-channels.md)

## Criar regras de processamento de Canal de marketing

Crie regras de processamento do Canal de marketing. Elas determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal.

Este procedimento utiliza uma regra de email como exemplo. O exemplo assume que você adicionou um canal de email à lista de canais na página do Gerenciador de canal marketing.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
2. Selecione um conjunto de relatórios.

   Se seu conjunto de ferramentas de relatório não tem canais definidos, a página [!UICONTROL Configuração inicial automática] é exibida.

   Consulte [Executar a configuração automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

3. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Regras de processamento de canal de marketing]**.

   ![Resultado da etapa](assets/marketing_channel_rules.png)

4. Em **[!UICONTROL Adicionar novo conjunto de regras]**, selecione **[!UICONTROL Email]**.

   Ao fazer isso, você não está selecionando o canal, mas um modelo que preenche a regra com alguns dos parâmetros necessários. Você pode modificar esse modelo conforme necessário.

   ![Resultado da etapa](assets/example_email.png)

5. Para continuar criando regras, clique em **[!UICONTROL Adicionar regra]**.
6. Para criar prioridades de regras, arraste-as e solte-as na posição desejada.
7. Clique em **[!UICONTROL Salvar.]**

Continue nesta página para ver as recomendações para a ordem das regras do canal, bem como mais exemplos de definição.

### Definir o valor do canal de marketing

**[!UICONTROL Adicionar ]**regraDefina o valor do canal]**define a dimensão de detalhes do canal de marketing que está disponível para esse canal. Isso permite detalhar as dimensões do canal de marketing e ver informações mais detalhadas sobre o canal.

Recomenda-se que o valor do canal seja definido com os mesmos critérios usados para definir o próprio canal. Por exemplo, se o parâmetro da string de query for usado para definir o canal, defina também o parâmetro da string de query como o valor do canal.

### Critérios da regra

Esta tabela de referência define os campos, as opções e os atributos de ocorrência que você pode usar para definir Regras de processamento de Canais de marketing.

| Termo | Definição |
|--- |--- |
| Todos | Ativa o canal apenas quando todas as regras da regra enumerada são verdadeiras. |
| Qualquer | Ativa este canal quando qualquer regra no conjunto de regras é verdadeira. Essa opção está disponível apenas se existir mais de uma regra na regra enumerada. |
| ID do AMO | O código de rastreamento primário usado pelas integrações da Advertising Cloud e do Advertising Analytics. Quando uma dessas integrações estiver ativada, o prefixo do código de rastreamento poderá ser usado para identificar canais específicos da Advertising Cloud. Usar &quot;ID do AMO&quot; começa com &quot;AL&quot; para Pesquisa, &quot;AC&quot; para Exibição ou &quot;AO&quot; para Social. Quando a ID do AMO é usada em canais de marketing, as métricas de clique/custo/impressão podem ser atribuídas ao canal correto (quando não estiver configurado, essas métricas irão para Direto ou Nenhum). |
| ID do AMO ED | O código de rastreamento secundário usado pela Advertising Cloud. O objetivo principal desse código de rastreamento é atuar como a chave para enviar dados de volta para a Ad Cloud. No entanto, ele também pode ser usado para identificar ClickThroughs de exibição vs. ViewThroughs de exibição, se você desejar vê-los como dois canais de marketing separados. Isso pode ser feito definindo a lógica do canal de marketing para &quot;AMO EF ID&quot; termina com &quot;:d&quot; para ClickThroughs de exibição ou &quot;AMO EF ID&quot; termina com &quot;:i&quot; para ViewThroughs de exibição. Se você não desejar dividir a Exibição em dois canais, use a dimensão da ID do AMO. |
| Variáveis de conversão | Consiste de eVars ativadas para esse conjunto de ferramentas de relatório, e se aplica apenas quando essas variáveis são definidas por meio do código Adobe na página.  Consulte o Guia de implementação . |
| Existe | Diversas seleções estão disponíveis, incluindo:<ul><li>**Não existe**: especifica que o atributo da ocorrência não existe no pedido. Por exemplo, em um domínio de referência, se o usuário digitar um URL ou clicar em um marcador, o atributo de domínio de referência não existe.</li><li>**Está vazio**: especifica que existe um atributo de ocorrência, geralmente um eVar ou parâmetro de sequência de consulta, mas não há valor associado ao atributo de ocorrência.</li><li>**Não Contém:** permite especificar, por exemplo, que um domínio de referência não contém um valor específico (em vez de usar a seleção &quot;Contém&quot;.)</li></ul> |
| Identificar o canal como | Associa a regra a um canal de marketing adicionado à página Gerenciador de canal de marketing.  Consulte Adicionar canais de marketing . |
| Corresponde a Regras de Detecção de Pesquisa Paga | Uma pesquisa paga detectada pela Adobe. Pesquisas pagas são quando as empresas pagam uma taxa para que o mecanismo de pesquisa relacione seus sites. As pesquisas pagas em geral aparecem no alto ou à direita dos resultados da pesquisa. |
| Corresponde a Regras de Detecção de Pesquisa Natural | Uma pesquisa não paga detectada pelo relatório da Adobe. |
| Referenciador corresponde a filtros internos de URL | Uma visita cujo URL da página corresponde a um filtro de URL interno, conforme definido para o conjunto de relatórios nas Ferramentas de administração. |
| Referenciador não corresponde a filtros internos de URL | O URL de referência não corresponde a um filtro de URL interno, conforme definido para o conjunto de relatórios nas Ferramentas de administração. Você pode utilizar essas configurações com   A  URL da página  e  existe  para configurar uma regra &quot;pega tudo&quot;, de forma que nenhuma visita chegue até a seção Nenhum canal identificado do relatório. |
| Ignorar ocorrências correspondentes a filtros de URL internos | (Para referenciadores) Acompanha apenas ocorrências provenientes de sites com referenciador externo. Em geral, mantenha essa configuração ativada, a menos que deseje incluir tráfego interno. |
| É a primeira página da visita | A primeira página da visita detectada por um relatório Adobe. |
| Página | O nome de uma página da Web no seu site que foi marcada usando o Web beacon. Este valor é equivalente a  s.pageName . Os exemplos incluem `Home Page` e `About Us`. |
| Domínio de página | O domínio da página onde o visitante chega, como `products.example.co.uk`. |
| Domínio e caminho da página | The domain and path, such as `products.example.co.uk/mens/pants/overview.html` . |
| Domínio raiz da página (TLD+1) | O domínio raiz da página onde o visitante chega como, por exemplo, example.co.uk . |
| URL da página | O URL da página da Web de seu site. |
| Domínio de referência | O domínio de onde seus visitantes vieram antes visitarem seu site, por exemplo, referenciadores vindos de `abcsite.com` x `xyzsite.com`. |
| Parâmetro da sequência de caracteres de consulta | If a page URL on your site looks like `https://example.com/?page=12345&cat=1`, then page and cat are both query string parameters. (Consulte `https://en.wikipedia.org/wiki/Query_string`.)  É possível especificar apenas um parâmetro da sequência de consulta por conjunto de regras. To add additional query string parameters, use `ANY` as your operator, then add new query string parameters to the rule. |
| Referenciador | O local da página da Web (URL completo) onde seus visitantes estavam antes de chegarem ao seu site. O referenciador existe fora do seu domínio definido. |
| Domínio e caminho de referência | A concatenação de domínio de referência e caminho de URL. Os exemplos incluem:    `www.example.com/products/id/12345` ou `ad.example.com/foo` |
| Parâmetro de referência | Um parâmetro da sequência de consulta no URL do referenciador. Por exemplo, se seus visitantes vêm de `example.com/?page=12345&cat=1`, page e cat são os parâmetros de referência. |
| Domínio raiz de referência | O domínio raiz do referenciador. O referenciador existe fora do seu domínio definido. |
| Mecanismo de pesquisa | Um mecanismo de pesquisa como Google ou Yahoo! que trouxe visitantes ao seu site. |
| Palavras-chave de pesquisa | Uma palavra usada para realizar uma pesquisa usando um mecanismo de pesquisa. |
| Mecanismo de pesquisa + Palavras-chave | Uma concatenação de palavra-chave de pesquisa e mecanismo de pesquisa para identificar de forma exclusiva o mecanismo de pesquisa. Por exemplo, se você pesquisar a palavra computador, o mecanismo de pesquisa e a palavra-chave serão identificados assim: `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**Nota:**n = natural; p = paga |
| Defina o valor do canal como | Além de saber qual canal de marketing traz um visitante ao seu site, talvez você também queira saber que anúncio de banner, palavra-chave de pesquisa ou campanha por email dentro do canal está obtendo crédito pela atividade de um visitante do site. Esse ID é um valor de canal armazenado juntamente com o canal. Muitas vezes esse valor é um ID de campanha integrado à página inicial ou ao URL referenciador, em outros casos, é a combinação do mecanismo de pesquisa com a palavra-chave de pesquisa ou o URL referenciador que identifica melhor o visitante de determinado canal. |

## Ordem e definições das regras do Canal de marketing {#channel-rules}

As regras de Canal são processadas na ordem especificada. Uma abordagem recomendada para a ordem do canal é colocar os canais pagos ou gerenciados primeiro (por exemplo, pesquisa paga, pesquisa natural, exibição, email) para que eles recebam crédito, seguido de canais orgânicos (por exemplo, domínios diretos, internos, de referência).

Abaixo está a ordem recomendada para regras de canal, bem como as definições de exemplo:

### Pesquisa paga {#paid-search}

Pesquisa paga é uma palavra ou frase que você paga a um mecanismo de pesquisa para colocação nos resultados da pesquisa. Normalmente, esse canal é definido com base no parâmetro da sequência de query (consulte Exemplo de canal de exibição) ou nas regras de detecção de pesquisa paga. A decisão depende dos detalhes do canal de marketing que você deseja gravar.

#### Detecção de pesquisa paga

Para corresponder às regras de detecção de pesquisa paga, o canal de marketing usa configurações definidas na página [!UICONTROL Detecção de pesquisa paga]. ( **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Gerais]** > **[!UICONTROL Detecção de pesquisa com anúncios]**). O URL de destino corresponde à regra de detecção de pesquisa paga existente para o mecanismo de pesquisa.

Para a regra de canal de marketing, as configurações de [!UICONTROL Pesquisa Paga] são:

![](assets/example_paid_search.png)

Consulte [Detecção de pesquisa paga](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) em Admin para obter mais informações.

### Pesquisa natural  {#natural-search}

A pesquisa natural ocorre quando os visitantes encontram seu Web site por meio de uma pesquisa na Web, onde o mecanismo de pesquisa classifica seu site sem que você pague para entrar na listagem.

Não existe detecção de pesquisa natural no Analytics. Após configurar a Detecção de pesquisa paga, o sistema saberá que se um referenciador de pesquisa não for do tipo pago, ele deve ser um referenciador de pesquisa natural. Consulte [Detecção de pesquisa paga](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) em Admin para obter mais informações.

Para a regra de canal de marketing, as configurações de Pesquisa natural são as seguintes:

![](assets/example_natural_search.png)

### Exibir {#display}

Essa regra identifica visitantes que se originam de anúncios em banners. Ela é identificada por um parâmetro de sequência de consulta na URL de destino, neste caso  *`Ad_01`*.

![](assets/example_display.png)

### Email  {#email}

Esta regra identifica visitantes originados de campanhas de e-mail. Ela é identificada por um parâmetro de sequência de consulta na URL de destino, neste caso *`eml`*:

![](assets/example_email.png)

### Afiliados  {#afilliates}

Essa regra identifica visitantes que se originam de um conjunto especificado de domínios de referência. Na regra, você relaciona os domínios de afiliados que gostaria de acompanhar, como segue:

![](assets/example_affiliates.png)

### Outras Campanhas {#other-campaigns}

Uma prática recomendada é incluir um canal &quot;Outras campanhas&quot; seguindo todas as regras de canal pagas. Este canal atua como um &quot;catch-all&quot; para o tráfego pago sem categoria.

### Redes sociais {#social-networks}

Esta regra identifica os visitantes que se originam de uma rede social, como o Facebook*. Muitas vezes, o canal é renomeado para Social orgânico. As configurações podem ser as seguintes:

![](assets/example_social.png)

### Canal interno (atualização de sessão){#internal}

Essa regra visitante onde o URL de referência corresponde à configuração dos Filtros de URL internos no Console de administração, o que significa que o visitante veio do site para start de sua visita. Esse canal geralmente é renomeado para Atualização de sessão.

![](assets/int-channel1.png)

Consulte [Motivos para interno (Atualização de sessão)](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-faq.html) para obter mais informações sobre por que esse canal ocorre.

### Direta  {#direct}

Essa regra identifica visitantes que não têm domínio de referência, o que inclui visitantes que chegam ao site diretamente, como de um link Favoritos ou colando um link no navegador. Esse canal geralmente é renomeado para Digitado/Marcado diretamente.

![](assets/example_direct.png)

### canal de domínios de referência {#referring-domains}

O canal Domínios de referência identifica visitantes que têm um domínio de referência. Juntos, os canais dos domínios Interno, Direto e Referenciador atuam como um catch-all para todas as ocorrências restantes que ainda não foram categorizadas em um canal.

