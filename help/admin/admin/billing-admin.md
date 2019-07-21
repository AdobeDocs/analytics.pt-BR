---
description: A página Faturamento permite acessar informações de faturamento, inclusive detalhes de tráfego de cada conjunto de relatórios. Somente um administrador autorizado tem acesso a essa página.
seo-description: A página Faturamento permite acessar informações de faturamento, inclusive detalhes de tráfego de cada conjunto de relatórios. Somente um administrador autorizado tem acesso a essa página.
seo-title: Faturamento
solution: Analytics
title: Faturamento
topic: Ferramentas administrativas
uuid: ad 6 ee 1 c 4-d 317-4320-a 36 e-ee 966 c 8 f 145 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Faturamento

A página Faturamento permite acessar informações de faturamento, inclusive detalhes de tráfego de cada conjunto de relatórios. Somente um administrador autorizado tem acesso a essa página.

>[!NOTE]
>
>Se o acesso à guia de faturamento estiver desativado para sua empresa, entre em contato com seu Gerente de contas.

Os dados de visão geral do tráfego da página de faturamento permite correlacionar os dados de exibição da página nos relatórios com chamadas cobráveis do servidor em sua fatura. A página [!UICONTROL Faturamento] permite fazer o seguinte:

* Auditar sua fatura.
* Decompor os custos por conjunto de relatórios para alocações contábeis internas.
* Exibir a distribuição de chamadas aos servidores primário e secundário.

A página [!UICONTROL Faturamento] organiza informações por mês.

Para exibir dados mensais de visão geral do tráfego, localize o mês cujos dados de tráfego deseja exibir e clique em **[!UICONTROL Exibir]**.

O relatório [!UICONTROL Faturamento mensal] resultante inclui as seguintes informações:

| Coluna | Descrição |
|--- |--- |
| Conjunto de relatórios | O conjunto de relatórios envolvido na atividade de coleção de dados. |
| Localização | O data center que armazena os dados do conjunto de relatórios: San Jose (Califórnia), Dallas (Texas), Noroeste do Pacífico (EUA), Londres (Reino Unido) ou Cingapura. Na maior parte dos casos, todos os conjuntos de relatórios da empresa estão localizados no mesmo centro de dados. |
| Chamadas de servidor primário | Solicitações recebidas diretamente de navegadores dos visitantes ao site ou da API de inserção de dados. Inclui Ocorrências primárias (Visualizações de página), Eventos personalizados primários, Eventos de download primários e Eventos de saída primários. |
| Chamadas de servidor secundário | Cópias das Chamadas do servidor primárias criadas por marcas de vários conjuntos ou copiadas/movidas por uma regra VISTA.  Se uma chamada ao servidor secundário tiver sido movida (não copiada) para um report suite diferente por uma regra VISTA, a página Faturamento identificará essa transferência com um número negativo. Nesse caso, as chamadas secundárias acumuladas são deduzidas das Chamadas do servidor principal. |
| Total de chamadas ao servidor | O total combinado de chamadas aos servidores primário e secundário deste conjunto de relatórios no local determinado. |
| Exibições de página | Totais de exibição de página para cada conjunto de relatórios. É possível confirmar os valores de visualização de página em Métricas do site &gt; Visualizações de página. |
| Downloads | Fazer download dos totais de cada conjunto de relatórios. É possível confirmar os valores de download em Conteúdo do site &gt; Links &gt; Downloads de arquivo. |
| Links personalizados | Totais de link personalizado para cada conjunto de relatórios. É possível confirmar os valores do link personalizado em Conteúdo do site &gt; Links &gt; Links personalizados. |
| Links de saída | Totais de link de saída para cada conjunto de relatórios. É possível confirmar os valores do link de saída em Conteúdo do site &gt; Links &gt; Links de saída. |

>[!NOTE]
>
>To obtain a working copy of the [!UICONTROL Monthly Invoice] report, copy it onto your clipboard, then paste it into a spreadsheet program such as Microsoft Excel*.

## Data do relatório x data de processamento {#section_51A48C2F223F4904BE1407C13333C457}

Na interface de relatório do usuário, os dados apresentados estão sempre vinculados à **Data de relatório**, que é o carimbo de data e hora vinculado ao evento.

Por outro lado, Utilização/Cobrança sempre utiliza a **Data de processamento**, ou quando os dados foram processados no sistema. Devido à latência básica, às importações de dados ou diferenças de fuso horário do evento (tudo é processado de acordo com a Hora do Pacífico), os Dados de relatório e a Data de processamento não correspondem por completo.
