---
description: Você pode criar um novo conjunto de relatórios selecionando um modelo predefinido ou usando um de seus conjunto de relatórios existentes para servir como modelo geral.
title: Configurações do novo conjunto de relatórios
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
TQID: https://experienceleague.adobe.com/9wZ2rIgzZtJduhFAx6XcD53H2qzB2SZMr0pbxCopBvk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: f52db89b-2666-4cad-9c50-9da4d3ffcfd0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 541
ht-degree: 73%

---

# Configurações do novo conjunto de relatórios

Você pode criar um novo conjunto de relatórios selecionando um modelo predefinido ou usando um de seus conjunto de relatórios existentes para servir como modelo geral.

Descrições dos elementos usados ao [criar um conjunto de relatórios](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md).

>[!NOTE]
>
>A [documentação dos conjuntos de relatórios virtuais](/help/components/vrs/c-workflow-vrs/vrs-create.md) mostra como criá-los.

| Elemento | Descrição |
| --- | --- |
| ID do conjunto de relatórios | Especifica uma ID exclusiva que pode conter somente caracteres alfanuméricos. Essa ID não pode ser alterada após ser criada. A Adobe define o prefixo da ID necessário e ele não pode ser alterado.  Ao criar vários conjunto de relatórios, certifique-se de que a convenção de nomeação que usar garanta IDs de conjunto de relatórios únicas. |
| Título do site | Identifica o conjunto de relatórios em Ferramentas administrativas. Esse título também é usado na lista suspensa do Conjunto de relatórios, no cabeçalho do conjunto. |
| Fuso horário | Programa eventos e dados de carimbo de data e hora. |
| URL básica | (Opcional) Define o domínio básico do conjunto de relatórios. Esse URL funciona como um filtro de URL interno se você não definir explicitamente filtros de URL internos para o conjunto de relatórios. |
| Página padrão | (Opcional) elimina dos URLs encontrados as ocorrências do valor Página padrão. Se seu relatório Páginas mais populares contiver URLs em vez de nomes de páginas, esta configuração impedirá que haja vários URLs para a mesma página da Web.  Por exemplo, os URLs `https://example.com` e `https://example.com/index.html` normalmente são a mesma página.<p> Você pode remover nomes de arquivo irrelevantes, de modo que esses dois URLs sejam exibidos como `https://example.com` em seus relatórios. Se você não definir esse valor, o Analytics removerá automaticamente os seguintes nomes de arquivos dos URLs: `index.htm`, `index.html`, `index.cgi`, `index.asp`, `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi`, e `home.asp`. Para desativar a remoção de nome de arquivo, especifique um valor de Página padrão que nunca ocorra em seus URLs. |
| Data de ativação | Informa o Adobe da data em que você espera que esse conjunto de relatórios se torne ativo. Se sua programação de implantação for alterada, forneça uma estimativa de tráfego atualizada usando a ferramenta Tráfego esperado permanente em Gerenciamento do tráfego. |
| Exibições de página estimadas por dia | Identifica o número estimado de exibições de página que você espera que esse conjunto de relatórios dê suporte em um dia. Grandes volumes de tráfego exigem um processo de aprovação mais longo. Para evitar atrasos de processamento, seja o mais preciso possível com essa estimativa. |
| Moeda de base | Especifica a moeda padrão usada para armazenar todos os dados monetários. O Analytics converte as transações em outras moedas para a moeda de base usando a taxa de conversão atual no momento em que recebe os dados. Os relatórios do Analytics usam a variável de JavaScript “currencyCode” para identificar a moeda de uma determinada transação. |
| Habilitar o processamento de palavras-chave em japonês | Habilita o suporte de caractere multibyte para o conjunto de relatórios. Se você desativar o suporte de caractere multibyte, o sistema partirá do princípio de que os dados estão no formato `ISO-8859-1`. As páginas da Web precisam especificar seu conjunto de caracteres na variável de JavaScript “charSet”. <p>O suporte a caracteres multibyte armazena caracteres no conjunto de relatórios usando UTF-8. No recebimento, o sistema converte os dados do conjunto de caracteres de sua página da Web para o conjunto de caracteres UTF-8, de modo a permitir o uso de qualquer idioma em seus relatórios de marketing.  Entre em contato com a equipe de contas ou o atendimento ao cliente da Adobe para alterar o suporte a caracteres multibyte de um conjunto de relatórios existente. |
| Use o menu de navegação simplificado | Este recurso fazia parte do [Reports &amp; Analytics](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?), que não tem mais suporte. |

{style="table-layout:auto"}
