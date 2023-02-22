---
description: Os segmentos permitem que você identifique subconjuntos de visitantes com base em características ou interações de site. Os segmentos são criados como informações de público-alvo codificadas que você pode criar de acordo com necessidades específicas e, em seguida, verificar, editar e compartilhar com outros membros da equipe, ou usar em outros produtos da Adobe e recursos do Analytics.
title: Sobre segmentos
feature: Segmentation
exl-id: 11d930ca-5d59-4ea5-b6e5-fe3d57be94fd
source-git-commit: 385c27de382b7bb047b6c62420d0471dd6e1650d
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 88%

---

# Sobre segmentos

Os segmentos permitem que você identifique subconjuntos de visitantes com base em características ou interações de site. Os segmentos são projetados como insights do público-alvo que você pode criar de acordo com suas necessidades específicas e, em seguida, verificar, editar e compartilhar com outros membros da equipe ou usar em outros produtos do Adobe e recursos do Analytics.

Os segmentos baseiam-se em uma hierarquia de nível de [!UICONTROL Visitante], [!UICONTROL Visita] e [!UICONTROL Ocorrência] por meio de um modelo de contêiner aninhado. Os contêineres aninhados permitem que você defina atributos de visitante e ações com base em regras entre e nos contêineres. Segmentos do Analytics podem ser construídos, aprovados, compartilhados, salvos e executados em vários produtos e recursos da [!DNL Adobe Experience Cloud]. Os segmentos podem ser gerados a partir de um relatório, construído em um relatório de painel, ou marcado para acesso rápido.

