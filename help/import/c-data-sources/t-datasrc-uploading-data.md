---
description: Etapas que descrevem como carregar arquivos de fontes de dados.
subtopic: Data sources
title: Carregar um arquivo de fontes de dados
topic: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Carregar um arquivo de fontes de dados

Etapas que descrevem como carregar arquivos de fontes de dados.

Após preparar um arquivo com dados das Fontes de dados, envie-o para Fontes de dados para processamento. O Adobe mantém diversos servidores FTP de Fontes de Dados, nos quais você pode carregar arquivos de Fontes de Dados. Com relação aos servidores FTP das Fontes de Dados, lembre-se:

* Selecione Informações do FTP, ao lado da entrada da fonte de dados, na guia [!UICONTROL Gerenciador de fontes de dados] para consultar informações do Host FTP, logon e senha da conta FTP da fonte de dados. Qualquer pessoa que tenha acesso a essas informações pode carregar dados no seu conjunto de relatórios.
* Para fins de segurança, as contas FTP são fechadas após 30 dias de inatividade.
* As contas FTP são específicas às fontes de dados. Não é possível utilizar uma conta FTP para carregar arquivos de fontes de dados para múltiplas fontes de dados.

**Para carregar um arquivo de fontes de dados**

1. Use um cliente FTP para enviar os dados para o FTP das suas fontes de dados.

   (Disponível no link Informações de FTP no Gerenciador de fontes de dados).

1. Carregue um arquivo [!DNL .fin] para notificar a Adobe de que o upload do arquivo de Fontes de dados foi concluído.

   O arquivo [!DNL .fin] deve ter exatamente o mesmo nome do arquivo de Fontes de dados, exceto pela extensão. A Adobe não coloca o arquivo de Fontes de dados na fila para o processamento até que você carregue o arquivo [!DNL .fin].

   Não carregue o arquivo até que todos os arquivos de Fontes de dados tenham sido carregados. Caso contrário, as Fontes de dados podem tentar processar um arquivo incompleto.
1. Fique atento a possíveis mensagens durante o processamento do arquivo de Fontes de dados.

   O Gerenciador de fontes de dados exibe todos os erros ocorridos durante o processamento do arquivo.

