---
description: Os Controles interativos permitem que você edite segmentos e intervalos de datas para uma ou mais solicitações diretamente da planilha. Isso proporciona maior flexibilidade ao atualizar solicitações do construtor de relatórios.
seo-description: Os Controles interativos permitem que você edite segmentos e intervalos de datas para uma ou mais solicitações diretamente da planilha. Isso proporciona maior flexibilidade ao atualizar solicitações do construtor de relatórios.
seo-title: Controles interativos
solution: Analytics
title: Controles interativos
topic: Construtor de relatórios
uuid: 5f324b61-e032-455e-9947-5037f013e0fa
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Controles interativos

Os Controles interativos permitem que você edite segmentos e intervalos de datas para uma ou mais solicitações diretamente da planilha. Isso proporciona maior flexibilidade ao atualizar solicitações do construtor de relatórios.

Os controles interativos foram criados em resposta a um fluxo de trabalho comum, no qual os analistas criam pastas de trabalho e as compartilham com a organização de marketing. Os controles interativos fornecem os comerciantes a capacidade de modificar e atualizar solicitações sem precisar de grandes conhecimentos sobre como o construtor de relatórios funciona. (Observe que para atualizar uma solicitação, o destinatário da pasta de trabalho deve ser um usuário do construtor de relatórios). Esses controles funcionam dentro de pastas de trabalho programadas. Há dois tipos de controles interativos no momento:

* Intervalo de datas contínuas
* Segmentos

>[!IMPORTANT]
>
>É necessário ter o Construtor de relatórios v5.0 instalado para que os controles interativos funcionem. &gt;
>* Se você estiver executando o Microsoft Excel no Windows, mas estiver executando uma versão inferior do Construtor de relatórios, ou se você não tiver o Construtor de relatórios instalado: Você pode alterar o valor no controle interativo, mas ele não atualizará a solicitação associada, nem atualizará os parâmetros associados da solicitação.
>* Se você estiver executando o Excel no Mac, alterar o valor no controle fará com que a seguinte mensagem seja exibida: "Não é possível localizar a macro 'Adobe.ReportBuilder.Bridge.FormControlClick.Event'."
>



>[!IMPORTANT]
>
>Não altere o nome do controle. (Para visualizar o nome, definir o foco no controle e o nome do controle aparece depois do grid do Excel, no canto superior esquerdo).

## Implement interactive date range control {#section_39B228F2D2C44985863D31424C953280}

1. Na Etapa 1 da seleção do Assistente de solicitações, por exemplo, o relatório **[!UICONTROL Página].**
1. Ao lado do menu suspenso **[!UICONTROL Datas utilizadas mais comuns]**, clique no ícone **Configurações de controle[!UICONTROL :]**

   ![](assets/date_range_control.png)

1. Na caixa de diálogo Configurações de controle, selecione todos os itens do intervalo de datas que você deseja exibir no controle interativo. Além disso, especifique a localização da célula superior esquerda do controle.

   ![](assets/control_settings.png)

1. Observe a opção para "Atualizar automaticamente solicitações vinculadas após a seleção do item".

   * Se marcadas, todas as solicitações que usam esse controle são atualizadas.
   * Não se for marcada, os parâmetros de solicitação associados são atualizados, mas a solicitação não é atualizada.

1. Clique em **[!UICONTROL OK]**. O controle aparece na localização da célula especificada:

   ![](assets/date_range_control_interactive.png)

1. Agora é possível alterar o intervalo de data e a solicitação será atualizada com esse intervalo de datas.
1. Também é possível copiar a solicitação e clicar com o botão direito do mouse para usar uma de duas opções de Colar solicitação:

   * **[!UICONTROL Colar solicitação]** &gt; **[!UICONTROL Usar célula]** de entrada absoluta. Isso significa que a solicitação copiada apontará para o mesmo controle de intervalo de datas interativo como a solicitação original.

   * **[!UICONTROL Colar solicitação]**&gt; **[!UICONTROL Usar célula]** de entrada relativa. Isso significa que a solicitação copiada apontará para seu próprio controle.

      >[!NOTE]
      >
      >Você pode usar a funcionalidade de controle Cortar/Copiar/Colar nativa do Microsoft Excel. O construtor de relatórios reconhece automaticamente os controles recém adicionados.

## Implement interactive segment control {#section_5003D3F724644280BF1BCD6E1B0CB784}

A implementação do controle de segmentos interativos é semelhante à implementação do controle de intervalo de datas.

1. Na Etapa 1 do Assistente de solicitação, ao lado da lista suspensa **[!UICONTROL Segmento], selecione o ícone de Configurações de controle do segmento:**

   ![](assets/segment_interactive_1.png)

1. Na caixa de diálogo Configurações de controle do segmento, selecione os segmentos que você deseja incluir no menu suspenso. Além disso, especifique a localização da célula superior esquerda do controle.

   ![](assets/segment_drop_down_properties.png)

1. O novo controle interativo agora aparece na pasta de trabalho:

   ![](assets/segment_interactive_3.png)

