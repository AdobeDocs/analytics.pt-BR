---
title: Integração do Brand Visibility
description: Integrar o Brand Visibility ao Adobe Analytics
feature:
role: User
source-git-commit: 841b09d487fb965fb2a5fce4a39a7480a5b01012
workflow-type: tm+mt
source-wordcount: '2637'
ht-degree: 1%
---

# Integração do Adobe Brand Visibility

O [Adobe Brand Visibility](https://experienceleague.adobe.com/pt-br/docs/llm-optimizer/using/home) é um aplicativo de primeira geração de IA para a Otimização de Mecanismo Gerativo, projetado para ajudar as marcas a melhorar sua visibilidade, precisão e influência em ambientes de pesquisa orientados por IA. O Brand Visibility fornece insights sobre a presença da marca em respostas geradas por IA, oferece recomendações prescritivas de conteúdo e automatiza correções de otimização.

A IA se tornou um canal de descoberta principal. Os agentes do Large Language Model (LLM), como ChatGPT, Claude, Copilot e Perplexity, rastream o conteúdo da marca.

>[!NOTE]
>
>A visibilidade da marca era anteriormente chamada de **LLM Optimizer (LLMO)**. Algumas documentações do Adobe podem continuar a usar a antiga terminologia LLMO durante a transição.


>[!PREREQUISITES]
>
>Você deve ter uma oferta de Visibilidade da marca paga provisionada e conectada à configuração do Experience Platform por meio do conector gerenciado.


>[!IMPORTANT]
>
>Como parte dessa integração, algum processamento temporário de dados do Brand Visibility ocorre nos Estados Unidos. Os dados são armazenados na região designada conforme configurado em seu contrato do Adobe Analytics.

Se você usar o Customer Jornada Analytics, uma integração de entrada separada e mais avançada fornecerá os mesmos dados de tráfego de CDN subjacentes no Customer Journey Analytics por meio da Adobe Experience Platform. Essa integração está disponível hoje. Consulte [integração do Brand Visibility com o Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv). Se você tiver o Customer Journey Analytics, revise essa integração primeiro, pois ela expõe mais campos e oferece suporte ao agrupamento de dados do Brand Visibility com outros conjuntos de dados. A integração do Analytics descrita neste guia foi projetada para clientes que usam o Adobe Analytics sem ter acesso ou uma licença do Customer Journey Analytics.


## Casos de uso

Você pode se beneficiar da integração entre o Adobe Analytics e o Brand Visibility de duas maneiras:

* **Integração de entrada**: use dados do Brand Visibility no Adobe Analytics para medir o tráfego orientado por LLM (rastreadores de bot, solicitações RAG, atividade de agente) junto com dados da Web e de dispositivos móveis existentes. Por exemplo, você pode:

  * Meça o tráfego orientado por LLM por fonte do agente ao lado dos canais tradicionais.

  * Identifique o conteúdo que é consumido intensamente pelos LLMs, mas tem desempenho inferior na conversão humana.

  * Detectar onde as solicitações de agente LLM falham em caminhos críticos.

  * Compare a demanda de bot do LLM para uma página com as conversões e a receita dessa página nos dados da Web, correspondentes no nível do URL e do host.

* **Integração de saída**: envie dados de desempenho do Adobe Analytics para o Brand Visibility para que você possa otimizar a visibilidade de IA para as fontes LLM que enviam tráfego valioso, como ChatGPT ou Perplexity. Por exemplo, você pode:

  * Veja quais fontes de LLM enviam visitantes humanos que passam a converter ou gerar receita. O Adobe Analytics mede isso no tráfego da Web referenciado, não no conjunto de dados do bot.
  * Classifique as fontes de LLM pelo valor de downstream dos visitantes humanos que elas enviam e concentre seu trabalho de visibilidade de IA nas fontes com melhor desempenho.


## Integração de entrada

Esta seção descreve os pré-requisitos e as etapas de configuração da integração de entrada do **Adobe Brand Visibility → Adobe Analytics**.


O conector de entrada do Adobe Analytics é configurado por conjunto de relatórios por meio do **Gerenciador de Conjunto de Relatórios**, descrito na Seção 6.

>[!PREREQUISITES]
>
>Os logs de acesso da CDN já devem ser encaminhados para e recebidos pela Adobe Brand Visibility para cada site do Brand Visibility antes que o conector Brand Visibility → Adobe Analytics possa ser ativado.
>
>Este requisito se aplica a **cada site de Visibilidade da marca**. Uma configuração de CDN ou feed de log para um site, domínio ou subdomínio não deve ser considerada como abrangendo outro site, a menos que a Adobe confirme essa cobertura.
>
>
>Antes de ativar o conector, confirme:
>
>1. O pipeline de log ou CDN relevante está configurado para encaminhar os logs de acesso necessários para o destino fornecido pela Adobe.
>1. O Brand Visibility confirmou que os registros estão sendo recebidos e detectados para o site relevante.
>1. Os dados estão visíveis no painel Tráfego do agente de Visibilidade da marca desse site.
>
>O Encaminhamento de Log BYOCDN fornece os dados de solicitação de CDN do lado do servidor usados para análise de tráfego de agente. Os dados não dependem da execução das tags JavaScript em um navegador. Sem o feed de log CDN necessário, o conector não terá dados de tráfego para trazer para o conjunto de relatórios.
>
>Consulte [Referência de encaminhamento de log BYOCDN](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview) para obter mais informações.


>[!IMPORTANT]
>
>Como parte dessa integração, algum processamento temporário de dados do Brand Visibility ocorre nos Estados Unidos. Os dados são armazenados na região designada conforme configurado em seu contrato do Adobe Analytics.


### Como funciona

A integração Visibilidade da marca de entrada → Adobe Analytics adiciona um conjunto de **variáveis reservadas** ao conjunto de relatórios. Essas variáveis carregam dados no nível de resumo sobre o tráfego de bot e agente automatizado detectado no seu site, incluindo o tráfego baseado em LLM, originado dos mesmos logs de acesso da CDN descritos nos [pré-requisitos](#inbound-integration).

Esse tráfego geralmente não executa tags JavaScript do navegador e não é capturado por meio de sua implementação existente do Adobe Analytics. As variáveis reservadas fornecem uma maneira de ver esse tráfego dentro do mesmo conjunto de relatórios que você já usa para o site.

As seguintes variáveis reservadas são adicionadas quando o conector é ativado:

| Reportado como | Tipo | Notas |
|---|---|---|
| URL | Dimensão | O URL da página associado à solicitação. |
| Tipo de bot | Dimensão | O tipo de bot ou agente automatizado que fez a solicitação (por exemplo, um rastreador de IA nomeado). |
| Agente do usuário | Dimensão | A sequência do agente do usuário reportada pelo bot ou agente. |
| Status | Dimensão | O código do status HTTP retornado para a solicitação. |
| Referer | Dimensão | O valor de referência HTTP da solicitação, quando presente. |
| Solicitações | Métrica | A contagem de solicitações de CDN de bot e agente. |


#### Cobertura em comparação ao Customer Journey Analytics

A integração de entrada do CJA é criada em um conjunto de dados mais amplo de Resumo de solicitações de CDN e é compatível com campos adicionais (por exemplo, host e provedor de CDN), além de unir-se a outros conjuntos de dados na Customer Journey Analytics. A integração do Adobe Analytics é um conjunto menor, nativo de conjuntos de relatórios, de variáveis reservadas projetadas para funcionar dentro do modelo de dados existente do Analytics. Se suas necessidades de relatórios forem além dos campos listados acima, avalie a integração do CJA.

#### Limitações importantes

- Nenhuma ID de visitante, ECID, visita ou dados de usuário único são incluídos. São dados de resumo agregados, não vinculados a visitantes.
- As variáveis reservadas não oferecem suporte às configurações de tipo de alocação ou expiração, pois não estão vinculadas a um visitante.
- Os dados não podem ser unidos a outros conjuntos de dados ou dimensões do Analytics da mesma maneira que no Customer Journey Analytics.
- Use a métrica **Solicitações** para medir o volume de tráfego de bot e agente. Não o use alternadamente com métricas baseadas em visitas ou ocorrências em outro lugar no conjunto de relatórios.

O conjunto exato de campos disponíveis deve ser confirmado em relação à configuração de variável do conjunto de relatórios depois que o conector for ativado.

### Responsabilidades

A instalação e a configuração do conector de entrada vieram com responsabilidades para a [Adobe](#adobe-managed-responsibilities) e o [você como cliente](#customer-owned-responsibilities).

#### Responsabilidades gerenciadas pela Adobe

1. Detecta e confirma o encaminhamento de log CDN para cada site de Visibilidade da marca integrado.
2. Disponibiliza as variáveis reservadas para provisionamento depois que o encaminhamento de log BYOCDN é confirmado.
3. Executa o preenchimento retroativo de 90 dias e a sincronização horária contínua assim que o conector é ativado para um conjunto de relatórios.

#### Responsabilidades de propriedade do cliente

1. Concluindo a integração do Brand Visibility e o encaminhamento de logs BYOCDN para cada site.
2. A confirmação dos dados está visível no painel Tráfego de agente de Visibilidade da marca antes de habilitar o conector.
3. Escolhendo o conjunto de relatórios ao qual cada site do Brand Visibility se conecta (um site por conjunto de relatórios).
4. Ativar o conector por meio do Gerenciador de conjunto de relatórios.
5. Criar relatórios, segmentos ou Visualizações de dados (quando aplicável) que usam as variáveis reservadas listadas em [Como funciona](#how-it-works).

### Antes de começar

Confirme o seguinte antes de habilitar o conector:

- Você concluiu a integração do Adobe Brand Visibility para o site que deseja conectar.
- O encaminhamento de log BYOCDN está configurado e confirmado para esse site (consulte [pré-requisitos](#inbound-integration)).
- Os dados são exibidos no painel Tráfego do Adobe Brand Visibility Agentic desse site.
- Você sabe a qual conjunto de relatórios deseja conectar o site.

Cada site do Adobe Brand Visibility se conecta a exatamente um conjunto de relatórios. Se quiser trazer dados de mais de um site do Brand Visibility, conecte cada site a um conjunto de relatórios separado.


### Ativar o conector

O conector é ativado e desativado no menu **Editar configurações** do conjunto de relatórios.

Para abrir as configurações do Adobe Brand Visibility para o conjunto de relatórios:

1. Faça logon no Adobe Analytics.
1. Vá para **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Selecione o conjunto de relatórios que deseja conectar.
1. Selecione **[!UICONTROL Editar Configurações]**.
1. No menu de contexto, selecione **[!UICONTROL Adobe Brand Visibility]**.

Para provisionar o conector:

1. Selecione **Provisionar Conector de Dados do Adobe Brand Visibility**.
1. Revise as dimensões e métricas que serão adicionadas a este conjunto de relatórios (listadas em [Como funciona](#how-it-works)).
1. Em **Selecionar Site do Adobe Brand Visibility**, escolha o site para se conectar a este conjunto de relatórios. Depois de conectado, os dados de resumo do site são sincronizados com este conjunto de relatórios a cada hora.
1. Selecione **Habilitar**.

   Após ativadas, essas variáveis não podem ser removidas do conjunto de relatórios. A ativação do conector inicia um preenchimento retroativo de 90 dias, importando os últimos 90 dias de dados do Adobe Brand Visibility para este conjunto de relatórios.

   Antes de habilitar o conector, confirme se você concluiu as etapas descritas em [Antes de começar](#before-you-start), isso inclui a verificação de que os dados já estão sendo exibidos no painel Tráfego do Adobe Brand Visibility Agentic.

Após habilitar o conector, aguarde o preenchimento retroativo inicial e a conclusão da primeira sincronização horária. Em seguida, confirme se as variáveis reservadas mencionadas em [Como funciona](#how-it-works) foram preenchidas no conjunto de relatórios. consulte a Seção 8, Etapa 3).

### Desative o conector

>[!WARNING]
>
>A desabilitação do conector é **não reversível**. A desativação interrompe a sincronização horária e exclui os dados históricos do Adobe Brand Visibility deste conjunto de relatórios.

Para desativar o conector:

1. Vá para **Admin → Conjuntos de relatórios → Editar configurações → Adobe Brand Visibility**.
1. Selecione **Desprovisionar Conector de Dados do Adobe Brand Visibility**.
1. Confirme se o site do Adobe Brand Visibility listado é o que você pretende desconectar.
1. Selecione **Desabilitar**.
1. Confirme o aviso para confirmar.

Se quiser pausar os relatórios temporariamente, não desative o conector. Entre em contato com a equipe de conta da Adobe para discutir as opções para pausar os relatórios antes de desabilitar.

### Critérios de conclusão da configuração

A integração de entrada está pronta para o relatório quando todos os itens a seguir forem confirmados:

* Os logs CDN são encaminhados para o site e recebidos pela Adobe Brand Visibility para ele.
* Os dados estão visíveis no painel Tráfego do Adobe Brand Visibility Agentic do site.
* O conector foi ativado para o conjunto de relatórios pretendido por meio do Gerenciador de conjunto de relatórios.
* O preenchimento retroativo inicial e pelo menos uma sincronização horária foram concluídos.
* As variáveis reservadas na Seção 4 retornam os valores esperados nos relatórios.

### Procedimento de verificação

O procedimento de verificação consiste nas seguintes etapas:

1. Confirme o site de Visibilidade da marca e a preparação do log de CDN:

   * Confirme o site ou domínio exato que você pretende conectar.
   * Confirme se os logs da CDN estão sendo encaminhados para esse site e se a Visibilidade da marca confirmou o recebimento.
   * Confirme se os dados estão visíveis no painel Tráfego do agente desse site.

1. Confirme se o conector está ativado:

   1. Acesse **Admin → Conjuntos de relatórios → Editar configurações → Adobe Brand Visibility** para obter o conjunto de relatórios de destino.
   1. Confirme se a página mostra o conector como ativado e lista o site de Visibilidade da marca conectado.

1. Confirmar dados no relatório:

   1. Abra o Analysis Workspace (ou o fluxo de trabalho de relatório padrão) no conjunto de relatórios conectado.
   1. Crie uma tabela ou visualização usando a métrica **Solicitações** detalhada por **Tipo de bot**.
   1. O volume de solicitação de confirmação é exibido para um intervalo de datas recente.
   1. Confirme se as dimensões **URL**, **Agente do Usuário**, **Status** e **Referenciador** retornam os valores esperados.

   O tempo exato necessário para os dados serem exibidos depende do preenchimento retroativo e do agendamento de sincronização descritos em [Habilitar o conector](#enable-the-connector).



### Solução de problemas

Consulte os seguintes problemas e como solucioná-los.

| Problema | Solução de problemas |
|---|---|
| O conector não será habilitado ou a lista de sites está vazia. | Verifique se:<ul><li>A integração do Adobe Brand Visibility foi concluída para o site.</li><li>O encaminhamento de log BYOCDN está configurado e confirmado para o site.</li><li>Você está trabalhando no conjunto de relatórios correto.</li><ul> |
| O conector está ativado, mas nenhum dado é exibido. | Verifique se: <ul><li>Os dados estão visíveis no painel Tráfego do agente para o site conectado (caso contrário, o problema é upstream do Analytics).</li><li>Já se passou tempo suficiente para o preenchimento retroativo inicial de 90 dias e pelo menos uma sincronização horária.</li><li>- O intervalo de datas selecionado no relatório inclui um ponto depois que o conector foi habilitado.</li></ul> |
| Os dados parecem incompletos ou inesperados. | Verifique se: <ul><li>Não se espera que o conjunto de relatórios também receba dados de um site de Visibilidade da marca diferente (cada conjunto de relatórios se conecta a exatamente um site).</li><li>Você está lendo a métrica **Solicitações** em vez de contar linhas ou ocorrências em outro lugar no conjunto de relatórios.</li><li>As dimensões que você está visualizando correspondem à lista na Seção 4; evars ou eventos não relacionados no mesmo conjunto de relatórios não fazem parte dessa integração.</li></ul> |

>[!MORELIKETHIS]
>
>[Referência de integração do Brand Visibility /LLMO](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv)
>[Referência de encaminhamento de log BYOCDN](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)

---

## Notas de redação para documentos (não para publicação)

Esta seção é para revisão interna e deve ser removida antes da publicação.

- **Source da verdade usada:** nomes de campo, lista de variáveis reservadas e fluxo de trabalho do Gerenciador de Conjunto de Relatórios são provenientes de [AN-468884](https://jira.corp.adobe.com/browse/AN-468884) (David Wardell, status Novo a partir de 28/08/2026), que é mais atual e mais específico do que a solicitação de documentação original [AN-449989](https://jira.corp.adobe.com/browse/AN-449989) (Rob In der Maur, status Novo). A cópia da página para as telas Provisionamento/Desprovisionamento incorpora os refinamentos de texto da revisão interna 2026-08-28 (`2026-08-28-an468884-abv-report-suite-ui-review.md`), que substituiu a abreviação &quot;ABV&quot; do tíquete bruto por &quot;Adobe Brand Visibility&quot; no texto voltado para o cliente.
- **Discrepância do conjunto de campos a ser reconciliada antes da publicação:** A lista de dimensões original do AN-449989 era Host, URL/Caminho da Página, Provedor CDN, Agente do Usuário e Tipo de Bot LLM, com uma única métrica de Contagem de Solicitações Agenciais. A lista real de variáveis reservadas do AN-468884 é URL, Tipo de bot, Agente do usuário, Status e Referenciador, com um único evento de Solicitações. O Host e o Provedor CDN não estão presentes como variáveis reservadas separadas em AN-468884; o Status é novo. Este rascunho segue AN-468884 como autoritativo de acordo com o ticket eng, mas os dois devem ser reconciliados com Aaron Kern / David Wardell antes que isso seja finalizado, já que os nomes de campo que os clientes veem podem não corresponder ao que as equipes de conta descreveram usando o idioma AN-449989 mais antigo.
- **Ainda não confirmado, não declarar como fato na versão publicada:**
  - Data exata de disponibilidade geral. O AN-431416 tem o FixVersion H2 2026 (janela de versão 2026-11-30) e está com status Executar em 1 de setembro de 2026; o AN-468884 (a implementação da variável reservada) e o AN-449989 (este documento) ainda são novos. Não publique até que o eng envie.
  - Se o tipo de alocação/tipo de expiração será totalmente suprimido nas evars reservadas na produção. A revisão de 28/08/2026 sinalizou que um conjunto de relatórios de teste atualmente mostra essas evars com Alocação definida como &quot;Mais recente (último)&quot;, que pode ser um padrão que precisa ser limpo, em vez de comportamento final confirmado.
  - O endpoint da API LLMO para listar sites ABV por organização IMS (preenche a lista suspensa Seleção de sites) e a API de desprovisionamento/desativação ainda estavam pendentes de Joe Bass a partir do comentário do tíquete 2026-08-26.
  - A comparação exata de contagem de campo do CJA. O ticket original do AN-449989 alega que o CJA tem &quot;9 dimensões adicionais&quot; e &quot;5 métricas adicionais&quot;, mas várias dessas (Compartimento de sessão do LLM, Contagem de sessão exclusiva do LLM, Contagem de duplicação de solicitação do LLM) não foram confirmadas no grupo de campos `cdn-requests-summary` entregue a partir da revisão de 2026-06-18. Esse rascunho evita intencionalmente citar contagens específicas na comparação do CJA por esse motivo.
  - A cadência de sincronização para esse caminho AA é declarada aqui como por hora, correspondendo ao idioma do tíquete AN-468884 (&quot;executar sincronizações por hora&quot; / &quot;processo de sincronização por hora&quot;). Isso não foi validado de forma independente em relação ao comportamento das Fontes de dados de produção do AA da maneira como a cadência do CJA era.


## Integração de saída

Este guia aborda somente a integração do Brand Visibility de entrada, que adiciona dados de tráfego de bot e agente automatizado a um conjunto de relatórios do Analytics. A documentação de integração publicada também descreve uma direção de saída, na qual os dados de desempenho do Analytics são disponibilizados para o Brand Visibility dentro do produto do Brand Visibility. Essa direção está fora do escopo deste guia. Consulte a [documentação do Brand Visibility](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/adobe-analytics-integration) para obter mais informações sobre a integração de saída.