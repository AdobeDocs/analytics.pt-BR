---
description: Rotular os dados do conjunto de relatórios significa que você atribui os rótulos de identidade, sensibilidade e governança de dados a cada variável em um determinado conjunto de relatórios. Certifique-se de se familiarizar primeiro com os rótulos e suas definições.
title: Rotular dados do conjunto de relatórios
uuid: a694851c-8933-496e-9118-113cc38cba8a
translation-type: ht
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# Rotular dados do conjunto de relatórios

Rotular os dados do conjunto de relatórios significa que você atribui os rótulos de identidade, sensibilidade e governança de dados a cada variável em um determinado conjunto de relatórios. Certifique-se de se familiarizar primeiro com os rótulos e suas definições.

> [!NOTE] Lembre-se de que a Rotulagem precisa ser revisada sempre que um novo conjunto de relatórios for criado ou quando uma nova variável for ativada em um conjunto de relatórios existente. Você também pode analisar a rotulagem quando novas integrações da solução forem ativadas, pois elas podem expor novas variáveis que podem exigir rótulos. A reimplementação de aplicativos ou sites móveis pode alterar como as variáveis existentes são usadas, o que também pode exigir atualizações nos rótulos.

## Atribuir ou editar rótulos do conjunto de relatórios {#section_39F829F35A274EACA532E2F6FF392996}

**Exemplo**: você, como controlador de dados, planeja coletar endereços de email e IDs de cookies de titulares de dados para processar suas solicitações de Privacidade de dados. Essas IDs de cookies são armazenadas em um conjunto de relatórios no Adobe Analytics. Para criar um rótulo para endereços de email e IDs de cookies, você deve usar o framework DULE (Data Usage Labeling &amp; Enforcement - Aplicação e rotulagem do uso de dados) da Adobe Cloud Platform no Analytics.

1. No Analytics, navegue até **[!UICONTROL Admin]** > **[!UICONTROL Governança de dados]** > **[!UICONTROL (selecione o conjunto de relatórios)]**![](assets/privacy_rs_settings.png)

1. Selecione qual grupo de variáveis você deseja rotular.

   ![](assets/variables.png)

   * **Dimensões padrão** (Dimensões prontas do Adobe Analytics)
   * **Métricas padrão** (Métricas prontas do Adobe Analytics)
   * **Eventos de conversão** (eventos bem-sucedidos personalizados)
   * **Dimensões de conversão de merchandising** (eVar de merchandising)
   * **Dimensões de conversão** (eVars que não são de merchandising)
   * **Dimensões de tráfego personalizado** (props)
   * **Dimensões e eventos da solução** (dimensões/eventos relacionados a soluções como Mobile, Vídeo, Activity Map etc. e integrações com soluções como o Adobe Campaign, o Adobe Experience Manager, a Advertising Cloud etc.)
   * **Dimensões de processamento de dados** (variáveis não expostas diretamente no relatório por meio da interface do usuário do Adobe Analytics, mas disponíveis por meio de solicitações de Feeds de dados e/ou do Data Warehouse)

1. (Opcional) Clique no ícone de informações (i) ao lado de cada variável para entender melhor seus valores mais comuns nos últimos 90 dias. (Esse recurso não está disponível para as Dimensões de processamento de dados, pois elas não estão disponíveis na interface do usuário do Analytics.)

   ![](assets/info.png)

1. Selecione uma ou mais variáveis ao clicar na caixa de seleção e, em seguida, selecione o ícone **[!UICONTROL Editar]** (à direita) para editar uma ou mais variáveis.

   ![](assets/edit.png)

1. A caixa de diálogo **Dados de identidade** é exibida automaticamente. Esses rótulos classificam os dados que podem ser usados isolados ou em combinação com outros dados para identificar ou permitir o contato direto com um indivíduo. Para obter mais informações sobre essas opções, consulte [Rótulos de dados de identidade (DULE).](/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels)

   >[!NOTE]
   >
   >A estrutura DULE (Label Usage Labeling &amp; Enforcement) foi criada para fornecer uma maneira uniforme em todas as soluções/serviços/plataformas para capturar, comunicar e usar metadados sobre dados na Adobe Experience Cloud. Os metadados ajudam os controladores de dados a indicar quais dados são informações pessoais, quais dados são sensíveis e quais restrições de contrato estão associadas aos dados.

   ![](assets/identity_labels.png)

