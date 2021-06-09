---
description: A variável de conversão do Custom Insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados. Uma eVar pode ter por base visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.
keywords: eVar
title: Variáveis de conversão (eVar)
feature: Ferramentas administrativas
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
source-git-commit: 212f9c66e2916e629693bf4bf61e767af164900a
workflow-type: tm+mt
source-wordcount: '1587'
ht-degree: 81%

---

# Variáveis de conversão (eVars)

A variável de conversão do Custom Insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados. Uma eVar pode ter por base visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.

Quando uma eVar é definida como um valor para um visitante, a Adobe se lembra automaticamente desse valor até sua expiração. Quaisquer eventos bem-sucedidos que um visitante encontrar enquanto o valor da eVar está ativo são contados no valor da eVar.

O melhor uso das eVars é para medir causa e efeito, como:

* Quais campanhas internas influenciaram a receita
* Quais anúncios em banner resultam em um registro
* O número de vezes em que uma pesquisa interna foi usada antes de um pedido ser feito

Se desejar a medida de tráfego ou de definição de caminho, é recomendado usar variáveis de tráfego.

>[!NOTE]
>
>Somente um valor único pode ser armazenado em uma eVar em uma solicitação de imagem. Se vários valores forem desejados no valor de uma eVar, recomendamos a implementação de [Listar variáveis (list vars)](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html).

## Variáveis de conversão - descrições {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descrições de campos usados ao [editar variáveis de conversão](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md).



