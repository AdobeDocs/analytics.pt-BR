---
title: Fazer upload do arquivo de fontes de dados para o Adobe
description: O processo para carregar um arquivo de fontes de dados no Adobe Analytics para assimilação.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# Fazer upload do arquivo de fontes de dados para o Adobe

O envio de um arquivo de fontes de dados para o Adobe envolve um fluxo de trabalho FTP autenticado típico. Você pode usar o Windows Explorer, o Finder ou um cliente FTP dedicado para carregar os arquivos desejados no local FTP do Adobe.

Localize as credenciais do FTP na [Gerenciador de fontes de dados](manage.md). Cada fonte de dados tem um link para sua **[!UICONTROL Informações de FTP]**. Cada local FTP é dedicado a essa fonte de dados específica; não é possível usar o mesmo local FTP para várias fontes de dados.

Por motivos de segurança, os locais FTP sem nenhuma atividade por mais de 30 dias são desativados.

## O `.fin` arquivo

Uma parte essencial da assimilação bem-sucedida de um arquivo de fontes de dados é a inclusão de um `.fin` arquivo. Esse arquivo indica ao Adobe que o arquivo de dados está pronto para processamento. Se você fizer upload de um arquivo de fontes de dados sem um `.fin` , o Adobe nunca processa esses dados.

O `.fin` O arquivo tem as seguintes propriedades:

* O arquivo tem um `.fin` extensão. Certifique-se de que seu sistema operacional permita que você veja e edite os tipos de arquivos.
* O arquivo está vazio. Não armazene dados dentro do `.fin` arquivo.
* O arquivo tem exatamente o mesmo nome do arquivo de fontes de dados. Por exemplo, se você carregar um arquivo de fontes de dados chamado `example.txt`, o `.fin` arquivo **must** ser nomeado `example.fin`. Se não tiverem um nome idêntico, o Adobe nunca processará o arquivo das fontes de dados.

Depois que o arquivo de fonte de dados e `.fin` forem carregados no site FTP, o Adobe processará o arquivo. Não carregue o `.fin` até que o arquivo das fontes de dados seja totalmente carregado. Se a variável `.fin` for carregado prematuramente, o Adobe recuperará e assimilará o arquivo parcialmente carregado, gerando possíveis erros.

## Processamento do pedido

Se você carregar vários arquivos ao mesmo tempo no site FTP, o Adobe os assimilará em ordem alfanumérica. Se sua organização exigir que os arquivos sejam assimilados em uma ordem específica, certifique-se de que seus nomes de arquivo sejam nomeados alfanuméricamente.

## Tempo de processamento

Para garantir o processamento mais rápido de arquivos, o Adobe recomenda agregar dados de métrica em uma única linha por data. Por exemplo, esse arquivo de fontes de dados, embora válido, seria processado mais lentamente:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` |  |  |
| `07/24/YYYY` | `red` | `1` |  |  |
| `07/24/YYYY` | `red` |  | `1` |  |
| `07/24/YYYY` | `red` |  |  | `1` |

Esse arquivo seria processado mais rápido, que contém os mesmos dados:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
