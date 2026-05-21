---
description: A conexão sem senha a contas FTP só é possível com uma conexão SFTP e um método de autenticação alternativo. Esse processo envolve um conjunto de dois arquivos (um que fica na conta FTP e outro que fica no seu computador) chamado de combinação de chave pública e privada.
keywords: ftp;sftp
title: Conexão com a Adobe via SFTP sem uma senha
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
TQID: https://experienceleague.adobe.com/qQmzBUalqWjJ7FYow1DBCEfVixzultPI2PJSNhOsLlY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 609
ht-degree: 38%

---

# Conexão com a Adobe via SFTP sem uma senha

A conexão sem senha a contas FTP só é possível com uma conexão SFTP e um método de autenticação alternativo. Esse processo envolve um conjunto de dois arquivos (um que fica na conta FTP e outro que fica no seu computador) chamado de combinação de chave pública e privada.

Isso não é menos seguro do que a autenticação por senha. É outra forma de autenticação que não requer que o usuário digite uma senha todas as vezes. Quando usados corretamente, esses arquivos permitem que determinado computador faça logon sem precisar especificar uma senha. Isso precisa ser configurado computador a computador. Todas as outras conexões que não usam esses arquivos-chave ainda precisam especificar uma senha.

Alguns clientes exigem um SFTP (Secure File Transfer Protocol) para a transferência de dados confidenciais. Uma conexão SFTP é mais segura do que uma conexão FTP comum porque ela permite a comunicação de dados criptografados. Por padrão, todas as contas FTP da Adobe estão configuradas para conexão SFTP. Uma conexão SFTP pode ser aberta com um nome de usuário e senha válidos por meio de um cliente SFTP que se conecta na porta 22 (as conexões FTP normais que não são seguras utilizam a porta 21).

Ao usar o SFTP é possível, em condições específicas, usar chaves privadas pra se conectar à conta sem uma senha. Esse método permite que o computador use arquivos de chave para autenticação em vez da autenticação de senha normal. Isso significa que somente o computador que contém a chave privada pode se conectar sem uma senha. Todos os outros computadores/usuários ainda precisam usar autenticação de senha (a menos que chaves privadas também tenham sido configuradas nesses outros computadores).

**Para configurar e usar chaves privadas para autenticação sem senha**

1. Conta FTP criada (Adobe).

   Um representante da Adobe pode criar uma conta FTP, caso ainda não exista uma. Entre em contato com a Equipe de conta da Adobe ou com o Atendimento ao cliente da Adobe para obter uma conta criada.
1. Criação de chave pública/privada (Cliente).

   Crie uma combinação de chave pública e privada. A chave privada é um arquivo que é privado para seu computador/servidor e reside nele. O arquivo de chave pública precisa ser carregado para a conta do Adobe. Quando usado dessa maneira, você pode se conectar sem autenticação de senha. O arquivo de chave pública no Adobe corresponde ao arquivo de chave privada no computador/servidor e é autenticado dessa maneira.

   Para criar esses arquivos, envolva o grupo de suporte da rede interna para criar um conjunto de chaves adequado ao seu ambiente. Há muitas ferramentas e aplicativos que podem ser usados para criar esses dois arquivos.

   Um exemplo de como isso pode ser feito em um ambiente shell UNIX é mostrado abaixo. Este é apenas um exemplo de como isso pode ser feito e serve como um ponto de referência útil para informar os requisitos à sua equipe ou grupo de rede interno.

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

1. Fazer upload da chave pública para a conta FTP (Cliente).

   Faça upload e teste da chave pública. Conecte-se à conta FTP da Adobe e crie um diretório [!DNL .ssh], caso ele ainda não exista. Faça upload do arquivo [!DNL authorized_keys] para o diretório [!DNL .ssh]. Isso pode ser feito de várias maneiras diferentes (linha de comando, cliente FTP gráfico e assim por diante). Basta criar um diretório e fazer upload de um arquivo.

   Aqui, novamente, está um exemplo de como fazer isso usando um shell UNIX.

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
