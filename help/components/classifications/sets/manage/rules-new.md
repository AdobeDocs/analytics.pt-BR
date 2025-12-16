---
title: Regras de conjuntos de classificações
description: Saiba como usar regras de conjuntos de classificação para definir regras para dados de classificação.
feature: Classifications
hide: true
hidefromtoc: true
source-git-commit: 0f80bb314c8e041a98af26734d56ab364c23a49b
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 10%

---


# Regras de conjuntos de classificação

As regras são usadas para oferecer suporte a classificações automáticas em cenários nos quais a dimensão principal é alterada constantemente. A atualização de classificações por meio de upload ou automação torna-se um processo complicado ou deixa de ser uma classificação adequada para novos valores de dimensão. Por exemplo, campanhas internas, códigos de rastreamento ou SKUs de produtos. A dimensão deve conter valores que permitam aplicar uma ou mais regras para que você possa derivar dados de classificação dos valores.

As regras são definidas no contexto de um conjunto de classificações. Esse contexto implica que as regras são aplicadas (quando ativadas) a todos os conjuntos de relatórios e combinações de dimensões principais que estão inscritos no conjunto de classificações. Essa implementação é um pouco diferente de como o construtor de regras de classificação herdado funciona. No Construtor de regras de classificação, defina uma ou mais regras como parte de um conjunto de regras separadamente e associe o conjunto de regras a um ou mais conjuntos de relatórios. Na nova interface, as regras no conjunto de classificações também são chamadas de conjunto de regras. No entanto, os conjuntos de regras são definidos na mesma interface em que você configura outros atributos do conjunto de classificações.


Para definir um conjunto de regras para um conjunto de classificações:

