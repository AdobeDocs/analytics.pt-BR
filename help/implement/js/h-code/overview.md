---
title: Visão geral da implementação do JavaScript do código H
description: Saiba mais sobre o fluxo de trabalho para implementar o Código H em seu site.
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Visão geral da implementação do JavaScript do código H

> [!IMPORTANT] Essa versão da coleta de dados não é mais suportada. Atualize para o [Adobe Experience Platform Launch](../../launch/overview.md) ou para o [AppMeasurement para JavaScript](../overview.md).

É necessário ter acesso aos servidores de hospedagem para implementar com êxito uma página com código para coletar dados. As etapas a seguir o orientam por uma implementação básica do Analytics H Code.

> [!NOTE] Você já deve ter uma cópia existente do para seguir `s_code.js` essas instruções. A Adobe não oferece mais uma opção para baixar o código H no Gerenciador de código.

1. **Atualizar variáveis** do arquivo JS principal: Edite o `s_code.js` arquivo e verifique se as seguintes variáveis foram atualizadas:
   * `s_account` contém a ID do conjunto de relatórios para a qual você deseja enviar dados. Consulte 
   * `s.trackingServer` contém os cookies de localização armazenados. Consulte [trackingServer](../../vars/config-vars/trackingserver.md).
2. **Hospede o`s_code.js`arquivo em seu site**: Normalmente, esse arquivo reside em outros scripts no servidor da Web.
3. **Referência`s_code.js`em todas as páginas**: Verifique se todas as páginas individuais chamam o arquivo JavaScript principal e faça isso dentro da `<body>` tag HTML (não a `<head>` tag).
   > [!TIP] O código H exige que o `s_code.js` script seja chamado dentro da `<body>` tag . Isso é diferente de outros métodos de implementação, a maioria dos quais requer referências de script na `<head>` tag .
4. **Defina variáveis específicas da página em cada página**: Cada página deve ter variáveis individuais definidas, como nome de página ou eVars. As variáveis individuais normalmente são definidas com uma `<script>` tag inline em cada página.
5. **Use o depurador para verificar a coleta** de dados: Baixe e instale o depurador [da](../../validate/debugger.md) Experience Cloud para garantir que os dados sejam enviados para a Adobe e que as variáveis de página sejam definidas corretamente.

## Armazenamento em cache 

O arquivo JavaScript é armazenado em cache no navegador do visitante depois que é carregado inicialmente, e também é feito o download não mais do que uma ver por sessão. O download não ocorre em todas as páginas, embora o arquivo seja usado por todas as páginas do site. Na maioria dos sites, os usuários têm em média mais do que algumas visualizações de página por sessão. Portanto, a transferência do JavaScript usado várias vezes neste arquivo pode resultar em menos download de dados em geral.

## Compactação de código H

Se você estiver preocupado com o tamanho do download do `s_code.js` arquivo, a Adobe recomenda compactar o `s_code.js` arquivo usando GZIP. O GZIP é compatível com todos os principais navegadores e oferece melhor desempenho do que a compactação JavaScript. Consulte [Apache Module mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) na documentação do Apache.
