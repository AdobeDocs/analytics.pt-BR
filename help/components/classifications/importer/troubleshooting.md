---
title: Solução de problemas do importador de classificação
description: Problemas comuns de upload ao usar o importador de classificação.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 14%

---


# Solução de problemas do importador de classificação

Os problemas mais comuns ao carregar dados de classificação para o Adobe.

## Formato ou extensão de arquivo incorretos

As classificações exigem um tipo e formato de arquivo específicos para serem carregadas com êxito. Caso tenha sido salvo incorretamente, retornará um erro e nenhuma linha será processada. O erro retornado é frequentemente *&quot;A primeira coluna deve ser a chave&quot;*, mas pode ser qualquer número de erros. Verifique o seguinte:

* **Carregando uma planilha (.xlsx) em vez de um arquivo**.tab ou .txt: O importador de classificação não sabe lidar com arquivos .xls ou .xlsx. Quando na caixa de diálogo &quot;Salvar como&quot; no Excel, defina o tipo Salvar como correto:
   * No Windows, use o formato de arquivo `Text (Tab delimited) (*.txt)`
   * No Mac, use o formato de arquivo `Windows Formatted Text`.
* **Alteração da extensão do nome de arquivo após salvá-la como uma pasta de trabalho**: A tentativa de renomear diretamente uma extensão de arquivo gera uma pasta de trabalho inválida. Use apenas a função Salvar como do Excel ou edite classificações em um editor de texto, como o Bloco de notas+.
* **Usando extensões** em maiúsculas: As extensões em maiúsculas (como `fileupload.TXT`) não funcionam. Rename the file to a lowercase extension (`fileupload.txt`).
* **Codificação** de caractere incompatível: Certifique-se de que a codificação do upload da classificação salva corresponde à codificação original quando o modelo foi baixado. Se você carregar um arquivo UTF-16 quando ele foi originalmente codificado em UTF-8, os uploads produzirão resultados inesperados. O Adobe recomenda carregar arquivos usando UTF-8 sem marcas de ordem de byte.

## Conteúdos de arquivo inválidos

Se o arquivo de upload estiver formatado corretamente, o carregador tentará importar a maior quantidade possível de linhas. Alguns problemas comuns com os dados de classificação:

* **Linhas já classificadas**: Ao tentar carregar linhas que já estão classificadas com o mesmo valor, o importador retorna linhas que não tiveram efeito. Esse resultado é esperado, já que as classificações não reclassificam um valor principal com a mesma classificação. É uma notificação em vez de um erro. Não é preciso se preocupar com isso se você não alterar todas as linhas em um arquivo de exportação. O Adobe recomenda carregar somente linhas alteradas.
* **O cabeçalho não corresponde à variável que está sendo carregada**: Se você baixar um modelo de classificação para a dimensão de código de rastreamento e tentar carregá-lo para uma classificação de eVar, ocorrerá falha. Use somente arquivos de exportação para as variáveis específicas das quais eles foram exportados.
* **Um valor de chave ou classificação contém o valor 0**: As classificações não podem diferenciar o valor 0 de uma célula em branco, portanto, não podem classificar esse valor. Consulte Perguntas frequentes sobre [classificações](../faq.md).
* **O arquivo de classificação contém vírgulas ou caracteres** especiais: Consulte Perguntas frequentes sobre [classificações](../faq.md).
* **Guias adicionais no arquivo** carregado: Às vezes, ao editar arquivos de classificação, uma guia extra pode ser colocada acidentalmente. Cada linha requer um número idêntico de guias para ser processada corretamente. Para verificar se há guias extras no arquivo, realce todo o texto em um editor de texto simples e verifique se nenhuma linha tem espaço extra no final.
* **Existem valores de chave de duplicado no arquivo**: Cada valor de chave pode ter apenas uma classificação por coluna. Se você tentar classificar o mesmo valor várias vezes, o importador emite um erro.
* **As subclassificações existem e estão configuradas** incorretamente: Se houver subclassificações, verifique o seguinte:
   * Todos os valores de subclassificações possuem um valor de classificação principal
   * Duas classificações não fazem referência ao mesmo valor de classificação principal

## Solução de problemas de importações FTP

As seguintes são causas comuns por trás das classificações FTP que não processam os arquivos carregados:

* **Arquivo**.fin ausente: Crie um documento de texto em branco na área de trabalho e renomeie a extensão de nome de arquivo de .txt para .fin. O nome deste arquivo .fin deve corresponder ao nome do arquivo de classificação em questão. Por exemplo, se o nome do arquivo FTP for `fileupload.tab`, nomeie o arquivo .fin `fileupload.fin`. Assim que o arquivo .fin for carregado, ambos os arquivos desaparecerão.
* **Carregando arquivo .fin antes do arquivo** de classificação: Às vezes, um .fin é criado antes que o arquivo de classificações seja concluído de upload para o site FTP. O processamento pode falhar quando os arquivos forem carregados fora de ordem. Remova ambos os arquivos, adicione primeiro o arquivo de classificação e depois o arquivo .fin depois que o arquivo de classificação for carregado por completo.
* **O tamanho do arquivo é excessivamente grande**: A Adobe recomenda manter os tamanhos de arquivo de classificação o mais pequenos possível para garantir um processamento rápido.
* **Arquivos existentes que já estão sendo processados**: Se vários arquivos forem carregados para a mesma variável e conjunto de relatórios, o arquivo antigo interrompe o processamento em favor do novo. Se as classificações forem carregadas com vários arquivos, aguarde a confirmação de que os arquivos existentes terminaram o processamento antes de carregar os novos arquivos.
* **Arquivos carregados não colocados no diretório** raiz: Os arquivos carregados no site FTP Adobe devem ser colocados no diretório raiz. Se os arquivos de importação de classificação forem colocados em subpastas, eles não serão coletados nem processados.

Se você ainda tiver problemas ao carregar um arquivo de classificação, entre em contato com o Atendimento ao cliente da Adobe.
