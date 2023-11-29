---
description: As configurações de coluna permitem que você configure a formatação da coluna; alguns elementos podem ser condicionais.
title: Configurações de coluna
uuid: 151d66da-04f7-4d0f-985c-4fdd92bc1308
feature: Freeform Tables
role: User, Admin
exl-id: 82034838-b015-4ca2-adb6-736f20a478d8
source-git-commit: 984406d00e5a5ae966fff60ec9fcfcb000958696
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 100%

---

# [!UICONTROL Configurações de coluna]

As [!UICONTROL Configurações de coluna] permitem que você configure a formatação da coluna; alguns elementos podem ser condicionais.

## Editar [!UICONTROL Configurações de coluna] {#edit-column-settings}

É possível editar as configurações de coluna para uma coluna individual ou para várias colunas simultaneamente.

1. No Analysis Workspace, arraste uma Tabela de forma livre para o seu projeto.

1. (Condicional) Para editar várias colunas simultaneamente, selecione cada coluna que deseja editar enquanto mantém a tecla Shift pressionada.

1. Passe o mouse sobre a coluna que deseja editar, em seguida, selecione o ícone de engrenagem.

   Se você selecionou várias colunas, clique no ícone de engrenagem para qualquer uma das colunas selecionadas. Todas as alterações feitas serão aplicadas a todas as colunas selecionadas.

   ![](assets/column_settings.png)

1. Continue com [Configurações de coluna](#column-settings).

## Configurações de coluna

Você pode atualizar as seguintes configurações de coluna para tabelas individuais no Analysis Workspace, conforme descrito em [Editar configurações de coluna](#edit-uicontrol-column-settings).

Algumas dessas mesmas configurações também podem ser gerenciadas para todos os novos projetos criados no Analysis Workspace, conforme descrito em [Preferências do usuário](/help/analyze/analysis-workspace/user-preferences.md)

| Elemento | Descrição |
| --- | --- |
| **Total de células** |  |
| Exibir totais | Normalmente esse total é uma parte do [!UICONTROL Total geral] ou igual a ele. Ele reflete todos os filtros de tabela aplicados na tabela de forma livre, incluindo a opção [!UICONTROL Não incluir]. |
| Exibir total geral | Esse total representa todas as ocorrências que foram coletadas, às vezes chamadas de &quot;total do conjunto de relatórios&quot;. Quando um segmento é aplicado no nível do painel ou na tabela de forma livre, esse total é ajustado para refletir todas as ocorrências que correspondem aos critérios do segmento. O total geral não é compatível com tabelas e detalhamentos com [linhas estáticas](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| **Células da tabela** |   |
| Número | Determina se uma célula exibe ou oculta o valor numérico para a métrica. Por exemplo, se a métrica for Exibições de página, o valor numérico será o número de exibições de página para o item da linha. |
| Porcentagem | Determina se uma célula exibe ou oculta o valor percentual para a métrica. Por exemplo, se a métrica for Exibições de página, o valor percentual será o número de exibições de página para o item da linha dividido pelo total de exibições de página para a coluna.  Observação: podemos apresentar percentuais maiores que 100%, para maior precisão. Também fixamos o limite superior como 1.000% para garantir que as colunas possam aumentar em largura. |
| Anomalias | Determina se a detecção de anomalias é executada nos valores desta coluna. Para obter mais informações, consulte [Exibir anomalias no Analysis Workspace](/help/analyze/analysis-workspace/c-anomaly-detection/view-anomalies.md). |
| Quebrar linha do texto do cabeçalho | Permite quebrar o texto de cabeçalho em tabelas de forma livre para tornar os cabeçalhos mais legíveis e as tabelas mais compartilháveis. Essa opção é útil para renderização de .pdf e para métricas com nomes compridos. Ativado por padrão. |
| Interpretar o zero como valor inexistente | Para células com valor 0, determina se exibirá um 0 ou uma célula em branco. Isso é útil para observar dados diários de um mês que ainda não tenha terminado.  Em vez de mostrar 0 para as datas futuras, pode-se exibir células em branco. Essa configuração também aplica-se a gráficos (ou seja, eles não exibem uma linha ou uma barra com valores de 0 quando essa configuração estiver selecionada). |
| Histórico | Determina se uma célula exibe ou oculta todas as formatações de célula, incluindo o gráfico de barras e a formatação condicional. |
| Gráfico de barras | Exibe um gráfico de barras horizontal que representa o valor da célula relativo ao total da coluna. |
| Formatação condicional | Consulte a seção abaixo. |
| Visualização de célula de tabela | Mostra uma visualização de como cada célula é exibida com a aplicação das opções de formatação atuais selecionadas. |

## Formatação condicional {#conditional-formatting}

A formatação condicional aplica formatação a limites superiores, intermediários e inferiores que você pode definir. A aplicação de formatação condicional (cores, por exemplo) nas tabelas de forma livre também é ativada automaticamente nos detalhamentos, a menos que sejam selecionados limites “Personalizados”.

![](assets/conditional-formatting.png)

| Elemento | Descrição |
| --- | --- |
| Formatação condicional | Aplica um conjunto de cores pré-configurado de sua escolha às células. Dependendo de qual dos 4 esquemas de cores disponíveis você selecionar, cores diferentes serão atribuídas a valores altos, valores médios e valores baixos. <br> Substituir uma dimensão na tabela redefine os limites da formatação condicional. Substituir uma métrica recalcula os limites da coluna (na qual haja uma métrica no eixo X e uma dimensão no eixo Y). |
| Usar limites de porcentagem | Alterar para que o intervalo limite se baseie em percentagens em vez de valores absolutos. Isso funciona com métricas exclusivamente baseadas em porcentagem (como a Taxa de retorno), além de métricas que possuem uma contagem e uma porcentagem (como Exibições de página). |
| Gerado automaticamente | Calcular limites superior/médio/inferior automaticamente de acordo com os dados. O limite superior é o valor mais alto na coluna. O limite inferior é o menor valor e o ponto intermediário é a média entre os limites superior e inferior. |
| Personalizado | Atribuir limites superior/médio/inferior manualmente. Isso oferece a flexibilidade de determinar quando o valor de uma coluna se torna bom, médio ou ruim. |
| Paleta de formatação condicional | Escolha qual dos 4 esquemas de cores disponíveis usar para a formatação condicional. |

## Usar modelo de atribuição não-padrão {#attribution}

O Analysis Workspace aceita a [atribuição](/help/analyze/analysis-workspace/attribution/overview.md) para quase qualquer métrica.

1. Clique no ícone de Configurações (engrenagem) em uma coluna de Tabela de forma livre.

   ![Caixa de seleção Atribuição](assets/attribution-checkbox.png)

1. Em **[!UICONTROL Configurações de dados]**, marque a opção **[!UICONTROL Usar modelo de atribuição não padrão]**. Para obter mais informações sobre os diferentes modelos de atribuição, consulte [Modelos de atribuição](/help/analyze/analysis-workspace/attribution/models.md).

   ![Selecionar modelo de atribuição](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [Gerenciar fontes de dados](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)

## Colunas dinâmicas

Veja um vídeo sobre como usar colunas dinâmicas no Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23138/?quality=12)
