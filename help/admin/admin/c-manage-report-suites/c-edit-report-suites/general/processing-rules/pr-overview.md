---
description: O processamento de regras simplifica a coleta de dados e o gerenciamento do conteúdo conforme é enviado para os relatórios.
subtopic: Processing rules
title: Visão geral das regras de processamento
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 3%

---

# Visão geral das regras de processamento

As regras de processamento permitem modificar como os dados são coletados antes de serem gravados em um conjunto de relatórios.

**[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de Relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de Processamento]**

>[!WARNING]
>
>As regras de processamento afetam diretamente a coleta de dados e podem causar perda de dados se usadas incorretamente. Sempre teste as regras de processamento em um conjunto de relatórios de desenvolvimento antes de ativá-las em um conjunto de relatórios de produção para atenuar problemas de qualidade de dados.

Os dois principais casos de uso das regras de processamento incluem:

* **Usar o fluxo de trabalho de implementação da variável de dados de contexto**: em vez de configurar diretamente as variáveis na implementação, você pode usar [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) para definir pares de chave/valor. Por exemplo, em vez de definir:

  ```js
  s.eVar1 = "Robert Munch";
  s.eVar2 = "Books";
  s.eVar3 = "Youth";
  ```

  Em vez disso, você pode definir:

  ```js
  s.contextData['author'] = "Robert Munch";
  s.contextData['section'] = "Books";
  s.contextData['genre'] = "Youth";
  ```

  Em seguida, é possível mapear as variáveis de dados de contexto para as dimensões e métricas desejadas na interface do usuário do Analytics.

  Ao se comunicar com desenvolvedores em sua organização para implementar o Analytics em uma propriedade, o uso de variáveis de dados de contexto simplifica o processo de comunicação. Os desenvolvedores podem simplesmente implementar cada par de chave/valor uma vez e, como administrador do Analytics, você pode garantir que os dados o tornem a variável de implementação correta.

* **Modificar os dados conforme são coletados**: este caso de uso tem uma grande variedade de aplicativos, como correções temporárias na qualidade dos dados ou para ajudar a preencher lacunas de implementação. Consulte [Casos de uso de regras de processamento](pr-use-cases.md) para obter mais informações e exemplos específicos.

## Permissões

Os administradores de produtos têm acesso às regras de processamento por padrão. Você pode conceder acesso às regras de processamento a não administradores, incluindo-os em um perfil de produto que inclua o item de permissão **[!UICONTROL Regras de processamento]**. Consulte [Permissões de perfil de produto para Ferramentas de Conjunto de relatórios](/help/admin/admin-console/permissions/report-suite-tools.md) para obter mais informações.

## Considerações ao criar ou editar regras de processamento

Ao criar ou editar regras de processamento, considere o seguinte:

* **Possíveis valores vazios**: ao criar uma regra, considere os casos em que o valor de substituição está vazio. Por exemplo, se você tiver uma regra que substitua eVar1 pela eVar2 e eVar2 estiver vazia, ambas as variáveis ficarão em branco. A Adobe recomenda adicionar uma condição que verifique um valor variável antes de usá-lo para substituir outro valor.
* **Aplicar imediatamente ao salvar**: as regras de processamento se aplicam aos dados coletados no momento em que você os salva. Eles não se aplicam retroativamente a dados que já foram coletados.
* **Ordem de processamento dentro das regras**: se você tiver várias regras de processamento, a ordem em que elas são executadas será importante. Certifique-se de que, se você usar uma determinada variável em várias regras, elas serão executadas na ordem correta. Se você substituir eVar3 na regra 1, esse valor original de eVar3 não estará disponível em nenhuma regra subsequente.
* **Ordem de processamento no pipeline de coleta de dados**: consulte [Ordem de processamento dos dados no Adobe Analytics](/help/technotes/processing-order.md) para saber onde as regras de processamento se aplicam ao pipeline de coleta de dados geral.
* **Codificação**: use a codificação UTF-8 em quase todos os casos.
* **Diferenciação de maiúsculas e minúsculas**: as comparações de cadeias de caracteres nas regras de processamento não diferenciam maiúsculas de minúsculas. Os valores de sequência usados para substituir valores usam as mesmas regras que preenchem diretamente a variável.
* **Conjunto de relatórios único**: quando você edita as regras de processamento, elas se aplicam a apenas um conjunto de relatórios. A seleção de vários conjuntos de relatórios no Gerenciador de conjunto de relatórios força você a selecionar um único conjunto de relatórios. Depois de criar ou editar as regras de processamento desejadas, você pode [copiar essas regras para outros conjuntos de relatórios](pr-copy.md).
* **Sem exclusão de dados**: a exclusão de dados não é um recurso pretendido das regras de processamento. Considere usar [`abort`](/help/implement/vars/config-vars/abort.md) no nível de coleta de dados ou use [regras VISTA](/help/technotes/vista.md) após a coleta de dados.
* **Variáveis disponíveis**: nem todas as dimensões e métricas estão disponíveis nas regras de processamento. Consulte [Dimensões e métricas disponíveis para as regras de processamento](pr-variables.md) para obter a lista completa do que é compatível.
* **Número de regras permitidas**: cada conjunto de relatórios pode conter até 150 regras. Cada regra pode conter até 30 condições.

>[!MORELIKETHIS]
>
>![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mapear variáveis de dados de contexto em props e eVars com regras de processamento](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/implementation/implementation-basics/map-contextdata-variables-into-props-and-evars-with-processing-rules){target="_blank"}
