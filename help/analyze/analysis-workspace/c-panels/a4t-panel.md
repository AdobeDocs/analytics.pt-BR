---
description: O painel Análises para Públicos alvos (A4T) permite que você analise suas atividades e experiências do Público alvo da Adobe na área de trabalho da Análise.
title: Painel Análises para Públicos alvos (A4T)
translation-type: tm+mt
source-git-commit: f688748e21b2b494845c682b380b12d3d346bfd3
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 13%

---


# Painel Análises para Públicos alvos (A4T)

>[!IMPORTANT]
>
>**[!UICONTROL O painel Analytics for Público alvo (A4T)]** está atualmente em testes limitados. [Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/landing/an-releases.html)

O painel Análises para Públicos alvos (A4T) permite que você analise suas atividades e experiências do Público alvo da Adobe na área de trabalho da Análise. Ele também permite que você veja incentivo e confiança para até três métricas de sucesso. Para acessar o painel A4T, navegue até um conjunto de relatórios com os componentes A4T ativados. Em seguida, clique no ícone do painel na extremidade esquerda e arraste o painel Analytics for Público alvo para o Projeto da área de trabalho da Análise.

## Construtor de painéis A4T

Você pode configurar o painel A4T usando estas configurações:

| Configuração | Descrição |
|---|---|
| Atividade do Target | Selecione de uma lista de Atividades de Públicos alvos ou arraste e solte uma atividade do painel esquerdo.<br>**Observação:**A lista é preenchida com os últimos 6 meses de atividades que tiveram pelo menos 1 ocorrência. Se não vir uma atividade na lista, pode ter mais de 6 meses. Ainda pode ser adicionado do painel esquerdo, que tem um período de retrospectiva de até 18 meses. |
| Experiência de controle | Selecione sua experiência de controle. Você pode alterá-la, se necessário, na lista suspensa. |
| Métrica de normalização | Escolha entre Visitantes únicos, Visitas ou Impressões de Atividade. visitantes únicos são recomendados para a maioria dos casos de uso de análise. |
| Métricas de sucesso | Selecione até 3 eventos bem-sucedidos padrão (não calculados) nos menus suspensos ou arraste e solte métricas do painel esquerdo. Cada métrica terá uma tabela e uma visualização dedicadas no painel renderizado. |
| Intervalo de datas do calendário | Isso será preenchido automaticamente com base no intervalo de datas da Atividade do Público alvo da Adobe. Você pode alterá-la se necessário. |

![](assets/a4t-panel-builder.png)

## Saída do painel A4T

O painel Análises para Públicos alvos retorna um conjunto avançado de dados e visualizações para ajudá-lo a entender melhor o desempenho da atividade e das experiências do Público alvo da Adobe. Na parte superior do painel, uma linha de resumo é fornecida para lembrá-lo das configurações do painel que você selecionou. A qualquer momento, você pode editar o painel clicando no lápis de edição na parte superior direita.

Para cada métrica de sucesso selecionada, uma tabela de forma livre e uma tendência de taxa de conversão serão mostradas:

![](assets/a4t-rendered.png)

Cada tabela de forma livre mostra as seguintes colunas de métrica:

| Métrica | Descrição |
|---|---|
| Normalização de métricas | Visitantes únicos, visitas ou impressões de Atividade. |
| Métrica de sucesso | A métrica selecionada no construtor |
| Índice de conversão | Métrica de sucesso/Métrica de normalização |
| Aumento | Compara o índice de conversão de cada experiência com a experiência de controle.<br>**Observação:**O incentivo é uma &quot;métrica bloqueada&quot; para as experiências do Público alvo; não pode ser desmembrada nem usada com outras dimensões. |
| Lift (inferior) | Representa o pior aumento que uma experiência de variante poderia ter sobre o controle. |
| Lift (médio) | Representa o aumento do ponto médio que uma experiência de variante poderia ter sobre o controle, em um intervalo de confiança de 95%. Este é o &quot;incentivo&quot; no Relatórios e análises. |
| Lift (superior) | Representa o melhor aumento que uma experiência de variante poderia ter sobre o controle. |
| Confiança | O teste t dos alunos calcula o nível de confiança, o que indica a probabilidade de que os resultados sejam duplicados se o teste for executado novamente. Um intervalo de formatação condicional fixo de 75%/85%/95% foi aplicado à métrica. Essa formatação pode ser personalizada, se necessário, em Configurações de coluna. <br>**Observação:**A confiança é uma &quot;métrica bloqueada&quot; para as experiências do Público alvo da Adobe. Não pode ser desmembrada nem usada com outras dimensões. |

Assim como em qualquer painel da área de trabalho da Análise, você pode continuar com sua análise adicionando tabelas e [visualizações](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) adicionais que ajudarão a analisar suas atividades do Público alvo da Adobe.

## Perguntas frequentes sobre o painel A4T

| Pergunta | Resposta |
|---|---|
| Que tipos de atividade são suportados no A4T? | [Saiba mais](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html) sobre os tipos de atividades suportados. |
| As métricas calculadas são suportadas no relatórios A4T? | Não. [Saiba mais](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) sobre por que as métricas calculadas não são suportadas. |
| Por que os visitantes únicos variam entre o Público alvo e o Analytics? | [Saiba mais](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) sobre as variações de visitantes únicos entre produtos. |

Para obter mais informações sobre o Analytics para relatórios de Públicos alvos, visite o relatórios [A4T](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)
