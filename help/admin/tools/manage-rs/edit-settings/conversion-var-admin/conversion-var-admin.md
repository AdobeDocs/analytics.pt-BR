---
description: A variável de conversão do Custom Insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados. Uma eVar pode ser baseada em visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.
keywords: eVar
title: Variáveis de conversão (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
TQID: https://experienceleague.adobe.com/rYLxVYB1oDyfEk8gQyesTSRRPHid-6zJ8QaqFG2b0Kc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '1726'
ht-degree: 29%
---
# Variáveis de conversão (eVars)

A variável de conversão do Custom Insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados. Uma eVar pode ser baseada em visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Variáveis de conversão]**

## Visão geral das variáveis de conversão (eVars)

Para obter uma visão geral em vídeo das variáveis de conversão, consulte [Introdução às variáveis de conversão](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars) no guia de tutoriais do Analytics.

Quando uma eVar é definida como um valor para um visitante, a Adobe lembra automaticamente desse valor até sua expiração. Quaisquer eventos bem-sucedidos que um visitante encontrar enquanto o valor do eVar estiver ativo serão contados em relação ao valor do eVar.

As eVars são usadas com mais eficiência para medir causa e efeito, como:

* Quais campanhas internas influenciaram a receita
* Quais anúncios de banner resultaram em um registro
* O número de vezes que uma pesquisa interna foi usada antes de fazer um pedido

Se desejar medir ou definir o caminho do tráfego, é recomendado usar variáveis de tráfego.

>[!NOTE]
>
>Somente um valor único pode ser armazenado em uma eVar em uma solicitação de imagem. Se vários valores forem desejados em um valor eVar, use [Variáveis de lista](/help/implement/vars/page-vars/page-variables.md).

### Variáveis de conversão - descrições {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

