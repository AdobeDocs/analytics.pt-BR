---
description: Se ocorrer um erro, ele será relatado na coluna Status da tarefa.
keywords: Data Feed;job;troubleshooting;error;ftp;chdir;connect;login;put
title: Solução de problemas de tarefas
uuid: 8fbb914e-03db-434e-b4d3-8594144ff2b7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Solução de problemas de tarefas

Se tiver problemas para que um feed de dados apareça no site FTP, use esta página para entender por que.

## Códigos de erro

Se ocorrer um erro, ele será relatado na coluna Status da tarefa.

### Erro FTP chdir

O feed não pode navegar ou gravar na pasta especificada. Verifique se a pasta de destino existe no site FTP e se as credenciais fornecidas têm as permissões de leitura/gravação corretas para essa pasta.

### Erro de conexão FTP

O feed não pode se conectar ao destino FTP. Verifique se o destino FTP está correto e válido.

### Erro FTP

Um erro genérico no qual o feed não consegue gravar o arquivo no site FTP. Esse erro pode vir do disco do servidor FTP que está cheio ou da cota excedida. O erro também pode ser originado de uma falha de rede ou de servidor de destino.

### Erro de logon FTP

O feed não pode fazer logon usando as credenciais fornecidas. Verifique se o nome de usuário e a senha do FTP estão corretos.

### Erro de Put FTP

O feed não pode gravar arquivos no site FTP. Certifique-se de que o logon FTP tenha as permissões corretas para ler e gravar dados no site FTP. Esse erro também pode vir de um disco completo ou de uma cota de disco excedida no servidor FTP.

## Etapas para solucionar problemas

Faça logon no site FTP e carregue qualquer arquivo nele. Na maioria dos casos, é possível determinar o ponto de falha usando essas etapas.

1. Faça logon no site FTP usando o Explorador de arquivos (Windows) ou o Finder (Mac). Certifique-se de usar o protocolo FTP (`ftp://`). Se não conseguir acessar o site FTP, você pode trabalhar com o proprietário do site FTP para determinar o destino correto.

   ![Explorador de arquivos](assets/file_explorer.png)

2. Um pop-up solicitando um nome de usuário e senha é exibido. Insira suas credenciais de autenticação. Se as credenciais forem aceitas, a janela mostrará o conteúdo atual no site FTP. Se as credenciais não forem aceitas, você poderá trabalhar com o proprietário do FTP para verificar se o nome de usuário e a senha estão corretos.
3. Carregue um arquivo no site FTP arrastando-o para a janela autenticada. Qualquer imagem ou documento de texto é adequado. Se você receber um erro ao tentar colocar um arquivo no site FTP, entre em contato com o proprietário do FTP para verificar se há espaço em disco suficiente e se o nome de usuário tem permissões de gravação no site FTP.
4. Depois de confirmar que o arquivo está no site FTP, você pode excluir o arquivo carregado na etapa anterior.
5. Se todas as etapas acima funcionarem e você ainda receber um erro FTP, peça a um representante do suporte ao cliente para entrar em contato com o Atendimento ao cliente.
