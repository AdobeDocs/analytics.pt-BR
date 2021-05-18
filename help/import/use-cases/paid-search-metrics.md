---
title: Importar métricas de pesquisa paga
description: Etapas para configurar o Adobe Analytics para rastrear suas métricas de pesquisa paga (por exemplo, Google AdWords, MSN, Yahoo etc.) uso das Fontes de dados.
exl-id: b25a2a26-d277-4a51-9194-973acb425095
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 8%

---

# Importe métricas de [!UICONTROL Pesquisa paga] usando [!UICONTROL Fontes de dados]

Para muitas organizações de marketing, a pesquisa paga é uma das maneiras mais valiosas e confiáveis &#x200B; alcançar novos clientes e manter os existentes. O recurso [!UICONTROL Data Sources] no Adobe Analytics facilita a importação de dados de pesquisa paga avançados de plataformas de publicidade digital como o Google AdWords. É possível integrá-lo ao restante dos dados de marketing, junto com dados comportamentais no site e de atributos do cliente, para permitir melhores insights sobre os esforços de pesquisa paga da organização.

Essas etapas mostram como configurar uma integração com o AdWords para importar dados de palavras-chave, bem como métricas como impressões, cliques, custo por clique e muito mais.

As etapas explicam como configurar uma importação única de dados por clique. No entanto, [!UICONTROL Fontes de Dados] permite a importação contínua de dados usando o formato de arquivo descrito aqui. Dependendo da sua plataforma de pesquisa paga, você pode agendar exportações periódicas (diariamente, mensalmente etc.), configurar processos automatizados para transformar essas exportações no formato de arquivo necessário pela Adobe Analytics e fazer upload desses arquivos no Adobe Analytics para relatórios de integração de pesquisa paga.

## Pré-requisitos

* Você implementou a detecção de pesquisa paga.
* Você está capturando dados do código de rastreamento.
* Você tem códigos de rastreamento exclusivos para cada Grupo de anúncios.

## Configurar [!UICONTROL Eventos bem-sucedidos]

Nosso primeiro passo é preparar o Adobe Analytics para receber as métricas. Para fazer isso, você precisa configurar alguns eventos bem-sucedidos.

[!UICONTROL Eventos bem-sucedidos são ações que podem ser rastreadas. ] Você determina o que é um [!UICONTROL evento bem-sucedido]. Para nosso objetivo de rastrear métricas de [!UICONTROL pesquisa paga], queremos configurar [!UICONTROL eventos bem-sucedidos] em torno de [!UICONTROL cliques], [!UICONTROL impressões], [!UICONTROL custo total] e ativar[!UICONTROL códigos de rastreamento].

1. Vá para **[!UICONTROL Adobe Analytics > Admin > Conjuntos de relatórios]**.
1. Selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações > Conversão > Eventos bem-sucedidos]**.

   ![Eventos bem-sucedidos](assets/success-events.png)

1. Em Eventos bem-sucedidos personalizados, use **[!UICONTROL Adicionar novo]** para criar três eventos bem-sucedidos personalizados: [!UICONTROL Cliques] (Contador), [!UICONTROL Impressões] (Contador) e [!UICONTROL Custo Total] (Moeda).

   ![Novo evento bem-sucedido](assets/new-success-events.png)

1. Clique em Salvar.
Você deve receber uma mensagem informando que seus salvamentos foram aprovados.
1. Navegue até **[!UICONTROL Admin > Conjuntos de relatórios > Editar configurações > Conversão > Variáveis de conversão]**.
1. Ative os códigos de rastreamento marcando a caixa de seleção ao lado de **[!UICONTROL Código de rastreamento]** em **[!UICONTROL Campanha > Variável de campanha]**.

   ![Variável da campanha](assets/campaign-variable.png)

## Configurar fontes de dados

[!UICONTROL As ] Fontes de dados permitem que você compartilhe dados que não são de sequência de cliques com o Adobe Analytics. Nesse caso, usamos o Adobe Analytics para rastrear métricas de pesquisa paga. Usamos o código de rastreamento como nossa chave para unir os dois dados - métricas de pesquisa paga e métricas do Adobe Analytics.

1. Navegue até **[!UICONTROL Adobe Analytics > Admin > Todos os administradores > Fontes de dados]**.
1. Selecione a guia **[!UICONTROL Create]** para começar a ativar novas fontes de dados.
1. Em **[!UICONTROL Selecionar Categoria]**, selecione **[!UICONTROL Campanha de publicidade]**.

   ![Fontes de dados](assets/data-sources.png)

1. Em **[!UICONTROL Selecionar Tipo]**, selecione **[!UICONTROL Serviço Pay-Per-Click Genérico]**.
1. Clique em **[!UICONTROL Ativar]**.
O [!UICONTROL Assistente de Ativação da Fonte de Dados] exibe:

   ![Assistente de ativação](assets/ds-activation-wizard.png)

1. Clique em **[!UICONTROL Next]** e nomeie a fonte de dados. Esse nome aparece no Gerenciador da Fonte de Dados.
1. Aceite o contrato de serviço e clique em **[!UICONTROL Next]**.
1. Selecione as três métricas padrão: [!UICONTROL Impressões], [!UICONTROL Cliques] e [!UICONTROL Custo Total] e clique em **[!UICONTROL Seguinte]**.
1. Agora, &quot;mapeie&quot; essa nova fonte de dados para os eventos personalizados que criamos em [Configurar eventos bem-sucedidos](/help/admin/admin/c-success-events/t-success-events.md).

   ![Mapeamento](assets/data-source-mapping.png)

