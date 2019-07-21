---
description: A conexão sem senha a contas FTP só é possível com uma conexão SFTP e um método de autenticação alternativo. Esse processo envolve um conjunto de dois arquivos (um que fica na conta FTP e outro que fica no seu computador) chamado de combinação de chave pública e privada.
keywords: ftp; sftp
seo-description: A conexão sem senha a contas FTP só é possível com uma conexão SFTP e um método de autenticação alternativo. Esse processo envolve um conjunto de dois arquivos (um que fica na conta FTP e outro que fica no seu computador) chamado de combinação de chave pública e privada.
seo-title: Conexão com a Adobe via SFTP sem senha
solution: Analytics
title: Conexão com a Adobe via SFTP sem senha
uuid: 88728309-50 d 2-450 b-b 0 e 6-7 dcdf 61 b 5 dbc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Conexão com a Adobe via SFTP sem senha

A conexão sem senha a contas FTP só é possível com uma conexão SFTP e um método de autenticação alternativo. Esse processo envolve um conjunto de dois arquivos (um que fica na conta FTP e outro que fica no seu computador) chamado de combinação de chave pública e privada.

Este método não é menos seguro do que a autenticação por senha. Ele é apenas uma outra forma de autenticação que não exige que o usuário digite a senha todas as vezes. Quando usando corretamente, esses arquivos permitem que um computador particular faça o logon sem que seja necessário digitar uma senha. Contudo, é necessário realizar esse processo em todos os computadores. Para todas as outras conexões que não usam esses arquivos-chave ainda é necessário digitar uma senha.

Um SFTP (Secure File Transfer Protocol) é exigido por alguns clientes para a transmissão de dados confidenciais. Uma conexão SFTP é mais segura do que uma conexão FTP comum, pois permite uma comunicação de dados criptografada. Por padrão, todas as contas FTP da Adobe estão prontas para SFTP. Uma conexão SFTP pode ser aberta com um nome de usuário e senha válidos usando um cliente SFTP que se conecta na porta 22 (as conexões FTP normais que não são seguras usam a porta 21).

Ao usar o SFTP, é possível, em condições específicas, usar chaves privadas para se conectar à conta sem uma senha. Este método permite que seu computador use arquivos-chave para autenticação no lugar da autenticação normal por senha. Isto significa que apenas o computador que tem a chave privada pode se conectar sem uma senha. Todos os outros computadores/usuários precisarão usar a autenticação por senha (a menos que chaves privadas também tenham sido configuradas nesses computadores).

**Configurar e usar chaves privadas para a autenticação sem senha**

1. Conta FTP criada (Adobe).

   Um representante da Adobe pode criar uma conta FTP, caso ainda não tenha uma. Entre em contato com seu Gerente de contas da Adobe ou com o Atendimento ao cliente da Adobe para criar a sua conta.
1. Criação de chave pública/privada (cliente).

   Crie uma combinação de chave pública e privada. A chave privada é um arquivo exclusivo do seu computador/servidor e que permanece lá. O arquivo de chave pública precisa ser enviado para a conta da Adobe. Quando usado desta forma, é possível se conectar sem realizar a autenticação por senha. Para a Adobe, o arquivo de chave pública é equivalente ao arquivo de chave privada do seu computador/servidor, e ele realiza a autenticação da mesma forma.

   Para criar esses arquivos, converse com seu grupo de suporte interno de rede para projetar uma configuração de chave adequada para seu ambiente. Há muitas ferramentas e aplicativos que podem ser usados na criação desses dois arquivos.

   Um exemplo de como isto pode ser feito em um ambiente UNIX shell é demonstrado abaixo. Este é apenas um exemplo de como isto pode ser feito e serve como um ponto de referência útil para informar sua equipe ou o grupo de rede interno sobre os requisitos.

   ```
   // Linux/Unix (bash shell)
   
   // First make sure the ".ssh" directory exists
   
   $ mkdir ~/.ssh
   
   $ cd ~/.ssh
   
   // Now actually generate the key pair
   
   // Usually we will want to create an empty passphrase (just hit "Enter" for both password prompts)
   
   $ ssh-keygen -q -t dsa
   
   Enter file in which to save the key (/home/user/.ssh/id_dsa):
   
   Enter passphrase (empty for no passphrase): ...
   
   Enter same passphrase again: ...
   
   // Rename or copy the public key file to "authorized_keys"
   
   // This "authorized_keys" file is the one that we will upload to the Adobe FTP server in step 3
   
   $ cp id_dsa.pub authorized_keys 
   ```

1. Upload de uma chave pública para a conta FTP (cliente).

   Faça upload e teste a chave pública. Connect to the Adobe FTP account and create a [!DNL .ssh] directory, if it does not already exist. Upload the [!DNL authorized_keys] file to this [!DNL .ssh] directory. Esse processo pode ser feito de diversas maneiras (linha de comando, cliente FTP gráfico etc). Só é necessário ter a capacidade de criar um diretório e fazer upload de um arquivo.

   Aqui temos mais um exemplo de como fazer isso usando um UNIX shell.

   ```
   $ ftp ftp.Adobe.com
   
   OR (depending on hostname provided by Adobe)
   
   $ ftp ftp2.Adobe.com
   
   // Enter username and password for account as prompted
   
   ftp> mkdir .ssh
   
   ftp> cd .ssh
   
   ftp> put authorized_keys
   
   ftp> exit
   
   // Now test the connection by logging in to the server using "sftp" command:
   
   $ sftp username@ftp.omniture.com
   
   OR (depending on hostname provided by Adobe)
   
   $ sftp username@ftp2.omniture.com
   
   // You should immediately receive an sftp prompt without having to enter the password:
   
   sftp>
   ```

