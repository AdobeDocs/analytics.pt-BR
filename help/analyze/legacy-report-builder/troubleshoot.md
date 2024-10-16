---
description: Saiba como otimizar o delivery de Report Builder e uma lista de mensagens de erro que podem ocorrer.
title: Resolução de problemas e práticas recomendadas do Report Builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
feature: Report Builder
role: User, Admin
exl-id: 41a640ce-2316-439b-b3ba-f0bace9af268
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 85%

---

# Resolução de problemas e práticas recomendadas do Report Builder

Este artigo descreve a solução de problemas e as práticas recomendadas que você pode usar para otimizar o Report Builder. Ele também inclui uma lista de mensagens de erro que podem ser exibidas.

## Usuários do Report Builder 5.0 e abertura das pastas de trabalho 5.1 {#section_C29898775999453FABB5FB0E098415C8}

A Adobe alterou o separador entre as dimensões e as classificações de um caractere sublinhado (_) para ||. Essa mudança tem implicações de compatibilidade para um usuário do Report Builder 5.0 que abre uma pasta de trabalho do Report Builder v5.1 com solicitações de classificação. Sempre que uma pasta de trabalho de uma versão anterior ao v5.1 é aberta, todas as solicitações de classificações serializadas são convertidas nesse formato.

Isso causa um problema de compatibilidade futura: depois de convertido em v5.1, se uma pasta de trabalho for compartilhada com um usuário no Report Builder v5.0, esse usuário não poderá reconhecer a solicitação de classificação (procura &quot;_&quot;, mas o v5.1 procura &quot;||&quot; serializado).

O problema ocorre ao abrir uma pasta de trabalho ARB v5.1 com a solicitação de classificação:

* Ao abrir uma pasta de trabalho, você receberá o seguinte aviso: &quot;Esta pasta de trabalho foi salva pela última vez com o Report Builder v5.1. Essa versão apresentou alguns recursos incompatíveis com a versão do Report Builder instalada no computador. É recomendado atualizar para a versão mais recente do Report Builder antes de atualizar esta pasta de trabalho&quot;.
* Se você clicar com o botão direito em uma solicitação de ARB com classificação, os menus de contexto do Report Builder (editar solicitação, adicionar solicitação dependente...) não aparecerão.
* Se você executar Atualizar tudo, ao clicar no terceiro botão, ou ao atualizar um conjunto de solicitações do formulário do Gerenciador de solicitação, a solicitação de classificação será executada sem erro. No entanto, os valores de classificação não serão expressos.
* Você ainda pode editar a solicitação ao abrir o Gerenciador de solicitações, de linha em linha, até atingir a solicitação apropriada.
* Se você editar a solicitação, não alterar os parâmetros e, em seguida, clicar em Concluir, a resposta será expressa apropriadamente. A edição da solicitação soluciona o problema à medida que os parâmetros do Layout de resposta são serializados novamente. Portanto, há uma solução, embora seja demorada.

## Problemas de autenticação no Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

O Report Builder exige autenticação para criar solicitações de dados dos seus conjuntos de relatórios. Às vezes, ocorrem questões ao fazer logon no Report Builder, dependendo de suas configurações no [!DNL Analytics] ou em sua rede.

* **Empresa de Logon Inválida**: este erro geralmente ocorre quando a empresa de logon é inserida incorretamente ou se houver problemas de atividade de rede. Faça o seguinte:
   * Verifique a ortografia da empresa de logon para garantir que não haja erro de digitação ou de espaçamento.
   * Faça logon no Analytics com a mesma empresa de logon para garantir que esteja correto. Se não conseguir fazer logon com essas credenciais, entre em contato com um dos administradores do de sua organização para obter a empresa de logon correta.
* **Firewall**: o Report Builder usa as portas 80 e 443. Assegure que essas portas estejam permitidas no firewall de sua organização. Veja também os endereços IP internos do Adobe para outras exclusões de firewall.

## Recomendações para solicitações de otimização {#section_33EF919255BF46CD97105D8ACB43573F}

Os seguintes fatores podem aumentar a complexidade do pedido e resultar em um processamento mais lento.

* **Fatores que podem atrasar deliveries**: muitos marcadores, painéis e pastas de trabalho do Report Builder foram agendados em poucas horas. Considere também que muitas pastas de trabalho do Report Builder foram agendadas ao mesmo tempo. Quando isso ocorre, a fila de relatórios do API fica lotada.
* **Fatores que podem retardar o tempo de execução da pasta de trabalho**: aumento significativo nas classificações ou aumento do intervalo de datas da solicitação ao longo do tempo.
* **Causas que resultam na falha de entrega da pasta de trabalho**: fórmulas complexas do Excel em uma pasta de trabalho, particularmente as que envolvem data e hora.
* **Células retornando 0s (sem valores)**: um apóstrofo ou uma aspa simples no nome da planilha do Excel fará com que o Report Builder não retorne valores. (Esta é uma limitação do Microsoft Excel).
* **Desempenho de solicitação individual**: a velocidade de processamento pode ser afetada pelas seguintes configurações:

  | Configuração | Desempenho mais rápido | Desempenho mais devagar |
  |--- |--- |--- |
  | Análises e a ordem da análise | Poucas | Muitas |
  |  | Exemplo: se você analisar A por Z, o número de itens para A deve sempre ser menor que o número de itens para Z. Se for o contrário, o tempo de solicitação pode aumentar significativamente. |
  | Intervalo de datas | Intervalo pequeno | Intervalo grande |
  | Filtragem | Filtragem específica | Filtragem mais popular |
  | Granularidade | Agregado | Por hora<ul><li>Diariamente</li><li>Semanalmente</li><li>Mensalmente</li><li>Trimestralmente</li><li>Anualmente</li></ul> |
  | Número de entradas | Conjunto de dados pequeno | Conjunto de dados grande |

