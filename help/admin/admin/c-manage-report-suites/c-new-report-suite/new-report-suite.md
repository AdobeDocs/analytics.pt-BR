---
description: Você pode criar um novo conjunto de relatórios selecionando um modelo predefinido ou usando um de seus conjunto de relatórios existentes para servir como modelo geral.
title: Configurações do novo conjunto de relatórios
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
source-git-commit: 8c0e88a22928d79599ab0a0ad3efc8159712d739
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 95%

---

# Configurações do novo conjunto de relatórios

Você pode criar um novo conjunto de relatórios selecionando um modelo predefinido ou usando um de seus conjunto de relatórios existentes para servir como modelo geral.

Descrições dos elementos usados ao [criar um conjunto de relatórios](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>A [documentação dos conjuntos de relatórios virtuais](/help/components/vrs/c-workflow-vrs/vrs-create.md) mostra como criá-los.

| Elemento | Descrição |
| --- | --- |
| ID do conjunto de relatórios | Especifica uma ID única que pode conter somente caracteres alfanuméricos. Essa ID não pode ser alterada depois de criada. A Adobe define o prefixo da ID necessário e ele não pode ser alterado.  Ao criar vários conjunto de relatórios, certifique-se de que a convenção de nomeação que usar garanta IDs de conjunto de relatórios únicas. |
| Título do site | Identifica o conjunto de relatórios em Ferramentas administrativas. Esse título também é usado na lista suspensa do Conjunto de relatórios, no cabeçalho do conjunto. |
| Fuso horário | Programa eventos e dados de carimbo de data e hora. |
| URL básica | (Opcional) Define o domínio básico do conjunto de relatórios. Este URL funciona como um filtro interno do URL se você não definir explicitamente os filtros internos do URL do conjunto de relatórios. |
| Página padrão | (Opcional) elimina dos URLs encontrados as ocorrências do valor Página padrão. Se seu relatório Páginas mais populares contiver URLs em vez de nomes de páginas, esta configuração impedirá que haja vários URLs para a mesma página da Web.  Por exemplo, os URLs `https://example.com` e `https://example.com/index.html` normalmente são a mesma página.<p> Você pode remover nomes de arquivo irrelevantes, de modo que esses dois URLs sejam exibidos como `https://example.com` em seus relatórios. Se você não definir esse valor, o Analytics removerá automaticamente os seguintes nomes de arquivos dos URLs: `index.htm`, `index.html`, `index.cgi`, `index.asp`, `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi`, e `home.asp`. Para desativar a eliminação dos nomes de arquivo, especifique um valor para Página padrão que nunca ocorra em seus URLs. |
| Data de ativação | Informa a Adobe quanto à data em que você espera que este conjunto de relatórios fique ativo. Se sua programação de implantação for alterada, forneça uma estimativa de tráfego atualizada usando a ferramenta Tráfego esperado permanente em Gerenciamento do tráfego. |
| Exibições de página estimadas por dia | Identifica o número estimado de Exibições de página a que você espera que este conjunto de relatórios preste suporte em um dia. Grandes volumes de tráfego requerem um processo de aprovação mais longo. Para evitar atrasos no processamento, seja tão preciso quanto possível com relação a esta estimativa. |
| Moeda de base | Especifica a moeda padrão usada para armazenar todos os dados monetários. O Analytics converte as transações em outras moedas para a moeda de base usando a taxa de conversão atual no momento em que recebe os dados. Os relatórios do Analytics usam a variável de JavaScript “currencyCode” para identificar a moeda de uma determinada transação. |
| Habilitar o processamento de palavras-chave em japonês | Habilita o suporte de caractere multibyte para o conjunto de relatórios. Se você desativar o suporte de caractere multibyte, o sistema partirá do princípio de que os dados estão no formato `ISO-8859-1`. As páginas da Web precisam especificar seu conjunto de caracteres na variável de JavaScript “charSet”. <p>O suporte a caracteres multibyte armazena caracteres no conjunto de relatórios usando UTF-8. No recebimento, o sistema converte os dados do conjunto de caracteres de sua página da Web para o conjunto de caracteres UTF-8, de modo a permitir o uso de qualquer idioma em seus relatórios de marketing.  Entre em contato com a equipe de contas ou o atendimento ao cliente da Adobe para alterar o suporte a caracteres multibyte de um conjunto de relatórios existente. |
| Usar menu de navegação simplificado | Este recurso fazia parte do [Reports &amp; Analytics](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?), que não tem mais suporte. |

{style="table-layout:auto"}
