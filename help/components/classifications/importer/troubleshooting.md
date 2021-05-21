---
title: Solução de problemas do importador de classificação
description: Problemas comuns de upload ao usar o importador de classificação.
exl-id: de3e9eca-9264-4711-b73a-4a1a3dd16715
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '855'
ht-degree: 100%

---

# Solução de problemas do importador de classificação

Os problemas mais comuns ao fazer upload de dados de classificação para a Adobe.

## Formato ou extensão de arquivo incorretos

As classificações requerem um tipo e um formato específicos de arquivo para que o upload seja feito com êxito. Caso tenha sido salvo incorretamente, retornará um erro e nenhuma linha será processada. O erro retornado frequentemente é *“A primeira coluna deve ser a chave”*, mas podem ocorrer vários outros erros. Verifique o seguinte:

* **Fazer upload de uma planilha (.xlsx) em vez de um arquivo .tab ou .txt**: você pode receber a mensagem de erro *&quot;A primeira coluna deve ser a chave&quot;* ao fazer upload de arquivos de classificação em um formato incorreto. O importador de classificação não sabe como lidar com arquivos .xls ou .xlsx. Na caixa de diálogo “Salvar como” no Excel, defina o tipo correto de Salvar como:
   * No Windows, use o formato de arquivo `Text (Tab delimited) (*.txt)`
   * No Mac, use o formato de arquivo `Windows Formatted Text`.
* **Alteração da extensão do nome do arquivo após salvá-lo como uma pasta de trabalho**: a tentativa de renomear diretamente uma extensão de arquivo gera uma pasta de trabalho inválida. Use apenas a função Salvar como do Excel ou edite as classificações em um editor de texto como o Notepad ++.
* **Uso de extensões em letras maiúsculas**: as extensões em letras maiúsculas (como `fileupload.TXT`) não funcionam. Renomeie o arquivo com uma extensão em letras minúsculas (`fileupload.txt`).
* **Codificação de caractere incompatível**: verifique se a codificação do upload de classificação salvo corresponde à codificação original quando o modelo foi baixado. Se você carregar um arquivo UTF-16 quando ele foi originalmente codificado em UTF-8, os uploads produzirão resultados inesperados. A Adobe recomenda fazer upload de arquivos usando UTF-8 sem marcas de ordem de byte.

## Conteúdos de arquivo inválidos

Se o arquivo de upload estiver formatado corretamente, o carregador tentará importar a maior quantidade possível de linhas. Alguns problemas comuns com os dados de classificação:

* **As linhas já foram classificadas**: ao tentar fazer upload de linhas que já foram classificadas com o mesmo valor, o importador retorna linhas que não tiveram efeito. Esse resultado é esperado, já que as classificações não reclassificam um valor principal com a mesma classificação. É uma notificação em vez de um erro. Não é preciso se preocupar se você não alterar todas as linhas em um arquivo de exportação. O Adobe recomenda fazer upload somente de linhas alteradas.
* **O cabeçalho não corresponde à variável que está sendo carregada**: se você baixar um modelo de classificação para a dimensão Código de rastreamento e tentar carregá-lo para uma classificação eVar, haverá uma falha. Use somente arquivos de exportação para as variáveis específicas das quais eles foram exportados.
* **Um valor principal ou de classificação contém o valor 0**: as classificações não conseguem diferenciar o valor 0 de uma célula em branco, então não podem classificar esse valor. Consulte [Perguntas frequentes sobre classificações](../faq.md).
* **O arquivo de classificação contém vírgulas ou caracteres especiais**: Consulte [Perguntas frequentes sobre classificações](../faq.md).
* **Guias adicionais no arquivo carregado**: certas vezes, ao editar os arquivos de classificação, uma guia adicional pode ser incluída acidentalmente. Cada linha requer um número idêntico de guias para ser processada corretamente. Para verificar se há guias extras no arquivo, realce todo o texto em um editor de texto simples e verifique se nenhuma linha tem espaço extra no final.
* **Existem valores principais duplicados no arquivo**: cada valor principal pode ter somente uma classificação por coluna. Se você tentar classificar o mesmo valor várias vezes, o importador emitirá um erro.
* **Existem subclassificações configuradas incorretamente**: se houver subclassificações, verifique o seguinte:
   * Todos os valores de subclassificações possuem um valor de classificação principal
   * Duas classificações não fazem referência ao mesmo valor de classificação principal
* **Incompatibilidade de coluna**: você poderá receber a mensagem de erro *&quot;A chave na linha tem muitas colunas&quot;* se houver um número inválido de colunas em uma linha específica. Por exemplo, você tem três colunas em seu upload de classificação e a variável tem apenas uma única classificação. Valide o arquivo de upload para garantir que o número de colunas não seja maior do que o número de classificações configuradas para essa variável.

## Solução de problemas de importações de FTP

A seguir são apresentadas causas comuns por trás das classificações de FTP que não processam arquivos carregados:

* **Arquivo .fin ausente**: crie um documento de texto em branco na área de trabalho e renomeie a extensão de nome de arquivo de .txt para .fin. O nome do arquivo .fin deve corresponder ao nome do arquivo de classificação em questão. Por exemplo, se o nome do arquivo FTP for `fileupload.tab`, nomeie o arquivo .fin `fileupload.fin`. Assim que o arquivo .fin for carregado, ambos os arquivos desaparecerão.
* **Upload do arquivo .fin antes do arquivo de classificação**: às vezes, um arquivo .fin é criado antes que o upload do arquivo de classificação seja concluído no site FTP. O processamento pode falhar quando os arquivos forem carregados fora de ordem. Remova os dois arquivos, adicione o arquivo de classificação primeiro e, em seguida, o arquivo .fin após o upload completo do arquivo de classificação.
* **O tamanho do arquivo é muito grande**: a Adobe recomenda manter os tamanhos dos arquivos de classificação os menores possíveis para garantir um processamento rápido.
* **Arquivos existentes já estão sendo processados**: se vários arquivos forem carregados para a mesma variável e conjunto de relatórios, o arquivo antigo para de ser processado em favor do novo. Se você estiver fazendo upload de classificações usando vários arquivos, aguarde a confirmação de que os arquivos existentes foram processados antes de fazer upload dos novos arquivos.
* **Arquivos carregados não são colocados no diretório raiz**: os arquivos carregados no site FTP da Adobe devem ser colocados no diretório raiz. Se os arquivos de importação de classificação forem colocados em subpastas, eles não serão coletados nem processados.

Se você ainda tiver problemas ao fazer upload de um arquivo de classificação, entre em contato com o Atendimento ao cliente da Adobe.
