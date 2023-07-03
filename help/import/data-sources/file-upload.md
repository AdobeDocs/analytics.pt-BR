---
title: Carregar arquivo de fontes de dados no Adobe
description: O processo para carregar um arquivo de fontes de dados no Adobe Analytics para assimilação.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# Carregar arquivo de fontes de dados no Adobe

O envio de um arquivo de fontes de dados para o Adobe envolve um fluxo de trabalho de FTP autenticado típico. Você pode usar o Windows Explorer, Finder ou um cliente FTP dedicado para fazer upload dos arquivos desejados no local FTP do Adobe.

Localize as credenciais FTP na [Gerenciador de fontes de dados](manage.md). Cada fonte de dados tem um link para sua **[!UICONTROL Informações de FTP]**. Cada local FTP é dedicado a essa fonte de dados específica; não é possível usar o mesmo local FTP para várias fontes de dados.

Por motivos de segurança, os locais FTP sem nenhuma atividade por mais de 30 dias são desativados.

## A variável `.fin` arquivo

Uma parte vital da assimilação bem-sucedida de um arquivo de fontes de dados é a inclusão de um `.fin` arquivo. Esse arquivo indica ao Adobe que o arquivo de dados está pronto para processamento. Se você fizer upload de um arquivo de fontes de dados sem um arquivo `.fin` arquivo, o Adobe nunca processa esses dados.

A variável `.fin` O arquivo tem as seguintes propriedades:

* O arquivo tem um `.fin` extensão. Verifique se o seu sistema operacional permite que você veja e edite tipos de arquivos.
* O arquivo está vazio. Não armazene dados dentro do `.fin` arquivo.
* O arquivo tem exatamente o mesmo nome do arquivo de fontes de dados. Por exemplo, se você fizer upload de um arquivo de fontes de dados chamado `example.txt`, o `.fin` arquivo **deve** ser nomeado `example.fin`. Se não tiverem nomes idênticos, o Adobe nunca processará o arquivo de fontes de dados.

Quando o arquivo de origem de dados e `.fin` forem carregados no site FTP, o Adobe processará o arquivo. Não carregue o `.fin` até que o arquivo de fontes de dados seja totalmente carregado. Se a variável `.fin` o arquivo for carregado prematuramente, o Adobe recuperará e assimilará o arquivo parcialmente carregado, gerando possíveis erros.

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