* **Horário de agendamento**: agendamento ordenado durante o período de 24 horas (consulte a tabela abaixo). Favoritos, painéis e pastas de trabalho do Report Builder já existentes que foram agendados muito próximos podem causar atrasos. Agende as solicitações maiores e mais complexas no início da manhã para permitir que o manual extraia e atualize para ocorrer durante o dia útil.

  | Período de agendamento | 1 h - 2 h | 2 h - 7 h | 7 h - 18 h | 18 h - Meia-noite |
  |--- |--- |--- |--- |--- |
  | Uso do Report Builder | Silencioso | Muito ocupado | Uso do lado do cliente.<br>Maiores volumes de usuários atualizando e solicitando para &quot;Enviar imediatamente&quot;.<br>Além disso, verifique se a fila da API é apagada ao programar tempo limite da pasta de trabalho. | Não ocupado |

* **Limites de tempo**: qualquer relatório agendado atinge o limite de tempo após quatro horas. O sistema tenta programar por mais três vezes, resultando em uma falha. (Geralmente, quanto maior o conjunto de dados, maior é o tempo para execução.) Estes podem ser vistos nos relatórios do [!DNL Analytics] e do Report Builder:

## Descrições de mensagem de erro de exemplo {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Esta seção inclui uma lista de exemplos de mensagens de erro que podem ocorrer quando você usa o Report Builder.

>[!NOTE]
>
>Este é um exemplo de mensagens de erro, não uma lista exaustiva. Para obter mais informações sobre como solucionar erros, contate o administrador.

* **Esse recurso pode ser aplicado somente a uma pasta de trabalho aberta.**: Se nenhuma pasta de trabalho (documentos de planilhas) estiver aberta no Excel e você clicar em um dos ícones na barra de ferramentas Report Builder, esta mensagem será exibida. Além disso, a barra de ferramentas fica desativada até que você abra uma planilha. No entanto, você pode clicar no ícone de Ajuda online enquanto a barra de ferramentas ainda está ativada, sem causar este erro.
* **Saia primeiro do [!UICONTROL Assistente de solicitações] antes de ativar o [!UICONTROL Gerenciador de solicitações].**: Embora o [!UICONTROL Gerenciador de solicitações] e o [!UICONTROL Assistente de solicitações] estejam vinculados funcionalmente, não é possível começar a trabalhar com o [!UICONTROL Gerenciador de solicitações] antes de concluir ou cancelar as ações iniciadas no [!UICONTROL Assistente de solicitações].
* **Não há solicitações associada a esse intervalo.**: Esta mensagem de erro ocorre se você clicar no botão [!UICONTROL Da planilha] no [!UICONTROL Gerenciador de solicitações] quando uma célula da planilha não contiver nenhuma solicitação. Para identificar quais células na planilha contêm solicitações, clique nas solicitações individuais listadas na tabela no [!UICONTROL Gerenciador de solicitações]. Se uma solicitação estiver associada a células, as células aparecerão realçadas quando a solicitação for selecionada na tabela.
* **O intervalo selecionado não é válido. Selecione outro intervalo.**: Se uma célula da planilha for selecionada e já houver uma solicitação mapeada para ela, este erro ocorrerá. Exclua a solicitação mapeada para as células ou escolha outro intervalo de células para mapear. Quando quiser excluir células, é importante localizar as que contenham solicitações e excluir as solicitações antes de excluir as células (removendo linhas ou colunas).
* **Saia da célula do Excel onde está o foco antes de usar esse recurso.**: Caso esteja no *modo de edição* em uma célula do Excel e clique em um dos ícones do Report Builder, esta mensagem de erro será exibida. O modo de edição em uma célula do Excel significa que a célula está selecionada e o cursor aparece dentro dela. Você também está no modo de edição em uma célula do Excel quando digita diretamente na barra de [!UICONTROL Fórmula] ou na [!UICONTROL Caixa de nome] na parte superior do Excel.
* **O intervalo selecionado faz interseção com o intervalo de outra solicitação. Altere sua seleção.**: Se você já tiver mapeado um conjunto de células para a planilha, este erro será exibido.
* **Reparos na pasta de trabalho (Registros removidos: Fórmula de /xl/calcChain.xml parte)**: às vezes, as fórmulas de uma pasta de trabalho são corrompidas ao salvar ou transferir. Quando o arquivo é aberto, o Excel tenta executar essas fórmulas e falha. Você pode resolver esse problema removendo `calcChain.xml` da planilha, forçando o Excel a atualizar seus cálculos de fórmula.
   1. Renomeie a extensão de arquivo da pasta de trabalho de `.xlsx` para `.zip`.
   2. Descompacte o conteúdo e abra a pasta `/xl/`.
   3. Excluir `calcChain.xml`.
   4. Volte a compactar o conteúdo e altere a extensão de arquivo para `.xlsx`.
   5. Abra a pasta de trabalho no Excel e atualize todas as solicitações do Report Builder.
* **As células do Excel associadas aos filtros de entrada ou ao intervalo de saída podem ter sido excluídas**: o Report Builder usa Nomes do Excel para anexar solicitações de dados a células. Se você excluir Nomes do Excel do Gerenciador de nomes, esse erro poderá ser exibido. As solicitações não poderão ser recuperadas se os Nomes do Excel forem excluídos. Se a pasta de trabalho foi agendada, você pode baixar uma cópia do Gerenciador de programação ou abrir cópias entregues anteriormente da pasta de trabalho.