Você pode criar e salvar segmentos no Construtor de segmentos ou gerar segmentos de um relatório de fallout (no  Analysis Workspace). Você também pode empregar e estender segmentos pré-construídos com base em regras específicas entre contêineres aninhados, o que lhe permite filtrar resultados e aplicar a relatórios. Além disso, os segmentos podem ser usados juntamente como [segmentos empilhados](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

Os segmentos identificam quem são seus visitantes (país, sexo, cafeteria), quais dispositivos e serviços eles usam (navegador, mecanismo de pesquisa, dispositivo móvel), de onde navegaram (mecanismo de pesquisa, página de saída anterior, pesquisa natural) e muito mais.

![](assets/seg.png)

Os segmentos podem ter por base os seguintes valores:

* Visitantes com base em atributos: tipo de navegador, dispositivo, número de visitas, país, gênero.
* Visitantes com base em interações: campanhas, pesquisa por palavras-chave, mecanismo de pesquisa.
* Visitantes com base em saídas e entradas: visitantes do Facebook, uma página inicial definida e um domínio de referência.
* Visitantes com base em variáveis personalizadas: campos do formulário, categorias definidas, ID do cliente.

Ao construir segmentos de público-alvo no Construtor de segmentos, você define condições com os operadores [!UICONTROL AND] e [!UICONTROL OR] entre os contêineres.

![](assets/standard_segment_containers.png)

Esse tipo de conjunto de dados de filtros de segmento com base em características unidas com operadores [!UICONTROL AND] e [!UICONTROL OR].

* É possível [aplicar vários segmentos a um relatório ou projeto](/help/components/segmentation/segmentation-workflow/seg-workflow.md).
* Os segmentos são universais para todos os conjuntos de relatórios.
* O [Construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) simplifica a criação de segmentos.
* O [Gerenciador de segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) permite que você configure [fluxos de trabalho](/help/components/segmentation/segmentation-workflow/seg-workflow.md) com verificação, marcação, compartilhamento de segmentos e recursos de aprovação.
* Você pode [adicionar tags a segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) para organizar e pesquisar depois, em vez de usar pastas.
* Você pode criar [Segmentos sequenciais](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
* O [!UICONTROL Exibição da página] agora é o [!UICONTROL Ocorrência] para indicar que esse contêiner segmenta todos os tipos de dados e não apenas visualizações de página. Por exemplo, chamadas de rastreamento de link e chamadas trackAction de SDKs móveis são todas incluídas ou excluídas pelo contêiner de ocorrências.

## Segmentação na Analysis Workspace

O Analysis Workspace contém estes recursos adicionais:

* Você pode [comparar segmentos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html?lang=pt-BR).
* Use [segmentos como dimensões](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR) em uma comparação.
* Use segmentos na [análise de fallout](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.html?lang=pt-BR).

## Segmentos fornecidos pelo Adobe

O painel Componente no lado esquerdo da tela mostra segmentos criados por você e pela sua empresa, bem como segmentos de Adobe fornecidos prontos para uso. Ao clicar em **[!UICONTROL Mostrar tudo]**, esses segmentos normalmente aparecem na parte inferior da lista e são identificados pelo logotipo do Adobe à direita:

![Segmentos Adobe](assets/adobe-segs.png)

## Segmentos sequenciais {#sequential}

Os segmentos sequenciais permitem que você identifique visitantes com base na navegação e visualização de página no site, o que fornece um segmento de ações e interações definidas. Os segmentos sequenciais ajudam você a identificar o que um visitante gosta e o que um visitante evita. Ao construir segmentos sequenciais, o operador [!UICONTROL THEN] é usado para definir e organizar a navegação do visitante.

![](assets/sequential_seg.png)

| Visita um | Visita dois | Visita três |
|---|---|---|
| Na primeira visita, o visitante foi para a página de aterrissagem principal (A), excluiu a página da campanha (B) e, em seguida, visualizou a página do Produto (C). | Na segunda visita, o visitante novamente foi para a página de aterrissagem principal (A), excluiu a página da campanha (B) e, novamente, foi para a página do Produto (C), em seguida, foi para a nova página (D). | Na terceira visita, o visitante entrou e seguiu o mesmo caminho da primeira e segunda visita, em seguida, excluiu a página F para ir diretamente para a página de produto direcionada (G). |

Os segmentos sequenciais podem ser baseados nos seguintes valores de ocorrência:

* Os visitantes com base na sequência de ocorrências de páginas, visualizações de página em uma única visita, visualizações de página em visitas separas, visitas que excluíram visualizações de página.
* Visitantes com base no tempo entre e após visualizações de página, após um tempo limite, entre ocorrências, após um evento.

![](assets/sequential_segmentation_containers_view.png)

Um segmento sequencial filtra conjuntos de dados com base nas ações do usuário com o operador [!UICONTROL THEN].

## Vídeo passo a passo {#segment-video}

Este vídeo fornece uma breve visão geral do que são os contêineres de segmento e como usá-los: [Contêineres de segmentos no Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-containers.html?lang=pt-BR)

## Acesse as Ferramentas de segmentação {#access}

+++ **Como obtenho o Construtor de segmentos?**

Para acessar o Construtor de segmentos, basta:

* Exibir um relatório existente e clicar no ![ícone de Segmentos](assets/segment_icon.png) na navegação à esquerda. No painel de segmentos exibido, clique em **[!UICONTROL Adicionar]** ou

* Clique em **[!UICONTROL Adicionar]** mais, na parte superior do Gerenciador de segmentos.  ![Botão Adicionar](assets/add_button.png)

   ou

* Clique em um título de segmento existente no Gerenciador de segmentos para editar o segmento no Construtor de segmentos.

+++

+++ **Como obtenho o Gerenciador de Segmentos?**

Para acessar o Gerenciador de segmentos:

* Vá até **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** na navegação superior e, Em seguida, clique em **[!UICONTROL Segmentos]** ou

* Exibir um relatório existente e clicar no ![ícone de Segmentos](assets/segment_icon.png) na navegação à esquerda. Em seguida, clique em **[!UICONTROL Gerenciar]** ou

* Pressione a tecla “/” em qualquer lugar na interface e pesquisando pelo gerenciador de segmentos.

+++

## Permissões {#section_648DFA3A882146C485A84ED014EEC707}

+++ **Quais direitos e privilégios são necessários para que eu possa usar, criar e gerenciar segmentos?**

Por padrão, todos os usuários podem criar e editar segmentos pessoais. Contudo, os administradores podem escolher quem deve ter [permissões para criar segmentos](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=pt-BR) e quem pode atribuí-los a grupos específicos. Esses segmentos podem ser compartilhados diretamente com qualquer outro usuário do Analytics.

Os administradores podem editar qualquer segmento e compartilhar segmentos com grupos e todos na organização. [Mais...](/help/components/segmentation/seg-reference/seg-rights.md)

+++

+++ **É possível visualizar todos os segmentos na minha empresa?**

Sim, administradores podem visualizar todos os segmentos nas interfaces do usuário do [!DNL Analysis Workspace] e do [!DNL Reports & Analytics].

O Report Builder exibe os segmentos de sua propriedade e os segmentos compartilhados com você.

+++

+++ **É possível gerenciar todos os segmentos do Analytics no Gerenciador de segmentos?**

Sim, todos os segmentos podem ser gerenciados no Gerenciador de segmentos. O Gerenciador de segmentos exibe segmentos que são visíveis para o proprietário (usuário que criou o segmento), usuários compartilhados e usuários administradores. O seletor de segmentos exibe segmentos de propriedade e compartilhados com o usuário.

Administradores podem visualizar todos os segmentos nas interfaces do usuário da Analysis Workspace e do [!DNL Reports & Analytics].

O Report Builder só exibe segmentos criados por você ou que tenham sido compartilhados especificamente com você.

+++

+++ **Por que não posso excluir esse segmento?**

Se o segmento foi [publicado na Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-workflow.md), você não pode excluí-lo ou editá-lo. Entretanto, é possível copiá-lo e editar a versão copiada.

+++