| Elemento | Descrição |
| --- | --- |
| [!UICONTROL Status] | Determina se o eVar está ativo:<ul><li>**[!UICONTROL Habilitado]**: o eVar está ativo.</li><li>**[!UICONTROL Desabilitado]**: desabilita o eVar e o remove da lista de variáveis de conversão.</li></ul> |
| [!UICONTROL Descrição] | Uma descrição opcional do eVar. Use-o para documentar o que o eVar captura e como ele é implementado. |
| [!UICONTROL Nome] | O nome de dimensão amigável da variável de conversão. É assim que a eVar é chamada em relatórios gerais. |
| [!UICONTROL Alocação] | Determina como o Analytics atribuirá crédito por um evento bem-sucedido se uma variável receber vários valores antes do evento. Os valores compatíveis incluem:<ul><li>**[!UICONTROL Mais recente (último)]**: o último valor de eVar sempre recebe crédito por eventos bem-sucedidos até que esse eVar expire.</li><li>**[!UICONTROL Valor original (primeiro)]**: a primeira eVar sempre recebe crédito por eventos bem-sucedidos até que essa eVar expire.</li><li>**[!UICONTROL Linear]**: aloca eventos bem-sucedidos igualmente entre todos os valores de eVar. Como a alocação Linear distribui valores somente em uma visita, use essa alocação com uma expiração eVar de Visita ou inferior. Essa opção não está disponível para eVars de merchandising.</li></ul>**Importante**: a Adobe recomenda não alternar de ou para a alocação [!UICONTROL Linear], pois ela oculta dados históricos nos relatórios até que você alterne de volta. Para alterar a alocação em uma eVar com histórico significativo, a Adobe recomenda usar uma nova eVar. |
| [!UICONTROL Expirar após] | Especifica quando o valor do eVar expira (não recebe mais crédito por eventos bem-sucedidos). Se um evento bem-sucedido ocorrer após a expiração da eVar, o valor Nenhum receberá o crédito pelo evento (nenhuma eVar estava ativa). Os valores compatíveis incluem:<ul><li>**[!UICONTROL Visita]**: o valor expira ao final da visita.</li><li>**[!UICONTROL Ocorrência]**: o valor se aplica somente à ocorrência em que está definido.</li><li>**[!UICONTROL Minuto]**, **[!UICONTROL Hora]**, **[!UICONTROL Dia]**, **[!UICONTROL Semana]**, **[!UICONTROL Mês]**, **[!UICONTROL Trimestre]** ou **[!UICONTROL Ano]**: o valor expira um período fixo após ser definido, para o segundo:<ul><li>Minuto = 60 segundos</li><li>Hora = 3600 segundos (60 minutos)</li><li>Dia = 86.400 segundos (24 horas)</li><li>Semana = 604800 segundos (7 dias)</li><li>Mês = 2678400 segundos (31 dias)</li><li>Trimestre = 8035200 segundos (93 dias - 3 meses de 31 dias)</li><li>Ano = 31536000 segundos (365 dias)</li></ul>Por exemplo, se uma eVar for definida às 7h15 da segunda-feira, a expiração de [!UICONTROL Dia] termina às 7h15 da terça-feira, a expiração de [!UICONTROL Semana] termina às 7h15 da segunda-feira seguinte e a expiração de [!UICONTROL Mês] termina 31 dias depois às 7h15.</li><li>**[!UICONTROL Personalizado]**: o valor expira após o número de dias inserido (86.400 segundos por dia).</li><li>**Um evento** ([!UICONTROL Compra], [!UICONTROL Exibição do Produto], [!UICONTROL Abertura do Carrinho], [!UICONTROL Check-out do Carrinho], [!UICONTROL Adição ao Carrinho], [!UICONTROL Remoção do Carrinho], [!UICONTROL Exibição do Carrinho] ou um evento personalizado): o valor expira quando o evento selecionado ocorre. Se o evento nunca ocorrer, o valor nunca expirará.</li><li>**[!UICONTROL Nunca]**: desde que um visitante use o mesmo identificador, qualquer quantidade de tempo poderá passar entre a eVar e o evento.</li></ul> |
| [!UICONTROL Tipo] | O tipo de valor da variável:<ul><li>**[!UICONTROL Cadeia de caracteres de texto]**: captura valores de texto. É o tipo mais comum de eVar e a configuração padrão. Ela age de forma semelhante a outras variáveis, onde o valor dentro dela é uma string de texto estática. Se você rastrear itens como campanhas internas ou palavras-chave de pesquisa interna, essa configuração é recomendada.</li><li>**[!UICONTROL Contador]**: conta o número de vezes que uma ação ocorre antes do evento bem-sucedido. Por exemplo, você pode contar o número de pesquisas feitas, independentemente dos termos de pesquisa usados, antes de um evento bem-sucedido.</li></ul> |
| [!UICONTROL Redefinir] | Ao salvar, expira imediatamente todos os valores persistentes do lado do servidor para essa variável em todos os visitantes, incluindo vínculos de produto de merchandising. Use [!UICONTROL Redefinir] ao redefinir a finalidade de uma eVar para que você não misture um valor antigo em um novo relatório. **A redefinição não apaga dados históricos.** |
| [!UICONTROL Habilitar merchandising] | Os valores compatíveis incluem:<ul><li>**[!UICONTROL Desabilitado]**: o eVar credita eventos bem-sucedidos ao valor que persiste para o visitante.</li><li>**[!UICONTROL Habilitado]**: a eVar se torna uma eVar de merchandising, que vincula valores a produtos individuais. Os eventos bem-sucedidos para cada produto são creditados ao valor vinculado a esse produto. Habilitar o merchandising mostra as configurações de [!UICONTROL Merchandising] e [!UICONTROL Evento de ligação de merchandising] e remove a alocação [!UICONTROL Linear].</li></ul>Habilite o merchandising somente para eVars que descrevem como os produtos são encontrados ou comprados. Um eVar de merchandising não credita mais eventos bem-sucedidos que não estão vinculados a um produto. Consulte [eVar (Merchandising)](/help/components/dimensions/evar-merchandising.md). |
| [!UICONTROL Merchandising] | Determina de onde vem o valor a ser vinculado aos produtos:<ul><li>**[!UICONTROL Sintaxe do Produto]**: o valor é definido em cada produto na variável `products` e vinculado a esse produto nessa ocorrência. Cada produto pode ter um valor diferente. Os eventos de ligação não são usados, portanto, o [!UICONTROL Evento de ligação de merchandising] está desativado.</li><li>**[!UICONTROL Sintaxe de variável de conversão]**: o valor é definido no próprio eVar e persiste como um valor em etapas, sempre refletindo o valor mais recente enviado independentemente de [!UICONTROL Alocação]. O valor será vinculado aos produtos em uma ocorrência somente se essa ocorrência contiver um [!UICONTROL Evento de vinculação de merchandising] selecionado. Cada produto nessa ocorrência recebe o mesmo valor.</li></ul>Alterar essa configuração sem atualizar sua implementação de acordo resultará na perda de dados. Consulte [eVar (Variável de merchandising)](/help/implement/vars/page-vars/evar-merchandising.md) para obter detalhes sobre a implementação. |
| [!UICONTROL Evento compulsório de merchandising] | Disponível somente quando [!UICONTROL Merchandising] está definido como [!UICONTROL Sintaxe de variável de conversão]. Determina quais eventos ou eVars vinculam o valor preparado do eVar aos produtos na mesma ocorrência. Se você não selecionar um evento de associação, [!UICONTROL Todos] será usado. Os valores compatíveis incluem:<ul><li>**[!UICONTROL Todos]**: qualquer outro evento ou eVar na ocorrência aciona uma associação. Essa configuração é a padrão.</li><li>**[!UICONTROL Evento de Compra]**, **[!UICONTROL Evento de Exibição de Produto]**, **[!UICONTROL Evento de Abertura do Carrinho]**, **[!UICONTROL Evento de Check-out do Carrinho]**, **[!UICONTROL Evento de Adição ao Carrinho]**, **[!UICONTROL Evento de Remoção do Carrinho]** ou **[!UICONTROL Evento de Exibição do Carrinho]**: a ligação ocorre em ocorrências que contêm o evento selecionado.</li><li>**[!UICONTROL Evento de campanha]**: a ligação ocorre em ocorrências que contêm uma instância da dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md) (variável [`campaign`](/help/implement/vars/page-vars/campaign.md)).</li><li>**Um evento personalizado**: ocorre uma ligação em ocorrências que contêm o evento personalizado selecionado.</li><li>**Uma eVar personalizada**: a ligação ocorre em ocorrências que definem a eVar selecionada.</li></ul>Props não podem acionar associação. Selecione vários valores pressionando e segurando Ctrl (Windows) ou cmd (Mac) e clicando em vários itens na lista. Quando um produto específico que já está vinculado a uma eVar recebe outra associação com essa mesma eVar, a [!UICONTROL Alocação] determina qual valor é mantido. |

