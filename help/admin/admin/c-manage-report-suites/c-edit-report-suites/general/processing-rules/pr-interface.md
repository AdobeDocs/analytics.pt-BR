---
title: Interface de regras de processamento
description: Navegue pela interface para criar, editar ou excluir regras de processamento.
feature: Processing Rules
role: Admin
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Interface de regras de processamento

A interface de regras de processamento permite criar, editar ou excluir regras de processamento.

**[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de Relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de Processamento]**

>[!WARNING]
>
>As regras de processamento afetam diretamente a coleta de dados e podem causar perda de dados se usadas incorretamente. Sempre teste as regras de processamento em um conjunto de relatórios de desenvolvimento antes de ativá-las em um conjunto de relatórios de produção para atenuar problemas de qualidade de dados.

## Estrutura global

Essa interface contém dois componentes principais:

* **[!UICONTROL Ordem de processamento]**: as regras são executadas exatamente na ordem especificada, iniciando na regra 1. Cada ocorrência passa por cada regra; não há condições de saída antecipada. Verifique se as condições de cada regra de processamento acomodam cada ocorrência enviada para o conjunto de relatórios.
* **[!UICONTROL Conjuntos de regras]**: as definições de cada uma das regras de processamento.

É possível ter até 150 regras de processamento e até 30 condições por regra de processamento. Não há um limite razoável para o número de ações por regra de processamento.

## Estrutura do conjunto de regras

Cada regra de processamento contém as seguintes seções:

* **Título da regra**: o rótulo da regra. Ela não afeta a lógica da regra de processamento, mas é importante para ajudar a rastrear o que a regra faz.
* **Condição**: exibida como o texto, &quot;[!UICONTROL Se qualquer/todos os itens a seguir forem verdadeiros]&quot;. Se você não incluir uma condição, a regra sempre será executada em cada ocorrência.
* **Ação**: se nenhuma condição existir, o texto será mostrado como, &quot;[!UICONTROL Sempre executar]&quot;. Se existir uma condição, o texto será mostrado como &quot;[!UICONTROL Faça o seguinte]&quot;. Se a condição acima for avaliada como `true`, cada ação listada nesta seção possivelmente será executada. Além da condição de uma regra, você pode _também_ anexar condições a ações individuais. As seguintes ações estão disponíveis:
   * **[!UICONTROL Substituir valor de]**: substitui a variável desejada por outra variável, um valor estático ou um valor concatenado.
   * **[!UICONTROL Excluir valor de]**: exclui o valor de variável desejado para essa ocorrência.
   * **[!UICONTROL Definir evento]**: aciona o evento desejado. Normalmente, você define eventos com um valor personalizado de `1`; a definição de eventos com valores diferentes de `1` ou até mesmo a definição deles como valores definidos em variáveis de dados de contexto também é permitida.
* **Ação de outra forma**: se existir uma condição, esta seção aparecerá como, &quot;[!UICONTROL Caso contrário, faça o seguinte]&quot;. Se a condição acima for avaliada como `false`, cada ação listada nesta seção possivelmente será executada. Esta seção segue as mesmas ações de regra descritas acima, incluindo a capacidade de substituir valores, excluir valores e definir eventos.
* **Motivo**: registre quem solicitou a regra e do que ela depende. Ela não afeta a lógica da regra de processamento, mas é importante para ajudar a acompanhar por que a regra existe.

Consulte [Dimensões e métricas disponíveis para regras de processamento](pr-variables.md) para obter uma lista abrangente de variáveis que podem ser usadas nesta interface.

* Qualquer variável que permita &quot;Ler&quot; pode ser usada em uma condição.
* Qualquer variável que permita &quot;Gravar&quot; pode ser usada em uma ação.
