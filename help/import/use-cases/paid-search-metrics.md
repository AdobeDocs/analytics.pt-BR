---
title: Importar métricas de pesquisa paga
description: Etapas para configurar o Adobe Analytics para monitorar suas métricas de pesquisa paga (por exemplo, Google AdWords, MSN, Yahoo etc.) usando Fontes de dados.
exl-id: b25a2a26-d277-4a51-9194-973acb425095
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 100%

---

# Importar métricas de [!UICONTROL Pesquisa paga] usando [!UICONTROL Fontes de dados]

Para muitas organizações de marketing, a pesquisa paga é uma das maneiras mais valiosas e confiáveis de alcançar novos clientes e manter os existentes. O recurso [!UICONTROL Fontes de dados] no Adobe Analytics facilita a importação de dados avançados de pesquisa paga de plataformas de publicidade digital, como o Google AdWords. É possível integrá-los ao restante dos dados de marketing, junto com dados comportamentais no site e de atributos do cliente, para permitir melhores insights sobre os esforços de pesquisa paga da organização.

Essas etapas mostram como configurar uma integração com o AdWords para importar dados de palavras-chave, além de métricas como impressões, cliques, custo por clique e muito mais.

As etapas explicam como configurar uma importação única de dados pay-per-click. No entanto, [!UICONTROL Fontes de dados] permitem a importação contínua de dados usando o formato de arquivo descrito aqui. Dependendo da sua plataforma de pesquisa paga, você poderá agendar exportações periódicas (diariamente, mensalmente etc.) e configurar processos automatizados para transformar essas exportações no formato de arquivo exigido pela Adobe Analytics. Também poderá fazer upload desses arquivos no Adobe Analytics para relatórios de integração de pesquisa paga em andamento.

## Pré-requisitos

* Você implementou a detecção de pesquisa paga.
* Você está capturando dados do código de rastreamento.
* Você tem códigos de rastreamento exclusivos para cada Grupo de publicidade.

## Configurar [!UICONTROL eventos bem-sucedidos]

Nosso primeiro passo é preparar o Adobe Analytics para receber as métricas. Para fazer isso, você precisa configurar alguns eventos bem-sucedidos.

[!UICONTROL Eventos bem-sucedidos] são ações que podem ser rastreadas. Você determina o que é um [!UICONTROL evento bem-sucedido]. Para fins de métricas de rastreamento de [!UICONTROL pesquisa paga], é desejável configurar [!UICONTROL eventos bem-sucedidos] em torno de [!UICONTROL cliques], [!UICONTROL impressões] e [!UICONTROL custo total], e ativar [!UICONTROL códigos de rastreamento].

1. Vá para **[!UICONTROL Adobe Analytics > Administrador > Conjuntos de relatórios]**.
1. Selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações > Conversão > Eventos bem-sucedidos]**.

   ![Eventos bem-sucedidos](assets/success-events.png)

1. Em Eventos bem-sucedidos personalizados, use **[!UICONTROL Adicionar novo]** para criar três eventos bem-sucedidos personalizados: [!UICONTROL Cliques] (Contador), [!UICONTROL Impressões] (Contador) e [!UICONTROL Custo total] (Moeda).

   ![Novo evento bem-sucedido](assets/new-success-events.png)

1. Clique em Salvar.
Você deve receber uma mensagem informando que seus salvamentos foram aprovados.
1. Navegue até **[!UICONTROL Administrador > Conjuntos de relatórios > Editar configurações > Conversão > Variáveis de conversão]**.
1. Ative os códigos de rastreamento marcando a caixa de seleção ao lado de **[!UICONTROL Código de rastreamento]** em **[!UICONTROL Campanha > Variável de campanha]**.

   ![Variável de campanha](assets/campaign-variable.png)

## Configurar Fontes de dados

[!UICONTROL Fontes de dados] permitem compartilhar dados com o Adobe Analytics que não ssejam de sequência de cliques. Nesse caso, usamos o Adobe Analytics para rastrear métricas de pesquisa paga. Usamos o código de rastreamento como nossa chave para unir os dois dados - métricas de pesquisa paga e métricas do Adobe Analytics.

1. Navegue até **[!UICONTROL Adobe Analytics > Administrador > Todos os administradores > Fontes de dados]**.
1. Selecione a guia **[!UICONTROL Criar]** para começar a ativar novas fontes de dados.
1. Em **[!UICONTROL Selecionar categoria]**, selecione **[!UICONTROL Campanha publicitária]**.

   ![Fontes de dados](assets/data-sources.png)

1. Em **[!UICONTROL Selecionar tipo]**, selecione **[!UICONTROL Serviço pay-per-click genérico]**.
1. Clique em **[!UICONTROL Ativar]**.
O [!UICONTROL Assistente de ativação da Fonte de dados] exibe:

   ![Assistente de ativação](assets/ds-activation-wizard.png)

1. Clique em **[!UICONTROL Próximo]** e nomeie a fonte de dados. Este nome aparecerá no Gerenciador de fonte de dados.
1. Aceite o contrato de serviço e clique em **[!UICONTROL Próximo]**.
1. Selecione as três métricas padrão: [!UICONTROL Impressões], [!UICONTROL Cliques] e [!UICONTROL Custo total] e clique em **[!UICONTROL Próximo]**.
1. Agora “mapeie” esta nova fonte de dados para os eventos personalizados que criamos em [Configurar eventos bem-sucedidos](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/t-success-events.md).

   ![Mapeamento](assets/data-source-mapping.png)