1. Abra a seção **Dados sensíveis** para definir os Rótulos de dados confidenciais que categorizam os dados de localização geográfica. Para obter mais informações sobre essas opções, consulte [Rótulos de dados sensíveis (DULE).](/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels)

   ![](assets/sensitive_data.png)

1. Abra a seção Privacidade de dados para definir os rótulos da **Governança de dados**. Use esta seção para instruir a Adobe sobre como lidar com cada variável das solicitações de acesso e exclusão da Privacidade de dados, bem como para definir quais variáveis devem ser verificadas para encontrar as IDs do titular de dados dessas solicitações. Para obter mais informações sobre essas opções, consulte [Rótulos de governança de dados (Privacidade de dados).](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels)

   ![](assets/privacy_labels.png)

1. Clique em **[!UICONTROL Aplicar]** após concluir toda a rotulagem.

## Copiar rótulos para os conjuntos de relatórios {#section_7C6FDAFF049F4126B84F6261F72668EE}

Se você quiser aplicar as mesmas configurações DULE/Privacidade de dados a mais de um conjunto de relatórios, poderá seguir estas etapas:

1. Selecione o grupo de variáveis (Dimensões padrão, Dimensões de conversão etc.) contendo a variável que você deseja copiar. Observe que você pode copiar os rótulos apenas para um grupo de variáveis por vez.
1. Selecione algumas ou todas as variáveis neste grupo.
1. Clique em **[!UICONTROL Copiar rótulos para os conjuntos de relatórios]** na parte superior direita da caixa de diálogo Governança de dados.

   ![](assets/apply_as_template.png)

1. Marque **[!UICONTROL Selecionar todos]** para copiar rótulos para as variáveis selecionadas para todos os conjuntos de relatórios ou selecione os conjuntos de relatórios individuais para os quais você deseja copiar os rótulos.

   >[!IMPORTANT]
   >
   >Lembre-se de que todos os conjuntos de relatórios selecionados precisam ser mapeados para a organização da Experience Cloud.

   Ao copiar os rótulos de uma variável ou um conjunto de variáveis para um conjunto de relatórios diferente, a cópia é encaminhada para a variável na posição correspondente do conjunto de relatórios de destino. Para as Dimensões padrão, Métricas padrão, Dimensões e eventos de solução e Dimensões de processamento de dados, os rótulos serão copiados para a variável com o **mesmo nome** no conjunto de relatórios de destino.

   No entanto, para as Variáveis de conversão (eVars), Dimensões de conversão de merchandising e Dimensões de tráfego personalizadas (props), a cópia será para a variável com o **mesmo número** no conjunto de relatórios de destino. Por exemplo, eVar12 será copiada para eVar12 em todos os conjuntos de relatórios de destino. Os nomes dessas variáveis serão ignorados ao determinar o destino da cópia. Se a variável correspondente não estiver ativada no conjunto de relatórios de destino, ocorrerá um falha na cópia dessa variável.

   Ao copiar os rótulos de classificações definidos para uma variável, eles serão copiados para uma classificação na variável correspondente do conjunto de relatórios de destino (como eVar7 a eVar7) que tenha um nome idêntico à classificação copiada. Caso contrário, ocorrerá uma falha na cópia dos rótulos dessa classificação.

   Uma mensagem de status é exibida após aplicar um conjunto de rótulos. A mensagem de status incluirá os nomes de quaisquer variáveis ou classificações de destino e seus conjuntos de relatórios nos ocorreram a falha da cópia.

   >[!IMPORTANT]
   >
   >Você sempre deve verificar os conjuntos de relatórios de destino para garantir que os rótulos sejam copiados corretamente. Isso é especialmente importante para variáveis com rótulos de ID ou DEL.

1. Clique em **[!UICONTROL Aplicar]**.

