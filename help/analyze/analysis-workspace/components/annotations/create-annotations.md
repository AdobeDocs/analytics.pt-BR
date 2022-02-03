---
title: Criar anotações
description: Como criar anotações no Workspace.
role: User, Admin
source-git-commit: 89cbecf109a8fa9a9fac1f1ed8ad198ffdd398d3
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 5%

---


# Criar anotações

>[!NOTE]
>
>No momento, esse recurso está em testes limitados.

1. Para criar anotações, você tem 4 maneiras de começar:

   * Ir para [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Anotação]. A página Gerenciador de anotações é aberta. Clique em [!UICONTROL Criar nova anotação] e o Construtor de anotações é aberto.

   * Clique com o botão direito do mouse em um ponto em uma tabela ou gráfico de linhas. O Construtor de anotações é aberto.

   * No Workspace, acesse [!UICONTROL Componentes] > [!UICONTROL Criar anotação]. O Construtor de anotações é aberto.

   * Use essa tecla de atalho para abrir o Construtor de anotações:
      * (PC) `ctrl` `shift` + o
      * (Mac) `shift` + `command` + o

1. Preencha os elementos do Construtor .

   ![](assets/ann-builder.png)

   | Elemento | Descrição |
   | --- | --- |
   | [!UICONTROL Título] | Nomeie a anotação, por exemplo &quot;Dia Memorial&quot; |
   | [!UICONTROL Descrição] | (Opcional) Forneça uma descrição para a anotação, por exemplo &quot;Feriado público observado nos EUA&quot;. |
   | [!UICONTROL Tags] | (Opcional) Organize as anotações criando ou aplicando uma tag. |
   | [!UICONTROL Data aplicada] | Selecione a data ou o intervalo de datas que precisa estar presente para que a anotação fique visível. |
   | [!UICONTROL Cor do canal] | Aplicar uma cor à anotação. A anotação aparece no projeto com a cor selecionada. A cor pode ser usada para categorizar anotações, como feriados, eventos externos, problemas de rastreamento etc. |
   | [!UICONTROL Escopo] | (Opcional) Arraste e solte as métricas que acionam a anotação. Em seguida, arraste e solte quaisquer dimensões ou segmentos que atuam como filtros (ou seja, com os quais a anotação estará visível). Se você não especificar um escopo, a anotação será aplicada a todos os seus dados.<ul><li>**[!UICONTROL Qualquer uma dessas métricas está presente]**: Arraste e solte até 10 métricas que dispararão a exibição da anotação.</li><li>**[!UICONTROL Com todos esses filtros]**: Arraste e solte até 10 dimensões ou segmentos que serão filtrados quando a anotação for exibida.</li></ul><p>Casos de uso: Um eVar parou de coletar dados de um intervalo de datas específico. Arraste o eVar para a **[!UICONTROL Qualquer uma dessas métricas está presente]** caixa de diálogo. Ou seu [!UICONTROL Visitas] não está relatando dados; siga o mesmo processo. |
   | [!UICONTROL Aplicar a todos os conjuntos de relatórios] | Por padrão, a anotação se aplica ao conjunto de relatórios de origem. Ao marcar essa caixa de seleção, é possível fazer com que a anotação se aplique a todos os conjuntos de relatórios na empresa. |
   | [!UICONTROL Aplicar a todos os projetos] | Por padrão, a anotação se aplica ao projeto atual. Ao marcar essa caixa de seleção, é possível fazer com que a anotação se aplique a todos os projetos que você possui. Observe que essa caixa de seleção aparece somente quando você inicia o Construtor de anotações no Gerenciador de anotações. |

1. Clique em [!UICONTROL Salvar].