1. Escolher dimensões de dados
Marque a caixa ao lado de Códigos de rastreamento e clique em **[!UICONTROL Próximo]**.
1. Mapear Dimension de dados.
Mapeie a dimensão de dados importada (atributo) para o atributo do Adobe Analytics no qual você deseja armazená-la. Pode ser uma dimensão padrão ou um eVar. Depois de clicar em **[!UICONTROL Next]**, os mapeamentos resultantes são mostrados no resumo:

   ![Resumo](assets/data-source-summary.png)

1. Clique em **[!UICONTROL Salvar]**.
1. Clique em **[!UICONTROL Download]** para baixar o arquivo de modelo para essa fonte de dados.
O nome do arquivo corresponde ao tipo de fonte de dados especificado inicialmente - neste caso, &quot;Generic Pay-Per-Click Service template.txt&quot;.
1. Abra o modelo no editor de texto favorito.
O arquivo já está preenchido com as métricas e dimensões e seus mapeamentos.

## Exportar dados PPC e carregá-los no Analytics

Etapas semelhantes a esses trabalhos para o Google Adwords, MSN, Yahoo e outras contas PPC.

### Exportar dados

1. Faça logon em sua conta PPC e crie um novo relatório ou exportação.
Certifique-se de que a exportação inclua os seguintes campos: data, URL de destino (página de aterrissagem), impressões, cliques e custo. A exportação pode incluir outros campos, mas você os excluirá das etapas abaixo.
1. Se possível, salve o relatório como um arquivo `.csv` ou delimitado por tabulação. Isso facilitará o trabalho com o nas etapas a seguir.
1. Abra o arquivo no Microsoft Excel.

### Editar o arquivo no Microsoft Excel

1. No Microsoft Excel, exclua todas as colunas além das mencionadas acima.
1. Exclua quaisquer linhas extras na parte superior.
1. Para isolar os códigos de rastreamento dos URLs de destino:
a. Copie e cole dados de todas as colunas.
b. Clique em **[!UICONTROL Data > Texto para Colunas]**.
c. Na Etapa 1 do assistente, verifique se **[!UICONTROL Delimitado]** está selecionado e clique em **[!UICONTROL Próximo]**.
d. Na Etapa 2 do assistente, especifique o delimitador dependendo de como você criou seus URLs (ou ? ou &amp;) e clique em **[!UICONTROL Next]**.
e. Na Etapa 3 do assistente, visualize seus dados e verifique se uma das colunas é &quot;trackingcodename=trackingcode&quot;. Se você tiver variáveis adicionais, repita essas etapas (usando &amp; como delimitador).
f. Exclua todas as colunas, exceto códigos de rastreamento, impressões, cliques e custo. Adicione uma nova coluna chamada Date e organize suas colunas na seguinte ordem: Data : Código de rastreamento : Impressões : Cliques : Custo.
1. Adicione esses dados ao modelo que você baixou na seção &quot;Configurar fontes de dados&quot; acima.
Agora você está pronto para fazer upload do arquivo.

### Fazer upload do arquivo para a Adobe Analytics via FTP

Retorne ao assistente da Fonte de Dados para obter instruções e faça upload do arquivo via FTP:

![Fazer upload do FTP](assets/upload-ftp.png)

## Criar métricas calculadas

Adicionar métricas calculadas será útil ao tomar decisões de pagamento por clique.

Por exemplo, você pode adicionar essas [métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=en#calculated-metrics):

| Nome | Fórmula | Tipo de métrica | Descrição |
| --- | --- | --- | --- |
| Exibições de página por visita | Exibições de página/visitas | Numérico | Quando aplicado no nível de site: mostra o número médio de páginas por visita. Quando aplicado no relatório Páginas mais populares: exibe o número médio de vezes que uma página foi visualizada por visita. |
| Valor médio de pedido | Receita/pedidos | Moeda | Exibe a receita média por pedido. |
| Receita por visita | Receita/visita | Moeda | Mostra a receita média por visita. |
| Índice de click-through (CTR) | Cliques/impressões | Numérico | Meça a proporção de cliques para impressões de um anúncio online ou campanha de marketing por email. |
| Lucro | Receita - Custo | Moeda | Mostra a receita de uma campanha menos o custo. |
| Lucro por Impressão (PPI) | (Receita - Custo)/Impressão | Moeda | Mostra quanta receita foi gerada sempre que um anúncio foi exibido, balanceado com o custo. |
| Retorno da despesa de anúncio (ROAS) | Valor de vendas/gasto com anúncio | Moeda | (ROI) Representa os dólares ganhos por dólares gastos na publicidade correspondente. |

## Configurar e executar relatórios

A etapa final é adicionar as métricas da fonte de dados e qualquer métrica calculada ao relatório do Código de rastreamento e detalhar uma campanha para obter uma visualização imediata do desempenho de cada Grupo de anúncios.

1. Em **[!UICONTROL Adobe Analytics > Relatórios]**, selecione o conjunto de relatórios no qual você importou fontes de dados.
1. Navegue até **[!UICONTROL Relatórios > Campanhas > Código de rastreamento > Código de rastreamento]**.
1. Selecione o intervalo de datas.
1. Clique em **[!UICONTROL Métricas > Adicionar]** e adicione suas métricas de fonte de dados (Cliques, Impressões, Custo total) da lista de Métricas padrão.
1. Faça o mesmo para qualquer métrica calculada que tenha adicionado. O relatório será atualizado à medida que você adiciona métricas.