1. Escolha as dimensões de dados
Marque a caixa ao lado de Códigos de rastreamento e clique em **[!UICONTROL Próximo]**.
1. Mapear dimensões de dados.
Mapeie a dimensão de dados importada (atributo) para o atributo do Adobe Analytics no qual você deseja armazená-la. Pode ser uma dimensão padrão ou um eVar. Depois de clicar em **[!UICONTROL Próximo]**, os mapeamentos resultantes são mostrados no resumo:

   ![Resumo](assets/data-source-summary.png)

1. Clique em **[!UICONTROL Salvar]**.
1. Clique em **[!UICONTROL Baixar]** para baixar o arquivo de modelo para essa fonte de dados.
O nome do arquivo corresponde ao tipo de fonte de dados especificado inicialmente — neste caso, &quot;Modelo de serviço de pagamento por clique genérico.txt&quot;.
1. Abra o modelo em seu editor de texto favorito.
O arquivo já está preenchido com as métricas e dimensões e seus mapeamentos.

## Exportar dados PPC e carregá-los no Analytics

Etapas semelhantes a essas funcionam para o Google Adwords, MSN, Yahoo e outras contas PPC.

### Exportar dados

1. Faça logon em sua conta PPC e crie um novo relatório ou exportação.
Certifique-se de que a exportação inclua os seguintes campos: data, URL de destino (página de aterrissagem), impressões, cliques e custo. A exportação pode incluir outros campos, mas você os excluirá das etapas abaixo.
1. Se possível, salve o relatório como um `.csv` ou arquivo delimitado por tabulação. Isso facilitará o trabalho com ele nas etapas a seguir.
1. Abra o arquivo no Microsoft Excel.

### Editar o arquivo no Microsoft Excel

1. No Microsoft Excel, exclua todas as colunas exceto aquelas mencionadas acima.
1. Exclua quaisquer linhas extras na parte superior.
1. Para isolar os códigos de rastreamento dos URLs de destino:
a. Copie e cole dados de todas as colunas.
b. Clique em **[!UICONTROL Dados > Texto para colunas]**.
c. Na Etapa 1 do assistente, certifique-se que **[!UICONTROL Delimitado]** esteja selecionado e clique em **[!UICONTROL Próximo]**.
d. Na Etapa 2 do assistente, especifique o delimitador dependendo de como você criou seus URLs (seja ? ou &amp;) e clique em **[!UICONTROL Próximo]**.
e. Na Etapa 3 do assistente, visualize seus dados e verifique se uma das colunas é &quot;trackingcodename=trackingcode&quot;. Se você tiver variáveis adicionais, repita essas etapas (usando &amp; como delimitador).
f. Exclua todas as colunas, exceto códigos de rastreamento, impressões, cliques e custo. Adicione uma nova coluna chamada Data e organize suas colunas na seguinte ordem: Data :: Código de rastreamento :: Impressões :: Cliques :: Custo.
1. Adicione esses dados ao modelo que você baixou na seção &quot;Configurar fontes de dados&quot; acima.
Agora você está pronto para fazer upload do arquivo.

### Fazer upload do arquivo para o Adobe Analytics pelo FTP

Retorne ao assistente da Fonte de dados para obter instruções e faça upload do arquivo pelo FTP:

![Fazer upload do FTP](assets/upload-ftp.png)

## Criar métricas calculadas

Adicionar métricas calculadas será útil ao tomar decisões de pagamento por clique.

Por exemplo, você poderia adicionar estas [métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=pt-BR#calculated-metrics):

| Nome | Fórmula | Tipo de métrica | Descrição |
| --- | --- | --- | --- |
| Exibições de página por visita | Exibições de página/visitas | Numérico | Quando aplicado no nível de site: mostra o número médio de páginas por visita. Quando aplicado no relatório Páginas mais populares: exibe o número médio de vezes que uma página foi visualizada por visita. |
| Valor médio de pedido | Receita/pedidos | Moeda | Exibe a receita média por pedido. |
| Receita por visita | Receita/visita | Moeda | Exibe a receita média por visita. |
| Índice de click-through (CTR) | Cliques/impressões | Numérico | Medir a proporção de cliques para impressões de um anúncio online ou campanha de marketing por email. |
| Lucro | Receita - Custo | Moeda | Mostra a receita de uma campanha menos o custo. |
| Lucro por Impressão (PPI) | (Receita - Custo)/Impressão | Moeda | Mostra quanta receita foi gerada sempre que um anúncio foi exibido, balanceado com o custo. |
| Retorno do investimento em publicidade (ROAS) | Valor de vendas/despesa com publicidade | Moeda | (ROI) Representa os dólares ganhos por dólares gastos na publicidade correspondente. |

## Configurar e executar relatórios

A etapa final é adicionar as métricas da fonte de dados e qualquer métrica calculada ao relatório do Código de rastreamento e detalhar uma campanha para obter uma visualização imediata do desempenho de cada Grupo de publicidade.

1. Em **[!UICONTROL Adobe Analytics > Relatórios]**, selecione o conjunto de relatórios no qual você importou fontes de dados.
1. Navegar para **[!UICONTROL Relatórios > Campanhas > Código de rastreamento > Código de rastreamento]**.
1. Selecione o intervalo de datas.
1. Clique em **[!UICONTROL Métricas > Adicionar]** e adicione suas métricas de fonte de dados (cliques, impressões, custo total) da lista de Métricas padrão.
1. Faça o mesmo para qualquer métrica calculada que tenha adicionado. O relatório será atualizado à medida que você adiciona métricas.