### Expiração

As `eVars` expiram depois de um período definido por você. Depois que a eVar expira, ela não recebe mais crédito por eventos bem-sucedidos. As eVars também podem ser configuradas para expirar em eventos bem-sucedidos. Por exemplo, se você tiver uma promoção interna que expira no final de uma visita, a promoção interna receberá crédito somente para compras ou registros que ocorrem durante a visita em que foram ativados.

Há duas maneiras de expirar uma eVar:

* É possível definir a eVar para expirar depois de um período ou evento especificado.
* Você pode forçar a expiração de uma eVar redefinindo-a, o que é útil quando se estabelece um novo objetivo para uma variável.

Por exemplo, se você alterar a expiração de uma eVar de 30 para 90 dias, os valores de eVar coletados continuarão a persistir pela duração do novo conjunto de expiração (nesse caso, 90 dias). O sistema simplesmente verifica a configuração de expiração atual e o último carimbo de data e hora definido do valor da eVar coletado para determinar a expiração. Somente a opção **[!UICONTROL Redefinir]** expira os valores e o faz imediatamente.

Outro exemplo: se uma eVar for usada em maio para refletir promoções internas e expirar depois de 21 dias, e em junho ela for usada para capturar as palavras-chaves da pesquisa interna, no dia 1º de junho você deverá forçar a expiração da variável ou redefini-la. Com isso, você ajudará a manter os valores da promoção interna fora dos relatórios de junho.

### Uso de maiúsculas e minúsculas

As eVars não diferenciam maiúsculas de minúsculas. A caixa alta ou baixa usada nos relatórios se baseia no primeiro valor registrado pelo sistema de back-end. Esse valor pode ser a primeira instância vista ou pode variar em determinado período (por exemplo, mensal), dependendo da variedade e da quantidade de dados associados ao conjunto de relatórios.

### Contadores

Embora as eVars sejam usadas com mais frequência para reter valores da string, elas também podem ser configuradas para atuar como contadores. As eVars são úteis como contadores quando você está tentando contar o número de ações que um usuário toma antes de um evento. Por exemplo, você pode usar uma eVar para capturar o número de pesquisas internas antes da compra. Cada vez que um visitante pesquisa, o eVar deve conter um valor de &#39;+1&#39;. Se um visitante pesquisar quatro vezes antes de uma compra, você verá uma instância para cada contagem total: 1,00, 2,00, 3,00 e 4,00. No entanto, somente a versão 4.00 recebe crédito pelo evento de compra (Pedidos e métricas de receita). Somente números positivos são permitidos como valores de um contador eVar.

## Adicionar ou editar variáveis de conversão

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Variáveis de conversão]**.
1. Na página [!UICONTROL Variáveis de conversão], clique em **[!UICONTROL Expandir]** [+] ao lado da variável de conversão que você deseja modificar.

   Ou

   Clique em **[!UICONTROL Adicionar novo]** para adicionar uma eVar não usada ao conjunto de relatórios.
1. Selecione os campos de variável de conversão que você deseja modificar.

   Consulte [Variáveis de conversão - Descrições](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF). Alguns campos permitem digitar diretamente no campo. Outros permitem selecionar em uma lista suspensa de valores compatíveis.
1. Clique em **[!UICONTROL Salvar]**.