| Elemento | Descrição |
| --- | --- |
| [!UICONTROL Nome] | O nome amigável da variável de conversão. Esse nome é como o eVar é referido em relatórios gerais e será o nome do relatório/dimensão no menu esquerdo. |
| [!UICONTROL Tipo]   (somente eVar) | O tipo de valor da variável:<ul><li>**[!UICONTROL Cadeia de caracteres de texto]**: captura os valores de texto usados do site. Esse é o tipo mais comum de eVar, e a configuração padrão. Funciona de maneira semelhante a outras variáveis, nas quais o valor é uma sequência de caracteres de texto estático. Se você estiver acompanhando coisas, como campanhas internas ou palavras-chave de pesquisa interna, essa é a configuração recomendada.</li><li>**[!UICONTROL Contador]**: conta o número de vezes que uma ação ocorre antes do evento bem-sucedido. Por exemplo, se você usa uma eVar para rastrear pesquisas internas no site, configure esse valor como [!UICONTROL sequência de caracteres de texto] para rastrear o uso de termos de pesquisa. Configure esse valor como [!UICONTROL contador] para contar o número de pesquisas efetuadas, independentemente dos temos de pesquisa usados. Por exemplo, você pode usar uma eVar contador para controlar o total de vezes que alguém usou sua pesquisa interna antes de fazer uma compra.</li></ul> |
| [!UICONTROL Alocação] | Determina como o Analytics atribuirá crédito por um evento bem-sucedido se uma variável receber vários valores antes do evento. Os valores compatíveis incluem:<ul><li>**[!UICONTROL Mais recente]**: o último valor de eVar sempre recebe crédito por eventos bem-sucedidos até que esse eVar expire.</li><li>**[!UICONTROL Valor original]**: a primeira eVar sempre recebe crédito por eventos bem-sucedidos até que essa eVar expire.</li><li>**[!UICONTROL Linear]**: aloca eventos bem-sucedidos igualmente entre todos os valores de eVar. Como a alocação Linear distribui com precisão os valores somente em uma visita, use essa alocação com Visita como expiração de eVar.</li></ul> **Observação**: A alternância da alocação de ou para Linear impede que os dados históricos sejam exibidos. A mistura tipos de alocação na interface de relatório pode resultar em dados informados incorretamente em relatórios. Por exemplo, a alocação Linear pode dividir a receita entre vários valores diferentes de eVar. Depois de voltar para a alocação Mais recente, 100% dessa receita será associada ao valor único mais recente. Essa associação pode levar os usuários a conclusões incorretas.<br><br>Para evitar a probabilidade de confusão nos relatórios, o Adobe Analytics não disponibiliza os dados históricos para a interface. Podem ser exibidos se decidir alterar a eVar de volta para a configuração de alocação inicial, embora não seja recomendável alterar as configurações de alocação de eVar simplesmente para acessar os dados históricos. A Adobe recomenda usar uma nova eVar quando há preferência por novas configurações de alocação de dados registradas, em vez de alterar as configurações de alocação em uma eVar que já tem uma quantidade significativa de dados históricos acumulada. |
| [!UICONTROL Expirar após] | Especifica o período ou evento após o qual o valor da eVar expira (não recebe mais crédito por eventos bem-sucedidos). Se um evento bem-sucedido ocorrer após a expiração da eVar, o valor Nenhum receberá o crédito pelo evento (nenhuma eVar estava ativa).  Se você selecionar um evento como valor de expiração, a variável expirará somente se o evento ocorrer. Se o evento não ocorrer, a variável nunca expirará.  As opções de expiração disponíveis podem ser classificadas em quatro categorias principais:<ul><li>**Em uma exibição da página ou em nível de visita.** Os eventos de conversão além da exibição de página ou da visita não estão associados à eVar.</li><li>**Com base em um período de tempo, como dia, semana, mês ou ano.** Os eventos de conversão além do período especificado não estão associados à eVar. O período de expiração começa quando a variável é definida. As eVars expiram com base no tempo de definição, com precisão de segundos (minutos, hora, dia, mês etc): <ul><li>MINUTO=60 segundos</li><li>HORA=3600 segundos (60 minutos)</li><li>DIA=86400 segundos (24 horas)</li><li>SEMANA=604800 segundos (7 dias)</li><li>MÊS=2678400 segundos (31 dias)</li><li>TRIMESTRE=8035200 segundos (93 dias - 3 meses de 31 dias)</li><li>ANO=31536000 segundos (365 dias)</li><br>Se uma visita iniciar às 7h de uma segunda-feira e uma eVar estiver definida na visita às 7h15, a expiração ocorre da seguinte forma:<li>Expiração do dia: eVar expira às 7h15 da terça-feira.</li><li>Expiração semanal: eVar expira na segunda-feira seguinte, às 7h15.</li><li>Expiração mensal: eVar expira 31 dias após a segunda-feira, às 7h15.</li></ul><li>**Eventos de conversão específicos.** Quaisquer eventos de conversão ativados depois de um evento específico designado estão associados à eVar.</li><li>**Nunca.** Desde que o cookie visitorID esteja intacto, qualquer período pode ser transcorrido entre o eVar e o evento.</li></ul> |
| [!UICONTROL Status]   (somente eVar) | Define o status [!UICONTROL eVar]:<ul><li>**Desativado**[!UICONTROL : desativa a eVar]. Remove o [!UICONTROL eVar] da lista de variáveis de conversão.</li><li>**Sem sub-relações**: Impede que você decomponha a   eVarby em uma dimensão.</li><li>**Sub-relações** básicas: Permite detalhar um eVar por qualquer dimensão completa (por exemplo, Produtos ou Campanhas).</li></ul> |
| [!UICONTROL Redefinir] | Redefine qualquer valor existente no eVar. Use esta configuração ao reaproveitar uma eVar, de modo a não confundir um valor antigo usando-o em um novo relatório. A redefinição não apaga dados históricos. |
| [!UICONTROL Merchandising]  (somente eVar) | As variáveis de merchandising podem seguir uma das duas sintaxes:<ul><li>**[!UICONTROL Sintaxe de produtos]**: associa o valor de eVar a um produto. **Observação**: Se  [!UICONTROL Sintaxe de produtos ] estiver selecionada, a seção   Evento de vinculação de merchandising é desativada e não poderá ser selecionada para edição. Para essa sintaxe, [!UICONTROL Eventos de vinculação] não são aplicáveis.</li><li>**[!UICONTROL Sintaxe de variável de conversão]**: associa a eVar a um produto somente se um evento compulsório ocorrer. Nesse caso, selecione os eventos que atuam como [!UICONTROL Binding Events].  Alterar essa configuração sem atualizar seu código JavaScript de acordo resultará na perda de dados. Ver [Variáveis de merchandising](https://experienceleague.adobe.com/docs/analytics/components/variables/merchandising-variables/var-merchandising.html).</li></ul> |
| [!UICONTROL Evento compulsório de merchandising] (somente eVar) | Se Merchandising estiver definido como [!UICONTROL Sintaxe de variável de conversão], os eventos selecionados vincularão o valor de eVar atual a um produto. Para usar um [!UICONTROL Evento de vinculação], defina [!UICONTROL Alocação] como [!UICONTROL Mais recente]. Se [!UICONTROL Alocação] estiver definido como [!UICONTROL Valor Original], a primeira vinculação de produto de eVar permanecerá até que o eVar expire. Vários eventos podem ser selecionados ao pressionar e segurar ctrl (Windows) ou cmd (Mac) e clicar em vários itens na lista. Você pode selecionar um evento somente quando [!UICONTROL Sintaxe de variável de conversão] for selecionada. |

**Expiração**

As `eVars` expiram depois de um período definido por você. Depois que a eVar expira, ela não recebe mais crédito por eventos bem-sucedidos. As eVars também podem ser configuradas para expirar em eventos bem-sucedidos. Por exemplo, se você tiver uma promoção interna que expira no fim de uma visita, a promoção interna recebe crédito apenas pelas compras ou registros ocorridos durante a visita em que foi ativada.

Existem duas formas de determinar a expiração de uma eVar:

* É possível definir a eVar para expirar depois de um período ou evento especificado.
* É possível forçar a expiração de uma eVar ao redefini-la, o que é útil quando se estabelece um novo objetivo para uma variável.

Por exemplo, se você alterar a expiração de uma eVar de 30 para 90 dias, os valores de eVar coletados continuarão a persistir pela duração do novo conjunto de expiração (nesse caso, 90 dias). O sistema simplesmente verifica a configuração de expiração atual e o último carimbo de data e hora definido do valor da eVar coletado para determinar a expiração. Somente a opção **[!UICONTROL Redefinir]** expira os valores e o faz imediatamente.

Outro exemplo: se uma eVar for usada em maio para refletir promoções internas e expirar depois de 21 dias, e em junho ela for usada para capturar as palavras-chaves da pesquisa interna, no dia 1º de junho você deverá forçar a expiração da variável ou redefini-la. Com isso, você ajudará a manter os valores da promoção interna fora dos relatórios de junho.

**Uso de maiúsculas e minúsculas**

As eVars não diferenciam maiúsculas de minúsculas. As letras maiúsculas ou minúsculas usadas no relatório se baseiam no primeiro valor registrado pelo sistema de back-end. Esse valor pode ser a primeira instância jamais vista ou variar em um período de tempo (por exemplo, mensal), dependendo da variedade e da quantidade de dados associados ao conjunto de relatórios.

**Contadores**

Embora as eVars sejam usadas com mais frequência para reter valores da string, elas também podem ser configuradas para atuar como contadores. As eVars são úteis como contadores quando você está tentando contar o número de ações adotadas por um usuário antes de um evento. Por exemplo, você pode usar uma eVar para capturar o número de pesquisas internas antes da compra. Sempre que um visitante pesquisar, a eVar deverá conter um valor de &quot;+1&quot;. Se um visitante pesquisar quatro vezes antes de uma compra, você verá uma instância para cada contagem total: 1,00, 2,00, 3,00 e 4,00. No entanto, somente a 4,00 receberá crédito pelo evento da compra (Pedidos e métricas de receita). Somente números positivos são permitidos como valores de um contador eVar.
