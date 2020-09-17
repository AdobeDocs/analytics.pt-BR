---
title: Arquivo de log
description: Obtenha um arquivo de log para fins de solução de problemas.
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 5%

---


# Arquivo de log

>[!IMPORTANT]
>
>A Adobe está mudando o Ad Hoc Analysis para o fim da sua vida útil em 1º de março de 2021. [Saiba mais](https://adobe.ly/discoverworkspace)

Ao solucionar problemas com o Ad Hoc Analysis, às vezes é necessário obter seu arquivo de log. O Adobe pode usar o arquivo de log para localizar a causa raiz do problema e fornecer uma resolução. O `discover.log` arquivo contém todas as interações do usuário, informações de carregamento de relatório e mensagens de erro Java em todas as sessões. Ele contém informações protegidas como, por exemplo, a senha do usuário. Arquivos de log grandes são divididos em incrementos de 10 MB. Ao fornecer Adobe com os arquivos de registro, verifique se todos os arquivos estão selecionados.

## Windows

Obtenha o `discover.log` arquivo para Windows:

1. Clique no menu start e selecione **Executar** ou pressione `[Win]` + `[R]`.
2. Cole o seguinte no campo de texto e clique em **OK**:

   ```text
   %appdata%/../Local/Adobe/Discover/log
   ```

3. Realce todos os arquivos na pasta, em seguida, clique com o botão direito do mouse e escolha **Enviar para > Pasta** compactada (zipada).
4. Forneça ao representante do Adobe o arquivo .zip.

## Mac

Para obter o `discover.log` arquivo para Mac OS, faça o seguinte:

1. Abra o Finder e navegue até `/Users/your-user/.adobe/Discover/log`
2. Realce todos os arquivos na pasta e clique com o botão direito do mouse e escolha **Compactar**.
3. Forneça ao representante do Adobe o arquivo .zip.

Se o tamanho total de arquivos compactados exceder 10 MB, um representante de Adobe pode fornecer um local FTP temporário.
