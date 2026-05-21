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
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1740
ht-degree: 56%

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
>Somente um valor único pode ser armazenado em uma eVar em uma solicitação de imagem. Se vários valores forem desejados no valor de uma eVar, recomendamos a implementação de [Listar variáveis (list vars)](/help/implement/vars/page-vars/page-variables.md).

### Variáveis de conversão - descrições {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descrições de campos usados ao [editar variáveis de conversão](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md).

| Elemento | Descrição |
| --- | --- |
| [!UICONTROL Nome] | O nome amigável da variável de conversão. Esse nome é como a eVar é mencionada em relatórios gerais e será o nome do relatório/dimensão no menu à esquerda. |
| [!UICONTROL Tipo] (somente eVar) | O tipo de valor da variável:<ul><li>**[!UICONTROL Cadeia de caracteres de texto]**: captura os valores de texto usados do site. Esse é o tipo mais comum de eVar e a configuração padrão. Ela age de forma semelhante a outras variáveis, onde o valor dentro dela é uma string de texto estática. Se você estiver rastreando itens como campanhas internas ou palavras-chave de pesquisa interna, essa é a configuração recomendada.</li><li>**[!UICONTROL Contador]**: conta o número de vezes que uma ação ocorre antes do evento bem-sucedido. Por exemplo, se você usa uma eVar para rastrear pesquisas internas no site, configure esse valor como [!UICONTROL sequência de caracteres de texto] para rastrear o uso de termos de pesquisa. Configure esse valor como [!UICONTROL contador] para contar o número de pesquisas efetuadas, independentemente dos temos de pesquisa usados. Por exemplo, você pode usar um eVar de contador para rastrear o número de vezes que alguém usou sua pesquisa interna antes de fazer uma compra.</li></ul> |
| [!UICONTROL Alocação] | Determina como o Analytics atribuirá crédito por um evento bem-sucedido se uma variável receber vários valores antes do evento. Os valores compatíveis incluem:<ul><li>**[!UICONTROL Mais recente]**: o último valor de eVar sempre recebe crédito por eventos bem-sucedidos até que esse eVar expire.</li><li>**[!UICONTROL Valor original]**: a primeira eVar sempre recebe crédito por eventos bem-sucedidos até que essa eVar expire.</li><li>**[!UICONTROL Linear]**: aloca eventos bem-sucedidos igualmente entre todos os valores de eVar. Como a alocação Linear distribui com precisão os valores somente em uma visita, use essa alocação com Visita como expiração de eVar.</li></ul> **Observação**: a mudança da alocação de ou para Linear impede que os dados históricos sejam exibidos. A combinação de tipos de alocação na interface de relatórios pode gerar dados incorretos nos relatórios. Por exemplo, a alocação linear pode dividir a receita em vários valores diferentes de eVar. Depois de voltar para a Alocação mais recente, 100% dessa receita seria associada ao valor único mais recente. Essa associação pode levar a conclusões incorretas por parte dos usuários.<br><br>Para evitar a probabilidade de confusão nos relatórios, o Adobe Analytics não disponibiliza os dados históricos para a interface. Ela poderá ser visualizada se você decidir alterar a eVar fornecida de volta para a configuração de alocação inicial, embora não altere as configurações de alocação do eVar simplesmente para acessar os dados históricos. A Adobe recomenda usar uma nova eVar quando novas configurações de alocação forem desejadas para dados que já estão sendo registrados, em vez de alterar configurações de alocação em uma eVar que já tenha uma quantidade significativa de dados históricos acumulados. |
| [!UICONTROL Expirar após] | Especifica o período ou evento após o qual o valor do eVar expira (não recebe mais crédito por eventos bem-sucedidos). Se um evento bem-sucedido ocorrer após a expiração da eVar, o valor Nenhum receberá o crédito pelo evento (nenhuma eVar estava ativa).  Se você selecionar um evento como valor de expiração, a variável expirará somente se o evento ocorrer. Se o evento não ocorrer, a variável nunca expirará.  As opções de expiração disponíveis podem ser classificadas em quatro categorias principais:<ul><li>**Em um nível de exibição de página ou visita.** Eventos de conversão além da exibição de página ou visita não estão associados à eVar.</li><li>**Com base em um período de tempo, como dia, semana, mês ou ano.** Os eventos de conversão além do período especificado não estão associados à eVar. O período de expiração começa quando a variável é definida. As eVars expiram com base no horário em que foram definidas, no segundo (minuto, hora, dia, mês etc.): <ul><li>MINUTE=60 segundos</li><li>HORA=3600 segundos (60 minutos)</li><li>DAY=86400 segundos (24 horas)</li><li>WEEK=604800 segundos (7 dias)</li><li>MONTH=2678400 segundos (31 dias)</li><li>QUARTER=8035200 segundos (93 dias - 3 meses de 31 dias)</li><li>YEAR=31536000 segundos (365 dias)</li><br>Se uma visita iniciar às 7:00 AM de segunda-feira e uma eVar estiver definida nessa visita às 7:15 AM, a expiração ocorre conforme mostrado abaixo:<li>Expiração do dia: o eVar expira às 7:15 da manhã de terça-feira.</li><li>Expiração da semana: o eVar expira na segunda-feira seguinte, às 7:15 AM.</li><li>Expiração do mês: o eVar expira 31 dias a partir de segunda-feira às 7:15 AM.</li></ul><li>**Eventos de conversão específicos.** Quaisquer outros eventos de conversão que são acionados após o evento específico designado como associado à eVar.</li><li>**Nunca.** Desde que um visitante use o mesmo identificador, qualquer quantidade de tempo pode passar entre a eVar e o evento.</li></ul> |
| [!UICONTROL Status] (somente eVar) | Define o status da [!UICONTROL eVar]:<ul><li>**Desativado**: desativa a [!UICONTROL eVar]. Remove a [!UICONTROL eVar] da lista de variáveis de conversão.</li><li>**Sem sub-relações**: impede que você decomponha a [!UICONTROL eVar] em uma dimensão.</li><li>**Sub-relações básicas**: permite decompor uma eVar em qualquer dimensão total (por exemplo, Produtos ou Campanhas).</li></ul> |
| [!UICONTROL Redefinir] | Redefine qualquer valor existente no eVar. Use essa configuração ao redefinir o objetivo de uma eVar para que você não misture um valor antigo em um novo relatório. A redefinição não apaga os dados históricos. |
| [!UICONTROL Merchandising] (somente eVar) | As variáveis de merchandising podem seguir uma das duas sintaxes:<ul><li>**[!UICONTROL Sintaxe de produtos]**: associa o valor de eVar a um produto. **Observação**: se a [!UICONTROL Sintaxe de produtos] estiver selecionada, a seção [!UICONTROL Evento compulsório de merchandising] será desativada e não poderá ser selecionada para edição. Os [!UICONTROL Eventos compulsórios] não se aplicam a essa sintaxe.</li><li>**[!UICONTROL Sintaxe de variável de conversão]**: associa a eVar a um produto somente se um [!UICONTROL evento compulsório] ocorre. Nesse caso, você seleciona os eventos que atuam como [!UICONTROL Eventos compulsórios].  Alterar essa configuração sem atualizar seu código JavaScript de acordo resultará na perda de dados. Consulte [Variáveis de merchandising](/help/components/dimensions/evar-merchandising.md).</li></ul> |
| [!UICONTROL Evento compulsório de merchandising] (somente eVar) | Se Merchandising estiver definido como [!UICONTROL Sintaxe de variável de conversão], os eventos selecionados vincularão o valor de eVar atual a um produto. Para usar um [!UICONTROL Evento compulsório], defina a [!UICONTROL Alocação] como [!UICONTROL Mais recente]. Se a [!UICONTROL Alocação] for definida como [!UICONTROL Valor original], a primeira ligação de produto de eVar permanecerá até que a eVar expire. Você pode selecionar vários eventos pressionando e segurando Ctrl (no Windows) ou cmd (no Mac) e clicando em vários itens na lista. Você pode selecionar um evento somente quando a [!UICONTROL Sintaxe de variável de conversão] está selecionada. |

### Expiração

As `eVars` expiram depois de um período definido por você. Depois que a eVar expira, ela não recebe mais crédito por eventos bem-sucedidos. As eVars também podem ser configuradas para expirar em eventos bem-sucedidos. Por exemplo, se você tiver uma promoção interna que expira no final de uma visita, a promoção interna receberá crédito somente para compras ou registros que ocorrem durante a visita em que foram ativados.

Há duas maneiras de expirar uma eVar:

* É possível definir a eVar para expirar depois de um período ou evento especificado.
* É possível forçar a expiração de uma eVar ao redefini-la, o que é útil quando se estabelece um novo objetivo para uma variável.

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