1. Selecione **[!UICONTROL Componentes]** na barra de menu superior do Adobe Analytics e selecione **[!UICONTROL Conjuntos de classificações]**.
1. Em **[!UICONTROL Conjuntos de classificações]**, selecione a guia **[!UICONTROL Conjuntos de classificações]**.
1. No gerenciador **[!UICONTROL Conjuntos de classificações]**, selecione o conjunto de classificações para o qual deseja definir as regras.
1. Na caixa de diálogo **[!UICONTROL Conjunto de classificações: _nome do conjunto de classificações_]**, selecione a guia **[!UICONTROL Regras]**.

   * Se você acessar a interface **[!UICONTROL Regras]** pela primeira vez para um conjunto de classificação ou decidir até o momento continuar a usar a interface herdada do construtor de regras, será exibida uma caixa de diálogo que permite selecionar como começar.

     ![Migração de regras](assets/rules-migration.png)

     As opções são:

      * **Migrar regras existentes**. Importe as regras de classificação atuais e continue a trabalhar com essas regras na nova interface. As regras existentes são preservadas e convertidas no novo formato.
         * Selecione **[!UICONTROL Migrar regras]** para continuar.
         * Na caixa de diálogo **[!UICONTROL Confirmar migração]**, leia as implicações da migração.
            * Selecione **[!UICONTROL Migrar regras]** para confirmar a migração. Após a conclusão da migração, use a [Interface do conjunto de regras](#rule-set-interface) para criar novas regras e editar as regras migradas existentes.
            * Selecione **[!UICONTROL Cancelar]** para cancelar a migração

      * **Iniciar novo**. Crie novas regras de classificação do zero usando o novo construtor de regras. Selecione essa opção se desejar reprojetar a lógica de classificação ou começar a usar novas regras de classificação.
         * Selecione **[!UICONTROL Criar novas regras]** para continuar.
         * Na caixa de diálogo **[!UICONTROL Confirmar reinício]**, leia as implicações de um novo início.
            * Selecione **[!UICONTROL Iniciar novo]** para confirmar uma nova inicialização e descartar todas as regras existentes. Use a [Interface do conjunto de regras](#rule-set-interface) para criar novas regras.
            * Selecione **[!UICONTROL Cancelar]** para cancelar.


      * **Usar interface herdada**. Continue a usar a interface anterior do construtor de regras. Você pode migrar para a nova experiência a qualquer momento quando estiver pronto.
         * Selecione **[!UICONTROL Ir para a interface herdada]** para continuar. Você é direcionado para a interface herdada **[!UICONTROL Construtor de regras de classificação]**.

   * Se já tiver migrado regras ou criado novas regras para um conjunto de classificações, você acabará diretamente na interface do Conjunto de regras.



## Interface do conjunto de regras {#rule-set-interface}

>[!CONTEXTUALHELP]
>id="classificationsets_rules_samplekeys"
>title="Chaves de amostra"
>abstract="Digite ou cole as teclas de teste para testar o conjunto de regras. Cada linha é um valor principal separado. Selecione **[!UICONTROL Testar Conjunto de Regras]** para mostrar uma caixa de diálogo com os resultados."


Para criar ou editar regras, use a interface de conjunto de regras.

![Interface do conjunto de regras](assets/rulesets-ui.png)

| | Nome | Descrição |
|---|---|---|
| 1 | **[!UICONTROL Funções]** | Use a área **[!UICONTROL Funções]** para selecionar e arrastar e soltar suas funções no construtor de conjuntos de regras. |
| 2 | **Construtor de conjunto de regras** | Crie o conjunto de regras usando uma ou mais regras. Uma regra é a implementação de uma função e sempre associada a apenas uma função. Uma função pode ter vários operadores. Crie uma regra arrastando e soltando uma função no construtor de conjuntos de regras. O tipo de função define a interface da regra. <br/>Consulte a [Interface de regra](#rule-interface) para obter mais informações.<br/>É possível inserir funções em qualquer lugar, e as funções são executadas em sequência para determinar os valores finais das classificações.<br/>Use **[!UICONTROL Recolher tudo]** para recolher todas as regras e use **[!UICONTROL Expandir tudo]** para expandir todas as regras. |
| 3 | **[!UICONTROL Status]** | Mostrar o status e a última data de modificação do conjunto de regras. <br/>Selecione **[!UICONTROL Ativar]** para ativar o conjunto de regras. <br/>Selecione **[!UICONTROL Desativar]** para desativar o conjunto de regras. |
| 4 | **[!UICONTROL Pesquisa]** | Especifique a janela de retrospectiva para o conjunto de regras.<br/>Selecione uma opção (de 1 mês a 6 meses) no menu suspenso.<br/>Selecione **[!UICONTROL Executar pesquisa]** para executar uma pesquisa usando o período de pesquisa selecionado. |
| 5 | **[!UICONTROL Opções de teste]** | Use valores de dimensão de chave de amostra para testar as classificações: <ul><li>Adicione ou cole valores na área de texto **[!UICONTROL Chaves de amostra]**.<br/>Verifique **[!UICONTROL Lembrar chaves de exemplo]** para garantir que as chaves de exemplo persistam em diferentes usos da interface do conjunto de regras.</li><li>Selecione **[!UICONTROL Testar conjunto de regras]** para testar seu conjunto de regras.</li></ul> |


## Interface de regras

Cada regra individual é definida no conjunto de regras na interface Regra. A interface consiste nos seguintes elementos:

![Interface de regra](assets/rule-ui.png)

| | Descrição |
|---|---|
| 1 | O nome da função selecionada e a entrada inserida para a função. |
| 2 | A entrada da função selecionada. A entrada depende da função selecionada. Por exemplo, para a função **[!UICONTROL Expressão regular]**, a entrada é uma expressão regular. E para a função **[!UICONTROL Split]**, a entrada é um token. Insira a entrada apropriada para a função específica. Por exemplo, `^(.+)\:(.+)\:(.+)$` para uma expressão regular que identifica três classificações em um código de campanha interno. |
| 3 | Cada operação define uma classificação específica como um valor. <br/>Selecione uma classificação no menu suspenso **[!UICONTROL Definir Classificação]** e insira um valor para **[!UICONTROL a]**. <br/>Use ![CrossSize400](/help/assets/icons/CrossSize400.svg) para excluir uma operação da lista. |
| 4 | Selecione ![Adicionar](/help/assets/icons/Add.svg) **[!UICONTROL Adicionar operação]** para adicionar outra operação à função. |
| 5 | Selecione ![Divisa](/help/assets/icons2/ChevronDown.svg) para recolher a regra. Selecione ![ChevronLeft](/help/assets/icons/ChevronLeft.svg) para expandir a regra.<br/>Selecione ![CrossSize400](/help/assets/icons/CrossSize400.svg) para excluir a regra. |

## Referência da função

Para cada função compatível, encontre abaixo os detalhes sobre os casos de uso de entrada e de amostra necessários.


### Começa com...

Define uma classificação com base em um valor específico com o qual a dimensão principal começa.

+++ Detalhes 

#### Entrada necessária

Insira um valor para **[!UICONTROL Começa com]**. Por exemplo: `em`.

#### Caso de uso

Você deseja definir uma regra para atribuir `Email` como o valor para a classificação **[!UICONTROL Canal]** quando o valor da dimensão principal Campanha interna começar com `em` (por exemplo: `em:FY2025:Summer Sale`).

>[!BEGINTABS]

>[!TAB Regra]

![Regra - Inicia com](assets/rule-startswith.png)

>[!TAB Resultados de teste]

![Regra - Inicia Com Resultados De Teste](assets/rule-startswith-test.png)

>[!ENDTABS]

+++



### Termina com...

Define uma classificação com base em um valor específico com o qual a dimensão principal termina.

+++ Detalhes 

#### Entrada necessária

Insira um valor para **[!UICONTROL Termina com]**. Por exemplo: `2025`.

#### Caso de uso

Você deseja definir uma regra para atribuir `2025` como valor à classificação **[!UICONTROL Ano]** quando o valor da dimensão principal Campanha Interna contiver `2025` (por exemplo: `em:Summer Sale:FY2025`).

>[!BEGINTABS]

>[!TAB Regra]

![Regra - Termina com](assets/rule-endswith.png)

>[!TAB Resultados de teste]

![Regra - Termina Com Resultados De Teste](assets/rule-endswith-test.png)

>[!ENDTABS]

+++


### Contém...

Define uma classificação com base em um valor específico que a dimensão principal contém.

+++ Detalhes 

#### Entrada necessária

Digite um valor para **[!UICONTROL Contém]**. Por exemplo: `Winter`.

#### Caso de uso

Você deseja definir uma regra para atribuir `Winter Sale` como um valor à classificação **[!UICONTROL Type]** quando o valor da dimensão principal Campanha Interna contiver com `Winter` (por exemplo: `fb:Winter:FY2024`).


>[!BEGINTABS]

>[!TAB Regra]

![Regra - Contém](assets/rule-contains.png)

>[!TAB Resultados de teste]

![Regra - Contém Resultados](assets/rule-contains-test.png)

>[!ENDTABS]

+++


### Corresponde 

Define uma classificação com base em um valor específico que corresponde ao valor da dimensão principal.

+++ Detalhes 

#### Entrada necessária

Insira um valor para **[!UICONTROL Correspondências]**. Por exemplo: `em:Summer:2025`.

#### Caso de uso

Você deseja definir uma regra para atribuir `Email` como valor à classificação **[!UICONTROL Canal]**, `Summer Sale` como valor à classificação **[!UICONTROL Tipo]** e `2025` à classificação **[!UICONTROL Ano]**. Mas somente quando o valor da dimensão principal Campanha interna corresponde a `em:Summer:2025`.


>[!BEGINTABS]

>[!TAB Regra]

![Regra - Corresponde](assets/rule-matches.png)

>[!TAB Resultados de teste]

![Regra - Corresponde](assets/rule-matches-test.png)

>[!ENDTABS]

+++


### Expressão regular

Define uma ou mais classificações com base em uma expressão regular aplicada ao valor da dimensão principal.

+++ Detalhes 

#### Entrada necessária

Insira um valor para **[!UICONTROL Expressão regular]**. Por exemplo: `^(.+)\:(.+)\:FY(.+)$`.

#### Caso de uso

Você deseja definir uma regra para atribuir valores às classificações **[!UICONTROL Canal]**, **[!UICONTROL Tipo]** e **[!UICONTROL Ano]** aplicando a expressão regular `^(.+)\:(.+)\:FY(.+)$` e usando grupos de correspondência (`$1`, `$2` e `$3`) aos valores da dimensão principal Campanha Interna.

>[!BEGINTABS]

>[!TAB Regra]

![Regra - Expressão regular](assets/rule-regex.png)

>[!TAB Resultados de teste]

![Regra - Resultados de teste de expressão regular](assets/rule-regex-test.png)

>[!ENDTABS]

+++


### Dividir

Divide o valor da dimensão principal, com base em um token, em uma ou mais classificações.

+++ Detalhes

#### Entrada necessária

Insira um valor para **[!UICONTROL Split]**. Por exemplo: `:`.

#### Caso de uso

Você deseja definir uma regra que divide os valores da dimensão principal Campanha Interna para as classificações **[!UICONTROL Canal]**, **[!UICONTROL Tipo]** e **[!UICONTROL Ano]** com base no `:` **[!UICONTROL Token]**.

>[!BEGINTABS]

>[!TAB Regra]

![Regra - Dividir](assets/rule-split.png)

>[!TAB Resultados de teste]

![Regra - Dividir resultados de Teste](assets/rule-split-test.png)

>[!ENDTABS]

+++


#### Tabela de referência {#section_0211DCB1760042099CCD3ED7A665D716}

| Expressão regular | Descrição |
|---|---|
| `(?ms)` | Corresponder toda a expressão regular a uma entrada de várias linhas, permitindo que o curinga `.` corresponda a qualquer caractere de nova linha |
| `(?i)` | Fazer a correspondência com toda a expressão regular para não diferenciar maiúsculas de minúsculas |
| `[abc]` | Um caractere único de: a, b ou c |
| `[^abc]` | Qualquer caractere único exceto: a, b ou c |
| `[a-z]` | Qualquer caractere único no intervalo a-z |
| `[a-zA-Z]` | Qualquer caractere único no intervalo a-z ou A-Z |
| `^` | Início da linha (corresponde ao início da linha) |
| `$` | Corresponder ao final da linha (ou antes da nova linha no final) |
| `\A` | Início da sequência |
| `\z` | Final da sequência |
| `.` | Corresponder a qualquer caractere (exceto uma nova linha) |
| `\s` | Qualquer caractere invisível |
| `\S` | Sem caracteres diferentes de invisíveis |
| `\d` | Qualquer dígito |
| `\D` | Qualquer não dígito |
| `\w` | Qualquer caractere da palavra (letra, número, sublinhado) |
| `\W` | Qualquer caractere que não seja da palavra |
| `\b` | Qualquer limite da palavra |
| `(...)` | Capturar tudo delimitado |
| `(a\b)` | a ou b |
| `a?` | Zero ou um de a |
| `a*` | Zero ou mais de a |
| `a+` | Um ou mais de a |
| `a{3}` | Exatamente 3 de a |
| `a{3,}` | 3 ou mais de a |
| `a{3,6}` | Entre 3 e 6 de a |



## Prioridade da regra

A última regra determina o valor da classificação se:

* Um valor de dimensão principal corresponde a várias regras.
* O conjunto de regras contém regras com a mesma operação **[!UICONTROL Definir Classificação]**.

Portanto, você deve classificar a operação **[!UICONTROL Definir Classificação]** mais importante como parte da última regra em seu conjunto de regras.

Se você criar várias regras que não compartilham a mesma operação **[!UICONTROL Definir Classificação]**, a ordem de processamento não será importante.


### Exemplo

Você deseja classificar com a classificação **[!UICONTROL Tipo]** como os usuários pesquisam por uma equipe, tipo genérico ou player usando a sequência de pesquisa como dimensão principal. Por exemplo, usando esse conjunto de regras:

+++ Detalhes


>[!BEGINTABS]

>[!TAB Regra]

![Regra - Prioridade](assets/rule-priority.png)

>[!TAB Resultados de teste]

![Regra - Resultados de teste de prioridade](assets/rule-priority-test.png)

>[!ENDTABS]

+++ 

