---
description: Perguntas frequentes sobre o Advertising Analytics.
title: Perguntas frequentes sobre análises de publicidade
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 36%

---

# Perguntas frequentes

## Acesso/Direitos {#access}

+++ Preciso ser um cliente do Adobe Advertising Cloud ou do Adobe Advertising Cloud (AMO) para acessar essa funcionalidade?

Não, essa funcionalidade está disponível para clientes que não são da Advertising Cloud ou do AMO.

Os clientes do AMO podem aproveitar da integração Analytics-AMO existente; eles não poderão usar o Advertising Analytics.

+++

+++ Quais SKUs do Adobe Analytics dão direito ao uso do Advertising Analytics?

O Advertising Analytics está disponível para o Adobe Analytics

* [Selecionar](https://www.adobe.com/br/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/br/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/br/data-analytics-cloud/analytics/ultimate.html)

+++

+++ Preciso pagar a mais para usar o Advertising Analytics?

Não, fora do provisionamento de SKU adequado, a Advertising Analytics não incorre em custo extra.

+++

+++ O Advertising Analytics conta com o meu uso de chamadas do servidor

Não, o Advertising Analytics usa um tipo de fonte de dados especial que não implica custos de chamada de servidor.

+++

+++ Se eu já usar o Advertising Cloud/AMO, ainda posso usar a funcionalidade do Advertising Analytics?

Qualquer conta de mecanismo de pesquisa compatível passará para o Advertising Analytics e será exibida como somente leitura. Todas as edições ou atualizações devem ser tratadas na Advertising Cloud/AMO.

+++

+++ Eu possuo o SKU correto, mas não consigo acessar o Advertising Analytics. Por quê?

O Advertising Analytics está disponível somente para administradores do Adobe Analytics; no entanto, os administradores podem conceder acesso a não administradores. Entre em contato com seu administrador para obter os direitos de acesso.

+++

## Usar o Advertising Analytics {#using}

+++ Quais contas de mecanismo de pesquisa são incluídas no Advertising Analytics?

As contas de mecanismo de pesquisa incluem o Google Ads e o Microsoft Advertising.

+++

+++ Onde acesso o Advertising Analytics?

Depois de fazer logon no Adobe Analytics, navegue até [!UICONTROL Admin]. Em seguida, selecione [!UICONTROL Advertising Analytics] para adicionar suas contas de mecanismo de pesquisa.

+++

+++ Como os dados são coletados e transmitidos para o Analytics?

O Advertising Analytics utiliza uma série de APIs personalizadas para transmitir dados de mecanismos de pesquisa por meio da Adobe Advertising Cloud para o Analytics.

+++

+++ Quais dados de pesquisa eu obtenho com essa integração?

Você obterá

* Impressões
* Cliques
* Custos
* Pontuação de qualidade
* Posição média diretamente dos mecanismos de pesquisa, bem como
* Instâncias de ID do AMO (instâncias de clique).

+++

+++ É possível detalhar meus dados do Advertising Analytics por outros dados do Analytics (métricas/dimensões)?

Não, os dados brutos de pesquisa entrarão como um conjunto de dados independente. Contudo, há uma versão de Instâncias dos dados de clique que pode ser detalhada por outros dados do Analytics.

+++ Qual é a definição dos vários indicadores de status para minhas contas (Pendente, Ativo, Pausado etc.)? Cada um desses indicadores de status identifica o estágio do ciclo de vida de cada conta de mecanismo de pesquisa.

* [!UICONTROL Pendente]
* [!UICONTROL Pausado] significa que a conta já tinha sido configurada mas foi colocada em um estado de inatividade.
* [!UICONTROL Ativo] significa que a conta foi totalmente configurada e está transferindo os dados de pesquisa.

+++

+++ Estou tentando mapear minhas contas do Advertising Analytics para um conjunto de relatórios específico, mas não está disponível no modal do Conjunto de relatórios. Por quê?

Antes de atribuir um conjunto de relatórios a uma conta do Advertising Analytics, o conjunto de relatórios desejado precisa ser [provisionado para os relatórios do Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
Isso é feito por meio de uma página de Admin separada, acessível em: Administração > Conjuntos de relatórios > `[select report suite]` > Editar configurações > Configuração do Advertising Analytics.

+++

+++ É possível atribuir um conjunto de relatórios virtual a uma conta do Advertising Analytics?

Os conjuntos de relatórios virtuais não coletam dados, portanto, não é possível mapear diretamente uma conta do Advertising Analytics para um conjunto de relatórios virtual. No entanto, é possível mapear a conta do Advertising Analytics para o Conjunto de relatórios principal do Conjunto de relatórios virtuais no qual você deseja ver os dados. As métricas do mecanismo de pesquisa (clique/custo/impressões) podem não ser exibidas no conjunto de relatórios virtual a menos que você inclua uma condição &quot;ou&quot; na lógica do segmento com base na ID do AMO (ou sua classificação). Exemplo: adicionar “todas as ocorrências em que a ID do AMO existe” incluirá as métricas do mecanismo de pesquisa no segmento.

+++

+++ Há métricas do Advertising Analytics reportáveis no relatório *Canais de marketing*?

Não, elas não estão incluídas no relatório de Canais de marketing.

+++

+++ Quando os dados de pesquisa são transferidos para o Analytics?

Os dados de pesquisa são transferidos dos mecanismos de pesquisa por volta de 6:00 no fuso horário de seu Data Center do Analytics. Nesse momento os dados do AMO são coletados e inseridos no conjunto de relatórios. Em seguida, são convertidos para o fuso horário do conjunto de relatórios como parte da inserção de dados no Analytics.

+++

+++ O que pode ser *capturado antes do clique*? Trazemos impressões, custo, posição média etc, mesmo sem o clique?

A ID do AMO capturará as métricas do mecanismo de pesquisa: Impressões, Custo, Cliques, Posição média e Pontuação de qualidade média. Se não houver nenhum clique, mas houver impressões, os dados de impressão/posição/pontuação de qualidade serão enviados para o Analytics. Normalmente, se não houver cliques também não há custo.

+++

+++ Em que nível esses dados estão sendo capturados? *Visitante? Ocorrência?*

As métricas do mecanismo de pesquisa são capturadas no nível de ocorrência e conectadas à ID do AMO (e suas classificações). São dados de nível de resumo e não são conectados a visitas/visitantes. Sendo assim, as métricas do mecanismo de pesquisa só podem ser usadas em segmentos do escopo de nível de ocorrência e que são baseados na ID do AMO (ou em suas classificações).

A ID do AMO também é capturada na página de aterrissagem na ocorrência dessa página (que a conecta à visita/ao visitante) e persiste em downstream para obter crédito de outras métricas do Analytics (até que expire ou seja substituída por uma nova ID do AMO). É totalmente incorporada ao conjunto de dados, como qualquer outra eVar.

+++

+++ Capturamos apenas google.com ou *versões de países* (como google.co.uk, google.it, google.fr ou google.de) também?

A classificação da Plataforma de anúncio captura estes valores: &quot;Google Adwords&quot; e &quot;Bing Ads&quot;. Uma prática recomendada é incluir o código do país como parte do nome das campanhas. Assim é possível filtrar ou segmentar (por exemplo, se todas as campanhas começarem com countrycode_, criar um segmento onde Campanhas (AMO ID) comece com “UK_” fornecerá apenas dados do Reino Unido).

+++

+++ A métrica &quot;Custo AMO&quot; é o custo pago por cada palavra-chave/anúncio, conforme relatado pelo mecanismo de pesquisa. Esse é o Custo líquido ou o Custo bruto?

&quot;Custo AMO&quot; é apenas o custo pago aos mecanismos de pesquisa. Ele não inclui taxas de plataforma para agência ou otimização/gerenciamento de pesquisa.

+++

+++ Há planos para incluir outros canais de publicidade, como *Exibição* ou *Social*?

Não, atualmente não temos planos para esses outros canais no roteiro.

+++


## Rastreamento automático vs. manual {#section_7437C4698A6D482EB7ED94A948390119}

+++ Ao configurar minha conta do Advertising, ele declara que o *rastreamento automático* pode levar a consequências não intencionais. Que tipos de consequências pode ocorrer?

O modo automático tenta anexar parâmetros de URL ao final dos modelos de rastreamento/URLs de destino no formato correto. No entanto, é sua responsabilidade garantir que os parâmetros de URL adicionados persistam corretamente na página inicial final. O modo automático pode inserir palavras-chave ao URL de aterrissagem, e seu servidor da Web pode não ser compatível com palavras-chave com caracteres especiais.

+++

+++ Se eu configurar o Rastreamento manual ou automático inicialmente, posso alternar para o outro modo de rastreamento posteriormente? Quais são as implicações?

Sim, você pode alternar os modos de rastreamento, mas precisa remover a lógica de rastreamento antiga antes de fazer a alteração. Isso pode resultar em inatividade do rastreamento no dia que a alteração for feita (especialmente se estiver mudando do manual para o automático). Assim, recomendamos não alternar, a menos que seja absolutamente necessário.

* Alternância de Manual para Automático: remova as adições manuais aos modelos de rastreamento e alterne a alternância na interface do usuário do Advertising Analytics de manual para Automático e salve a configuração. Observe que pode levar várias horas para que o sistema preencha os códigos de rastreamento automático.

* Alternância de Automático para Manual: atualize a alternância de manual para automático na interface de configuração do Advertising Analytics e implante os códigos de rastreamento manual o mais rápido possível. Ao implantar os códigos de rastreamento manual, se você encontrar os códigos de rastreamento automático nos modelos de rastreamento do mecanismo de pesquisa, remova-os.

+++
