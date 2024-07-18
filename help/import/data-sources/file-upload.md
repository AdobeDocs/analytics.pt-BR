---
title: Carregar arquivo de fontes de dados no Adobe
description: O processo para carregar um arquivo de fontes de dados no Adobe Analytics para assimilação.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 1%

---

# Carregar arquivo de fontes de dados no Adobe

O envio de um arquivo de fontes de dados para o Adobe envolve um fluxo de trabalho de FTP autenticado típico. Você pode usar o Windows Explorer, Finder ou um cliente FTP dedicado para fazer upload dos arquivos desejados no local FTP do Adobe.

Localize as credenciais de FTP no [Gerenciador de fontes de dados](manage.md). Cada fonte de dados tem um link para suas **[!UICONTROL Informações de FTP]**. Cada local FTP é dedicado a essa fonte de dados específica; não é possível usar o mesmo local FTP para várias fontes de dados.

Por motivos de segurança, os locais FTP sem nenhuma atividade por mais de 30 dias são desativados.

## O arquivo `.fin`

Uma parte essencial da assimilação bem-sucedida de um arquivo de fontes de dados é a inclusão de um arquivo `.fin`. Esse arquivo indica ao Adobe que o arquivo de dados está pronto para processamento. Se você carregar um arquivo de fontes de dados sem um arquivo `.fin` correspondente, o Adobe nunca processará esses dados.

O arquivo `.fin` tem as seguintes propriedades:

* O arquivo tem uma extensão `.fin`. Verifique se o seu sistema operacional permite que você veja e edite tipos de arquivos.
* O arquivo está vazio. Não armazene dados dentro do arquivo `.fin`.
* O arquivo tem exatamente o mesmo nome do arquivo de fontes de dados. Por exemplo, se você carregar um arquivo de fontes de dados chamado `example.txt`, o arquivo `.fin` **deverá** ser nomeado como `example.fin`. Se não tiverem nomes idênticos, o Adobe nunca processará o arquivo de fontes de dados.

Depois que o arquivo de fonte de dados e o arquivo `.fin` forem carregados no site FTP, o Adobe processará o arquivo. Não carregue o arquivo `.fin` até que o arquivo das fontes de dados seja carregado completamente. Se o arquivo `.fin` for carregado prematuramente, o Adobe recuperará e assimilará o arquivo parcialmente carregado, gerando possíveis erros.

## Processamento do pedido

Se você fizer upload de vários arquivos ao mesmo tempo no site FTP, o Adobe os assimilará em ordem alfanumérica. Se sua organização exigir que os arquivos sejam assimilados em uma ordem específica, verifique se os nomes dos arquivos são nomeados alfanumericamente.

## Tempo de processamento

Para garantir o processamento mais rápido de arquivos, a Adobe recomenda agregar dados de métrica em uma única linha por data. Por exemplo, esse arquivo de fontes de dados, embora válido, seria processado mais lentamente:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | | `1` | |
| `07/24/YYYY` | `red` | | | `1` |

Esse arquivo seria processado mais rápido, que contém os mesmos dados:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
