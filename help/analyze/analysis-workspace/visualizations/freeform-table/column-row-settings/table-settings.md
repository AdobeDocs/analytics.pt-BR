---
description: As configurações de linha variam de acordo com qual componente foi arrastado para a tabela.
title: Configurações de linha
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
feature: Tabelas de forma livre
role: User, Admin
exl-id: 9057e930-b4c6-439e-b82a-8ab9828de91d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: ht
source-wordcount: '392'
ht-degree: 100%

---

# Configurações de linha

As configurações de linha variam de acordo com qual componente foi arrastado para a tabela. Para acessar as configurações das linhas da tabela, clique o ícone de Configuração próximo a uma dimensão, segmento, métrica, período de tempo ou um detalhamento em cada uma dessas:

![](assets/row-settings.png)

| Configuração | Descrição |
|--- |--- |
| Alinhar datas | Esta é uma configuração em nível de tabela que alinha as datas de cada coluna para que todas comecem na mesma linha. O alinhamento de datas é ativado por padrão quando uma dimensão de tempo é usada nas linhas da tabela e intervalos de datas diferentes são aplicados nas colunas. Por exemplo, em uma tabela diária com outubro e setembro aplicados às colunas, a coluna da esquerda começa com 1º de outubro e a coluna da direita começa com 1º de setembro. |
| Detalhamento por posição | Por padrão, essa configuração é desativada e os detalhamentos são corrigidos em itens de linha estáticos. Por exemplo, vamos supor que você detalhe os 3 principais itens de dimensão de Página (Página inicial, Resultados de pesquisa, Check-out) por Canal de marketing. Você sai do projeto e retorna duas semanas depois. Ao abrir o projeto novamente, as 3 principais páginas foram alteradas e, agora, a Página inicial, os Resultados da pesquisa e o Check-out são as 4 a 6 principais páginas. Por padrão, os detalhamentos do Canal de marketing ainda aparecerão em Página inicial, Resultados de pesquisa e Check-out, mesmo que agora estejam nas linhas 4 a 6. <br> Por outro lado, o **Detalhamento por posição** sempre detalhará os 3 itens principais, independentemente de quais eles sejam. Voltando ao nosso exemplo, quando você reabrir o projeto, os detalhamentos do Canal de marketing serão vinculados às 3 principais páginas da tabela, não à Página inicial, aos Resultados de pesquisa e ao Check-out que estão agora nas linhas 4 a 6. |
| Porcentagens | **Calcular porcentagens por coluna** é a configuração padrão; as porcentagens visíveis em uma coluna são calculadas com base no total da coluna. <br>**Calcular porcentagem por linha** força a tabela de forma livre a calcular as porcentagens de células na linha e não na coluna, com o total geral como denominador. Essa configuração é útil para porcentagens de tendência. Essa configuração é ativada por padrão ao usar o ícone Visualizar. |
| Totais de colunas | Essas configurações estão disponíveis somente para [linhas estáticas](manual-vs-dynamic-rows.md). <br> **Mostrar a soma das linhas atuais**: mostra uma soma do lado do cliente das linhas na tabela, o que significa que o total *não* deduplicará métricas como visitas ou visitantes. <br> **Mostrar total geral** mostra uma soma do lado do servidor, o que significa que o total deduplicará as métricas. |
