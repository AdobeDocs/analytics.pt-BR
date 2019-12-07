---
description: AJAX é um conceito emergente em web design que usa várias tecnologias para criar e gerenciar conteúdo dinâmico nas páginas da Web.
keywords: Analytics Implementation
title: Aplicativos de mídia avançada AJAX
topic: Developer and implementation
uuid: ffe6a263-ae18-4875-badb-b3aea3efcb64
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Aplicativos de mídia avançada AJAX

AJAX é um conceito emergente em web design que usa várias tecnologias para criar e gerenciar conteúdo dinâmico nas páginas da Web.

A necessidade de rastrear a interação do usuário com [!UICONTROL AJAX] e outros aplicativos é fundamental para o sucesso da análise e realização de retorno de investimento em web design. O foco deste documento é oferecer recomendações para rastrear os RIA (Rich Internet Applications), especificamente aqueles que usam [!UICONTROL AJAX].

## RIA (Rich Internet Applications) {#section_CDCAFC4E05B44985BCBF34DFCB35DCA6}

Os RIA (Rich Internet Applications) estão mudando a aparência da Web. Eles fazem a ponte entre a promessa de tecnologias sob demanda para as massas e as experiências realistas do usuário. Os RIAs têm sido amadurecidos com o passar dos anos. Os grandes saltos para frente ocorreram com a adoção de navegadores em larga escala, com o suporte de tecnologia subjacentes que potencializam esses aplicativos. Embora os RIA tenham muitas formas e tecnologias de suporte, as mais comuns e talvez mais amplamente adotadas sejam o AJAX e o Flash. É importante compreender que não é a tecnologia que define um RIA, mas sua capacidade de uso e aplicação.

## O que rastrear {#section_E96EC5127E554B8384FD0A7A0B3118DF}

Uma das perguntas mais frequentes com relação aos RIA é como rastrear a atividade em nível micro separadamente da atividade em nível macro, e quando isso é apropriado. Por exemplo, digamos que você tenha um aplicativo que permita aos clientes configurar unicamente um produto. O aplicativo pode ter várias etapas significativas às quais o usuário fica exposto. Essas etapas são consideradas exibições de página? Além disso, existem atividades em nível micro em cada etapa. Essas atividades devem ser rastreadas como exibições de página?

E se você quiser compreender o fluxo entre as atividades, ou quais recursos obtêm mais atividade? O problema com o RIA é que cada aplicativo é único. Eles são criados para imitar ações realistas e, como as ações são relativas a uma situação, as possibilidades são infinitas. Entretanto, a maioria dos aplicativos tem alguns componentes importantes: etapas marcantes, recursos e ações de nível micro dentro dos recursos. Portanto, embora o aplicativo requeira uma consideração sobre o que especificamente deve ser medido, existem algumas generalizações que podem ser aplicadas ao rastreamento de RIA.
A atividade de nível macro geralmente constitui o carregamento do aplicativo. Ela oferece informações sobre visitas, visitantes, instâncias, valor para ações futuras e assim por diante. Ela pode - e deve - representar também etapas importantes no processo. Um princípio básico é que se uma ação do RIA alterar o aplicativo mais que 50% (ou o que for considerado significativo para alteração da experiência do usuário ou conteúdo), então ela será de nível macro e deverá ser considerada uma exibição de página.
A atividade de nível micro inclui quaisquer alterações inferiores a 50% (ou não considerada como alterando significativamente a experiência do usuário ou conteúdo). A alteração das seleções de cores, por exemplo, seria considerada uma atividade em nível micro. A Adobe recomenda que o rastreamento de nível micro seja relacionado aos recursos. Por exemplo, no caso de alternância de cores, é realmente importante compreender quais cores são consideradas? Ou é mais importante saber qual recurso de seleção de cor foi usado? Talvez ambos sejam importantes, e nesse caso, capture ambos, mas no caso de medir a eficácia do RIA, considere a atividade do nível de recurso como mais relevante.

Todas as atividades de nível micro devem ser rastreadas como links personalizados com medições específicas por meio das variáveis de tráfego associadas (props e eVars, se for necessário medir o uso com relação a eventos bem-sucedidos). Isso garante que as exibições de página não serão infladas por atividade de nível micro, e permite a análise de caminhos por meio da variável de tráfego.

## O que analisar {#section_56824EF675874BA99127A566F6B1383F}

É importante compreender como seu RIA está conduzindo efetivamente o sucesso. O sucesso costuma ser medido por meio de conversões. Uma análise de nível macro oferece ideias sobre a eficácia do RIA como um todo. A análise de nível macro oferece ideias sobre quais recursos ajudam a orientar a conversão.

Você deve medir a eficiência de seu RIA. Esta é uma análise de atividade em nível micro relativa às métricas macros do RIA. Os usuários percorrem mais etapas que o necessário para chegar à mesma meta? As métricas de análise podem incluir atividade de visitas/recursos; atividades de exibições de página/recurso; atividades de visitantes/recursos e assim por diante.

Conduza a análise no fluxo do caminho e desistência. Os usuários estão evitando o RIA e encontrando outro caminho até sua meta? Execute relatórios de desistência criados para o fluxo do site e do RIA. Execute análise de caminho de páginas iniciais para medir os padrões verdadeiros de tráfego. Observe barreiras e incentivos para orientar os usuários para a meta.

## Métricas sugeridas {#section_AB7047D6C74740C6B6E47ED93602DB07}

* Visitas do RIA
* Visitantes do RIA
* Exibições de página do RIA
* Atividade de clique para medir a atividade de recurso (links personalizados) do RIA por recurso

## Análise sugerida {#section_5BE0FB9ECA3049E5965BEAD733DA5B6E}

* Atividade de recurso do RIA / Exibições de página do RIA
* Atividade de recurso do RIA / Visitas do RIA -
* Exibições de página do RIA / Métrica do sucesso - Taxa de conversão: mede a eficácia do aplicativo
* Atividade total do RIA / Métrica de sucesso - Taxa de conversão: mede a eficácia do aplicativo
* Atividade do RIA do recurso/ Métrica de sucesso - Taxa de conversão: mede a eficácia do aplicativo
* Fluxo do caminho para e do RIA
* Taxas de desistência por meio do processo de conversão do RIA

