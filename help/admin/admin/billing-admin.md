---
description: A página Faturamento permite acessar informações de faturamento, incluindo detalhes de tráfego para cada conjunto de relatórios. Somente um administrador autorizado tem acesso a esta página.
title: Faturamento
topic: Admin tools
uuid: ad6ee1c4-d317-4320-a36e-ee966c8f145e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Faturamento

A página Faturamento permite acessar informações de faturamento, incluindo detalhes de tráfego para cada conjunto de relatórios. Somente um administrador autorizado tem acesso a esta página.

>[!NOTE] Se o acesso à guia de faturamento estiver desativado em sua empresa, entre em contato com o Gerente de conta.

Os dados de visão geral do tráfego da página de faturamento permitem correlacionar os dados de visualização da página em relatórios com chamadas faturáveis do servidor em sua fatura. A [!UICONTROL Billing] página permite fazer o seguinte:

* Auditar sua fatura.
* Analise os custos por conjunto de relatórios para alocações contábeis internas.
* Visualização na distribuição de chamadas de servidor primário e secundário.

A [!UICONTROL Billing] página organiza informações por mês.

To view monthly traffic overview data, locate the month where you want to view traffic data, then click **[!UICONTROL View]**.

O [!UICONTROL Monthly Invoice] relatório resultante inclui as seguintes informações:

| Coluna | Descrição |
|--- |--- |
| Conjunto de relatórios | O conjunto de relatórios envolvido na atividade de coleção de dados. |
| Localização | O centro de dados que armazena os dados do conjunto de relatórios: San Jose (Califórnia), Dallas (Texas), Noroeste do Pacífico (EUA), Londres (Reino Unido) ou Cingapura. Na maioria dos casos, todos os conjuntos de relatórios de empresa estão localizados no mesmo data center. |
| Chamadas de servidor primário | Solicitações recebidas diretamente de navegadores de visitantes do site ou da API de inserção de dados. Inclui Ocorrências primárias (Visualizações de página), Eventos personalizados primários, Eventos de download primários e Eventos de saída primários. |
| Chamadas de servidor secundário | Cópias das Chamadas do servidor primárias criadas por marcas de vários conjuntos ou copiadas/movidas por uma regra VISTA.  Se uma chamada ao servidor secundário tiver sido movida (não copiada) para um report suite diferente por uma regra VISTA, a página Faturamento identificará essa transferência com um número negativo. Nesse caso, as chamadas secundárias acumuladas são deduzidas das Chamadas do servidor principal. |
| Total de chamadas ao servidor | O total combinado de chamadas aos servidores primário e secundário deste conjunto de relatórios no local determinado. |
| Exibições de página | Totais de exibição de página para cada conjunto de relatórios. É possível confirmar os valores de visualização de página em Métricas do site > Visualizações de página. |
| Downloads | Fazer download dos totais de cada conjunto de relatórios. É possível confirmar os valores de download em Conteúdo do site > Links > Downloads de arquivo. |
| Links personalizados | Totais de link personalizado para cada conjunto de relatórios. É possível confirmar os valores do link personalizado em Conteúdo do site > Links > Links personalizados. |
| Links de saída | Totais de link de saída para cada conjunto de relatórios. É possível confirmar os valores do link de saída em Conteúdo do site > Links > Links de saída. |

>[!NOTE] Para obter uma cópia funcional do [!UICONTROL Monthly Invoice] relatório, copie-o na área de transferência e cole-o em um programa de planilha, como o Microsoft Excel*.

## Data do relatório x data de processamento {#section_51A48C2F223F4904BE1407C13333C457}

Na interface do usuário do relatórios, os dados apresentados são sempre anexados à Data **do** Relatórios, que é o carimbo de data e hora anexado ao evento.

Por outro lado, o uso/cobrança sempre usa a Data **de** processamento ou quando os dados foram processados no sistema. Devido à latência básica, às importações de dados ou às diferenças de fuso horário do evento (tudo é processado no Horário do Pacífico), a Data do Relatórios e a Data de Processamento normalmente não correspondem completamente.
